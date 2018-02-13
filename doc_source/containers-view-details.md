# Viewing the Details for a Container<a name="containers-view-details"></a>

Details for a container include the container policy, endpoint, ARN, and creation time\.

**To view the details for a container \(console\)**

1. Sign in to the AWS Elemental MediaStore console at **https://<*region*>\.console\.aws\.amazon\.com/mediastore/home/region=<*region*>**\.

1. On the **Containers** page, choose the name of the container\. 

   The container details page appears\. This page is divided into two sections:

   + The **Objects** section, which lists the objects and folders in the container\.

   + The **Container** policy section, which shows the resource\-based policy that is associated with this container\. For information about resource policies, see [](policies.md)\.

**To view the details for a container \(AWS CLI\)**

+ In the AWS CLI, use the **describe\-container** command\.

  Example:

  ```
  aws mediastore --region us-west-2 describe-container -–container-name=ExampleContainer
  ```

  Example return value:

  ```
  {
      "Container": {
          "Status": "ACTIVE",
          "Endpoint": "https://aaabbbcccdddee.data.mediastore.us-west-2.amazonaws.com",
          "CreationTime": 1506528818.0,
          "Name": "ExampleContainer",
          "ARN": "arn:aws:mediastore:us-west-2:111222333444:container/ExampleContainer"
      }
  }
  ```