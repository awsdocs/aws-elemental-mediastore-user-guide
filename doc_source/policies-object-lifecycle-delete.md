# Deleting an Object Lifecycle Policy<a name="policies-object-lifecycle-delete"></a>

When you delete an object lifecycle policy, it takes up to 20 minutes for the change to take effect\. 

**To delete an object lifecycle policy \(AWS CLI\)**
+ In the AWS CLI, use the `delete-lifecycle-policy` command:

  ```
  aws mediastore delete-lifecycle-policy --container-name LiveEvents
  ```

  This command has no return value\. The service deletes the object lifecycle policy within 20 minutes\.