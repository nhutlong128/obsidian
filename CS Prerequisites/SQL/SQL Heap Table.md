# SQL Heap Table
- [[SQL Heap Table]] is similar to [[SQL B-Tree]], but:
	- [[SQL B-Tree]] each [[SQL Row Data]] is orded based on [[SQL Primary Key]]
	- [[SQL B-Tree]] each [[SQL Row Data]] is non-orded, a column [[SQL Row ID]] is added to play [[SQL Primary Key]] role

# Index Seek
- [[SQL Index Seek]] happens when we create [[SQL Non Clustered Index Key]] on any columns, [[SQL Database Engine]] still uses it to find the mapping [[SQL Non Clustered Index Key]] - [[SQL Row ID]] Row
- Then it will retrieve the corresponding [[SQL Row Data]] with the help of [[SQL Row ID]]
- ![[Pasted image 20210719215026.png]]

# Table Scan
- [[SQL Table Scan]] is similar to [[SQL Index Scan]] on [[SQL B-Tree]], but it happens in [[SQL Heap Table]]
