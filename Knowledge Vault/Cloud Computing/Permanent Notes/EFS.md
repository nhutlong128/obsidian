---
cards-deck: Obsidian::Cloud-Computing::Storage::EFS
tags: ebs, storage
---
### Metadata

-  Type: #permanent #storage
    Date written: #2021-07-14
    Source:  
    Status: #wip
    Keywords:  #cloudcomputing #aws #efs
	References:
	Related:
	
### Notes
- [[EFS Storage Type]]
- [[EFS Provision Instance]]
- [[EFS Location]]
- [[EFS Type]]
- [[EFS High Availability Mechanism]]
- [[EFS Scalability Mechanism]]
- [[EFS Security]]
- [[EFS Replication]]
- [[EFS Optimize]]
- [[EFS Fees charged]] (Not Done)
- [[EFS Specific]] (Not Done)

### Questions

1. What is the Storage Type of EFS?
#card 
File Storage
^1626791109846

2. Do we need to provision an instance for EFS?
#card 
Yes
^1626791109857

3. Where is the location that an EFS instance bound to?
#card 
Region
^1626791109868

4. How many types are there of EFS?
#card 
4 Types: Standard, Standard IA, One Zone, One Zone IA
^1626791109880

5. What is the difference between Standard and One Zone type of EFS?
#card 
In Standard type, an EFS instance is available on 3 Availability Zones
In One Zone type, an EFS instance is available on 1 Availability Zone
^1626791109891

6. Does EFS has the storage limit?
#card 
No. It's unlimited 
^1626791109903

7. What is the AWS service helps replicate, data transfer between EFS instances?
#card 
Data Sync
^1626791109915

8. How many types of Performance Mode of EFS?
#card 
Two types. Gerneral Performance and Max IO
^1626791109927

9. What is the difference between General Performance and Max IO Performance of EFS?
#card 
General Performance: Lower Latency & Lower IO operations per second
Max IO Performance: Higher Latency & Higher IO operations per second
^1626791109938

10. How many types of ThroughPut Mode of EFS?
#card 
Bursting
Provisioned
^1626791109949

11. What is the different between Bursting and Provisioned in ThroughPut Mode of EFS?
#card 
Bursting: scale with file system size
Provisioned: fixed
^1626791109960

12.  Step 1: Create the EFS file system and assign a ____ to it. Step 2: Create at least two EC2 instances (Amazon Linux) and assign them to the same ___ as the EFS.
#card 
Security Group
^1626791109971

13. What Amazon EC2 instance types and AMIs work with Amazon EFS?
#card 
Amazon EFS is compatible with all Linux-based AMIs for Amazon EC2.
^1626791109981

14. You can mount to EFS from which of the following:  
A. RDS Instances  
B. EC2 instances running Windows  
C. On-prem servers running Linux  
D. EC2 instances running Linux
#card 
C + D  
Only linux compatible
^1626791109992

15. How can you improve the performance of your Elastic File System?  
A. Divide your files system into multiple smaller file systems.  
B. Provision more throughput than is required  
C. Provision higher IOPs for your EFS.  
D. Use an instance-store backed EC2 instance.
#card 
C. Provision higher IOPs for your EFS.  
^1626791110003

16. Which feature of Intel processors help to encrypt data without significant impact on performance?  
A. TSX  
B. AES-NI  
C. Turbo Boost  
D. AVX
#card 
AES-NI provide hardware acceleration of encryption.
^1626791110014

17. What command should you run on an instance to view its bootstrap script?
#card 
curl http://169.254.169.254/latest/user-data
^1626791110025

