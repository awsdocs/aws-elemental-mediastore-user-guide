# What Is AWS Elemental MediaStore?<a name="what-is"></a>

AWS Elemental MediaStore is a video origination and storage service that offers the high performance and immediate consistency required for live origination\. With AWS Elemental MediaStore, you can manage video assets as objects in containers to build dependable, cloud\-based media workflows\.

To use the service, you upload your objects from a source, such as an encoder or data feed, to a container that you create in AWS Elemental MediaStore\.


+ [AWS Elemental MediaStore Concepts](#concepts)
+ [Related Services](#related-services)
+ [Pricing for AWS Elemental MediaStore](#pricing)
+ [Regions for AWS Elemental MediaStore](#regions)

## AWS Elemental MediaStore Concepts<a name="concepts"></a>

ARN  
An [Amazon Resource Name](http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html)\.

Body  
The data to be uploaded into an object\.

\(Byte\) range  
A subset of object data to be addressed\. For more information, see [range](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.35) from the HTTP specification\.

Container  
A namespace that holds objects\. A container has an endpoint that you can use for writing and retrieving objects and attaching access policies\.

Endpoint  
An entry point to the AWS Elemental MediaStore service, given as an HTTP\(S\) root URL\.

ETag  
An [entity tag](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.19), which is a hash of the object data\.

Folder  
A division of a container\. A folder can hold objects and other folders\.

Item  
A term used to refer to objects and folders\.

Object  
An asset, similar to an [Amazon S3 object](http://docs.aws.amazon.com/s3/)\. Objects are the fundamental entities that are stored in AWS Elemental MediaStore\. The service accepts all file types\.

Origination service  
AWS Elemental MediaStore is considered an *origination service* because it is the point of distribution for media content delivery\.

Path  
A unique identifier for an object or folder, which indicates its location in the container\.

Part  
A subset of data \(chunk\) of an object\.

Policy  
An [IAM policy](http://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)\.

**AWS Elemental MediaStore verbs**Create  
Creates an object, often implemented with HTTP POST\.

Delete  
Deletes an object, often implemented with HTTP DELETE\.

Describe  
Returns metadata about an object, often implemented with HTTP HEAD\.

Get  
Retrieves an object\.

List  
Retrieves a list of items, which can be objects**or folders*\.*

Put  
Updates an object, often implemented with HTTP PUT\.

## Related Services<a name="related-services"></a>

+ **AWS CloudTrail** is a service that lets you monitor the calls made to the CloudTrail API for your account, including calls made by the AWS Management Console, AWS CLI, and other services\. For more information, see [AWS CloudTrail User Guide](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/)\.

+ **Amazon CloudWatch** is a monitoring service for AWS cloud resources and the applications that you run on AWS\. Use CloudWatch Events to track changes in the status of containers and objects in AWS Elemental MediaStore\. For more information, see [Amazon CloudWatch](http://docs.aws.amazon.com/cloudwatch/)\.

+ **Amazon S3** is object storage built to store and retrieve any amount of data from anywhere\.

+ **AWS Identity and Access Management \(IAM\)** is a web service that helps you securely control access to AWS resources for your users\. Use IAM to control who can use your AWS resources \(authentication\) and what resources users can use in which ways \(authorization\)\. For more information, see [[ERROR] BAD/MISSING LINK TEXT](setting-up.md)\.

## Pricing for AWS Elemental MediaStore<a name="pricing"></a>


| **Request Price** | **US West \(Oregon\)** | **US East \(N\. Virginia\)** | **EU \(Ireland\)** | **Asia Pacific \(Sydney\)** | 
| --- | --- | --- | --- | --- | 
| Storage price \(per GB per month\) | $0\.023 | $0\.023 | $0\.023 | $0\.025 | 
| PUT \(per 1k\) | $0\.005  | $0\.005  | $0\.005  | $0\.005  | 
| Media optimization \(per GB ingested\) | $0\.020  | $0\.020 | $0\.020 | $0\.025  | 
| GET, HEAD \(per 10k\) | $0\.004  | $0\.004  | $0\.004  | $0\.004  | 
| DELETE or LIST \(per 1k\) | $0\.005  | $0\.005  | $0\.005  | $0\.005  | 

## Regions for AWS Elemental MediaStore<a name="regions"></a>

AWS Elemental MediaStore is available in the following AWS Regions:


| Region Name | Region | 
| --- | --- | 
| Asia Pacific \(Sydney\)  | ap\-southeast\-2 | 
| EU \(Ireland\) | eu\-west\-1 | 
| US East \(N\. Virginia\)  | us\-east\-1 | 
| US West \(Oregon\)  | us\-west\-2 | 