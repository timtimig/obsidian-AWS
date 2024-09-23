# Identity and Access Management

**Authentication** answers the question, "Who are you?" 
**Authorization** answers the question, "What actions can you perform?"

##### IAM policy
IAM allows to create users. To provide authorization rights we can attach IAM policy to users. Json structure setting.
There are 2 types of policies:
- **Identity-based policy** are attached to an IAM user, group or role. These policies let you specify what identity can do (it's permissions)
- **Resource-based policy** are attached to a resource. (S3, SQS, VPC endpoints, DynamoDB...)
- 
##### Permissions boundary
It sets the maximum permissions that the entity can have. This can change the effective permissions for that user or role.

##### IAM group
A policy can be attached to IAM group. Using the groups is the best practice.
##### IAM user
User has a username and a password. And users can have associated credentials like an **access key ID** and a **secret access key**.
##### IAM role
It's identity that can be assumed by someone who needs temporary access to AWS credentials.
A role doesn't have login credentials, only temporary creds.
A role should be used when one AWS service wants to call another AWS service (service role).
##### Access key
Access keys allow users to make programmatic calls to AWS API (CLI, SDK).
It contains an access key and a secret key.

##### Best practices
- apply policies to groups
- use the principal of least privilege

#IAM