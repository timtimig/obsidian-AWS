AMI -------->          PENDING                        <----- |
		            |                                           |
	REBOOTING <- RUNNING -> STOPPING -> STOPPED
				    |
			 SHUTTING DOWN
					|
			 TERMINATED

- **PENDING** - when we launch an instance, it enters the pending state. Billing has not started. Here AWS prepares an instance to run
- **RUNNING** - an instance is ready to use. Billing begins
- **REBOOTING** - rebooting OS. An instance keeps its DNS names and IP addresses
- **STOPPED** - stopped state. Billing stops (only for an instance, not for a storage). An instance retains DNS and IPs. Here we can modify some attributes, like an instance type. The data from RAM lost.
- **STOP-HIBERNATE** - In instances that have Amazon [[EBS]] we can save a state of the instance (RAM). OS saves it to EBS root volume. We can hibernate an instance only if hibernation is turned on and the instance meets the hibernation prerequisites.

#instance_lifecycle