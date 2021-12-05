# AWS Certified Database – Specialty
* If you want to migrate a RDS for PostgreSQL to Aurora create an Aurora Replica from the existing production RDS for PostgreSQL instance. Stop the writes on the master, check that the replication lag is zero, and then promote the Aurora Replica as a standalone Aurora PostgreSQL DB cluster.
* You are experiencing performance issues when saving data in an Amazon ElastiCache for Redis cluster with cluster mode disabled. The performance issues are occurring during the cluster's backup window. The cluster runs in a replication group containing three nodes. Memory on the nodes is fully utilized. The solution:
  * Configure the backup job to take a snapshot of a read replica.
  * Increase the reserved-memory-percent parameter value. 
* To encripyt RDS MySQL Create a snapshot of the database. Create an encrypted copy of the snapshot and Create a new database from the encrypted snapshot.
* To make a alerting and a monitoring strategy for SQL Server database installed in a EC2 instance you can configure Amazon CloudWatch Application Insights for .NET and SQL Server to monitor and detect signs of potential problems. Configure CloudWatch Events to send notifications to an Amazon SNS topic.
* Add more storage space to the DB instance using the ModifyDBInstance action if yu run out of storage space in a MySQL RDS.
* To support proper traceability, governance, and compliance, each database administration team member must start using individual, named accounts. Furthermore, longterm database user credentials should not be used. For that Enable IAM database authentication on the Aurora cluster. Create a database user for eachv team member without a password. Attach an IAM policy to each administrator’s IAM user account that grants the connect privilege using their database user account.
* Use Amazon DynamoDB global tables and configure DynamoDB auto scaling for the tables if you want to run an application in several regions and low-latency.
* Schedule an AWS Lambda function to create an hourly snapshot of the DB instance and another Lambda function to copy the snapshot to the second Region. For disaster recovery, create a new RDS Multi-AZ DB instance from the last snapshot. With that you can restore a database in a different region within 2 hours. 
* Take a manual snapshot of the source DB instance and share the snapshot privately with the new account. Specify the snapshot ARN in an RDS resource in an AWS CloudFormation template and use StackSets to deploy to the new account. ow you can achieve centrally manage resource provisioning for its development teams across multiple accounts.
* Today, RDS allows you to create an Aurora Read Replica. Create an Aurora MySQL Read Replica of the RDS DB instance and promote it once the replication lag drops to 0 if you want to migrate an Amazon RDS DB Instance for MySQL to Amazon Aurora with near zero-downtime.
* Configure the RDS database to use IAM DB Authentication. Generate the access token using the ***aws rds generate-db-auth-token*** command. With that you will secure an Amazon RDS for MySQL database. Instead of an alphanumeric password, the database will only be accessed via a short-lived authentication token for greater security.
* Configure a DynamoDB Accelerator to cache data to handle a large volume of requests.
* You can copy a snapshot that has been encrypted using an AWS KMS encryption key. If you copy an encrypted snapshot, the copy of the snapshot must also be encrypted. If you copy an encrypted snapshot within the same AWS Region, you can encrypt the copy with the same KMS encryption key as the original snapshot, or you can specify a different KMS encryption key. If you copy an encrypted snapshot across Regions, you can't use the same KMS encryption key for the copy as used for the source snapshot, because KMS keys are Region-specific. Instead, you must specify a KMS key valid in the destination AWS Region. The source snapshot remains encrypted throughout the copy process. You can also encrypt a copy of an unencrypted snapshot. This way, you can quickly add encryption to a previously unencrypted DB instance.
* Before you move a RDS DB instance to a new network, configure the new VPC, including the security group inbound rules, the subnet group, and the route tables. When you change the VPC for a DB instance, the instance reboots when the instance moves from one network to another. Because the DB instance isn't accessible during the network modification, change the VPC during a scheduled maintenance window. You can't change the VPC for a DB instance if the DB instance is in multiple Availability Zones. Convert the DB instance to a single Availability Zone, and then convert it back to a Multi-AZ DB instance after moving to the new VPC. 
* Amazon DynamoDB global tables provide a fully managed solution for deploying a multi-regional, multi-master database, without having to build and maintain your replication solution.
* DynamoDB optionally supports conditional writes for PutItem, UpdateItem, DeleteItem. A conditional write will succeed only if the item attributes meet one or more expected conditions. Otherwise, it returns an error. Conditional writes are helpful in cases where multiple users attempt to modify the same item.
* Create the RDS DB instance with Multi-AZ deployment and set the RDS maintenance window to perform maintenance items during a low activity period to minimize downtime due to maintenance.
* You can create an AWS DMS task that captures ongoing changes to the source data store. You can do this capture while you are migrating your data. You can also create a task that captures ongoing changes after you complete your initial (full-load) migration to a supported target data store. This process is called ongoing replication or change data capture (CDC). AWS DMS uses this process when replicating ongoing changes from a source data store. This process works by collecting changes to the database logs using the database engine's native API.
* With Amazon DocumentDB (with MongoDB compatibility), you can audit events that were performed in your cluster. Examples of logged events include successful and failed authentication attempts, dropping a collection in a database, or creating an index. By default, auditing is disabled on Amazon DocumentDB and requires that you to opt-in use this feature.
* If you see the error ***Error Code: 1290. The MySQL server is running with the -–read-only option*** check if The user was connected to the Aurora cluster's reader endpoint when the error occurred.
* Enable automatic workload management in the Redshift cluster and assign the group's queries to a queue with the ***HIGHEST*** priority. Enable short query acceleration. With that you will ensure that the group's critical queries, especially the short-running ones, get prioritized over less critical and more complex queries, minimize query management and avoid any additional costs.
* AWS DMS uses the ***fn_dblog()*** or ***fn_dump_dblog()*** function in SQL Server to read the changes in the transaction log based on the log sequence number (LSN). This is how AWS DMS reads the ongoing changes from the source database in a on-premise to RDS migration involving SQL Server.
* Launch the AWS DMS replication instance in the same AWS Region, VPC, and Availability Zone where the Oracle database instance is running if you want to migrate a Oracle database instance to a different region using AWS DMS and make sure that the performance impact in the Oracle database is minimized and if the source database is configured to dynamically transform and manipulate data using transformation rule expressions.
* Using database cloning, you can quickly and cost-effectively create clones of all of the databases within an Aurora DB cluster. The clone databases require only minimal additional space when first created. Database cloning uses a copy-on-write protocol, in which data is copied at the time that data changes, either on the source databases or the clone databases.
* Monitoring is an integral part of maintaining the reliability, availability, and performance of Amazon RDS and your AWS solutions. Two of the recommended RDS monitoring tools are:
  * ***Amazon RDS Enhanced Monitoring*** — provides metrics in real-time for the operating system (OS) that your DB instance runs on. 
  * ***Performance Insights*** - expands on existing Amazon RDS monitoring features to illustrate your database's performance and analyze any issues that affect it. With the Performance Insights dashboard, you can visualize the database load and filter the load by waits, SQL statements, hosts, or users. 
