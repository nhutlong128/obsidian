---
cards-deck: Obsidian::Cloud-Computing::Database::RDS
tags: rds, database
---
### Metadata

-  Type: #permanent #database
    Date written: #2021-06-27
    Source:  https://aws.amazon.com/vi/rds/
	https://quizlet.com/358279792/rds-flash-cards/
    Status: #wip 
    Keywords:  #cloudcomputing #aws #rds
	Related:
	
### Notes
- [[RDS Database Type]]
- [[RDS Provision Instance]]
- [[RDS Location]]
- [[RDS Type]]
- [[RDS High Availability Mechanism]]
- [[RDS Scalability Mechanism]]
- [[RDS Storage]]
- [[RDS Replication]]
- [[RDS Security]]
- [[RDS Optimize]]
- [[RDS Fees charged]]
- [[RDS Specific]]

### Questions

1. My company would like to have a MySQL database internally that is going to be available even in case of a disaster in the AWS Cloud. I should setup
- Read Replicas
- Encryption
- Multi AZ
#card 
Multi AZ
^1626790243377

2. Our RDS database struggles to keep up with the demand of the users from our website. Our million users mostly read news, and we don't post news very often. Which solution is **NOT** adapted to this problem?
- An ElastiCache cluster
- RDS Read Replicas
- RDS Multi AZ
#card 
RDS Multi AZ
^1626790243386

3. We have setup read replicas on our RDS database, but our users are complaining that upon updating their social media posts, they do not see the update right away
- There must be a bug in our application
- Read Replicas have asynchronous replication and therefore it's likely our users will only observe eventual consistency
- We should have setup multi-az instead
#card 
Read Replicas have asynchronous replication and therefore it's likely our users will only observe eventual consistency
^1626790243396

4. Which RDS Classic (not Aurora) feature does not require us to change our SQL connection string?
- Read Replicas
- Multi AZ
#card 
Multi AZ keeps the same connection string regardless of which database is up. Read Replicas imply we need to reference them individually in our application as each read replica will have its own DNS name
^1626790243406

5. You want to ensure your Redis cluster will always be available
- Enable Read Replicas
- Enable Multi AZ
#card 
Multi AZ ensures high availability
^1626790243416

6. Your application functions on an ASG behind an ALB. Users have to constantly log back in and you'd rather not enable stickiness on your ALB as you fear it will overload some servers. What should you do?
- Create your own Load Balancer and deploy that on EC2 instances
- Store session data in RDS
- Store session data in ElastiCache
- Store session data in a shared EBS volume
#card 
Store session data in ElastiCache. Storing Session Data in ElastiCache is a common pattern to ensuring different instances can retrieve your user's state if needed.
^1626790243425

7. One analytics application is currently performing its queries against your main production database. These queries slow down the database which impacts the main user experience. What should you do to improve the situation?
- Setup a Read Replica
- Setup Multi AZ
- Run the analytics queries at night
- Increase the RDS instance size
#card 
 Read Replica
 
8. You have a requirement to use TDE (Transparent Data Encryption) on top of KMS. Which database technology does NOT support TDE on RDS?
- PostgreSQL
- Oracle
- MS SQL Server
#card 
PostgreSQL
^1626790243435

9. You would like to ensure you have a database available in another region if a disaster happens to your main region. Which database do you recommend?
- RDS Read Replicas
- RDS Multi AZ
- Aurora Read Replicas
- Aurora Global Database
#card 
Aurora Global Database. Global Databases allow you to have cross region replication
^1626790243445

10. How can you enhance the security of your Redis cache to force users to enter a password?
- Use Redis Auth
- Use IAM Auth
- Use Security Groups
#card 
Use Redis Auth
^1626790243454

11. Your company has a production Node.js application that is using RDS MySQL 5.6 as its data backend. A new application programmed in Java will perform some heavy analytics workload to create a dashboard, on a regular hourly basis. You want to the final solution to minimize costs and have minimal disruption on the production application, what should you do?
- Enable Multi-AZ for the RDS database and run the analytics workload on the standby database
- Create a Read Replica in a different AZ and run the analytics workload on the replica database
- Create a Read Replica in a different AZ and run the analytics workload on the source database
#card 
Create a Read Replica in a different AZ and run the analytics workload on the replica database
^1626790243463

12. You would like to create a disaster recovery strategy for your RDS PostgreSQL database so that in case of a regional outage, a database can be quickly made available for Read and Write workload in another region. The DR database must be highly available. What do you recommend?
- Create a Read Replica in the same region and enable multi-AZ on the main database
- Create a Read Replica in a different region and enable multi-AZ on the main database
- Create a Read Replica in the same region and enable multi-AZ on the read replica
- Enable Multi-Region on the main database
#card 
Create a Read Replica in a different region and enable multi-AZ on the main database
^1626790243473

13. You are managing a PostgreSQL database and for security reasons, you would like to ensure users are authenticated using short-lived credentials. What do you suggest doing?
- Install PostgreSQL on EC2 and install the pg_iam module. Authenticate using IAM username and password
- Use PostgreSQL for RDS and install the pg_iam module. Authenticate using IAM username and password
- Use PostgreSQL for RDS and authenticate using a token obtained through the RDS service.
- Use PostgreSQL for RDS and force SSL connections. Authenticate using SSL certificates that you regularly rotate
#card 
Use PostgreSQL for RDS and authenticate using a token obtained through the RDS service. In this case, IAM is leveraged to obtain the RDS service token, so this is the IAM authentication use case.
^1626790243483

14. Which RDS database technology does NOT support IAM authentication?
- Oracle
- PostgreSQL
- MySQL
#card 
Oracle
^1626790243492

