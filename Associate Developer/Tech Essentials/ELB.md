## Elastic Load Balancing

Load balancing refers to the process of distributing tasks across a set of resources. A load balancer needs to take all the traffic and redirect it to the backend servers based on an algorithm. The most popular algorithm is round robin, which sends the traffic to each server one after the other.
ELB can distribute incoming application traffic across EC2 instances, containers, IP addresses, and Lambda functions. Because ELB can load balance to IP addresses, it can work in a **hybrid mode**, which means it also load balances to on-premises servers.

#### Health checks
Monitoring is an important part of load balancers because they should route traffic to only healthy EC2 instances. ELB supports two types of health checks as follows:
- Establishing a connection to a backend EC2 instance using TCP and marking the instance as available if the connection is successful
- Making an HTTP or HTTPS request to a resource that you specify and validating that an HTTP response code is returned
After determining the availability of a new EC2 instance, the load balancer starts sending traffic to it. If ELB determines that an EC2 instance is no longer working, it stops sending traffic to it and informs [[EC2 Auto Scaling]]. The Auto Scaling removes that instance from the group and replace it with a new EC2 instance.

#### ELB components
The ELB service is made up of three main components: rules, listeners, and target groups.

**Rule** - to associate a target group to a listener. Rules are made up of two conditions. The first condition is the source IP address of the client. The second condition decides which target group to send the traffic to.

**Listener**. The client connects to the listener. To define a listener, a port must be provided in addition to the protocol. There can be many listeners for a single load balancer.

**Target group**. Resources are defined in one or more target groups. This is where you define the type of backend you want to direct traffic to, such as EC2 instances, Lambda functions, or IP addresses. Also, a health check must be defined for each target group.

#### Types of load balancers
