### Metadata

-  Type: #permanent #storage
    Date written: [[2021-06-29, Mon]]  
    Source:  
    Status: #todo  
    Keywords:  #cloudcomputing #aws #snow
	References: 
	Related:
	
### Notes
- [[Snow Cone]] ~ least storage & compute
- [[Snowball Edge]] ~ mid 
- [[Snowmobile]] ~ high storage & compute
- All data will be sent to [[S3]] after migrated, not directly to [[S3 Glacier]] => have to go through [[S3 Lifecycle Rules]]
![[Pasted image 20210629234503.png]]
- [[Ops Hub]] is a software to manage [[Snow Familiy]] device
- While being transporting, data will be [[Edge Computing]]
![[Pasted image 20210629234020.png]]
![[Pasted image 20210629234117.png]]

### Questions

##### You need to move hundreds of Terabytes into the cloud in S3, and after that pre-process it using many EC2 instances in order to clean the data. You have a 1 Gbit/s broadband and would like to optimize the process of moving the data and pre-processing it, in order to save time. What do you recommend?
- Use the network
- Use Snowball
- Use AWS Data Migration
- Use Snowball Edge
#card 
Snowball Edge is the right answer as it comes with computing capabilities and allows use to pre-process the data while it's being moved in Snowball, so we save time on the pre-processing side as well.