15. An application is running in production, using an Aurora database as its backend. Your development team would like to run a version of the application in a scaled-down application, but still, be able to perform some heavy workload on a need-basis. Most of the time, the application will be unused. Your CIO has tasked you with helping the team while minimizing costs. What do you suggest?
- Use an Aurora Global Database
- Use an RDS database instead
- Use Aurora Serverless
- Run Aurora on EC2, and write a script to shut down the EC2 instance at night
#card 
Use Aurora Serverless
^1626790243502

16. You are looking to perform OLTP, and would like to have the underlying storage with the maximum amount of replication and auto-scaling capability. What do you recommend?
- ElastiCache
- Redshift
- Aurora
- RDS
#card 
Aurora
^1626790243511

17. As a solution architect, you plan on creating a social media website where users can be friends with each other, and like each other's posts. You plan on performing some complicated queries such as "What are the number of likes on the posts that have been posted by the friends of Mike?". What database do you suggest?
- RDS
- Redshift
- Neptune
- ElastiSearch
#card 
Neptune
^1626790243521

18. You would like to store big objects of 100 MB into a reliable and durable Key Value store. What do you recommend? 
- S3
- DynamoDB
- ElastiCache
#card 
S3. S3 is indeed a key value store! (where the key is the full path of the object in the bucket)
^1626790243530

19. Amazon's ElastiCache uses which two engines?  
A. Reddit & Memcrush  
B. MyISAM & InnoDB  
C. Redis & Memory  
D. Redis & Memcached 
#card 
D
^1626790243540

20. Which of the following DynamoDB features are chargeable, when using a single region? (Choose 2)
A. Incoming Data Transfer  
B. The number of tables created  
C. Read and Write Capacity  
D. Storage of Data
#card 
C, D  
There will always be a charge for provisioning read and write capacity and the storage of data within DynamoDB, therefore these two answers are correct. There is no charge for the transfer of data into DynamoDB, providing you stay within a single region (if you cross regions, you will be charged at both ends of the transfer.) There is no charge for the actual number of tables you can create in DynamoDB, providing the RCU and WCU are set to 0, however in practice you cannot set this to anything less than 1 so there always be a nominal fee associated with each table.
^1626790243549

21. Under what circumstances would I choose provisioned IOPS over standard storage when creating an RDS instance?  
A. If your business was trying to save money.  
B. If you have workloads that are not sensitive to latency/lag.  
C. If you use online transaction processing in your production environment.  
D. If this was a test DB.
#card 
C
^1626790243559

22. When creating an RDS instance, you can select the Availability Zone into which you deploy it.  
A. False  
B. True
#card 
B
^1626790243568

23. In RDS, changes to the backup window take effect ________.  
A. The next day  
B. Immediately  
C. You cannot back up in RDS.  
D. After 30 minutes
#card 
B
^1626790243578

24. Which of the following is not a feature of DynamoDB?  
A. The ability to perform operations by using a user-defined primary key  
B. The ability to store relational based data  
C. Data reads that are either eventually consistent or strongly consistent  
D. The primary key can either be a single-attribute or a composite
#card 
B
^1626790243587

25. MySQL installations default to port number ________.  
A. 3306  
B. 80  
C. 1433  
D. 3389
#card 
A
^1626790243597

26. If you want your application to check RDS for an error, have it look for an ______ code in the response from the Amazon RDS API.  
A. Exit  
B. Abort  
C. Incorrect  
D. Error
#card 
D
^1626790243606

27. You are hosting a MySQL database on the root volume of an EC2 instance. The database is using a large number of IOPS, and you need to increase the number of IOPS available to it. What should you do?  
A. Use Cloud Front to cache the database.  
B. Migrate the database to Glacier.  
C. Add 4 additional EBS SSD volumes and create a RAID 10 using these volumes.  
D. Migrate the database to an S3 bucket.
#card 
C
^1626790243615

28. If you are using Amazon RDS Provisioned IOPS storage with a Microsoft SQL Server database engine, what is the maximum size RDS volume you can have by default?  
A. 500GB  
B. 16TB  
C. 1TB  
D. 6TB  
E. 32TB
#card 
B. 16TB  
^1626790243625

29. If I wanted to run a database on an EC2 instance, which of the following storage options would Amazon recommend?  
A. EBS  
B. S3  
C. RDS  
D. Glacier
#card 
A
^1626790243634

30. When you have deployed an RDS database into multiple availability zones, can you use the secondary database as an independent read node?  
A. Yes.  
B. It depends on how you set it up.  
C. No.  
D. Only in US-West-1.
#card 
C. The secondary database is to be thought of as a DR site ~ high availability, it will be active only when the primary fails, as per the documentation. You need read replicas to increase your read speed. https://aws.amazon.com/rds/details/multi-az/
^1626790243644

31. When you add a rule to an RDS DB security group, you must specify a port number or protocol.  
A. True  
B. False
#card 
B. Technically a destination port number is needed, however with a DB security group the RDS instance port number is automatically applied to the RDS DB Security Group.
^1626790243654

32.   Which set of RDS database engines is currently available?  
A. MariaDB, SQL Server, MySQL, Cassandra 
B. PostgreSQL, MariaDB, MongoDB, Aurora  
C. Oracle, SQL Server, MySQL, PostgreSQL  
D. Aurora, MySQL, SQL Server, Cassandra
#card 
C
^1626790243664

33. Which of the following is most suitable for OLAP?  
A. Redshift  
B. RDS  
C. ElastiCache  
D. DynamoDB
#card 
A
^1626790243673

34. What happens to the I/O operations of a single-AZ RDS instance during a database snapshot or backup?  
A. I/O operations to the database are sent to a Secondary instance of a Multi-AZ installation (for the duration of the snapshot.)  
B. I/O operations will function normally.  
C. Nothing.  
D. I/O may be briefly suspended while the backup process initializes (typically under a few seconds), and you may experience a brief period of elevated latency.
#card 
D. I/O may be briefly suspended while the backup process initializes (typically under a few seconds), and you may experience a brief period of elevated latency.
^1626790243683

