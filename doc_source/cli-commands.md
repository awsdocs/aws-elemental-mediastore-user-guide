# AWS CLI Commands for AWS Elemental MediaStore<a name="cli-commands"></a>

The following table shows the AWS CLI commands that you can use to create or modify containers and objects in AWS Elemental MediaStore\.


| Applies to\.\.\. | Command | Description | 
| --- | --- | --- | 
| containers \(mediastore\) | create\-container | Creates a container\. | 
| containers \(mediastore\) | delete\-container | Deletes a container\. You can’t delete a container that has objects; you can delete only empty containers\. | 
| containers \(mediastore\) | delete\-container\-policy | Removes a container policy from a container\. | 
| containers \(mediastore\) | get\-container\-policy | Retrieves the current policy of a container\. | 
| containers \(mediastore\) | list\-containers | Lists all of your containers\. | 
| containers \(mediastore\) | put\-container\-policy | Replaces the current policy of a container with the specified policy\. | 
| objects \(mediastore\-data\) | delete\-object | Deletes an object that is stored in a container\. | 
| objects \(mediastore\-data\) | describe\-object | Retrieves information about an object that is stored in a container\. | 
| objects \(mediastore\-data\) | get\-object | Downloads an object from AWS Elemental MediaStore to a specified endpoint\. You can provide a byte range to download only the part of the object that corresponds to the range\. | 
| objects \(mediastore\-data\) | help | Displays information about the command being called\. Append the keyword help to the end of any partial command line\. | 
| objects \(mediastore\-data\) | list\-items | Lists folders and objects stored in a container\. | 
| objects \(mediastore\-data\) | put\-object | Writes an object to AWS Elemental MediaStore\. | 