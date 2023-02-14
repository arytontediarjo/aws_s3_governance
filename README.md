# DataBrew S3 Data Governance

This repository is a list of json files used for provisioning SSO Roles via AWS Inline Policies. It will be means of version control for any changes related to bucket provisioning. **Please update this repository whenever there are any changes to the Inline Policy in IAM Identity Center for version control :)**

## Prerequisites
- Administrator Access to DataBrew `Root` Account

## Step 1: Accessing AWS IAM Identity Center

1. Go to DataBrew [SSO Portal](https://databrewllc.awsapps.com/start#/)

2. Assume `Administrator Access Role` in the SSO Portal under `joebrew` account

3. Search for **IAM Identity Center**

## Step 2: Providing Access

1. In IAM Identity Center, start by creating a `IAM group`. You can create one by going to **Groups** in the sidebar and Create a Group there
2. After `IAM group` is created, you'd like to invite users to this group. You can do so by going to the **Users** section from the sidebar
3. User will receive email notification to create their own personal password 
4. As user is onboarded to IAM Identity Center, put user based on their respective groups/persona by clicking their specific groups and using the add button there

## Step 3: Using Inline Policy for Restricting Access
Each group will only have limited access to DataBrew buckets, inline policy will be used to accomodate this data governing process. 

1. Under **Multi-account permissions** go to Permission Sets
2. Click **Create permission Set**
3. Click **Custom permission set**
4. Go to **Inline Policy**
5. In the inline policy section, you will be able to use an JSON editor to control access to a certain bucket. Check this [Official AWS Docs](https://aws.amazon.com/blogs/security/writing-iam-policies-grant-access-to-user-specific-folders-in-an-amazon-s3-bucket/) for detailed information
6. Finish the remaining description and tags information

## Step 4: Tagging the Permission to DataBrew Accounts
You have created the permissions, now it's time to apply that permission to your desired bucket. 
1. Under **Multi-account permissions** go to AWS accounts
2. Click on the target AWS Accounts
3. Click on **Assign users or groups**
4. Choose the group to have the access to this account
5. Choose the **Inline Policy** you just created in step 3
6. Submit the assignments to the target AWS Account

## Step 5: Update this Repository Inline Policy 
After all said and done, please update the inline policy inside this repository for version control
