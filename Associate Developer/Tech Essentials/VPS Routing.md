#### Route tables
A route table contains a set of rules, called routes, that are used to determine where network traffic is directed.

#### A main route table
When you create a VPC, AWS creates a route table called the main route table. AWS assumes that when you create a new VPC with subnets, you want traffic to flow between them. Therefore, the default configuration of the main route table is to allow traffic between all subnets in the local network.

#### Custom route tables
If you associate a subnet with a custom route table, the subnet will use it instead of the main route table.
Each custom route table that you create will have the local route already inside it, allowing communication to flow between all resources and subnets inside the VPC.
To provide an access to a subnet from internet we need to create a route in a route table with access to an internet gateway. Then attach the table to the subnet.