* Graph databases are useful for connected, contextual, relationship-driven data. Graph databases have advantages over relational databases for certain use cases—including social networking, recommendation engines, and fraud detection—when you want to create relationships between data and quickly query these relationships. They can represent how entities relate by using actions, ownership, parentage, etc. Amazon Neptune uses graph structures such as nodes (data entities), edges (relationships), and properties to represent and store data. Edges can describe parent-child relationships, actions, product recommendations, purchases, and so on. A relationship, or edge, is a connection between two vertices that always has a start node, end node, type, and direction.
* Many applications can benefit from the ability to capture changes to items stored in a DynamoDB table, at the point in time when such changes occur. DynamoDB Streams enables solutions such as these, and many others. DynamoDB Streams captures a time-ordered sequence of item-level modifications in any DynamoDB table and stores this information in a log for up to 24 hours. Applications can access this log and view the data items as they appeared before and after they were modified, in near-real-time. When an item in the table is modified, StreamViewType determines what information are written to the stream for this table. Valid values for StreamViewType are:
  * ***KEYS_ONLY*** — Only the key attributes of the modified item.
  * ***NEW_IMAGE*** — The entire item, as it appears after it was modified.
  * ***OLD_IMAGE*** — The entire item, as it appeared before it was modified.
  * ***NEW_AND_OLD_IMAGES*** — Both the new and the old images of the item.
