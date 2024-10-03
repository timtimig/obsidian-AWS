## AWS Security Token Service

Providing temporary access to your AWS resources is achieved with the use of STS.
STS is used to request limited permissions, temporary credentials for IAM users.

**Temporary credentials**:
- we can specify expiry interval
- they are generated dynamically and provided to the user only when requested.

#### Benefits of temporary credentials:
- No need to distribute or embed long-term AWS security credentials with an application.
- You can provide access to your AWS resources to users without having to define an AWS identity for them
- After temporary security credentials expire, they cannot be reused. So, you do not have to rotate them or explicitly revoke them when they're no longer required