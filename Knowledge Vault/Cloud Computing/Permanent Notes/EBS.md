---
cards-deck: Obsidian::Cloud-Computing::Storage::EBS
tags: ebs, storage
---
### Metadata

-  Type: #permanent #storage
    Date written: #2021-07-15
    Source:  
    Status: #wip
    Keywords:  #cloudcomputing #aws #ebs
	References:
	Related:
	
### Notes
- [[EBS Storage Type]]
- [[EBS Provision Instance]]
- [[EBS Location]]
- [[EBS Type]]
- [[EBS High Availability Mechanism]]
- [[EBS Scalability Mechanism]]  
- [[EBS Security]]
- [[EBS Replication]]
- [[EBS Optimize]]
- [[EBS Fees charged]] (Not Done)
- [[EBS Specific]]

### Questions

1. What is the Storage Type of EBS
#card 
Block Storage
^1626791093532

2. Do we need to provision an instance for EBS
#card 
Yes.
^1626791093543

3. Where is the location that an EBS instance bound to?
#card 
One Availability Zone
^1626791093554

4. How many types are there of EBS?
#card 
4 types: gp2/gp3, io2/op3, st1, sc1
^1626791093565

5. What is the difference between gp2/gp3/io2/io3 and st1/sc1
#card 
The first group is SSD disk, the second group is HDD disk
^1626791093576

6. Does EBS has the storage limit?
#card 
Yes. It's storage size config (**16 TiB**)
^1626791093587

7. Does EBS support replication?
#card 
Yes. With the help of [[EBS Point-in-time Snapshots]]
^1626791093598

8. Which RAID config is good for Better Performance of EBS?
#card 
RAID 0
^1626791093610

9. Which RAID config is good for Fault Tolerance of EBS?
#card 
RAID 1
^1626791093621

10. Which type of EBS support Multi-Attach?
#card 
io2/io3
^1626791093632

11. What is EBS automatic replication?
#card 
Each volume is automatically replicated whitin its Availability zone to protect you from component failure, offering high availability and durability
^1626791093643

12. What is the threshold to consider using gp2/gp3 and io2/io3
#card 
10000 IOPS
^1626791093653

13. What is the process of EBS encryption for unencrypted volume
#card 
1.- Create and mount a new encrypted volume  
2.- Move the data to the new volume  
3.- Delete old unencrypted volume
^1626791093664

14. What is the process of EBS snapshot for RAID?
#card 
1.- Stop applications from writing the RAID array  
2.- Flush all caches to the disk  
3.- Confirm that the associated EC2 instance is not longer writing the array by taking actions like freezing file system or unmount the array  
4.- Take a snapshot to each EBS volume in the array
^1626791093675

15. How to Move EBS volume to new Availability Zone
#card 
1.- Create an snapshot of the volume  
2.- Create a volumen from the snapshot in the new availability zone  
The availability zone must be within the same AWS region
^1626791093686

16. Move EBS volume to new Region
#card 
1.- Create an snapashot of the volume  
2.- Copy the EBS volume to the new Region
^1626791093696

17. Do EBS Volumes persists independently from the running life of a single EC2 instance?
#card 
Yes. These are **network-attached storage that persists independently from the running life of a single EC2 instance**.
^1626791093707

18. How are EBS Volumes protected in terms of High Availability?
#card 
Each Amazon EBS volume is **automatically replicated within its Availability Zone** to protect you from component failure, offering high availability and durability.
^1626791093717

19. What application workloads benefit from EBS?
#card 
**data that must be quickly accessible and require long-term persistence**
^1626791093728

20. Can sc1 and st1 type of EBS be boot volume?
#card 
No
^1626791093739

21. What are Throughput Optimized HDD (st1) Volume Types and some use cases?
#card 
**low cost HDD Volume**  
**frequently accessed, throughput intensive workloads**  
Uses -  
**Streaming workloads requiring consistent, fast throughput at a low price**  
**Big data**  
**Data warehouses**  
**EMR**  
**Log processing**
^1626791093750

22. What are Cold HDD (sc1) Volume Types and some use cases?
#card 
**lowest cost HDD**  
**less frequently accessed workloads**  
Uses -  
**Throughput-oriented storage for large volumes of data that is infrequently accessed**  
**Scenarios where the lowest storage cost is important**
^1626791093761

23. Which EBS Volume Types can be used as Boot Volumes?
#card 
**General SSD (gp2)**  
**Provisioned IOPS SSD (io1)**
^1626791093773

24. What is the max size of an EBS Volume?
#card 
**16 TiB**
^1626791093783

25. Can you change an encrypted volume to an unencrypted and vice versa?
#card 
**not directly**  
**can migrate between volume types**  
**can change encryption status while copying a snapshot**
^1626791093794

26. Can you remove encryption from an encrypted snapshot?
#card 
No
^1626791093805

27. What are the performance specifications and general uses for General Purpose SSD (gp2) EBS Volumes?
#card 
**ability to burst to 3,000 IOPS**  
**max of 10,000 IOPS**  
**max throughput of 16 MB/s**
^1626791093816

