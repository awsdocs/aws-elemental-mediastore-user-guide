# Step 2: Create User Groups<a name="setting-up-IAM-users-create-nonadmin-user-groups"></a>

You can create a user group for each policy and assign users to a group rather than attaching individual policies to each user\. Using the steps below, create two user groups: one for the **MediaStoreAllAccess** policy and one for the **MediaStoreReadOnlyAccess** policy\.

**To create user groups**

1. In the navigation pane of the IAM console, choose **Groups**, and then choose **Create New Group**\. 

1. On the **Set Group Name** page, type a name for the group, such as **MediaStoreAdmins**\.

1. Choose **Next Step**\.

1. On the **Attach Policy** page, for **Filter**, choose **Customer Managed**\.

1. In the policy list, choose the **MediaStoreAllAccess** policy that you created\.

1. Choose **Next Step**\.

1. On the **Review** page, verify that the correct policies are added to this group, and then choose **Create Group**\.

1. On the **Groups** page, repeat steps 1\-7 to create a user group with a read\-only permissions\. Use the following guidelines:
   + In step 2, type a group name such as **MediaStoreReaders**\.
   + In step 4, choose the **MediaStoreReadOnlyAccess** policy\.