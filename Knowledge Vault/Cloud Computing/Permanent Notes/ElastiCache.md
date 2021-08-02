---
cards-deck: Obsidian::Cloud-Computing::Database::ElastiCache
tags: elasticache, database
---
### Metadata

-  Type: #permanent #database #cache
    Date written: #2021-06-27
    Source:  https://aws.amazon.com/vi/elasticache
    Status: #wip 
    Keywords:  #cloudcomputing #aws #elasticache 
	Related:
	
### Notes
- [[ElastiCache Database Type]]
- [[ElastiCache Provision Instance]]
- [[ElastiCache Location]]
- [[ElastiCache Type]]
- [[ElastiCache High Availability Mechanism]]
- [[ElastiCache Scalability Mechanism]]
- [[ElastiCache Replication]]
- [[ElastiCache Security]]
- [[ElastiCache Optimize]]
- [[ElastiCache Fees charged]]
- [[ElastiCache Specific]]

### Questions

1. Can application session state be stored in cache?
#card 
yes
^1626790400721

2. What is the cache aside pattern?
#card 
app server checks the cache first for the data it needs. If it isn't there, it gets it from the DB, and leaves a copy in cache
^1626790400732

3. Can Redis support read replicas?
#card 
Yes, and you can fail over to them if the primary malfunctions
^1626790400742

4. What do you do when a new Memcached version comes out?
#card 
You have the option of spinning up a new cluster with the new version
^1626790400753

5. Which engine lets you store strings, lists and sets?
#card 
Redis
^1626790400763

6. Which caching engine lets you persist the in-memory data onto disk?
#card 
Redis
^1626790400773

7. Which engine uses key/value data stores?
#card 
Memcached
^1626790400783

8. Which caching engine lets you take snapshots to backup and recover?
#card 
Redis
^1626790400793

9. How many read replicas can you have in a Redis cluster?
#card 
5
^1626790400802

10. In Redis, If your primary node fails, can you make a read replica the new master?
#card 
If you use Multi-AZ replication groups
^1626790400812

11. Which engine lets you sort and rank data?
#card 
Redis
^1626790400822

12. Which caching engine has a loosely coupled publish and subscribe messaging architecture?
#card 
Redis
^1626790400832

13. Which elasticache engine could be used to build a leaderboard for a mobile app?
#card 
redis
^1626790400842

14. A single Memcached cluster can contain up to __ nodes.
#card 
20
^1626790400852

15. Multiple Redis clusters can be grouped into __
#card 
a redis replication group
^1626790400862

16. Node types of ElastiCache
#card 
t2 node family- dev/low volume;  
m3 node family- blend of compute & memory;  
r3 node family- memory optimized
^1626790400872

17. Elasticache horizontal scaling
#card 
memcached- scale to 20 nodes  
redis- only one node handles writes, 5 read replicas, can add add'l replication groups
^1626790400882

18. New Memcached clusters start with __ nodes.
#card 
0
^1626790400892

19. Which engine's cluster can be started from a backup of ElastiCache?
#card 
Redis
^1626790400903

20. Can you replicate with Memcached?
#card 
no, it is standalone in memory service without any redundant data protection
^1626790400912

21. How many nodes in cluster can you have in a Redis replication group?
#card 
up to 6 (5 of which are read replicas)
^1626790400923

22. Is replication between nodes synchronous in Redis?
#card 
no, it is asynchronous
^1626790400933

23. How can you take a Redis snapshot without taking a performance hit?
#card 
set up a replication group, take snapshot of a read replica. These can be scheduled for a time with low utilization
^1626790400943

24. New clusters can be created from manual or automated backups at any time in Redis. What config will they have?
#card 
The same as the source cluster, but you can override that.
^1626790400953

25. Can you access an Elasticache node from the Internet or from EC2 instances outside your VPC?
#card 
No
^1626790400963

26. Does an elasticache node have an IP address?
#card 
yes, a private one
^1626790400973

27. How can you get access to manage the config and infrastructure of the cluster?
#card 
IAM
^1626790400983

28. Which of the following objects are good candidates to store in a cache? (Choose 3 answers)  
a. Session state b. Shopping cart c. Product catalog d. Bank account balance
#card 
A, C, D. Many types of objects are good candidates to cache because they have the potential to be accessed by numerous users repeatedly. Even the balance of a bank account could be cached for short periods of time if the back-end database query is slow to respond.
^1626790400993

29. Which of the following cache engines are supported by Amazon ElastiCache? (Choose 2 answers)  
a. MySQL b. Memcached c. Redis d. Couchbase
#card 
B, C
^1626790401003

30. How many nodes can you add to an Amazon ElastiCache cluster running Memcached?
#card 
The default limit is 20 nodes per cluster
^1626790401013

31. An application currently uses Memcached to cache frequently used database queries. Which steps are required to migrate the application to use Amazon ElastiCache with minimal changes? (Choose 2 answers)  
a. Recompile the application to use the Amazon ElastiCache libraries. 
b. Update the configuration file with the endpoint for the Amazon ElastiCache cluster. 
c. Configure a security group to allow access from the application servers. 
d. Connect to the Amazon ElastiCache nodes using Secure Shell (SSH) and install the latest version of Memcached
#card 
B, C. Amazon ElastiCache is Application Programming Interface (API)-compatible with existing Memcached clients and does not require the application to be recompiled or linked against the libraries. Amazon ElastiCache manages the deployment of the Amazon ElastiCache binaries.
^1626790401023

32. How can you back up data stored in Amazon ElastiCache running Redis? (Choose 2 answers)  
a. Create an image of the Amazon Elastic Compute Cloud (Amazon EC2) instance. b. Configure automatic snapshots to back up the cache environment every night. 
c. Create a snapshot manually. 
d. Redis clusters cannot be backed up.
#card 
B, C
^1626790401033

33. How can you secure an Amazon ElastiCache cluster? (Choose 3 answers)  
a. Change the Memcached root password. 
b. Restrict Application Programming Interface (API) actions using AWS Identity and Access Management (IAM) policies. 
c. Restrict network access using security groups. 
d. Restrict network access using a network Access Control List (ACL).
#card 
B, C, D. Limit access at the network level using security groups or network ACLs, and limit infrastructure changes using IAM.
^1626790401044

34. You are working on a mobile gaming application and are building the leaderboard feature to track the top scores across millions of users. Which AWS services are best suited for this use case?  
a. Amazon Redshift 
b. Amazon ElastiCache using Memcached 
c. Amazon ElastiCache using Redis 
d. Amazon Simple Storage Service (S3)
#card 
C. Amazon ElastiCache with Redis provides native functions that simplify the development of leaderboards. With Memcached, it is more difficult to sort and rank large datasets. Amazon Redshift and Amazon S3 are not designed for high volumes of small reads and writes, typical of a mobile game.
^1626790401054

35. You have built a large web application that uses Amazon ElastiCache using Memcached to store frequent query results. You plan to expand both the web fleet and the cache fleet multiple times over the next year to accommodate increased user traffic. How do you minimize the amount of changes required when a scaling event occurs?
#card 
Configure AutoDiscovery on the client side
^1626790401064

36. What is Auto Discovery of ElastiCache Memcached 
#card 
the ability for client programs to automatically identify all of the nodes in a cache cluster, and to initiate and maintain connections to all of these nodes.
^1626790401074