* In the ***IO:XactSync wait*** event, a session is issuing a COMMIT or ROLLBACK, requiring the current transaction’s changes to be persisted. Aurora is waiting for Aurora storage to acknowledge persistence. This wait event most often arises when there is a very high rate of commit activity on the system. You can sometimes alleviate this by modifying applications to commit transactions in batches.
* Increase the size allocated to the RDS DB instance storage to reduce latency in RDS with general purpose SSD.
* DynamoDB deletes expired items on a best-effort basis to ensure there's enough throughput for other data operations. Depending on the size and activity level of a table, an expired item's actual delete operation can vary. Because TTL is meant to be a background process, the nature of the capacity used to expire and delete items via TTL is variable (but free of charge). TTL typically deletes expired items within 48 hours of expiration. Processing takes place automatically, in the background, and doesn't affect read or write traffic to the table.
* An ElastiCache Redis cluster provides varying levels of data durability, performance, and cost for implementing disaster recovery or fault tolerance of your cached data. You can choose the following options to improve the data durability of your ElastiCache cluster:
  * Daily automatic backups
  * Manual backups using Redis append-only file (AOF)
  * Setting up a Multi-AZ with Automatic Failover
* Check if the client-side application's time-to-live is set too high and is caching the old DNS data. This can cause the connection failure for many minutes.
* You can use the profiler in Amazon DocumentDB (with MongoDB compatibility) to log the execution time and details of operations that were performed on your cluster. The profiler is useful for monitoring the slowest operations on your cluster to improve individual query performance and overall cluster performance.
* With the ***DeletionPolicy*** attribute, you can preserve or (in some cases) backup a resource when its stack is deleted. You specify a ***DeletionPolicy*** attribute for each resource that you want to control. If a resource has no ***DeletionPolicy*** attribute, AWS CloudFormation deletes the resource by default.
  * ***Delete*** - CloudFormation deletes the resource including its content if applicable during stack deletion.
  * ***Retain*** - CloudFormation keeps the resource without deleting the resource or its contents when its stack is deleted
  * ***Snapshot*** - For resources that support snapshots, AWS CloudFormation creates a snapshot for the resource before deleting it.
* An Aurora DB cluster is fault-tolerant by design. The cluster volume spans multiple Availability Zones in a single AWS Region, and each Availability Zone contains a copy of the cluster volume data. This functionality means that your DB cluster can tolerate a failure of an Availability Zone without any loss of data and only a brief interruption of service. If the primary instance in a DB cluster using single-master replication fails, Aurora automatically fails over to a new primary instance in one of two ways:
  * By promoting an existing Aurora Replica to the new primary instance
  * By creating a new primary instance
