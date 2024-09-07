## Amazon Relational Database Service

RDS is a managed database. It is built from compute and storage. The compute portion is called the database (DB) instance, which runs the DB engine. A DB instance can contain multiple databases with the same engine, and each DB can contain multiple tables.

Underneath the DB instance is an EC2 instance. However, this instance is managed through the Amazon RDS console instead of the Amazon EC2 console.

#### Storage on RDS
RDS uses #EBS for storage. This includes MySQL, MariaDB, PostgreSQL, Oracle, and SQL Server. 

When using Aurora, data is stored in cluster volumes, which are single, virtual volumes that use SSDs. A cluster volume contains copies of your data across three Availability Zones in a single AWS Region. For nonpersistent, temporary files, Aurora uses local storage.

Amazon RDS provides three storage types: General Purpose SSD (also called gp2 and gp3), Provisioned IOPS SSD (also called io1), and Magnetic (also called standard). They differ in performance characteristics and price, which means you can tailor your storage performance and cost to the needs of your database workload.

#### RDS in VPC
When you create a DB instance, you select the Amazon Virtual Private Cloud ( #VPC) your databases will live in. Then, you select the subnets that will be designated for your DB. This is called a DB subnet group, and it has at least two Availability Zones in its Region. The subnets in a DB subnet group should be private, so they don’t have a route to the internet gateway. This ensures that your DB instance, and the data inside it, can be reached only by the application backend.

#### Backup
**Automated backups** are turned on by default. When you create your DB instance, you set a backup window that is the period of time that automatic backups occur. Backup can cause increased latency and downtime. 
**Retaining backups:** Automated backups are retained between 0 and 35 days. You might ask yourself, “Why set automated backups for 0 days?” The 0 days setting stops automated backups from happening. If you set it to 0, it will also delete all existing automated backups.
**Point-in-time recovery:** This creates a new DB instance using data restored from a specific point in time. This restoration method provides more granularity by restoring the full backup and rolling back transactions up to the specified time range.

**Manual snapshots**: If you want to keep your automated backups longer than 35 days, use manual snapshots. They exist until you delete them. If you restore data from a manual snapshot, it creates a new DB instance using the data from the snapshot.

#### Redundancy with RDS Multi-AZ
In an Amazon RDS Multi-AZ deployment, Amazon RDS creates a redundant copy of your database in another Availability Zone. You end up with two copies of your database—a primary copy in a subnet in one Availability Zone and a standby copy in a subnet in a second Availability Zone.
The primary copy of your database provides access to your data so that applications can query and display the information. The data in the primary copy is synchronously replicated to the standby copy. The standby copy is not considered an active database, and it does not get queried by applications.
When you create a DB instance, a Domain Name System (DNS) name is provided. AWS uses that DNS name to fail over to the standby database. In an automatic failover, the standby database is promoted to the primary role, and queries are redirected to the new primary database.