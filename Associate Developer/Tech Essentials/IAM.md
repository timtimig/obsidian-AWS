# Identity and Access Management

**Authentication** answers the question, "Are you who you say you are?" 
**Authorization** answers the question, "What actions can you perform?"

##### IAM policy
IAM allows to create users. To provide authorization rights we can attach IAM policy to users.
##### IAM group
A policy can be attached to IAM group. Using the groups is the best practice.
##### IAM user
User has a username and a password. And users can have associated credentials like an **access key ID** and a **secret access key**.
##### IAM role
It's identity that can be assumed by someone who needs temporary access to AWS credentials.
A role doesn't have login credentials, only temporary creds.
A role should be used when one AWS service wants to call another AWS service.
##### Access key
Access keys allow users to make programmatic calls to AWS API (CLI, SDK).
It contains an access key and a secret key.

#IAM