# Data Table structure as B-Tree
- [[SQL Primary Key]] is also called [[SQL Clustered Index Key]]
![[Pasted image 20210719205910.png]]

# Index Seek
## DB Engine retrieve the Row table from Clustered Index Key
- [[SQL Index Seek]] happens when [[SQL Clustered Index Key]] is used to help [[SQL Database Engine]] retrieve the right [[SQL Row Data]]
![[Pasted image 20210719210111.png]]

## DB Engine retrieve the Clustered Index Key from Non Clusteted Index Key
- We can create [[SQL Non Clustered Index Key]] on other columns to help [[SQL Database Engine]] retrieve the right [[SQL Non Clustered Index Key]] - [[SQL Clustered Index Key]] mapping. 
- When [[SQL Database Engine]] get the corresponding [[SQL Clustered Index Key]], then it will next try to retrieve the right [[SQL Row Data]]
![[Pasted image 20210719210531.png]]
- This is also called [[SQL Index Seek]]
![[Pasted image 20210719215050.png]]

# Index Scan
- [[SQL Index Scan]]: [[SQL Database Engine]] search for all [[SQL Row Data]] in [[SQL B-Tree]] for the right [[SQL Row Data]]