# Viewing a Container Policy<a name="policies-view"></a>

You can use the console or the AWS CLI to view the resource\-based policy of a container\.

**To view a container policy \(console\)**

1. Open the MediaStore console at [https://console\.aws\.amazon\.com/mediastore/](https://console.aws.amazon.com/mediastore/)\.

1. On the **Containers** page, choose the container name\.

   The container details page appears\. The policy is displayed in the **Container policy** section\. 

**To view a container policy \(AWS CLI\)**
+ In the AWS CLI, use the **get\-container\-policy** command\.

  Example:

  ```
  aws mediastore get-container-policy --container-name=ExampleLiveDemo –-region us-west-2
  ```

  Example return value

  ```
  {
    "Policy": {
      "Version": "2012-10-17",
      "Statement": [
        {
          "Sid": "MediaStoreFullAccess",
          "Effect": "Allow",
          "Principal": "*",
          "Action": "mediastore:*",
          "Resource": "arn:aws:mediastore:us-west-2:111222333444:container/ExampleLiveDemo/*",
          "Condition": {
            "Bool": {
              "aws:SecureTransport": "true"
            }
          }
        }
      ]
    }
  }
  ```