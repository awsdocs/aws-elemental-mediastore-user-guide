# AWS Elemental MediaStore resource\-based policy examples<a name="security_iam_resource-based-policy-examples"></a>

To access the AWS Elemental MediaStore console, you must have a minimum set of permissions that allows you to list and view details about the MediaStore resources in your AWS account\. The IAM policies in this section show examples of policies that allow specific actions on resources in AWS Elemental MediaStore\.

**Note**  
MediaStore also supports container policies that define which principal entities \(accounts, users, roles, and federated users\) can perform actions on the container\. For more information, see [Container policies](policies.md)\.

## Allow read access to all MediaStore resources<a name="iam-policy-examples-for-mediastore-actions-read-only-all-resources"></a>

To access the AWS Elemental MediaStore console, you must have a policy that defines which actions you are allowed to take on MediaStore resources in your AWS account\. The IAM policy below provides the following permissions\. The section for the `mediastore:List*` and `mediastore:Describe*` actions allows read\-only access to all resources that you create in MediaStore\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "mediastore:List*",
                "mediastore:Describe*"
            ],
            "Effect": "Allow",
            "Resource": "arn:aws:mediastore:*:*:*"
        }
        
    ]
}
```

## Allow all actions on all MediaStore resources<a name="iam-policy-examples-for-mediastore-actions-all-actions-all-resources"></a>

Every user of MediaStore must have a policy that defines permissions on MediaStore resources\. The IAM policy below provides the following permissions:
+ The section for the `mediastore:*` action allows all actions on all resources that you create in MediaStore\.
+ The section for the `iam:PassRole` action grants permission to pass the MediaStoreAccessLogs IAM role to MediaStore\. This allows the service to assume the role later and publish CloudWatch Logs into your account\. This portion of the policy is required to enable access logging\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "mediastore:*"
            ],
            "Effect": "Allow",
            "Resource": "arn:aws:mediastore:*:*:*"
        },
      
        {
            "Action": [
                "iam:PassRole"
            ],
            "Effect": "Allow",
            "Resource": "arn:aws:iam:*:*:role/MediaStoreAccessLogs"
        }
    ]
}
```

## Allow or deny actions based on tags on MediaStore resources<a name="iam-policy-examples-for-mediastore-tag-based-access"></a>

To allow access based on a resource's tags, use a tag\-based access policy\. 

**Note**  
Tag\-based access control works with only the data types listed in the [AWS Elemental MediaStore](https://docs.aws.amazon.com/mediastore/latest/apireference/API_Operations_AWS_Elemental_MediaStore.html) section of the *AWS Elemental MediaStore API Reference*\. Tag\-based access control doesn't apply for MediaStore data plane APIs\.

The IAM policy below provides the following permissions:
+ Allow `DeleteContainer` actions on all resources that are tagged with the key `company` and value `ITW`
+ Allow `DeleteContainer` actions on all resources that are tagged with the key `environment` and value `ITW-prod`

```
{
    "Version": "2012-10-17",
    "Statement": {
        "Sid": "AllowDeleteForITW",
        "Effect": "Allow",
        "Action": [
            "mediastore:DeleteContainer"
        ],
        "Resource": "arn:aws:mediastore:*:*:container/*",
        "Condition": {
            "StringEquals": {
                "aws:ResourceTag/company": "ITW",
                "aws:ResourceTag/environment": "ITW-prod"
            }
        }
    }
}
```

To create a policy that denies access in these circumstances, change the permission line in the policy to the following:

```
"Effect": "Deny",
```