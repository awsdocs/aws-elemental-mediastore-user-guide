# AWS Elemental MediaStore Information in CloudTrail<a name="monitoring-service-info-in-cloudtrail"></a>

AWS Elemental MediaStore supports logging the following actions as events in CloudTrail log files:
+ [CreateContainer](http://docs.aws.amazon.com/mediastore/latest/apireference/API_CreateContainer.html)
+ [DeleteContainer](http://docs.aws.amazon.com/mediastore/latest/apireference/API_DeleteContainer.html)
+ [DeleteContainerPolicy](http://docs.aws.amazon.com/mediastore/latest/apireference/API_DeleteContainerPolicy.html)
+ [DescribeContainer](http://docs.aws.amazon.com/mediastore/latest/apireference/API_DescribeContainer.html)
+ [GetContainerPolicy](http://docs.aws.amazon.com/mediastore/latest/apireference/API_GetContainerPolicy.html)
+ [ListContainers](http://docs.aws.amazon.com/mediastore/latest/apireference/API_ListContainers.html)
+ [PutContainerPolicy](http://docs.aws.amazon.com/mediastore/latest/apireference/API_PutContainerPolicy.html)

Every event or log entry contains information about who generated the request\. The identity information helps you determine the following: 
+ Whether the request was made with root or IAM user credentials\.
+ Whether the request was made with temporary security credentials for a role or federated user\.
+ Whether the request was made by another AWS service\.

For more information, see the [CloudTrail userIdentity Element](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-event-reference-user-identity.html)\.

 You can create a trail and store your log files in your Amazon S3 bucket for as long as you want, and define Amazon S3 lifecycle rules to archive or delete log files automatically\. By default, your log files are encrypted with Amazon S3 server\-side encryption \(SSE\)\.

To be notified of log file delivery, configure CloudTrail to publish Amazon SNS notifications when new log files are delivered\. For more information, see [Configuring Amazon SNS Notifications for CloudTrail](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/getting_notifications_top_level.html)\.

You can also aggregate AWS Elemental MediaStore log files from multiple AWS regions and multiple AWS accounts into a single Amazon S3 bucket\. 

For more information, see [Receiving CloudTrail Log Files from Multiple Regions](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-receive-logs-from-multiple-accounts.html) and [Receiving CloudTrail Log Files from Multiple Accounts](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-receive-logs-from-multiple-accounts.html)\.