28. What are the performance specifications and general uses for Provisioned IOPS SSD (io1) EBS Volumes?
#card 
**max of 32,000 IOPS**  
**max throughput of 500 MB/s**
^1626791093827

29. What are the performance specifications and general uses for Throughput Optimized HDD (st1) EBS Volumes?
#card 
**max of 500 IOPS**  
**max throughput of 500 MB/s**
^1626791093838

30. What are the performance specifications and general uses for Cold HDD (sc1) EBS Volumes?
#card 
**max of 250 IOPS**  
**max throughput of 250 MB/s**
^1626791093849

31. What happens to my data on EBS when an Amazon EC2 instance terminates?
#card 
Incase, the EBS volume is not boot volume.
Data stored on an Amazon EBS volume can persist independently of the life of the instance
^1626791093860

32. How to not delete all data on EBS Boot Volume after terminating EC2 instance?
#card 
If you are using an Amazon EBS volume as a root partition, set the Delete on termination flag to "No" if you want your Amazon EBS volume to persist outside the life of the instance.
^1626791093870

33. How do I modify the capacity, performance, or type of an existing EBS volume?
#card 
Changing a volume configuration is easy. The Elastic Volumes feature allows you to increase capacity, tune performance, or change your volume type with a single CLI call, API call or a few console clicks
^1626791093881

34. Are Provisioned IOPS SSD (io1) volumes available for all Amazon EC2 instance types?
#card 
Yes, Provisioned IOPS SSD (io1) volumes are available for all Amazon EC2 Instance Types.
^1626791093891

35. Does the I/O size of my application reads and writes affect the rate of IOPS I get from my Provisioned IOPS SSD (io1) volumes?
#card 
Yes. For a given allocation of resources, the IOPS rate you get depends on the I/O size of your application reads and writes.  
Provisioned IOPS volumes have a base I/O size of 16KB. Volumes up to 32,000 IOPS have an enhanced throughput I/O size of 256KB, up to 500 MB/s throughput. Every increase in I/O size above the base size (16KB) or enhanced throughput size (256KB) linearly increase the resources you need to achieve the same IOPS rate.  
For example, if you have provisioned a volume with 40,000 IOPS it will achieve up to 40,000 16KB writes per second, 20,000 32KB writes per second, or 10,000 64KB writes per second, and so on. If you have provisioned a volume with 500 IOPS it can achieve up to 500 256KB writes per second, 250 512KB writes per second, or 125 1024KB writes per second, and so on.
^1626791093903

36. Does the I/O size of my application reads and writes affect the rate of throughput I get from my HDD-backed volumes?
#card 
Yes. The throughput rate you get depends on the I/O size of your application reads and writes. HDD-backed volumes process reads and writes in I/O sizes of 1MB. Sequential I/Os are merged and processed as 1 MB units while each non-sequential I/O is processed as 1MB even if the actual I/O size is smaller. Thus, while a transactional workload with small, random IOs, such as a database, won't perform well on HDD-backed volumes, sequential I/Os and large I/O sizes will achieve the advertised performance of st1 and sc1 for a longer period of time.
^1626791093914

37. Will I be able to access my snapshots using the regular Amazon S3 API?
#card 
No, snapshots are only available through the Amazon EC2 API.
^1626791093926

38. Does it take longer to snapshot an entire 16 TB volume as compared to an entire 1 TB volume?
#card 
By design, an EBS Snapshot of an entire 16 TB volume should take no longer than the time it takes to snapshot an entire 1 TB volume. However, the actual time taken to create a snapshot depends on several factors including the amount of data that has changed since the last snapshot of the EBS volume.
^1626791093937

39. Does EBS encryption support boot volumes?
#card 
Yes
^1626791093948

40. Will I be billed for the IOPS provisioned on a Provisioned IOPS volume when it is disconnected from an instance?
#card 
Yes, you will be billed for the IOPS provisioned when it is disconnected from an instance. When a volume is detached, we recommend you consider creating a snapshot and deleting the volume to reduce costs.
^1626791093959

41. If you are running an application in a production environment and must add a new EBS volume with data from a snapshot, what could you do to avoid degraded performance during the volume's first use?
#card 
Pre-warm every blocks of volume before using
^1626791093970

42. What best describes the characteristics of EBS volumes?  
A. They will be deleted anytime the instance is stopped or terminated  
B. They are persistent and can live past the lifetime of the instance  
C. They are ephemeral and wiped when an instance is stopped  
D. They cannot be used as an instance's root storage device
#card 
B. EBS volumes are network-attached, persistent storage volumes. When Delete on Termination is disabled they live past the life of an EC2 instance.
^1626791093981

43. What best describes how EBS snapshots work?  
A. Each snapshot stores the entire volume and is stored in S3  
B. Snapshots are another term used to describe an AMI  
C. Snapshots automatically freeze all writes to your EBS volume before saving for consistency.  
D. Snapshots are incremental in nature and are stored in S3
#card 
Snapshots are incremental in nature and are stored in S3^1626791093992