35. RDS Reserved instances are available for multi-AZ deployments.  
A. True  
B. False
#card 
A
^1626790243692

36. How many copies of my data does RDS - Aurora store by default?  
A. 1  
B. 3  
C. 6  
D. 2
#card 
C
^1626790243702

37. In RDS, what is the maximum value I can set for my backup retention period?  
A. 45 Days  
B. 15 Days  
C. 30 Days  
D. 35 Days
#card 
D
^1626790243711

38. Can I "force" a failover for any RDS instance that has Multi-AZ configured?
A. Yes.  
B. Only for Oracle RDS instances.  
C. No.
#card 
A
^1626790243721

39. What data transfer charge is incurred when replicating data from your primary RDS instance to your secondary RDS instance?  
A. There is no charge associated with this action.  
B. The charge is the same as the standard data transfer charge.  
C. The charge is double the standard data transfer charge.  
D. The charge is half of the standard data transfer charge.
#card 
A
^1626790243730

40. With new RDS Db instances, automated backups are enabled by default?  
A. True 
B. False
#card 
A
^1626790243740

41. You can RDP or SSH in to an RDS instance to see what is going on with the operating system.  
A. False  
B. True
#card 
A
^1626790243750

42. Which of the following data formats does Amazon Athena support? (Choose 3)  
A. XML  
B. JSON  
C. Apache ORC  
D. Apache Parquet
#card 
B, C, D
^1626790243760

43. You are a solutions architect working for a media company that hosts its website on AWS. Currently, there is a single Amazon Elastic Compute Cloud (Amazon EC2) Instance on AWS with MySQL installed locally to that Amazon EC2 Instance. You have been asked to make the company's production environment more resilient and to increase performance. You suggest that the company split out the MySQL database onto an Amazon RDS Instance with Multi-AZ enabled. This addresses the company's increased resiliency requirements. Now you need to suggest how you can increase performance. Ninety-nine percent of the company's end users are magazine subscribers who will be reading additional articles on the website, so only one percent of end users will need to write data to the site. What should you suggest to increase performance?  
A. Alter the connection string so that if a user is going to write data, it is written to the secondary copy of the Multi-AZ database.  
B. Alter the connection string so that if a user is going to write data, it is written to the primary copy of the Multi-AZ database.  
C. Recommend that the company use read replicas, and distribute the traffic across multiple read replicas.  
D. Migrate the MySQL database to Amazon Redshift to take advantage of columnar storage and maximize performance.
#card 
C. In this scenario, the best idea is to use read replicas to scale out the database and thus maximize read performance. When using Multi-AZ, the secondary database is not accessible and all reads and writes must go to the primary or any read replicas.  
Multi-AZ Notes:  
1) For disaster recovery  
2) Synchronous DB copy  
3) Same region (intra-region)  
4) Offline (no query capability)  
5) SQL Server, Oracle, MySQL, Postgres, MariaDB  
Read Replica Notes:  
1) For performance primarily  
2) Asynchronous DB copy  
3) Across AZs AND regions  
4) Queryable  
5) MySQL, Postgres, MariaDB, Aurora  
6) No Oracle, No SQL Server
^1626790243769

44. You have been using Amazon Relational Database Service (Amazon RDS) for the last year to run an important application with automated backups enabled. One of your team members is performing routine maintenance and accidentally drops an important table, causing an outage. How can you recover the missing data while minimizing the duration of the outage?  
A. Perform an undo operation and recover the table.  
B. Restore the database from a recent automated DB snapshot.  
C. Restore only the dropped table from the DB snapshot.  
D. The data cannot be recovered.
#card 
B. DB Snapshots can be used to restore a complete copy of the database at a specific point in time. Individual tables cannot be extracted from a snapshot.
^1626790243779

45. Which Amazon Relational Database Service (Amazon RDS) database engines support Multi-AZ?  
A. All of them  
B. Microsoft SQL Server, MySQL, and Oracle  
C. Oracle, Amazon Aurora, and PostgreSQL  
D. MySQL
#card 
A
^1626790243789

46. Which Amazon Relational Database Service (Amazon RDS) database engines support read replicas?  
A. Microsoft SQL Server and Oracle  
B. MySQL, MariaDB, PostgreSQL, and Aurora  
C. Aurora, Microsoft SQL Server, and Oracle  
D. MySQL and PostgreSQL
#card 
B
^1626790243799

47. Your team is building an order processing system that will span multiple Availability Zones. During testing, the team wanted to test how the application will react to a database failover. How can you enable this type of test?  
A. Force a Multi-AZ failover from one Availability Zone to another by rebooting the primary instance using the Amazon RDS console.  
B. Terminate the DB instance, and create a new one. Update the connection string.  
C. Create a support case asking for a failover.  
D. It is not possible to test a failover.
#card 
A. You can force a failover from one Availability Zine to another by rebooting the primary instance in the AWS Management Console. This is often how people test a failover in the real world. There is no need to create a support case.
^1626790243809

48. You are a system administrator whose company has moved its production database to AWS. Your company monitors its estate using Amazon CloudWatch, which sends alarms using Amazon Simple Notification Service (Amazon SNS) to your mobile phone. One night, you get an alert that your primary Amazon Relational Database Service (Amazon RDS) Instance has gone down. You have Multi-AZ enabled on this instance. What should you do to ensure the failover happens quickly?  
A. Update your Domain Name System (DNS) to point to the secondary instance's new IP address, forcing your application to fail over to the secondary instance.  
B. Connect to your server using Secure Shell (SSH) and update your connection strings so that your application can communicate to the secondary instance instead of the failed primary instance.  
C. Take a snapshot of the secondary instance and create a new instance using this snapshot, then update your connection string to point to the new instance.  
D. No action is necessary. Your connection string points to the database endpoint, and AWS automatically updates this endpoint to point to your secondary instance.
#card 
D. Monitor the environment while Amazon RDS attempts to recover automatically. AWS will update the DB endpoint to point to the secondary instance automatically.
^1626790243819

