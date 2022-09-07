# Allowing Amazon CloudFront to access your AWS Elemental MediaStore container<a name="cdns-allowing-cloudfront-to-access-mediastore"></a>

You can use Amazon CloudFront to serve the content that you store in a container in AWS Elemental MediaStore\. To get started, you attach a policy to your container that grants read access or greater to CloudFront\. 

**To allow CloudFront to access your container \(console\)**

1. Open the MediaStore console at [https://console\.aws\.amazon\.com/mediastore/](https://console.aws.amazon.com/mediastore/)\.

1. On the **Containers** page, choose the container name\.

   The container details page appears\.

1. In the **Container policy** section, attach a policy that grants read access or greater to Amazon CloudFront\.  
**Example**  

   The following example policy, which is similar to the example policy for [Public Read Access over HTTPS](policies-examples-public-https.md), matches these requirements because it allows `GetObject` and `DescribeObject` commands from anyone who submits requests to your domain through HTTPS\. Furthermore, the following example policy better secures your workflow because it allows CloudFront access to MediaStore objects only when the request occurs over an HTTPS connection and contains the correct Referer header\.

   ```
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "CloudFrontRead",
         "Effect": "Allow",
         "Principal": "*",
         "Action": [
           "mediastore:GetObject",
           "mediastore:DescribeObject"
         ],
         "Resource": "arn:aws:mediastore:<region>:<owner acct number>:container/<container name>/*",
         "Condition": {
           "StringEquals": {
             "aws:Referer": "<secretValue>"
           },
           "Bool": {
             "aws:SecureTransport": "true"
           }
         }
       }
    ]}
   ```

1. In the **Container CORS policy** section, assign a policy that allows the appropriate access level\. 
**Note**  
A [CORS policy](cors-policy.md) is necessary only if you want to provide access to a browser\-based player\.

1. Make note of the following details:
   + The data endpoint that is assigned to your container\. You can find this information in the **Info** section of the **Containers** page\. In CloudFront, the data endpoint is referred to as the *origin domain name*\.
   + The folder structure in the container where the objects are stored\. In CloudFront, this is referred to as the *origin path*\. Note that this setting is optional\. For more information about origin paths, see the [Amazon CloudFront Developer Guide](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/distribution-web-values-specify.html#DownloadDistValuesOriginPath)\.

1. In CloudFront, create a distribution that is [configured to serve content from AWS Elemental MediaStore](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/live-streaming.html#video-streaming-mediastore)\. You will need the information that you collected in the preceding step\.

After attaching the policy to your MediaStore containers, you must configure CloudFront to use only HTTPS connections for origin requests, and also add a custom header with the correct secret value\.

**To configure CloudFront to access your container via an HTTPS connection with a secret value for the Referer header \(console\)**

1. Open the CloudFront console\.

1. On the **Origins** page, choose your MediaStore origin\.

1. Choose **Edit**\.

1. Choose **HTTPS only** for the protocol\.

1. In the **Add custom header** section, choose **Add header**\.

1. For the **Name**, choose **Referer**\. For the **value**, use the same *<secretValue>* string that you used in your container policy\.

1. Choose **Save** and let the changes deploy\.