* You can use Amazon RDS Event Notifications and create proper event subscriptions that send notifications to the Manager using the RDS Console.
* A ***local secondary index*** maintains an alternate sort key for a given partition key value. A local secondary index also contains a copy of some or all of the attributes from its base table; you specify which attributes are projected into the local secondary index when you create the table. The data in a local secondary index is organized by the same partition key as the base table, but with a different sort key. This lets you access data items efficiently across this different dimension. For greater query or scan flexibility, you can create up to five local secondary indexes per table.
* To set the retention period for system logs, use the ***rds.log_retention_period*** parameter. You can find ***rds.log_retention_period*** in the DB parameter group associated with your DB instance. The unit for this parameter is minutes. For example, a setting of 1,440 retains logs for one day. The default value is 4,320 (three days).
* AUTH can only be enabled for ElastiCache for Redis clusters if in-transit encryption was enabled during creation.
* Amazon RDS provides metrics in real time for the operating system (OS) that your DB instance runs on. You can view the metrics for your DB instance using the console, or consume the Enhanced Monitoring JSON output from CloudWatch Logs in a monitoring system of your choice. By default, Enhanced Monitoring metrics are stored in the CloudWatch Logs for 30 days. To modify the amount of time the metrics are stored in the CloudWatch Logs, change the retention for the RDSOSMetrics log group in the CloudWatch console.
* For applications that need to read or write multiple items, DynamoDB provides the ***BatchGetItem*** and ***BatchWriteItem*** operations. Using these operations can reduce the number of network round trips from your application to DynamoDB. In addition, DynamoDB performs the individual read or write operations in parallel. Your applications benefit from this parallelism without having to manage concurrency or threading.
* You can authenticate to your DB instance using AWS Identity and Access Management (IAM) database authentication. IAM database authentication works with MySQL and PostgreSQL. With this authentication method, you don't need to use a password when you connect to a DB instance. Instead, you use an authentication token. By default, IAM database authentication is disabled on DB instances. You can enable IAM database authentication (or disable it again) using the AWS Management Console, AWS CLI, or the API. IAM authentication for PostgreSQL DB instances requires that the SSL value be 1. To allow an IAM user or role to connect to your DB instance, you must create an IAM policy. After that, you attach the policy to an IAM user or role. To use IAM authentication with PostgreSQL, connect to the DB instance, create database users, and then grant them the rds_iam role.
* Which combination of steps should the Database Specialist do to protect the ElastiCache cluster from unauthorized access?
  * Set the associated security group to allow inbound traffic on TCP port 6379 from trusted clients only.
  * Enable encryption in-transit and encryption at-rest on the ElastiCache cluster including Redit AUTH. Configure the clients to use the auth-token parameter when connecting to the Redis cluster.
* Take note that Amazon RDS is a fully-managed database service which means that AWS controls and manages the underlying servers that power your databases. Unlike a database hosted in Amazon EC2, you don't have the ability to directly connect to server and the configuration artifacts such as the pg_hba.conf or postgresql.conf files. You can use the GRANT or REVOKE commands to control table-level access.
* To migrate from an RDS PostgreSQL DB instance to an Aurora PostgreSQL DB cluster, it is recommended to create an Aurora Read Replica of your source PostgreSQL DB instance. When the replica lag between the PostgreSQL DB instance and the Aurora PostgreSQL Read Replica is zero, you can stop replication. At this point, you can promote the Aurora Read Replica to be a standalone Aurora PostgreSQL DB cluster. This standalone DB cluster can then accept write loads.
* You can use ***Microsoft Windows Authentication*** to authenticate users when they connect to your Amazon RDS for Microsoft SQL Server DB instance. The DB instance works with AWS Directory Service for Microsoft Active Directory, also called AWS Managed Microsoft AD, to enable Windows Authentication. When users authenticate with a SQL Server DB instance joined to the trusting domain, authentication requests are forwarded to the domain directory that you create with AWS Directory Service.
* AWS CloudFormation StackSets extends the functionality of stacks by enabling you to create, update, or delete stacks across multiple accounts and regions with a single operation. Using an administrator account, you define and manage an AWS CloudFormation template, and use the template as the basis for provisioning stacks into selected target accounts across specified regions.
* DynamoDB supports two types of secondary indexes:
  * Global secondary index — an index with a partition key and a sort key that can be different from those on the base table. A global secondary index is considered "global" because queries on the index can span all of the data in the base table, across all partitions.
  * Local secondary index — an index that has the same partition key as the base table, but a different sort key. A local secondary index is "local" in the sense that every partition of a local secondary index is scoped to a base table partition that has the same partition key value.