49. You are working for a small organization without a dedicated database administrator on staff. All of your current workloads use MySQL. You need to install Microsoft SQL Server Enterprise edition quickly to support an accounting back office application on Amazon Relational Database Service (Amazon RDS). What should you do?  
A. Launch an Amazon RDS DB Instance, and select Microsoft SQL Server Enterprise Edition under the Bring Your Own License (BYOL) model.  
B. Provision SQL Server Enterprise Edition using the License Included option from the Amazon RDS Console.  
C. SQL Server Enterprise edition is only available via the Command Line Interface (CLI).  
Install the command-line tools on your laptop, and then provision your new Amazon RDS Instance using the CLI.  
D. You cannot use SQL Server Enterprise edition on Amazon RDS. You should install this on to a dedicated Amazon Elastic Compute Cloud (Amazon EC2) Instance.
#card 
B. Provision SQL Server Enterprise Edition using the License Included option from the Amazon RDS Console.
^1626790243829

50. You are building the database tier for an enterprise application that gets occasional activity throughout the day. Which storage type should you select as your default option?  
A. Magnetic storage  
B. General Purpose Solid State Drive (SSD)  
C. Provisioned IOPS (SSD)  
D. Storage Area Network (SAN)-attached
#card 
B. General Purpose (SSD) volumes are generally the right choice for databases that have bursts of activity.
^1626790243838

51. You are designing an e-commerce web application that will scale to potentially hundreds of thousands of concurrent users. Which database technology is best suited to hold the session state for large numbers of concurrent users?  
A. Relational database using Amazon Relational Database Service (Amazon RDS)  
B. NoSQL database table using Amazon DynamoDB  
C. Data warehouse using Amazon Redshift  
D. Amazon Simple Storage Service (Amazon S3)
#card 
B. NoSQL databases like Amazon DynamoDB excel at scaling to hundreds of thousands of requests with key/ value access to user profile and session.
^1626790243848

52. Which of the following techniques can you use to help you meet Recovery Point Objective (RPO) and Recovery Time Objective (RTO) requirements? (Choose 3 answers)  
A. DB snapshots  
B. DB option groups  
C. Read replica  
D. Multi-AZ deployment
#card 
A, C, D. DB snapshots allow you to back up and recover your data, while read replicas and a Multi-AZ deployment allow you to replicate your data and reduce the time to failover.
^1626790243857

53. When using Amazon Relational Database Service (Amazon RDS) Multi-AZ, how can you offload read requests from the primary? (Choose 2 answers)  
A. Configure the connection string of the clients to connect to the secondary node and perform reads while the primary is used for writes.  
B. Amazon RDS automatically sends writes to the primary and sends reads to the secondary.  
C. Add a read replica DB instance, and configure the client's application logic to use a read-replica.  
D. Create a caching environment using ElastiCache to cache frequently used data. Update the application logic to read/ write from the cache.
#card 
C, D. Amazon RDS allows for the creation of one or more read-replicas for many engines that can be used to handle reads. Another common pattern is to create a cache using Memcached and Amazon ElastiCache to store frequently used queries. The secondary slave DB Instance is not accessible and cannot be used to offload queries.
^1626790243867

54. You are building a large order processing system and are responsible for securing the database. Which actions will you take to protect the data? (Choose 3 answers)  
A. Adjust AWS Identity and Access Management (IAM) permissions for administrators.  
B. Configure security groups and network Access Control Lists (ACLs) to limit network access.  
C. Configure database users, and grant permissions to database objects.  
D. Install anti-virus software on the Amazon RDS DB Instance.
#card 
A, B, C. Protecting your database requires a multilayered approach that secures the infrastructure, the network, and the database itself. Amazon RDS is a managed service and direct access to the OS is not available.
^1626790243876

55. Your team manages a popular website running Amazon Relational Database Service (Amazon RDS) MySQL back end. The Marketing department has just informed you about an upcoming television commercial that will drive thousands of new visitors to the website. How can you prepare your database to handle the load? (Choose 3 answers)  
A. Vertically scale the DB Instance by selecting a more powerful instance class.  
B. Create read replicas to offload read requests and update your application.  
C. Upgrade the storage from Magnetic volumes to General Purpose Solid State Drive (SSD) volumes.  
D. Upgrade to Amazon Redshift for faster columnar storage.
#card 
A, B, C. Vertically scaling up is one of the simpler options that can give you additional processing power without making any architectural changes. Read replicas require some application changes but let you scale processing power horizontally. Finally, busy databases are often I/ O- bound, so upgrading storage to General Purpose (SSD) or Provisioned IOPS (SSD) can often allow for additional request processing.
^1626790243885

56. You are building a photo management application that maintains metadata on millions of images in an Amazon DynamoDB table. When a photo is retrieved, you want to display the metadata next to the image. Which Amazon DynamoDB operation will you use to retrieve the metadata attributes from the table?  
A. Scan operation  
B. Search operation  
C. Query operation  
D. Find operation
#card 
C. Query is the most efficient operation to find a single item in a large table.
^1626790243895

57. You are creating an Amazon DynamoDB table that will contain messages for a social chat application. This table will have the following attributes: Username (String), Timestamp (Number), Message (String). Which attribute should you use as the partition key? The sort key?  
A. Username, Timestamp  
B. Username, Message  
C. Timestamp, Message  
D. Message, Timestamp
#card 
A. Using the Username as a partition key will evenly spread your users across the partitions. Messages are often filtered down by time range, so Timestamp makes sense as a sort key.
^1626790243905

