# Logging AWS Elemental MediaStore API Calls with AWS CloudTrail<a name="logging-using-cloudtrail"></a>

AWS Elemental MediaStore is integrated with AWS CloudTrail, a service that provides a record of actions taken by a user, role, or an AWS service in MediaStore\. CloudTrail captures a subset of API calls for MediaStore as events, including calls from the MediaStore console and from code calls to the MediaStore APIs\. If you create a trail, you can enable continuous delivery of CloudTrail events to an Amazon S3 bucket, including events for MediaStore\. If you don't configure a trail, you can still view the most recent events in the CloudTrail console in **Event history**\. Using the information collected by CloudTrail, you can determine the request that was made to MediaStore, the IP address from which the request was made, who made the request, when it was made, and additional details\. 

To learn more about CloudTrail, including how to configure and enable it, see the [AWS CloudTrail User Guide](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/)\.

**Topics**
+ [AWS Elemental MediaStore Information in CloudTrail](monitoring-service-info-in-cloudtrail.md)
+ [Example: AWS Elemental MediaStore Log File Entries](monitoring-example-log-file-entries.md)