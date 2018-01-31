# Deleting a Container<a name="containers-delete"></a>

You can delete a container only if it has no objects\. 

**To delete a container \(console\)**

1. Sign in to the AWS Elemental MediaStore console at **https://<*region*>\.console\.aws\.amazon\.com/mediastore/home/region=<*region*>**\.

1. On the **Containers** page, choose the radio button to the left of the container name\.

1. Choose **Delete**\.

**To delete a container \(AWS CLI\)**

+ In the AWS CLI, use the **delete\-container** command\.

  Example:

  ```
  aws mediastore --region us-west-2 delete-container -–container-name=ExampleLiveDemo
  ```

  This command has no return value\.