58. Which statement about Amazon DynamoDB tables is true? (Choose 1 answer)  
A. Global secondary indexes can only be created when the table is being created.  
B. Local secondary indexes can only be created when the table is being created.  
C. You can only have one global secondary index.  
D. You can only have one local secondary index.
#card 
B. You can have multiple local secondary indexes, and they must be created at the same time the table is created. You can create multiple global secondary indexes associated with a table at any time.
^1626790243915

59. Which of the following workloads are a good fit for running on Amazon Redshift? (Choose 2 answers)  
A. Transactional database supporting a busy e-commerce order processing website  
B. Reporting database supporting back-office analytics  
C. Data warehouse used to aggregate multiple disparate data sources  
D. Manage session state and user profile data for thousands of concurrent users
#card 
B, C. Amazon Redshift is an Online Analytical Processing (OLAP) data warehouse designed for analytics, Extract, Transform, Load (ETL), and high-speed querying. It is not well suited for running transactional applications that require high volumes of small inserts or updates.
^1626790243925

60. You are running your MySQL database in RDS. The database is critical for you, and you can't afford to lose any data in the case of any kind of failure. What kind of architecture will you go with for RDS?  
A. Create the RDS across multiple regions using a cross-regional read replica  
B. Create the RDS across multiple AZs in master standby mode  
C. Create the RDS and create multiple read replicas in multiple AZs with the same region  
D. Create a multimaster RDS database across multiple AZs
#card 
B. If you use a cross-regional replica and a read replica within the same region, the data replication happens asynchronously, so there is a chance of data loss. Multimaster is not supported in RDS. By creating the master and standby architecture, the data replication happens synchronously, so there is zero data loss.
^1626790243934

61. Your application is I/O bound, and your application needs around 36,000 IOPS. The application you are running is critical for the business. How can you make sure the application always gets all the IOPS it requests and the database is highly available?  
A. Install the database in EC2 using an EBS-optimized instance, and choose a I/O optimized instance class with an SSD-based hard drive  
B. Install the database in RDS using SSD  
C. Install the database in RDS in multi-AZ using Provisioned IOPS and select 36,000 IOPS  
D. Install multiple copies of read replicas in RDS so all the workload gets distributed across multiple read replicas and you can cater to the I/O requirement
#card 
C. You can choose to install the database in EC2, but if you can get all the same benefits by installing the database in RDS, then why not? If you install the database in SSD, you don't know if you can meet the 36,000 IOPS requirement. A read replica is going to take care of the read-only workload. The requirement does not say the division of read and write IO between 36,000 IOPS.
^1626790243944

62. You have a legacy application that needs a file system in the database server to write application files. Where should you install the database?  
A. You can achieve this using RDS because RDS has a file system in the database server  
B. Install the database on an EC2 server to get full control  
C. Install the database in RDS, mount an EFS from the RDS server, and give the EFS mount point to the application for writing the application files  
D. Create the database using a multi-AZ architecture in RDS
#card 
B. In this example, you need access to the operating system, and RDS does not give you access to the OS. You must install the database in an EC2 server to get complete control.
^1626790243954

63. You are running a MySQL database in RDS, and you have been tasked with creating a disaster recovery architecture. What approach is easiest for creating the DR instance in a different region?  
A. Create an EC2 server in a different region and constantly replicate the database over there.  
B. Create an RDS database in the other region and use third-party software to replicate the data across the database.  
C. While installing the database, use multiple regions. This way, your database gets installed into multiple regions directly.  
D. Use the cross-regional replication functionality of RDS. This will quickly spin off a read replica in a different region that can be used for disaster recovery.
#card 
D. You can achieve this by creating an EC2 server in a different region and replicating, but when your primary site is running on RDS, why not use RDS for the secondary site as well? You can use third-party software for replication, but when the functionality exists out of the box in RDS, why pay extra to any third party? You can't install a database using multiple regions out of the box.
^1626790243964

64. If you encrypt a database running in RDS, what objects are going to be encrypted? A. The entire database  
B. The database backups and snapshot  
C. The database log files  
D. All of the above
#card 
D. When you encrypted a database, everything gets encrypted including the database, backups, logs, read replicas, snapshot, and so on.
^1626790243974

65. Your company has just acquired a new company, and the number of users who are going to use the database will double. The database is running on Aurora. What things can you do to handle the additional users? (Choose two.)  
A. Scale up the database vertically by choosing a bigger box  
B. Use a combination of Aurora and EC2 to host the database  
C. Create a few read replicas to handle the additional read-only traffic  
D. Create the Aurora instance across multiple regions with a multimaster mode
#card 
A, C. You can't host Aurora on a EC2 server. Multimaster is not supported in Aurora.
^1626790243984

66. Which RDS engine does not support read replicas?  
A. MySQL  
B. Aurora MySQL  
C. PostgreSQL  
D. Oracle
#card 
D. Only RDS Oracle does not support read replicas; the rest of the engines do support it.
^1626790243994

67. What are the various ways of securing a database running in RDS? (Choose two.) A. Create the database in a private subnet  
B. Encrypt the entire database  
C. Create the database in multiple AZs  
D. Change the IP address of the database every week
#card 
A, B. Creating the database in multiple AZs is going to provide high availability and has nothing to do with security. Changing the IP address every week will be a painful activity and still won't secure the database if you don't encrypt it.
^1626790244003

