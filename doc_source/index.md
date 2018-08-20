# AWS Elemental MediaStore User Guide

-----
*****Copyright &copy; 2018 Amazon Web Services, Inc. and/or its affiliates. All rights reserved.*****

-----
Amazon's trademarks and trade dress may not be used in 
     connection with any product or service that is not Amazon's, 
     in any manner that is likely to cause confusion among customers, 
     or in any manner that disparages or discredits Amazon. All other 
     trademarks not owned by Amazon are the property of their respective
     owners, who may or may not be affiliated with, connected to, or 
     sponsored by Amazon.

-----
## Contents
+ [What Is AWS Elemental MediaStore?](what-is.md)
   + [AWS Elemental MediaStore Concepts and Terminology](what-is-concepts.md)
   + [Related Services](what-is-related-services.md)
   + [Accessing AWS Elemental MediaStore](what-is-accessing.md)
   + [Pricing for AWS Elemental MediaStore](what-is-pricing.md)
   + [Regions for AWS Elemental MediaStore](what-is-regions.md)
+ [Setting Up AWS Elemental MediaStore](setting-up.md)
   + [Signing Up for AWS](aws-sign-up.md)
   + [Creating an Admin IAM User](IAM-user-create.md)
   + [Creating a Non-Admin IAM User](setting-up-IAM-users-create-nonadmin.md)
      + [Step 1: Create Policies](setting-up-IAM-users-create-nonadmin-policies.md)
      + [Step 2: Create User Groups](setting-up-IAM-users-create-nonadmin-user-groups.md)
      + [Step 3: Create Users](setting-up-IAM-users-create-nonadmin-users.md)
+ [Getting Started with AWS Elemental MediaStore](getting-started.md)
+ [Working with Containers in AWS Elemental MediaStore](containers.md)
   + [Rules for Container Names](containers-rules-for-names.md)
   + [Creating a Container](containers-create.md)
   + [Viewing the Details for a Container](containers-view-details.md)
   + [Viewing a List of Containers](containers-view-list.md)
   + [Deleting a Container](containers-delete.md)
+ [Working with Container Policies in AWS Elemental MediaStore](policies.md)
   + [Viewing a Container Policy](policies-view.md)
   + [Editing a Container Policy](policies-edit.md)
   + [Example Container Policies](policies-examples.md)
      + [Example Container Policy: Default](policies-examples-default.md)
      + [Example Container Policy: Public Read Access over HTTPS](policies-examples-public-https.md)
      + [Example Container Policy: Public Read Access over HTTP or HTTPS](policies-examples-public-httphttps.md)
      + [Example Container Policy: Cross-Account Read Access—HTTP Enabled](policies-examples-cross-acccount-http.md)
      + [Example Container Policy: Cross-Account Read Access over HTTPS](policies-examples-cross-acccount-https.md)
      + [Example Container Policy: Cross-Account Read Access to a Role](policies-examples-cross-acccount-read.md)
      + [Example Container Policy: Cross-Account Full Access to a Role](policies-examples-cross-acccount-full.md)
      + [Example Container Policy: Post Access to an AWS Service to a Folder](policies-examples-post-access-folder.md)
      + [Example Container Policy: Post Access to an AWS Service to Multiple Folders](policies-examples-post-access-multiple-folders.md)
+ [Cross-Origin Resource Sharing (CORS) in AWS Elemental MediaStore](cors-policy.md)
   + [CORS Use-case Scenarios](cors-policy-use-case-scenarios.md)
   + [Adding a CORS Policy to a Container](cors-policy-adding.md)
   + [Viewing a CORS Policy](cors-policy-viewing.md)
   + [Editing a CORS Policy](cors-policy-editing.md)
   + [Deleting a CORS Policy](cors-policy-deleting.md)
   + [Troubleshooting CORS Issues](cors-policy-troubleshooting.md)
   + [Example CORS Policies](cors-policies-examples.md)
      + [Example CORS Policy: Read Access for Any Domain](cors-policies-examples-read-all-domains.md)
      + [Example CORS Policy: Read Access for a Specific Domain](cors-policies-examples-read-specific-domain.md)
+ [Working with Folders in AWS Elemental MediaStore](folders.md)
   + [Rules for Folder Names](folders-rules-for-names.md)
   + [Creating a Folder](folders-create.md)
   + [Deleting a Folder](folders-delete.md)
+ [Working with Objects in AWS Elemental MediaStore](objects.md)
   + [Uploading an Object](objects-upload.md)
   + [Viewing a List of Objects](objects-view-list.md)
   + [Viewing the Details of an Object](objects-view-details.md)
   + [Downloading an Object](objects-download.md)
   + [Deleting an Object](objects-delete.md)
+ [AWS CLI Commands for AWS Elemental MediaStore](cli-commands.md)
+ [Monitoring AWS Elemental MediaStore](monitoring.md)
   + [Logging AWS Elemental MediaStore API Calls with AWS CloudTrail](logging-using-cloudtrail.md)
      + [AWS Elemental MediaStore Information in CloudTrail](monitoring-service-info-in-cloudtrail.md)
      + [Example: AWS Elemental MediaStore Log File Entries](monitoring-example-log-file-entries.md)
+ [Working with Content Delivery Networks (CDNs)](cdns.md)
   + [Allowing Amazon CloudFront to Access Your AWS Elemental MediaStore Container](cdns-allowing-cloudfront-to-access-mediastore.md)
+ [Limits in AWS Elemental MediaStore](limits.md)
+ [Document History for User Guide](doc-history.md)
+ [AWS Glossary](glossary.md)