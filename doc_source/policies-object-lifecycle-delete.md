# Deleting an Object Lifecycle Policy<a name="policies-object-lifecycle-delete"></a>

When you delete an object lifecycle policy, it takes up to 20 minutes for the service to apply the change to the container\. 

**To delete an object lifecycle policy \(AWS CLI\)**
+ In the AWS CLI, use the `delete-lifecycle-policy` command:

  ```
  aws mediastore delete-lifecycle-policy --container-name LiveEvents
  ```

  This command has no return value\. 