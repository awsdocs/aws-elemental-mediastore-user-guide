# AWS CLI commands for AWS Elemental MediaStore<a name="cli-commands"></a>

The following table shows the AWS CLI commands that you can use to create or modify containers and objects in AWS Elemental MediaStore\.


| Applies to\.\.\. | Command | Description | 
| --- | --- | --- | 
| containers \(mediastore\) | create\-container | Creates a container\. | 
| containers \(mediastore\) | delete\-container | Deletes a container\. You can’t delete a container that has objects; you can delete only empty containers\. | 
| containers \(mediastore\) | delete\-container\-policy | Removes a container policy from a container\. | 
| containers \(mediastore\) | delete\-lifecycle\-policy | Removes an object lifecycle policy from a container\. | 
| containers \(mediastore\) | get\-container\-policy | Retrieves the current policy of a container\. | 
| containers \(mediastore\) | get\-lifecycle\-policy | Retrieves the object lifecycle policy that is assigned to a container\. | 
| containers \(mediastore\) | list\-containers | Lists all of your containers\. | 
| containers \(mediastore\) | put\-container\-policy | Replaces the current policy of a container with the specified policy\. | 
| containers \(mediastore\) | put\-lifecycle\-policy | Writes an object lifecycle policy to a container\. If the container already has an object lifecycle policy, the service replaces the previous policy with the new policy\.  | 
| objects \(mediastore\-data\) | delete\-object | Deletes an object that is stored in a container\. | 
| objects \(mediastore\-data\) | describe\-object | Retrieves information about an object that is stored in a container\. | 
| objects \(mediastore\-data\) | get\-object | Downloads an object from AWS Elemental MediaStore to a specified endpoint\. You can provide a byte range to download only the part of the object that corresponds to the range\. | 
| objects \(mediastore\-data\) | help | Displays information about the command being called\. Append the keyword help to the end of any partial command line\. | 
| objects \(mediastore\-data\) | list\-items | Lists folders and objects stored in a container\. | 
| objects \(mediastore\-data\) | put\-object | Writes an object to a container\. | 