68. You're running a mission-critical application, and you are hosting the database for that application in RDS. Your IT team needs to access all the critical OS metrics every five seconds. What approach would you choose?  
A. Write a script to capture all the key metrics and schedule the script to run every five seconds using a cron job  
B. Schedule a job every five seconds to capture the OS metrics  
C. Use standard monitoring  
D. Use advanced monitoring
#card 
D. In RDS, you don't have access to OS, so you can't run a cron job. You can't capture the OS metrics by running a database job. Standard monitoring provides metrics for one minute.
^1626790244013

69. Which of the following statements are true for Amazon Aurora? (Choose three.)  
A. The storage is replicated at three different AZs.  
B. The data is copied at six different places.  
C. It uses a quorum-based system for reads and writes.  
D. Aurora supports all the commercial databases.
#card 
A, B, C. Amazon Aurora supports only MySQL and PostgreSQL. It does not support commercial databases.
^1626790244023

70. Which of the following does Amazon DynamoDB support? (Choose two.)  
A. Graph database  
B. Key-value database  
C. Document database  
D. Relational database
#card 
B, C. Amazon DynamoDB supports key-value and document structures. It is not a relational database. It does not support graph databases.
^1626790244033

71. I want to store JSON objects. Which database should I choose?  
A. Amazon Aurora for MySQL  
B. Oracle hosted on EC2  
C. Amazon Aurora for PostgreSQL  
D. Amazon DynamoDB
#card 
D. A JSON object needs to be stored in a NoSQL database. Amazon Aurora for MySQL and PostgreSQL and Oracle are relational databases.
^1626790244043

72. I have to run my analytics, and to optimize I want to store all the data in columnar format. Which database serves my need?  
A. Amazon Aurora for MySQL  
B. Amazon Redshift  
C. Amazon DynamoDB  
D. Amazon Aurora for Postgres
#card 
B. Amazon Redshift stores all the data in columnar format. Amazon Aurora for MySQL and PostgreSQL store the database in row format, and Amazon DynamoDB is a NoSQL database.
^1626790244053

73. What are the two in-memory key-value engines that Amazon ElastiCache supports? (Choose two.)  
A. Memcached  
B. Redis  
C. MySQL  
D. SQL Server
#card 
A, B
^1626790244063

74. You want to launch a copy of a Redshift cluster to a different region. What is the easiest way to do this?  
A. Create a cluster manually in a different region and load all the data  
B. Extend the existing cluster to a different region  
C. Use third-party software like Golden Gate to replicate the data  
D. Enable a cross-region snapshot and restore the database from the snapshot to a different region
#card 
D. Loading the data manually will be too much work. You can't extend the cluster to a different region. A Redshift cluster is specific to a particular AZ. It can't go beyond an AZ as of writing this book. Using Golden Gate is going to cost a lot, and there is no need for it when there is an easy solution available.
^1626790244072

75. How is load balancing enabled for multiple tasks to the same container instance?  
A. Path-based routing  
B. Reverse proxy  
C. NAT  
D. Dynamic port mappng  
E. Dynamic listeners
#card 
D. AWS recently launched a new Application Load Balancer (ALB) that supports Dynamic Port Mapping with ECS. It allows you to run two containers of a service on a single server on dynamic ports which ALB automatically detects and reconfigures itself.
^1626790244082

76. What encryption support is available for tenants that are deploying AWS DynamoDB?  
A. Server-side encryption  
B. Client-side encryption  
C. Client-side and server-side encryption  
D. Encryption not supported  
E. Block level encryption
#card 
B
^1626790244092

77. What are three primary reasons for deploying ElastiCache?  
A. Data security  
B. Managed service  
C. Replication with REDIS  
D. Durablility  
E. Low latency
#card 
B, C, E
^1626790244102

78. What service does not support session data persistence store to enable web-based stateful applications?  
A. RDS  
B. Memcached  
C. DynamoDB  
D. Redis  
E. RedShift
#card 
B
^1626790244112

79. How does Memcached implement horizontal scaling?  
A. Auto-Scaling  
B. Database store  
C. Partitioning  
D. EC2 instances S3 bucket
#card 
C
^1626790244121

80. What two options are available for tenants to access ElastiCache (Choose 2)?  
A. VPC peering link  
B. EC2 instances  
C. EFS mount  
D. Cross-region VPC
#card 
A, B
^1626790244131

81. What two statements correctly describe in-transit encryption support on ElastiCache platform (Choose 2)?  
A. not supported for ElastiCache platform  
B. supported on Redis replication group  
C. encrypts cached data at rest  
D. not supported on Memcached cluster  
E. IPsec must be enabled first
#card 
B, D
^1626790244141

82. What Amazon AWS platform is designed for complex analytics of a variety of large data sets based on custom code? The applications include machine learning and data transformation.  
A. EC2  
B. Beanstalk  
C. Redshift  
D. EMR
#card 
D. Amazon EMR (Elastic Map Reduce) processes big data across a Hadoop cluster of virtual servers on Amazon Elastic Compute Cloud (EC2) and Amazon Simple Storage Service (S3). The elastic in EMR's name refers to its dynamic resizing ability, which allows it to ramp up or reduce resource use depending on the demand at any given time.
^1626790244150

83. What are two primary advantages of DynamoDB?  
A. SQL support  
B. Managed service  
C. Performance  
D. CloudFront integration
#card 
B, C
^1626790244160

84. What two fault tolerant features does Amazon RDS support?  
A. Copy snapshot to a different region  
B. Create read replica to a different region  
C. Copy unencrypted read-replica only  
D. Copy read/write replica and snapshot
#card 
A, B
^1626790244170

85. What managed services are included with Amazon RDS? (select four)  
A. Assign network capacity to database instances  
B. Install database software  
C. Perform regular backups  
D. Data replication across multiple availability zones  
E. Data replication across single availability zone only  
F. Configure database  
G. Performance tuning
#card 
A, B, C, D
^1626790244180

