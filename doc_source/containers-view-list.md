# Viewing a List of Containers<a name="containers-view-list"></a>

You can view a list of all the containers that are associated with your account\.

**To view a list of containers \(console\)**

+ Open the AWS Elemental MediaStore console at [https://console\.aws\.amazon\.com/mediastore/](https://console.aws.amazon.com/mediastore/)\.

  The **Containers** page appears, listing all the containers that are associated with your account\.

**To view a list of containers \(AWS CLI\)**

+ In the AWS CLI, use the **list\-containers** command\.

  Example:

  ```
  aws mediastore –-region us-west-2 list-containers
  ```

  Example return value:

  ```
  {
      "Inputs": [
         {
      "Containers": [
          {
              "Status": "ACTIVE",
              "Endpoint": "https://aaabbbcccdddee.data.mediastore.us-west-2.amazonaws.com",
              "CreationTime": 1505317931.0,
              "Name": "ExampleLiveDemo",
              "ARN": "arn:aws:mediastore:us-west-2:111222333444:container/ExampleLiveDemo"
          },
          {
              "Status": "ACTIVE",
              "Endpoint": "https://fffggghhhiiijj.data.mediastore.us-west-2.amazonaws.com",
              "CreationTime": 1506528818.0,
              "Name": "ExampleContainer",
              "ARN": "arn:aws:mediastore:us-west-2:111222333444:container/ExampleContainer"
          }
      ]
  }
  ```