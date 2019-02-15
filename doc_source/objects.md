# Objects in AWS Elemental MediaStore<a name="objects"></a>

AWS Elemental MediaStore assets are called *objects*\. You can upload an object to a container or to a folder within the container\.

In AWS Elemental MediaStore, you can upload, download, and delete objects: 
+ **Upload** – Add an object to a container or folder\. This is not the same as creating an object\. You must create your objects locally before you can upload them to AWS Elemental MediaStore\.
+ **Download** – Copy an object from AWS Elemental MediaStore to another location\. This does not remove the object from MediaStore\.
+ **Delete** – Remove an object from AWS Elemental MediaStore completely\. You can delete objects individually, or you can [add an object lifecycle policy](policies-object-lifecycle-add.md) to automatically delete objects within a container after a specified duration\.

AWS Elemental MediaStore accepts all file types\. 

**Topics**
+ [Uploading an Object](objects-upload.md)
+ [Viewing a List of Objects](objects-view-list.md)
+ [Viewing the Details of an Object](objects-view-details.md)
+ [Downloading an Object](objects-download.md)
+ [Deleting an Object](objects-delete.md)