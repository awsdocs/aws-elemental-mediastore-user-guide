# Creating a Container<a name="containers-create"></a>

You can create up to 100 containers for each AWS account\. However, there is no limit to the number of folders that you can create in each of those containers\. In addition, there is no limit to the number of objects that you can upload to each container\.

**To create a container \(console\)**

1. Open the AWS Elemental MediaStore console at [https://console\.aws\.amazon\.com/mediastore/](https://console.aws.amazon.com/mediastore/)\.

1. On the **Containers** page, choose **Create container**\.

1. For **Container** name, type a name for the container\. For more information, see [Rules for Container Names](containers-rules-for-names.md)\.

1. Choose **Create container**\. AWS Elemental MediaStore adds the new container to a list of containers\. Initially, the status of the container is **Creating**, and then it changes to **Active**\.

**To create a container \(AWS CLI\)**

+ In the AWS CLI, use the **create\-container** command\.

  Example:

  ```
  aws mediastore --region us-west-2 create-container -–container-name=ExampleContainer
  ```

  Example return value:

  ```
  {
      "Container": {
          "Status": "CREATING",
          "CreationTime": 1506528818.0,
          "Name": "ExampleContainer",
          "ARN": "arn:aws:mediastore:us-west-2:111222333444:container/ExampleContainer"
      }
  }
  ```