86. What two configuration features are required to create a private database instance?  
A. Security group  
B. Network ACL  
C. CloudWatch  
D. Elastic IP (EIP)  
E. Nondefault VSP  
F. DNS
#card 
A, F
^1626790244189

87. What storage type is recommended for an online transaction processing (OLTP) application deployed to Multi-AZ RDS with significant workloads?  
A. General Purpose SSD  
B. Magnetic  
C. EBS volumes  
D. Provisioned IOPS
#card 
D. Provisioned IOPS
^1626790244199

88. What features are supported with Amazon RDS? (Select three)  
A. Horizontal scaling with multiple read replicas  
B. Elastic load balancing RDS read replicas  
C. Replicate read replicas cross-region  
D. Automatic failover to master database instance  
E. Application load balancer (ALB)
#card 
A, C, E
^1626790244209

89. What are three advantages of standby replica in a Multi-AZ RDS deployment?  
A. Fault tolerance  
B. Eliminate I/O freezes  
C. Horizontal scaling  
D. Vertical scaling  
E. Data redundancy
#card 
A, B, E. Vertical scaling implies increasing the size (cpu and memory) of the server.  Horizontal scaling implies read replicas.
^1626790244219

90. What consistency model is the default used by DynamoDB?  
A. Strongly consistent  
B. Eventually consistent  
C. No default model  
D. Casual consistency  
E. Sequential consistency
#card 
B
^1626790244229

91. What does RDS use for database and log storage?  
A. EBS  
B. S3  
C. Instance store  
D. Local store  
E. SSD
#card 
A
^1626790244239

92.   What statements correctly describe support for Microsoft SQL Server within Amazon VPC? (select three)  
A. read/write replica  
B. Read replica only  
C. Vertical scaling  
D. Native load balancing  
E. EBS storage only  
F. S3 storage only
#card 
B, C, D
^1626790244248

93. Select two features available with Amazon RDS for MySQL?  
A. Auto-Scaling  
B. Read requests to standby replicas  
C. Real-time database replication  
D. Active read requests only
#card 
B, C
^1626790244258

94. What are two characteristics of Amazon RDS (choose 2)?  
A. Database managed service  
B. NoSQL queries  
C. Native load balancer  
D. Database write replicas  
E. Automatic failover of read replica
#card 
A, C
^1626790244267

95.   What caching engines are supported with Amazon ElastiCache? (Select two)  
A. HAProxy  
B. Route 53  
C. RedShift  
D. REdis  
E. Memcached  
F. CloudFront
#card 
D, E
^1626790244277

96. What are three primary characteristics of DynamoDB?  
A. Less scalable than RDS  
B. Static content  
C. Store metadata for S3 objects  
D. Replication to three Availability Zones  
E. High read/write throughput
#card 
C, D, E
^1626790244287

97. What are three examples of using Lambda functions to move data between AWS services?  
A. Read data directly from DynamoDB streams to RDS  
B. Read data from Kinesis stream and write data to DynamoDB  
C. Read data from DynamoDB stream to Firehose and write to S3  
D. Read data from S3 and write metadata to DynamoDB  
E. Read data from Kinesis firehose to Kinesis data stream
#card 
B, C, D. Kinesis Streams. The more customizable option, Streams is best suited for developers building custom applications or streaming data for specialized needs. The customizability of the approach, however, requires manual scaling and provisioning. Data typically is made available in a stream for 24 hours, but for an additional cost, users can gain data availability for up to seven days.  
Kineses Firehose. The simpler approach, Firehose handles loading data streams directly into AWS products for processing. Scaling is handled automatically, up to gigabytes per second, and allows for batching, encrypting, and compressing. Firehose also allows for streaming to S3, Elasticsearch Service, or Redshift, where data can be copied for processing through additional services.
^1626790244297

98. You have enabled Amazon RDS database services in VPC1 for an application with public web servers in VPC2. How do you connect the web servers to the RDS database instance so they can communicate considering the VPC's are in different regions?  
A. VPC endpoints  
B. VPN gateway  
C. Path-based routing  
D. Publicly accessible database  
E. VPC peering
#card 
D
^1626790244307

99. You have a requirement to create an index to search customer objects stored in S3 buckets. The solution should enable you to create a metadata search index for each object stored to an S3 bucket. Select the most scalable and cost effective solution.  
A. RDS, ElastiCache  
B. DynamoDB,. Lambda  
C. RDS, EMR, ALB  
D. RedShift
#card 
DynamoDB,. Lambda  
^1626790244317

100. What are three advantages of using DynamoDB over S3 for storing IoT sensor data where there are 100,000 datapoint samples sent per minute?
A. S3 must create a single file for each event  
B. IoT can write data directly to DynamoDB  
C. DynamoDB provides fast read/writes to a structured table for queries  
D. DynamoDB is designed for frequent access and fast lookup of small records
E. S3 is designed for frequent access and fast lookup of smaller records  
F. IoT can write data directly to S3
#card 
B, C, D
^1626790244326

101. Your company is a provider of online gaming that customers access with various network access devices including mobile phones. What is a data warehousing solutions for large amounts of information on player behavior, statistics and events for analysis using SQL tools?  
A. redShift  
B. DynamoDB  
C. RDS  
D. Elasticsearch
#card 
A
^1626790244336

102. What two statements are correct when comparing Elasticsearch and RedShift as analytical tools?  
A. Elasticsearch is a text search engine and document indexing tool  
B. RedShift supports complex SQL-based queries with Petabyte sized data store  
C. Elasticsearch supports SQL queries  
D. RedShift provides only basic analytical services  
E. Elasticsearch does not support JSON data type
#card 
A, B
^1626790244345

