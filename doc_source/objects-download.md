# Downloading an Object<a name="objects-download"></a>

You can use the console to download an object\. You can use the AWS CLI to download an object or only part of an object\.

**To download an object \(console\)**

1. Open the MediaStore console at [https://console\.aws\.amazon\.com/mediastore/](https://console.aws.amazon.com/mediastore/)\.

1. On the **Containers** page, choose the name of container that has the object that you want to download\.

1. If the object that you want to download is in a folder, continue choosing the folder names until you see the object\.

1. Choose the name of the object\.

1. On the **Object** details page, choose **Download**\.

**To download an object \(AWS CLI\)**
+ In the AWS CLI, use the **get\-object** command\.

  Example:

  ```
  aws mediastore-data --region us-west-2 get-object --endpoint=https://aaabbbcccdddee.data.mediastore.us-west-2.amazonaws.com --path=/test/document/README3.md README3.md
  ```

  Example return value:

  ```
  {
      "ContentType": "binary/octet-stream",
      "ContentLength": "2774",
      "CacheControl": "pre-commit",
      "StatusCode": 200
  }
  ```

**To download part of an object \(AWS CLI\)**
+ In the AWS CLI, use the **get\-object** command, and specify a range\.

  Example:

  ```
  aws mediastore-data --region us-west-2 get-object --endpoint=https://aaabbbcccdddee.data.mediastore.us-west-2.amazonaws.com --path=/test/document/README3.md --range="bytes=0-100" README4.md
  ```

  Example return value:

  ```
  {
      "ContentType": "binary/octet-stream",
      "ContentRange": "bytes 0-100/2774",
      "CacheControl": "pre-commit",
      "ContentLength": "101",
      "StatusCode": 206
  }
  ```