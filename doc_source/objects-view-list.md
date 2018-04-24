# Viewing a List of Objects<a name="objects-view-list"></a>

You can use the AWS Elemental MediaStore console to view items \(objects and folders\) stored in the top\-most level of a container or in a folder\. Items stored in a subfolder of the current container or folder will not be displayed\. You can use the AWS CLI to view a list of objects and folders within a container, regardless of how many folders or subfolders are within the container\.

**To view a list of objects in a specific container \(console\)**

1. Open the AWS Elemental MediaStore console at [https://console\.aws\.amazon\.com/mediastore/](https://console.aws.amazon.com/mediastore/)\.

1. On the **Containers** page, choose the name of the container that has the folder that you want to view\. 

1. Choose the name of the folder from the list\.

   A details page appears, showing all folders and objects that are stored in the folder\.

**To view a list of objects in a specific folder \(console\)**

1. Open the AWS Elemental MediaStore console at [https://console\.aws\.amazon\.com/mediastore/](https://console.aws.amazon.com/mediastore/)\.

1. On the **Containers** page, choose the name of the container that has the folder that you want to view\. 

   A details page appears, showing all folders and objects that are stored in the container\.

**To view a list of objects and folders in a specific container \(AWS CLI\)**
+ In the AWS CLI, use the **list\-items** command\.

  Example:

  ```
  aws mediastore-data --region us-west-2 list-items --endpoint=https://aaabbbcccdddee.data.mediastore.us-west-2.amazonaws.com
  ```

  Example return value:

  ```
  {
      "Items": [
          {
              "Type": "FOLDER",
              "Name": "ExampleLiveDemo"
          },
          {
              "Type": "FOLDER",
              "Name": "folder_1"
          }
      ]
  }
  ```

**To view a list of objects and folders in a specific folder \(AWS CLI\)**
+ In the AWS CLI, use the **list\-items** command, with the specified folder name at the end of the request\.

  Example:

  ```
  aws mediastore-data --region us-west-2 list-items --endpoint=https://aaabbbcccdddee.data.mediastore.us-west-2.amazonaws.com --path=/folder_1
  ```

  Example return value:

  ```
  {
      "Items": [
          {
              "Type": "OBJECT",
              "Name": "1512519711640.ts"
          },
          {
              "Type": "OBJECT",
              "Name": "test_file.pdf"
          }
      ]
  }
  ```