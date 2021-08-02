---
cards-deck: Obsidian::Cloud-Computing::Database::Redshift
tags: redshift, database
---
## Metadata

-  Type: #permanent #database
    Date written: #2021-07-01
    Source:  https://aws.amazon.com/vi/rds/
    Status: #wip 
    Keywords:  #cloudcomputing #aws #redshift
	Related:
	
### Notes
- [[Redshift Database Type]]
- [[Redshift Provision Instance]]
- [[Redshift Location]]
- [[Redshift Type]]
- [[Redshift High Availability Mechanism]]
- [[Redshift Scalability Mechanism]]
- [[Redshift Storage]]
- [[Redshift Replication]]
- [[Redshift Security]]
- [[Redshift Optimize]]
- [[Redshift Fees charged]]
- [[Redshift Specific]]

### Questions

1. What is the database type of Redshift
#card 
Relational Database
^1626790343283

2. Do we need to provision an instance for Redshift?
#card 
Yes. We have to provision an instance for Redshift cluster.
^1626790343294

3. Where is the location that Redshift bound to
#card 
Availability Zone
^1626790343304

4. How many types are there of Redshift
#card 
3 types: RA3, DC2, DS2
^1626790343314

5. Which cluster type of Redshift is most cheapest?
#card 
DC2
^1626790343325

6. Which cluster type of Redshift is most expensive?
#card 
RA3
^1626790343335

7. Does Redshift support Multi AZ?
#card 
No
^1626790343345

8. How many layers of Encryption Hierarchy of Redshift?
#card 
4-tier
^1626790343356

9. How many distribution types are there of Redshift?
#card 
3 types: EVEN, KEY, ALL
^1626790343366

10. When do we should use Redshift or RDS?
#card 
OLAP - Redshift, OLTP - RDS
^1626790343376

11. What is the maximum number of Compute Node of Redshift?
#card 
128 compute nodes
^1626790343387

12. What is the main job of Leader Node In Redshift Cluster
#card 
Manages client connection and recieves queries
^1626790343397

13. What is the main job of Compute Node in Redshift Cluster
#card 
Store data and perform queries and computations
^1626790343407

14. In addition to compression, what else makes Redshift really fast?
#card 
Massively Parallel Processing (MPP): Amazon Redshift automatically distributes data and query load across all nodes. It makes it easy to add nodes to your data warehouse and enables you to maintain fast query performance as your data warehouse grows.
^1626790343417

15. What are three pillars of Redshift pricing?
#card 
Compute Node Hours, Backups, Data transfers (only within a VPC, not outside it)
^1626790343427

16. What are the elements of Redshift Security?
#card 
Not designed to be Multi-AZ, available only in 1 AZ  
Can restore snapshots to new AZ's in the event of an outage
^1626790343437

17. What is Redshift Spectrum
#card 
Redshift Spectrum is a feature of Amazon Redshift that enables you to run queries against exabytes of unstructured data in Amazon S3, with no loading or ETL required.
^1626790343447

18. With a Redshift Single Node configuration how large is each node?
#card 
160GB
^1626790343457

19. With Redshift how is similar data stored on the disk to help with compression?
#card 
Similar data is stored sequentially on the disk
^1626790343467

20. How many copies of your data does Redshift always try to maintain?
#card 
At least 3 copies
^1626790343477

21. The Algorithm that is used when Redshift data encrypted when at-rest?
#card 
AES-256 Encryption
^1626790343487

22. How is Redshift data encrypted with in-transit?
#card 
SSL
^1626790343497

23. What is Amazon Redshift Enhanced VPC Routing?
#card 
Amazon Redshift forces all COPY and UNLOAD traffic between your cluster and your data repositories through your Amazon VPC.
^1626790343507

24. What dense nodes that are optimized for processing data but are limited in how much data they can store?
#card 
Dense compute nodes
^1626790343517

25. What dense nodes are optimized for warehouses with a lot more data? More than 500 GB based on our rule of thumb.
#card 
dense storage nodes
^1626790343527

26. What is the meaning of DC2 cluster type of Redshift?
#card 
Dense Compute node
^1626790343538

27. What is the meaning of DS2 cluster type of Redshift?
#card 
Dense Storage node
^1626790343548

28. What node manages communications with client programs and all communication with other nodes in Redshift Cluster?
#card 
Leader node
^1626790343558

29. What node execute the compiled code and send intermediate results back to the leader node for final aggregation in Redshift cluster?
#card 
Compute node
^1626790343568

30. T/F you can configure redshift for cross region snapshots
#card 
Yes
^1626790343579

31. Encryption in Redshift if achieved with the following two features
#card 
KMS  
S3 encryption
^1626790343589

32. T/F Redshift can handle more storage than Aurora and RDS
#card 
True - petabyte size. Aurora max is 64TB and RDS is 16TB^1626790343599
