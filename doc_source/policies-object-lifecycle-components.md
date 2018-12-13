# Components of an Object Lifecycle Policy<a name="policies-object-lifecycle-components"></a>

Object lifecycle policies govern how long objects remain in an AWS Elemental MediaStore container\. Each object lifecycle policy consists of one or more rules, which dictate the lifespan of objects\. A rule can apply to one folder, multiple folders, or the entire container\. 

You can attach one object lifecycle policy to a container, and each object lifecycle policy can contain up to 10 rules\. You can't assign an object lifecycle policy to an individual object\. 

For example, a container named `LiveEvents` has four subfolders: `Football`, `Baseball`, `Basketball`, and `AwardsShow`\. The object lifecycle policy assigned to the `LiveEvents` folder might look like this:

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
        }
        {
            "definition": {
                "path": [ { "prefix": "AwardsShow/" }  ],
                "days_since_create": [
                    {"numeric": [">" , 15]}
                ]
            },
            "action": "EXPIRE"
        }
        {
            "definition": {
                "path": [ { "prefix": "" }  ],
                "days_since_create": [
                    {"numeric": [">" , 40]}
                ]
            },
            "action": "EXPIRE"
        }
    ]
}
```

The preceding policy specifies the following:
+ The first rule instructs AWS Elemental MediaStore to delete objects that are stored in the `LiveEvents/Football` folder and the `LiveEvents/Baseball` folder after they are older than 28 days\.
+ The second rule instructs the service to delete objects that are stored in the `LiveEvents/AwardsShow` folder after they are older than 15 days\.
+ The third rule instructs the service to delete objects that are stored anywhere in the `LiveEvents` container after they are older than 40 days\. This rule applies to objects stored directly in the `LiveEvents` container, as well as objects stored in any of the container's four subfolders\.