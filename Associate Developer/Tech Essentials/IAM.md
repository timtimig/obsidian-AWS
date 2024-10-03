# Identity and Access Management

**Authentication** answers the question, "Who are you?" 
**Authorization** answers the question, "What actions can you perform?"

##### Principals
Users, Roles, Applications, AWS Services. Principal is who making a request to AWS API.

##### IAM user
User has static credentials: a username and a password. And users can have associated credentials like an **access key ID** and a **secret access key**.
##### IAM group
A logical group of users. It's more convinient way to manage an access control. Each of these groups have set of policies and permissions. 
A policy can be attached to IAM group. Using the groups is the best practice.
##### IAM role
It's identity that can be assumed by someone who needs temporary access to AWS credentials.
A role doesn't have login credentials, only temporary creds.
A role should be used when one AWS service wants to call another AWS service (service role).
##### Access key
Access keys allow users to make programmatic calls to AWS API (CLI, SDK).
It contains an access key and a secret key.
##### IAM policy
To provide authorization rights we have policies and can attach them to users, groups, roles etc. 
It's json structure setting.
There are 2 types of policies:
- **Identity-based policy** are attached to an IAM user, group or role. These policies let you specify what identity can do (it's permissions). It can be attached to many different types of principals.
- **Resource-based policy** are attached to a resource. (S3, SQS, VPC endpoints, DynamoDB...)
##### Permissions boundary
It sets the maximum permissions that the entity can have. This can change the effective permissions for that user or role.

##### Best practices
- apply policies to groups
- use the principal of least privilege

#IAM