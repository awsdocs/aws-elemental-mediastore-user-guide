# Example container policy: Default<a name="policies-examples-default"></a>

When you create a container, AWS Elemental MediaStore automatically attaches the following resource\-based policy: 

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "MediaStoreFullAccess",
      "Action": [ "mediastore:*" ],
      "Principal":{
          "AWS" : "arn:aws:iam::<aws_account_number>:root"},
      "Effect": "Allow",
      "Resource": "arn:aws:mediastore:<region>:<owner acct number>:container/<container name>/*",
      "Condition": {
        "Bool": { "aws:SecureTransport": "true" }
      }
    }
  ]
}
```

The policy is built into the service, so you don’t have to create it\. The default policy can’t be changed; however, you can edit a container’s policy\.

The default policy that is assigned to all new containers allows access to all MediaStore operations on the container\. It specifies that this access has the condition of requiring HTTPS for the operations\.