103. What happens when read or write requests exceed capacity units (throughput capacity) for a DynamoDB table or index? (select two)  
A. DynamoDB automatically increases read/write units  
B. DynamoDB can throttle requests so that requests are not exceeded  
C. HTTP 400 code is returned (Bad Request)  
D. HTTP 500 code is returned (Server Error)  
E. DynamoDB automatically increases read/write units if provisioned throughput is enabled
#card 
B, C
^1626790244355

104. What read consistency method provides lower latency for GetItem requests?  
A. Strongly persistent  
B. Eventually consistent  
C. Strongly consistent  
D. Write consistent
#card 
B
^1626790244365

105. You must specify strongly consistent read and write capacity for you DynamoDB database. You have determined read capacity of 128 Kbps and write capacity of 25 Kbps is required for your application. What is the read and write capacity units required for DynamoDB table?  
A. 32 read units, 25 write units  
B. 1 read unit, 1 write unit  
C. 16 read units, 2.5 write units  
D. 64 read units, 10 write units
#card 
A. Read Capacity: single read per second for 4 KB. Write Capcity: single write per second for 1 KB
^1626790244374

106. What DynamoDB capacity management technique is based on the tenant specifying an upper and lower range for read/write capacity units?  
A. Demand  
B. Provisioned throughput  
C. Reserved capacity  
D. Auto scaling  
E. General purpose
#card 
D
^1626790244384

107. What is the maximum volume size of a MySQL RDS database?  
A. 6 TB  
B. 3 TB  
C. 16 TB  
D. unlimited
#card 
C
^1626790244394

108. What is the maximum size of a dynamoDB record (item)?  
A. 400 KB  
B. 64 KB  
C. 1 KB  
D. 10 KB
#card 
A
^1626790244404

109. Which of the following objects are good candidates to store in a cache? (Choose 3 answers)  
A. Session state  
B. Shopping cart  
C. Product catalog  
D. Bank account balance
#card 
B, C. Many types of objects are good candidates to cache because they have the potential to be accessed by numerous users repeatedly. Even the balance of a bank account could be cached for short periods of time if the back-end database query is slow to respond.
^1626790244413

110. Which of the following cache engines are supported by Amazon ElastiCache? (Choose 2 answers)  
A. MySQL  
B. Memcached  
C. Redis  
D. Couchbase
#card 
B, C. Amazon ElastiCache supports Memcached and Redis cache engines. MySQL is not a cache engine, and Couchbase is not supported.
^1626790244423

111. How many nodes can you add to an Amazon ElastiCache cluster running Memcached?  
A. 1  
B. 5  
C. 20  
D. 100
#card 
C. The default limit is 20 nodes per cluster.
^1626790244433

112. How many nodes can you add to an Amazon ElastiCache cluster running Redis?  
A. 1  
B. 5  
C. 20  
D. 100
#card 
A. Redis clusters can only contain a single node; however, you can group multiple clusters together into a replication group.
^1626790244442

113. An application currently uses Memcached to cache frequently used database queries. Which steps are required to migrate the application to use Amazon ElastiCache with minimal changes? (Choose 2 answers)  
A. Recompile the application to use the Amazon ElastiCache libraries.  
B. Update the configuration file with the endpoint for the Amazon ElastiCache cluster.  
C. Configure a security group to allow access from the application servers.  
D. Connect to the Amazon ElastiCache nodes using Secure Shell (SSH) and install the latest version of Memcached.
#card 
B, C. Amazon ElastiCache is Application Programming Interface (API)-compatible with existing Memcached clients and does not require the application to be recompiled or linked against the libraries. Amazon ElastiCache manages the deployment of the Amazon ElastiCache binaries.
^1626790244452

114. How can you back up data stored in Amazon ElastiCache running Redis? (Choose 2 answers)  
A. Create an image of the Amazon Elastic Compute Cloud (Amazon EC2) instance.  
B. Configure automatic snapshots to back up the cache environment every night.  
C. Create a snapshot manually.  
D. Redis clusters cannot be backed up.
#card 
B, C. Amazon ElastiCache with the Redis engine allows for both manual and automatic snapshots. Memcached does not have a backup function.
^1626790244461

115. How can you secure an Amazon ElastiCache cluster? (Choose 3 answers)
A. Change the Memcached root password.  
B. Restrict Application Programming Interface (API) actions using AWS Identity and Access Management (IAM) policies.  
C. Restrict network access using security groups.  
D. Restrict network access using a network Access Control List (ACL).
#card
B, C, D. Limit access at the network level using security groups or network ACLs, and limit infrastructure changes using IAM.
^1626790244471

116.   You are working on a mobile gaming application and are building the leaderboard feature to track the top scores across millions of users. Which AWS services are best suited for this use case?  
A. Amazon Redshift  
B. Amazon ElastiCache using Memcached  
C. Amazon ElastiCache using Redis  
D. Amazon Simple Storage Service (S3)
#card 
C. Amazon ElastiCache with Redis provides native functions that simplify the development of leaderboards. With Memcached, it is more difficult to sort and rank large datasets. Amazon Redshift and Amazon S3 are not designed for high volumes of small reads and writes, typical of a mobile game
^1626790244481

117. You have built a large web application that uses Amazon ElastiCache using Memcached to store frequent query results. You plan to expand both the web fleet and the cache fleet multiple times over the next year to accommodate increased user traffic. How do you minimize the amount of changes required when a scaling event occurs?  
A. Configure AutoDiscovery on the client side  
B. Configure AutoDiscovery on the server side  
C. Update the configuration file each time a new cluster  
D. Use an Elastic Load Balancer to proxy the requests
#card 
A. When the clients are configured to use AutoDiscovery, they can discover new cache nodes as they are added or removed. AutoDiscovery must be configured on each client and is not active server side. Updating the configuration file each time will be very difficult to manage. Using an Elastic Load Balancer is not recommended for this scenario.^1626790244491
