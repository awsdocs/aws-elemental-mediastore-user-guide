# Viewing an Object Lifecycle Policy<a name="policies-object-lifecycle-view"></a>

An object lifecycle policy specifies how long objects should be stored in a container\. To view an object lifecycle policy that is attached to a container, use the AWS CLI\. 

**To view an object lifecycle policy \(AWS CLI\)**
+ In the AWS CLI, use the `get-lifecycle-policy` command:

  ```
  aws mediastore get-lifecycle-policy --container-name LiveEvents
  ```

  The following example shows the return value:

  ```
  {
      "LifecyclePolicy": "{
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
          ]
      }"
  }
  ```