# Metadata

-  Type: #permanent #sql
    Date written: #2021-07-19
    Source:  https://viblo.asia/p/su-khac-nhau-giua-sql-server-clustered-index-scan-va-index-seed-RQqKLOvN57z
    Status: #wip 
    Keywords:  #database #sql
	Related: 
	
# Notes
- [[SQL Table Data]] is split into [[SQL Data Page]] internally

### SQL Database Structure & Index
##### B-Tree Index Based Structured
- When [[SQL Table Data]] is created with [[SQL Primary Key]], [[SQL Table Data]] is then stored as [[SQL B-Tree]]

##### Heap Tree Index Based Structured
- When [[SQL Table Data]] is created without [[SQL Primary Key]], then it stored as [[SQL Heap Table]]

##### Index
- [[SQL Index]] helps retrieve data faster

### SQL Query Tip
- Dont used * in [[SQL SELECT]] when not needed =>Redudant Columns
- [[SQL Index]] cant work with not, negative operators like:
```SQL
"IS NULL", "!=", "!>", "!<", "NOT", "NOT EXISTS", "NOT IN", "NOT LIKE",
```

- [[SQL Index]] cant also work with double operators like:
```SQL
SELECT userid, username FROM user WHERE user_amount <=3000
```

- [[SQL Index]] will hardly get %V key instead of V%
```SQL
 SELECT lname, fname, address FROM Customers WHERE fname LIKE ‘V%’
```

- Dont use function on [[SQL Index]] => Different value for Index => Cant use Index to retrieve
`SELECT member_number, first_name, last_name FROM members WHERE DATEDIFF(yy,datofbirth,GETDATE()) > 21`
Use the below instead
`SELECT member_number, first_name, last_name FROM members WHERE dateofbirth < DATEADD(yy,-21,GETDATE())`

- [[SQL UNION ALL]] will be more faster than [[SQL UNION]] => [[SQL UNION]] will have to remove duplicated Rows

- To check the existence of Records, should use [[SQL IF EXISTS]] instead of [[SQL COUNT]]

- Different Order in [[SQL WHERE]] doesnt matter much
![[Pasted image 20210719230044.png]]

- OR makes [[SQL SELECT]] performs worse => Have to scan whole table
![[Pasted image 20210719230139.png]]


### SQL Index Problems
- [[SQL Index]] helps improve [[SQL SELECT]] performance but slow down [[SQL UPDATE]] and [[SQL INSERT]] and [[SQL DELETE]]