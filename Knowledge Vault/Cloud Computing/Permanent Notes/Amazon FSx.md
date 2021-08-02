### Metadata

-  Type: #permanent #storage
    Date written: #2021-06-30
    Source:  
    Status: #wip
    Keywords:  #cloudcomputing #aws #fsx
	References:
	Related:
	
### Notes
- [[FSx for Windows]]
- [[FSx for Lustre]]
- [[FSx File System Deployment Options]]

### Questions

###### You would like to have a distributed POSIX compliant file system that will allow you to maximize the IOPS in order to perform some HPC and genomics computational research. That file system will have to scale easily to millions of IOPS. What do you recommend?
- EFS with MAX IO enabled
- FSx for Lustre
- Amazon S3 mounted on the instances
- EC2 Instance Stores
#card 
FSx for Lustre

##### Your EC2 Windows Servers need to share some data by having a Network File System mounted, that respect the Windows security mechanisms and has integration with Active Directory. What do you recommend putting in place as an NFS? 
- EFS
- FSx for Windows
- FSx for Lustre
- Amazon S3 with FIle Gateway
#card 
Fsx for Windows