# Deleting an Object<a name="objects-delete"></a>

You can delete objects individually using the console or the AWS CLI\. Alternatively, you can attach an object lifecycle policy that automatically deletes objects after they reach a certain age in a container\.

**Note**  
When you delete the only object in a folder, AWS Elemental MediaStore automatically deletes the folder and any empty folders above that folder\. For example, suppose that you have a folder named `premium` that doesn’t contain any files but does contain one subfolder named `canada`\. The `canada` subfolder contains one file named `mlaw.ts`\. If you delete the file `mlaw.ts`, the service deletes both the `premium` and `canada` folders\. 

**To delete an object \(console\)**

1. Open the MediaStore console at [https://console\.aws\.amazon\.com/mediastore/](https://console.aws.amazon.com/mediastore/)\.

1. On the **Containers** page, choose the name of the container that has the object that you want to delete\.

1. If the object that you want to delete is in a folder, continue choosing the folder names until you see the object\.

1. Choose the option to the left of the object name\.

1.  Choose **Delete**\.

**To delete an object \(AWS CLI\)**
+ In the AWS CLI, use the `delete-object` command\.

  Example:

  ```
  aws mediastore-data --region us-west-2 delete-object --endpoint=https://aaabbbcccdddee.data.mediastore.us-west-2.amazonaws.com --path=/test/document/README3.md
  ```

  This command has no return value\.

**To automatically delete objects based on their age in the container \(AWS CLI\)**

1. Create a file that defines the object lifecycle policy:

   ```
   {        
       "rules": [
            {
               "definition": {
                   "path": [ 
                       {"prefix": "LiveEvents/Football/"}, 
                       {"prefix": "LiveEvents/Baseball/"}
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

   This command has no return value\.