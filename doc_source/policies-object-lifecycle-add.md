# Adding an Object Lifecycle Policy to a Container<a name="policies-object-lifecycle-add"></a>

An object lifecycle policy lets you specify how long to store your objects in a container\. You set an expiration date, and after the expiration date AWS Elemental MediaStore deletes the objects\. To create the object lifecycle policy and attach it to a container, you use the AWS CLI\. If the container already has an object lifecycle policy, the service replaces the existing policy with the new policy\. It takes up to 20 minutes for the new policy to take effect\.

**To create an object lifecycle policy \(AWS CLI\)**

1. Create a file that defines the object lifecycle policy:

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
       ]
   }
   ```

1. In the AWS CLI, use the `put-lifecycle-policy` command:

   ```
   aws mediastore put-lifecycle-policy --container-name LiveEvents --lifecycle-policy file://LiveEventsLifecyclePolicy
   ```

   This command has no return value\. The service attaches the specified policy to the container\. 