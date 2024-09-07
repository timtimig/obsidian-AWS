We have 2 options to secure our VPC resources: **ACL** and security groups

#### ACL (Network access control list)
Like a firewall for a subnet. What kind of traffic is allowed to enter and leave a subnet. 
Network ACLs are considered stateless, so you need to include both the inbound and outbound ports used for the protocol.
*Everything is allowed by default.*

#### Security groups
These are firewall for EC2 instance level. For example to allow traffic from internet we need to create an inbound rule for the security group.
Security groups are stateful. That means that they will remember if a connection is originally initiated by the EC2 instance or from the outside, and temporarily allow traffic to respond without modifying the inbound rules.
*All inbound traffic is blocked by default, all outbound is allowed*.
A common design pattern is to organize instances into different groups and create security groups for each to control network communication between them.

#ACL #security_groups