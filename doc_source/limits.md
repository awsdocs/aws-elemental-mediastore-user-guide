# Limits in AWS Elemental MediaStore<a name="limits"></a>

The following table describes limits in AWS Elemental MediaStore\. 


****  

|  Resource or Operation  |  Default Limit  |  Comments  | 
| --- | --- | --- | 
| Containers | 100 | The maximum number of containers that you can create in this account\. | 
|  [DeleteObject](https://docs.aws.amazon.com/mediastore/latest/apireference/API_objstore_DeleteObject.html)  |  100 transactions per second \(TPS\)  |  The maximum number of operation requests that you can make per second\. Additional requests are throttled\. You can [request a limit increase](https://console.aws.amazon.com/support/home#/case/create?issueType=service-limit-increase&limitType=service-code-mediastore)\.  | 
|  [DescribeObject](https://docs.aws.amazon.com/mediastore/latest/apireference/API_objstore_DescribeObject.html)  |  1,000 transactions per second \(TPS\)  |  The maximum number of operation requests that you can make per second\. Additional requests are throttled\. You can [request a limit increase](https://console.aws.amazon.com/support/home#/case/create?issueType=service-limit-increase&limitType=service-code-mediastore)\.  | 
| Folder Levels | 10 | The maximum number of folder levels that you can create in a container\. You can create an unlimited number of folders, as long as they are not nested more than 10 levels within a container\. | 
| Folders | Unlimited | There is no limit to the number of folders that you can create in a container\. You can create an unlimited number of folders, as long as they are not nested more than 10 levels within a container\. | 
|  [GetObject](https://docs.aws.amazon.com/mediastore/latest/apireference/API_objstore_GetObject.html)  |  1,000 transactions per second \(TPS\)  |  The maximum number of operation requests that you can make per second\. Additional requests are throttled\. You can [request a limit increase](https://console.aws.amazon.com/support/home#/case/create?issueType=service-limit-increase&limitType=service-code-mediastore)\.  | 
|  [ListItems](https://docs.aws.amazon.com/mediastore/latest/apireference/API_objstore_ListItems.html)  |  5 transactions per second \(TPS\)  |  The maximum number of operation requests that you can make per second\. Additional requests are throttled\. You can [request a limit increase](https://console.aws.amazon.com/support/home#/case/create?issueType=service-limit-increase&limitType=service-code-mediastore)\.  | 
| Object Size | 25 MB | The maximum file size of a single object\. | 
| Objects | Unlimited | There is no limit to the number of objects that you can save to a folder or container in your account\. | 
|  [PutObject](https://docs.aws.amazon.com/mediastore/latest/apireference/API_objstore_PutObject.html)  |  100 transactions per second \(TPS\)  |  The maximum number of operation requests that you can make per second\. Additional requests are throttled\. You can [request a limit increase](https://console.aws.amazon.com/support/home#/case/create?issueType=service-limit-increase&limitType=service-code-mediastore)\.  | 
| Rules in an Object Lifecycle Policy | 10 | 