# Components of an Object Lifecycle Policy<a name="policies-object-lifecycle-components"></a>

Object lifecycle policies govern how long objects remain in an AWS Elemental MediaStore container\. Each object lifecycle policy consists of one or more rules, which dictate the lifespan of objects\. A rule can apply to one folder, multiple folders, or the entire container\. 

You can attach one object lifecycle policy to a container, and each object lifecycle policy can contain up to 10 rules\. You can't assign an object lifecycle policy to an individual object\. 

## Rules in an Object Lifecycle Policy<a name="policies-object-lifecycle-components-rules"></a>

You can create two types of rules:
+ [Transient Data](#policies-object-lifecycle-components-rules-seconds)
+ [Delete Object](#policies-object-lifecycle-components-rules-days)

### Transient Data<a name="policies-object-lifecycle-components-rules-seconds"></a>

A transient data rule sets objects to expire within seconds\. An example of a rule for transient data looks like this:

```
        {
            "definition": {
                "path": [ {"wildcard": "Football/index*.m3u8"} ],
                "seconds_since_create": [
                    {"numeric": [">", 120]}
                ]
            },
            "action": "EXPIRE"
        },
```

This rule has three parts:
+ `path`: Always set to `wildcard`\. You use this part to define which objects you want to delete\. You can use one or more wildcards, represented by an asterisk \(\*\)\. Each wildcard represents any combination of zero or more characters\. For example, `"path": [ {"wildcard": "Football/index*.m3u8"} ],` applies to all files in the `Football` folder that match the pattern of `index*.m3u8` \(such as index\.m3u8, index1\.m3us8, and index123456\.m3u8\)\. You can include up to 10 paths in a single rule\.
+ `seconds_since_create`: Always set to `numeric`\. You can specify a value from 1\-300 seconds\. You can also set the operator to greater than \(>\) or greater than or equal to \(>=\)\.
+ `action`: Always set to `EXPIRE`\.

For transient data rules \(objects expire within seconds\), there is no lag between the expiration of an object and the deletion of the object\.

**Note**  
Objects that are subject to a transient data rule are not included in a `list-items` response\.

### Delete Object<a name="policies-object-lifecycle-components-rules-days"></a>

A delete object rule sets objects to expire within days\. An example of a rule for deleting objects looks like this:

```
        {
            "definition": {
                "path": [ { "prefix": "FolderName/" }  ],
                "days_since_create": [
                    {"numeric": [">" , 5]}
                ]
            },
            "action": "EXPIRE"
        }
```

This rule has three parts:
+ `path`: Always set to `prefix`\. You use this part to specify the folder name\. If the parameter is empty \(`"path": [ { "prefix": "" } ],`\), the target is all objects that are stored anywhere within the current container\. You can include up to 10 paths in a single rule\.
+ `days_since_create`: Always set to `numeric`\. You can specify a value from 1\-36,500 days\. You can also set the operator to greater than \(>\) or greater than or equal to \(>=\)\. 
+ `action`: Always set to `EXPIRE`\.

For delete object rules \(objects expire within days\), there might be a slight lag between the expiration of an object and the deletion of the object\. However, changes in billing happen as soon as the object expires\. For example, if a lifecycle rule specifies 10 `days_since_create`, the account isn't billed for the object after the object is 10 days old, even if the object isn't deleted yet\.

## Example<a name="policies-object-lifecycle-components-example"></a>

Suppose that a container named `LiveEvents` has four subfolders: `Football`, `Baseball`, `Basketball`, and `AwardsShow`\. The object lifecycle policy assigned to the `LiveEvents` folder might look like this:

```
{        
    "rules": [
         {
            "definition": {
                "path": [ 
                    {"prefix": "Football/"}, 
                    {"prefix": "Baseball/"}
                ],
                "days_since_create": [
                    {"numeric": [">" , 28]}
                ]
            },
            "action": "EXPIRE"
        },
        {
            "definition": {
                "path": [ { "prefix": "AwardsShow/" }  ],
                "days_since_create": [
                    {"numeric": [">=" , 15]}
                ]
            },
            "action": "EXPIRE"
        },
        {
            "definition": {
                "path": [ { "prefix": "" }  ],
                "days_since_create": [
                    {"numeric": [">" , 40]}
                ]
            },
            "action": "EXPIRE"
        },
        {
            "definition": {
                "path": [ 
                    {"wildcard": "Football/index*.m3u8"}
                ],
                "seconds_since_create": [
                    {"numeric": [">" , 15]}
                ]
            },
            "action": "EXPIRE"
        }
    ]
}
```

The preceding policy specifies the following:
+ The first rule instructs AWS Elemental MediaStore to delete objects that are stored in the `LiveEvents/Football` folder and the `LiveEvents/Baseball` folder after they are older than 28 days\.
+ The second rule instructs the service to delete objects that are stored in the `LiveEvents/AwardsShow` folder when they are 15 days old or older\.
+ The third rule instructs the service to delete objects that are stored anywhere in the `LiveEvents` container after they are older than 40 days\. This rule applies to objects stored directly in the `LiveEvents` container, as well as objects stored in any of the container's four subfolders\.
+ The fourth rule instructs the service to delete objects in the `Football` folder that match the pattern `index*.m3u8` after they are older than 15 seconds\. AWS Elemental MediaStore deletes these files 16 seconds after they are placed in the container\.