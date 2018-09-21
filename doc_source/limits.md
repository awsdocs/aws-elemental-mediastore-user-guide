# Limits in AWS Elemental MediaStore<a name="limits"></a>

The following table describes limits in AWS Elemental MediaStore\. 


****  

|  Resource or Operation  |  Default Limit  |  Comments  | 
| --- | --- | --- | 
| Containers | 100 |  | 
|  [DeleteObject](https://docs.aws.amazon.com/mediastore/latest/apireference/API_objstore_DeleteObject.html)  |  100 transactions per second \(TPS\)  |  The maximum number of operation requests that you can make per second\. Additional requests are throttled\. You can [request a limit increase](https://console.aws.amazon.com/support/home#/case/create?issueType=service-limit-increase&limitType=service-code-mediastore)\.  | 
|  [DescribeObject](https://docs.aws.amazon.com/mediastore/latest/apireference/API_objstore_DescribeObject.html)  |  1,000 transactions per second \(TPS\)  |  The maximum number of operation requests that you can make per second\. Additional requests are throttled\. You can [request a limit increase](https://console.aws.amazon.com/support/home#/case/create?issueType=service-limit-increase&limitType=service-code-mediastore)\.  | 
| Folder Levels | 10 |  | 
| Folders | Unlimited |  | 
|  [GetObject](https://docs.aws.amazon.com/mediastore/latest/apireference/API_objstore_GetObject.html)  |  1,000 transactions per second \(TPS\)  |  The maximum number of operation requests that you can make per second\. Additional requests are throttled\. You can [request a limit increase](https://console.aws.amazon.com/support/home#/case/create?issueType=service-limit-increase&limitType=service-code-mediastore)\.  | 
|  [ListItems](https://docs.aws.amazon.com/mediastore/latest/apireference/API_objstore_ListItems.html)  |  5 transactions per second \(TPS\)  |  The maximum number of operation requests that you can make per second\. Additional requests are throttled\. You can [request a limit increase](https://console.aws.amazon.com/support/home#/case/create?issueType=service-limit-increase&limitType=service-code-mediastore)\.  | 
| Object Size | 20 MB |  | 
| Objects | Unlimited |  | 
|  [PutObject](https://docs.aws.amazon.com/mediastore/latest/apireference/API_objstore_PutObject.html)  |  100 transactions per second \(TPS\)  |  The maximum number of operation requests that you can make per second\. Additional requests are throttled\. You can [request a limit increase](https://console.aws.amazon.com/support/home#/case/create?issueType=service-limit-increase&limitType=service-code-mediastore)\.  | 