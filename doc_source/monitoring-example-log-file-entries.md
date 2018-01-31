# Example: AWS Elemental MediaStore Log File Entries<a name="monitoring-example-log-file-entries"></a>

 A trail is a configuration that enables delivery of events as log files to an Amazon S3 bucket that you specify\. CloudTrail log files contain one or more log entries\. An event represents a single request from any source and includes information about the requested action, the date and time of the action, request parameters, and so on\. CloudTrail log files are not an ordered stack trace of the public API calls, so they do not appear in any specific order\.

The following example shows a CloudTrail log entry that demonstrates the CreateContainer action\.

```
{
    'awsRegion': 'us-west-2',
    'eventID': '3b99ba80-fc04-44c5-8a2d-93e652088882',
    'eventName': 'CreateContainer',
    'eventSource': 'mediastore.amazonaws.com',
    'eventTime': '2017-11-15T21:26:29Z',
    'eventType': 'AwsApiCall',
    'eventVersion': '1.05',
    'recipientAccountId': '123456789012',
    'requestID': 'UNUR2YGS3HQRPM4LFJWUEOZLTSGK2KXX4KEMRFGVEP3WWXAOENJCI5VRWCWGHLKKQ33UVDQ4CSFAZAUL7G4FXPY',
    'requestParameters': {'containerName': 'MediaStoreContainer'},
    'responseElements': 
        {
        'container': 
            {
                'aRN': 'arn:aws:mediastore:us-west-2:123456789012:container/MediaStoreContainer',
                'creationTime': 'Nov 15, 2017 9:26:29PM',
                'name': 'MediaStoreContainer',
                'status': 'CREATING'
            }
        },
    'sourceIPAddress': '205.251.233.176',
    'userAgent': 'aws-cli/1.11.138 Python/2.7.10 Darwin/16.7.0 botocore/1.6.5',
    'userIdentity': 
        {
            'accessKeyId': 'EXAMPLE_KEY_ID',
            'accountId': '123456789012',
            'arn': 'arn:aws:iam::123456789012:user/Alice',
            'principalId': 'EXAMPLE_PRINCIPAL_ID',
            'type': 'IAMUser',
            'userName': 'Alice'
        }
}
```