# Viewing a CORS Policy<a name="cors-policy-viewing"></a>

Cross\-origin resource sharing \(CORS\) defines a way for client web applications that are loaded in one domain to interact with resources in a different domain\. You can use the console or the AWS CLI to view a CORS policy on a container\.

**To view a CORS policy \(console\)**

1. Open the MediaStore console at [https://console\.aws\.amazon\.com/mediastore/](https://console.aws.amazon.com/mediastore/)\.

1. On the **Containers** page, choose the name of the container that you want to view the CORS policy for\.

   The container details page appears, with the CORS policy in the **Container CORS policy** section\.

**To view a CORS policy \(AWS CLI\)**
+ In the AWS CLI, use the `get-cors-policy` command:

  ```
  aws mediastore get-cors-policy --container-name ExampleContainer --region ap-southeast-2 --endpoint https://mediastore.ap-southeast-2.amazonaws.com/
  ```

  The following example shows the return value:

  ```
  [
   {
    "AllowedOrigins": ["http://example.com"],
    "AllowedMethods": ["GET"],
    "AllowedHeaders": ["*"],
    "MaxAgeSeconds": 3000
   },
   {
    "AllowedOrigins": ["https://*"],
    "AllowedMethods": ["GET", "PUT"],
    "AllowedHeaders": ["x-amzn*"],
    "MaxAgeSeconds": 0
   }
  ]
  ```