# Amazon Elastic Compute Cloud

To create an EC2 instance we must define the following:
- **Hardware specifications:** CPU, memory, network and storage
- **Logical configurations:** Networking location, firewall rules, authentication, and the operating system of your choice
#### AMI
#AMI - Amazon Machine Image. It contains information how we want our instance to be configured: OS, launch permissions, pre-installed apps etc...
We can use one image to launch multiple instances in EC2.
There are multiple ways to select AMI include AMI marketplace.

#### Instance types
AWS offers a variety of instances that differ based on performance. To get an overview of the capacity details for a particular instance, you should look at the instance type. For example: 
**c5n.xlarge**
**c** - instance family. This indicates that this instance belongs to the compute optimized family.
**5** - instance generation.
**n** -  additional attributes, such as local NVMe storage.
**xlarge** - instance size

#### Auto scaling
The EC2 Auto Scaling service adds and removes capacity to keep a steady and predictable performance at the lowest possible cost.

Links:
[[Instance lifecycle]]
[[Pricing]]

#EC2 #EC2_Auto_Scaling 