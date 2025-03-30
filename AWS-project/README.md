# Project Overview
This Project is designed to help you understand AWS, specifically focusing on identity and Access Management (IAM).

## Project Goals and Learning Outcomes

1. Gain an understaning of AWS IAM, Including how to create and manage users, roles, groups and policies.

2. Apply IAM concepts to secure a cloud infrastructure.

## Use Case
For Company/Businesses dealing with security and compliance issues, AWS IAM plays a crucial role in defining who is Authenticated (Signed In) and Authorized (has permissions) to use resources

## Project Setups

- Log in to the AWS Management console: Use the administrator account to log in
- Navigate to the IAM dashboard: You can manage users, groups, policies and roles from here.

### Create Policy for the Development Team to have access to EC2
1. Goto IAM Dashboard, click on policies

2. Create a new Policy (Developer).
3. In the select a service, Search for EC2 and select all EC2 services.

4. Create group to host the created policy (Developer), assign the policy for EC2 access to the Developer group.
5. Create User to assign to "Developer" group.

#### This user should have access to create, manage and deploy EC2 instances in AWS, We will go ahead to create another user with access to S3 bucket.

### Create Policy for the Development Team to have access to 
1. Goto IAM Dashboard, click on policies

2. Create a new Policy (S3 Access).
3. In the select a service, Search for S3 and select all S3 services.

4. Create group to host the created policy (S3 permission), assign the policy for S3 access to the Developer group.
5. Create User to assign to "S3 permission" group.

#### This will grant access to manage, create and deploy S3 services in AWS.