# Editing a Container Policy<a name="policies-edit"></a>

You can edit the permissions in the default container policy, or you can create a new policy that replaces the default policy\. It takes 5 minutes for the new policy to become effective\. 

**To edit a container policy \(console\)**

1. Open the AWS Elemental MediaStore console at [https://console\.aws\.amazon\.com/mediastore/](https://console.aws.amazon.com/mediastore/)\.

1. On the **Containers** page, choose the container name\.

1. Choose **Edit policy**\. For examples that show how to set different permissions, see [Example Container PoliciesExample CORS Policies](policies-examples.md)\.

1. Make the appropriate changes, and then choose **Save**\.

**To edit a container policy \(AWS CLI\)**
+ In the AWS CLI, use the **put\-container\-policy** command\.

  Example:

  ```
  aws mediastore put-container-policy –-region us-west-2 –-container-name ExampleLiveDemo –-policy-name=default –-policy={\"Version\" : \"2012-10-17\",  \"Statement\" : [ {    \"Sid\" : \"MediaStoreFullAccess\",    \"Effect\" : \"Allow\",    \"Principal\" : \"*\",    \"Action\" : \"mediastore:*\",    \"Resource\" : \"arn:aws:mediastore:us-west-2:111222333444:container/ExampleLiveDemo/*\",    \"Condition\" : {      \"Bool\" : {        \"aws:SecureTransport\" : \"true\"      }    }  } ]}"
  }
  ```

  This command has no return value\.