To speed up queries on non-key attributes, you can create a global secondary index. A global secondary index contains a selection of attributes from the base table, but they are organized by a primary key that is different from that of the table. The index key does not need to have any of the key attributes from the table; it doesn't even need to have the same key schema as a table.
* If the Amazon RDS instance is configured for Multi-AZ, you can perform the reboot with a failover. An Amazon RDS event is created when the reboot is completed. If your DB instance is a Multi-AZ deployment, you can force a failover from one Availability Zone (AZ) to another when you reboot.
* An important part of the AWS Schema Conversion Tool is the database migration assessment report that it generates to help you convert your schema. The report summarizes all of the schema conversion tasks and details the action items for schema that can't be converted to the DB engine of your target DB instance. You can view the report in the application. To do so, export it as a comma-separated value (CSV) or PDF file.
* Amazon DynamoDB Time to Live (TTL) allows you to define a per-item timestamp to determine when an item is no longer needed. Shortly after the date and time of the specified timestamp, DynamoDB deletes the item from your table without consuming any write throughput. TTL is provided at no extra cost as a means to reduce stored data volumes by retaining only the items that remain current for your workload’s needs.
* Amazon Redshift Federated Query enables you to use the analytic power of Amazon Redshift to directly query data stored in Amazon Aurora PostgreSQL and Amazon RDS for PostgreSQL databases.
* Configure all Aurora Replicas to have the same instance class as the primary DB instance. Implement Aurora PostgreSQL DB cluster cache management. Set the failover priority to tier-0 for the primary DB instance and one replica with the same instance class. Set the failover priority to tier-1 for the other Aurora Replicas. With that you can avoid problems if a failover event occurs.
* With Amazon Aurora with MySQL compatibility, you can backtrack a DB cluster to a specific time, without restoring data from a backup.

Backtracking allows you to rewind the DB cluster to the time you specify. When you specify a time for a backtrack, Aurora automatically chooses the nearest possible consistent time. Although backtracking is not a replacement for backing up your database, it provides the following advantages over traditional backup and restore:
  * 1) You can easily undo mistakes. If you mistakenly perform a destructive action, such as a DELETE without a WHERE clause, you can backtrack the DB cluster to a time before the destructive action with minimal interruption of service.
  * 2) You can backtrack a DB cluster quickly. Restoring a DB cluster to a point in time launches a new DB cluster and restores it from backup data or a DB cluster snapshot, which can take hours. Backtracking a DB cluster doesn't require a new DB cluster and rewinds the DB cluster in minutes.
  * 3) You can explore earlier data changes. You can repeatedly backtrack a DB cluster back and forth in time to help determine when a particular data change occurred. For example, you can backtrack a DB cluster for three hours and then backtrack forward in time for one hour. In this case, the backtrack time is two hours before the original time.
* For data protection, AWS recommends that you protect your AWS account credentials and set up principals with AWS Identity and Access Management (IAM). Doing this means that each user is given only the permissions necessary to fulfill their job duties. It is also recommended that you secure your data in the following ways:
  * Use multi-factor authentication (MFA) with each account.
  * Use SSL/TLS to communicate with AWS resources.
  * Set up API and user activity logging with AWS CloudTrail.
  * Use AWS encryption solutions, along with all default security controls within AWS services.
  * Use advanced managed security services such as Amazon Macie, which assists in discovering and securing personal data that is stored in Amazon S3.
* If yo need to migrate large LOBs configure an AWS DMS task to migrate the tables without LOBs. Configure another AWS DMS task using limited LOB mode with a LobMaxSize setting of 100MB to migrate LOB data to the target RDS instance.