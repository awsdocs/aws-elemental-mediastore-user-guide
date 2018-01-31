# Step 1: Create Policies<a name="setting-up-IAM-users-create-nonadmin-policies"></a>

Create two policies for AWS Elemental MediaStore: one to provide read/write access and one to provide read\-only access\. Perform these steps one time only for each policy\.

**To create policies**

1. Use your AWS account ID or account alias, and the credentials for your admin IAM user to sign in to the [IAM console](https://console.aws.amazon.com/iam)\.

1. In the navigation pane of the console, choose **Policies**, and then choose **Create policy**\.

1. Choose the **JSON** tab and paste the following policy:

   ```
   {
       "Version": "2012-10-17",
       "Statement": [
           {
               "Action": [
                   "mediastore:*"
               ],
               "Effect": "Allow",
               "Resource": "*",
               "Condition": {
                   "Bool": {
                       "aws:SecureTransport": "true"
                   }
               }
           }
       ]
   }
   ```

   This policy allows all actions on all resources in AWS Elemental MediaStore\.

1. Choose **Review policy**\.

1. On the **Review policy** page, for **Name**, type **MediaStoreAllAccess** , and then choose **Create policy**\.

1. On the **Policies** page, repeat steps 1\-5 to create a read\-only policy\. Use the following policy and call it **MediaStoreReadOnlyAccess**:

   ```
   {
       "Version": "2012-10-17",
       "Statement": [
           {
               "Action": [
                   "mediastore:Get*",
   
                   "mediastore:List*",
                   "mediastore:Describe*"
               ],
               "Effect": "Allow",
               "Resource": "*",
               "Condition": {
                   "Bool": {
                       "aws:SecureTransport": "true"
                   }
               }
           }
       ]
   }
   ```