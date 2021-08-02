---
cards-deck: Obsidian::Cloud-Computing::Database::DynamoDB
tags: dynamodb, database
---
### Metadata

-  Type: #permanent #database
    Date written: #2021-07-01
    Source:  https://aws.amazon.com/vi/rds/
    Status: #wip 
    Keywords:  #cloudcomputing #aws #dynamodb
	Related:
	
### Notes
- [[DynamoDB Database Type]]
- [[DynamoDB Provision Instance]]
- [[DynamoDB Location]]
- [[DynamoDB Type]]
- [[DynamoDB High Availability Mechanism]]
- [[DynamoDB Scalability Mechanism]]
- [[DynamoDB Storage]]
- [[DynamoDB Replication]]
- [[DynamoDB Security]]
- [[DynamoDB Optimize]]
- [[DynamoDB Fees charged]]
- [[DynamoDB Specific]]

### Questions

1.  We have to provision the instance type for our DynamoDB database
- true
- false
#card 
DynamoDB is a serverless service and as such we don't provision an instance type for our database. We just say how much RCU and WCU we require for our table (or auto scaling)
^1626790298001

2. A DynamoDB table has been provisioned with 10 RCU and 10 WCU. You would like to increase the RCU to sustain more read traffic. What is true about RCU and WCU?
- RCU and WCU are decoupled, so WCU can stay the same
- You will also have to increase WCU to match the RCU value
#card 
RCU and WCU are decoupled, so WCU can stay the same
^1626790298012

3. You are about to enter the Christmas sale and you know a few items in your website are very popular and will be read often. Last year you had a **ProvisionedThroughputExceededException.** What should you do this year?
- Increase the RCU to a very, very high value
- Create a DAX cluster
- Migrate the database away from DynamoDB for the time of the sale
#card 
A DynamoDB Accelerator (DAX) cluster is a cache that fronts your DynamoDB tables and caches the most frequently read values. They help offload the heavy reads on hot keys off of DynamoDB itself, hence preventing the ProvisionedThroughputExceededException
^1626790298022

4. You would like to automate sending welcome emails to the users who subscribe to the Users table in DynamoDB. How can you achieve that?
- Create a Lambda function to scan the table every minute looking for new users.
- Enable DynamoDB Streams and have the Lambda function receive the events in real-time
- Enable the SNS and DynamoDB integration
#card 
Enable DynamoDB Streams and have the Lambda function receive the events in real-time
^1626790298032

5. Your production application is leveraging DynamoDB as its backend and is experiencing smooth sustained usage. There is a need to make the application run in development as well, where it will experience unpredictable, sometimes high, sometimes low volume of requests. You would like to make sure you optimize for cost. What do you recommend?
- Provision WCU & RCU and enable auto-scaling for both development and production
- Provision WCU & RCU and enable auto-scaling for production and use on-demand capacity for development
- Provision WCU & RCU and enable auto-scaling for development and use on-demand capacity for production
- Use on-demand capacity for both development and production
#card 
Provision WCU & RCU and enable auto-scaling for production and use on-demand capacity for development
^1626790298042

6. Amazon DynamoDB synchronously replicates data across ________ facilities in an AWS Region, giving you high availability and data durability.
#card 
3
^1626790298052

7. ____________________ represents the manner and timing in which the successful write or update of a data item is reflected in a subsequent read operation of that same item.
#card 
Read Consistency
^1626790298062

8. What is the consistency model of Amazon DynamoDB?
#card 
When reading data from Amazon DynamoDB, users can specify whether they want the read to be eventually consistent or strongly consistent
^1626790298072

9. Eventually Consistent Reads (Default) - the eventual consistency option maximizes your ___________ throughput.
#card 
read
^1626790298082

10. Consistency across all copies of data is usually reached within a ___________.
#card 
second
^1626790298092

11. A ___________ read returns a result that reflects all writes that received a successful response prior to the read.
#card 
strongly consistent
^1626790298102

12. Does DynamoDB support in-place atomic updates?
#card 
Yes. Amazon DynamoDB supports fast in-place updates. You can increment or decrement a numeric attribute in a row using a single API call.
^1626790298112

13. Amazon DynamoDB runs exclusively on ____________.
#card 
Solid State Drives (SSDs)
^1626790298122

14. The high I/O performance of ___________ also enables us to serve high-scale request workloads cost efficiently, and to pass this efficiency along in low request pricing.
#card 
SSDs
^1626790298132

15. Is DynamoDB only for high-scale applications?
#card 
No. DynamoDB offers seamless scaling so you can start small and scale up and down in line with your requirements. If you need fast, predictable performance at any scale then DynamoDB may be the right choice for you.
^1626790298142

16. DynamoDB provides flexible querying by letting you query on non-primary key attributes using ____________ Indexes and _________________ Indexes.
#card 
Global Secondary and Local secondary
^1626790298152

17. A primary key can either be a _____________ partition key or a ____________ partition-sort key.
#card 
single-attribute/composite
^1626790298162

18. Does Amazon DynamoDB support increment or decrement operations?
#card 
Yes, Amazon DynamoDB allows atomic increment and decrement operations on scalar values.
^1626790298172

19. Amazon DynamoDB stores structured data, indexed by primary key, and allows low latency read and write access to items ranging from 1 byte up to ____________.
#card 
400KB
^1626790298182

20. Amazon S3 stores unstructured ____________ and suited for storing large objects up to 5 TB.
#card 
blobs
^1626790298192

21. An Item is composed of a primary or composite key and a flexible number of attributes. There is no explicit limitation on the number of attributes associated with an individual item, but the aggregate size of an item, including all the attribute names and attribute values, cannot exceed __________.
#card 
400KB
^1626790298202

22. UpdateTable - Updates the ___________________ values for the given table.
#card 
provisioned throughput
^1626790298212

23. GetItem - The GetItem operation returns a set of Attributes for an item that matches the ________________. The GetItem operation provides an eventually consistent read by default. If eventually consistent reads are not acceptable for your application, use ConsistentRead.
#card 
primary key
^1626790298222

24. The BatchGetItem operation returns the attributes for multiple items from multiple tables using their _______________.
#card 
primary keys
^1626790298231

25. What is the consistency model of the Scan operation?
#card 
The Scan operation supports eventually consistent and consistent reads.
^1626790298241

26. A Scan operation on a table or secondary index has a limit of 1___ of data per operation.
#card 
MB
^1626790298251

27. How many read capacity units does a Scan operation consume?
#card 
The read units required is the number of bytes fetched by the scan operation, rounded to the nearest 4KB, divided by 4KB. Scanning a table with consistent reads consumes twice the read capacity as a scan with eventually consistent reads.
^1626790298261

28. What data types does DynamoDB support?
#card 
DynamoDB supports four scalar data types: Number, String, Binary, and Boolean. Additionally, DynamoDB supports collection data types: Number Set, String Set, Binary Set, heterogeneous List and heterogeneous Map. DynamoDB also supports NULL values.
^1626790298271

29. What types of data structures does DynamoDB support?
#card 
DynamoDB supports key-value and document data structures.
^1626790298281

30. Does DynamoDB have a JSON data type?
#card 
No, but you can use the document SDK to pass JSON data directly to DynamoDB.
^1626790298291

31. Is there a limit to how much data I can store in Amazon DynamoDB?
#card 
No. There is no limit to the amount of data you can store in an Amazon DynamoDB table.
^1626790298301

32. Is there a limit to how much throughput I can get out of a single table?
#card 
No, you can increase the throughput you have provisioned for your table using UpdateTable API or in the AWS Management Console.
^1626790298311

33. If you wish to exceed throughput rates of _________ writes/second or _______ reads/second, you must first contact Amazon
#card 
10,000
^1626790298320

34. _____________________ indexes are indexes that contain a partition or partition-and-sort keys that can be different from the table's primary key.
#card 
Global secondary
^1626790298330

35. Amazon DynamoDB supports two types of secondary indexes:
#card 
Local secondary index — an index that has the same partition key as the table, but a different sort key. A local secondary index is "local" in the sense that every partition of a local secondary index is scoped to a table partition that has the same partition key.  
Global secondary index — an index with a partition or a partition-and-sort key that can be different from those on the table. A global secondary index is considered "global" because queries on the index can span all items in a table, across all partitions.
^1626790298340

36. When should I use global secondary indexes?
#card 
Global secondary indexes are particularly useful for tracking relationships between attributes that have a lot of different values.
^1626790298349

37. How do global secondary indexes differ from local secondary indexes?
#card 
An LSI is attached to a specific partition key value, whereas a GSI spans all partition key values.
^1626790298359

38. What is the consistency model for global secondary indexes?
#card 
GSIs support eventual consistency.
^1626790298369

39. What is provisioned throughput?
#card 
Amazon DynamoDB lets you specify your throughput needs in terms of units of read capacity and write capacity for your table.
^1626790298379

40. A unit of Write Capacity enables you to perform one write per second for items of up to __KB in size.
#card 
1
^1626790298389

41. a unit of Read Capacity enables you to perform one strongly consistent read per second (or two eventually consistent reads per second) of items of up to ___KB in size.
#card 
4
^1626790298398

42. Units of Capacity required for writes = Number of item writes per second x item size in ___KB blocks
#card 
1
^1626790298408

43. Units of Capacity required for reads* = Number of item reads per second x item size in ___KB blocks
#card 
4
^1626790298418

44. If you use _______________ consistent reads you'll get twice the throughput in terms of reads per second.
#card 
eventually
^1626790298428

45. The smallest provisioned throughput you can request is ___ write capacity unit and ___ read capacity unit.
#card 
1 and 1
^1626790298438

46. There are two ways to update the provisioned throughput of an Amazon DynamoDB table. You can either make the change in the __________________, or you can use the ____________ API call.
#card 
management console, UpdateTable
^1626790298448

47. Table Item Attributes of DynamoDB?
#card 
Table contains Items, Item contains Attributes. Attribute is where the data is stored in DynamoDb database.
^1626790298457

48. What is Hash Key (or Partition Key) on DynamoDB?
#card 
This is where the data is stored. The most important key is the Hash Key (or Partition Key)
^1626790298468

49. What is Range Key (or Sort Key) on DynamoDB?
#card 
Allows multiple Items to exist.
^1626790298477

50. What is Atomic Counters on DynamoDB?
#card 
Atomic counters are a way of updating an Attribute Value and everytime an Update is made the counter will get indexed by one. It will be assured the update will happen.  
This would not be used with financial applications because the Atomic counter may not get updated for some reason during a request failure, but then again it may be updated. Needing absolute certainty that the Atomic counter is updated.
^1626790298487

51. What is ProvisionedThroughPutExceededException?
#card 
This is when you have exceed all of your Read and Writes ThroughPuts
^1626790298497

52. What is DynamoDB Partition?
#card 
Consists of Compute, Storage and any attached Components.  
One Table equals One Partition  
You cannot See nor configure the number of Partitions however you design your tables.  
One partition can store 10Gig of Data.  
One partition can delever 3000 RCU and 1000 WCU.  
So if you need to Store more than 10Gig of Data or need more than 3000 RCU or 1000 WCU you will need more than One Partition  
There is a Relationship between Performance Required, Data Stored and Number of Partitions
^1626790298506

53. When DynamoDB Re-Partitioning?
#card 
As a Partition grows from 1 to more due to RCU, WCU or Data Size the 1 Partition will be Re-Partitioned into Multi Partitions.
^1626790298516

54. DynamoDB: Can have up to 5  ___ Indexes and 5  __ Indexes on each Table.
#card 
Local Secondary, Global Secondary
^1626790298526

55. What is DynamoDB Streams?
#card 
This is a new feature and when an Item is either Added, Removed or Updated in DynamoDb a before and after copy of that data is sent to a DynamoDb Stream where it is stored for 24hours.
^1626790298535

56. What is Scan operation of DynamoDB?
#card 
Scan returns all of the rows and Items in a Table
^1626790298545

57. What is DynamoDB Conditional Writes
#card 
ConditionalExpressions are a way of assuring that the value you are changing has NOT been changed by another user.  
Example: Say two users are Writing a value=$10 and $20. The original value is $5. With a conditional Write you can say set the value to 20 only if the value is currently 10. In this scenario if the value is 20 you will get a ConditionalCheckedFailedException returned and your write will not take place.
^1626790298555

58. What is DynamoDB Projected Attributes?
#card 
When creating Local Secondary Indexes you can Project attributes from the Table into the Index making searching against the LSI mo're efficient.  
You can have a Max of 20 Projected Attributes onto LSI's for one table.  
If you try to pull attributes from the LSI table that are not Projected onto it, there will be an extra Nested Query made by AWS that will query the Table itself for these attribute values.
^1626790298565

59. If your DynamoDB items are 5 KB and you want to read 80 items per second from your table, then you need to provision ___ read capacity units for strong consistency.  
A. 40  
B. 80  
C. 120  
D. 160
#card 
D  
One read capacity unit represents one strongly consistent read per second, or two eventually consistent reads per second, for an item up to 4 KB in size.  
5 KB requires two strongly consistent (4 KB) read capacity units  
2 x 80 = 160
^1626790298575

60. The DynamoDB data model concepts include:  
• Tables  
• Items  
• Attribute  
A. True  
B. False
#card 
A  
The following are the basic DynamoDB components:  
Tables - Similar to other database systems, DynamoDB stores data in tables. A table is a collection of data. For example, see the example  
table called People that you could use to store personal contact information about friends, family, or anyone else of interest. You could also have a Cars table to store information about vehicles that people drive.  
Items - Each table contains zero or more items. An item is a group of attributes that is uniquely identifiable among all of the other items. In a People table, each item represents a person. For a Cars table, each item represents one vehicle. Items in DynamoDB are similar in many ways to rows, records, or tuples in other database systems. In DynamoDB, there is no limit to the number of items you can store in a table.  
Attributes - Each item is composed of one or more attributes. An attribute is a fundamental data element, something that does not need to be broken down any further. For example, an item in a People table contains attributes called PersonID, LastName, FirstName, and so on. For a Department table, an item might have attributes such as DepartmentID, Name,Manager, and so on. Attributes in DynamoDB are similar in many ways to fields or columns in other database systems.
^1626790298585

61. In Amazon DynamoDB, a database is a collection of items. An item is a collection of tables and each table is a collection of attributes.  
A. True  
B. False
#card 
B  
A database is a collection of tables. An table is a collection of items and each item is a collection of attributes.
^1626790298595

62. DynamoDB supports cross-table joins.  
A. True  
B. False
#card 
B  
DynamoDB is a simple NoSQL database, not a relational database. It does not support joins.
^1626790298604

63. Amazon DynamoDB supports the following data types:  
A. Scalar types - Number, String, Binary, Boolean, and Null.  
B. Multi-valued types - String Set, Number Set, and Binary Set.  
C. Document types - List and Map.  
A. True  
B. False
#card 
A
^1626790298614

64. DynamoDB supports both eventually consistent and strongly consistent read options.  
A. True  
B. False
#card 
A
^1626790298625

65. I need to create a total of 10 DynamoDB secondary indexes including 5 global secondary indexes. Is this possible?  
A. True  
B. False
#card 
A  
You can create up to 5 global secondary indexes and up to 5 local secondary indexes per table.
^1626790298635

66. A DynamoDB global secondary index has the same partition (hash) key as the table, but a different sort (range) key.  
A. True  
B. False
#card 
B  
Every global secondary index must have a partition key, and can have an optional sort key. The index key schema can be different from the base table schema; you could have a table with a simple primary key (partition key), and create a global secondary index with a composite primary key (partition key and sort key) — or vice-versa.
^1626790298646

67. DynamoDB supports types that represent number sets, string sets and binary sets.  
A. True  
B. False
#card 
A  
DynamoDB supports types that represent sets of Number, String, or Binary values. All of the elements within a set must be of the same type. For example, an attribute of type Number Set can only contain numbers; String Set can only contain strings; and so on.
^1626790298656

68. DynamoDB provides operations to create, update and delete tables.  
A. True  
B. False
#card 
A
^1626790298666

69. The DynamoDB  __________ operation allows you to update existing attribute values, add new attributes, and delete existing attributes from an item.  
A. UpdateTableItem  
B. UpdateItem  
C. UpdateAttribute  
D. UpdateDeleteAttribute  
E. All of the above
#card 
B  
To update an existing item in a table, you use the UpdateItem operation. You must provide the key of the item you want to update. You must also provide an update expression, indicating the attributes you want to modify and the values you want to assign to them.  
An update expression specifies how UpdateItem will modify the attributes of an item—for example, setting a scalar value, or removing elements from a list or a map.
^1626790298676

70. You can query, using the query API command, only DynamoDB tables whose primary key is of hash or hash-and-range type; you can also query any secondary index on such tables.  
A. True  
B. False
#card 
B  
You can use GetItem or PutItem to read or write an item using its primary key only. The Query API/SDK command can query without using the sort key but you can only query a table or secondary index that has a composite primary key (a partition key and a sort key).
^1626790298686

71. Query is the most efficient way to retrieve items from a DynamoDB table or a secondary index.  
A. True  
B. False
#card 
A  
The Query operation finds items based on primary key values. A Scan operation reads every item in a table or a secondary index. By default, a Scan operation returns all of the data attributes for every item in the table or index.
^1626790298696

72. DynamoDB supports a _________ feature that lets you specify a condition when updating an item. DynamoDB writes the item only if the specified condition is met; otherwise it returns an error.  
A. Strongly Consistent Write  
B. Conditional Write  
C. Eventually Consistent Write  
D. None of the above
#card 
B  
By default, the DynamoDB write operations (PutItem, UpdateItem, DeleteItem) are unconditional: each of these operations will overwrite an existing item that has the specified primary key.
^1626790298707

73. A DynamoDB unit of write capacity represents one write per second for items as large as 4 KB.  
A. True  
B. False
#card 
B  
You specify throughput capacity in terms of read capacity units and write capacity units:
One read capacity unit represents one strongly consistent read per second, or two eventually consistent reads per second, for an item up to 4 KB in size. If you need to read an item that is larger than 4 KB, DynamoDB will need to consume additional read capacity units. The total number of read capacity units required depends on the item size, and whether you want an eventually consistent or strongly consistent read.  
One write capacity unit represents one write per second for an item up to 1 KB in size. If you need to write an item that is larger than 1 KB, DynamoDB will need to consume additional write capacity units. The total number of write capacity units required depends on the item size.
^1626790298717

74. A DynamoDB unit of read capacity represents one strongly consistent read per second (or two eventually consistent reads per second) for items as large as 4 KB.  
A. True  
B. False
#card 
A
^1626790298728

75. Calculate the number of DynamoDB read operations (read capacity units) for an item of 13 KB:  
A. 3  
B. 4  
C. 2  
D. 6
#card 
B  
13/4 = 3.25  
4 (3.25 rounded up) read capacity units required
^1626790298738

76. If your DynamoDB items are 5 KB and you want to read 80 items per second from your table, then you need to provision ___ read capacity units for eventual consistency.  
A. 40  
B. 80  
C. 120  
D. 160
#card 
One write capacity unit represents one write per second for an item up to 1 KB in size.  
4 capacity units required for 3.5 KB.  
4x20 = 80
^1626790298748

77. The following are valid DynamoDB table names:  
• Id  
• cool.table.name  
• cool-table-name  
• cool:table:name  
A. True  
B. False
#card 
B  
cool.table.name  
cool-table-name  
For table and secondary index names, allowed characters are a-z, A-Z, 0-9, '_' (underscore), '-' (dash), and '.' (dot). Names can be between 3 and 255 characters long.
^1626790298758

78. If you expect upcoming spikes in your workload (such as a new product launch) that will cause your throughput to exceed the current provisioned throughput for your table, you can use the DynamoDB UpdateTable operation to increase the ProvisionedThroughput value.  
A. True  
B. False
#card 
A  
As your application data and access requirements change, you might need to adjust your table's throughput settings. If you're using DynamoDB auto scaling, the throughput settings are automatically adjusted in response to actual workloads. You can also use the UpdateTable operation to manually adjust your table's throughput capacity. You might decide to do this if you need to bulk-load data from an existing data store into your new DynamoDB table. You could create the table with a large write throughput setting and then reduce this setting after the bulk data load is complete.
^1626790298768

79. The DynamoDB capacity units consumed by an operation depends on the following:  
• Item size  
• Read consistency (in case of a read operation)  
• Provisioned IOPS  
A. True  
B. False
#card 
B  
Item size, Read consistency (in case of a read operation).  
Provisioned IOPS only makes them consumed faster.
^1626790298778

80. The optimal usage of a DynamoDB table's provisioned throughput depends on these factors:  
• Database schema  
• The primary key selection.  
• The workload patterns on individual items  
A. True  
B. False
#card 
B  
The primary key selection.The workload patterns on individual items
^1626790298788

81. Choose the DynamoDB partition (hash) key schema for provisioned throughput efficiency:  
A. Status code, where there are only a few possible status codes.  
B. User ID, where the application has many users.  
C. Device ID, where even if there are a lot of devices being tracked, one is by far more popular than all the others.  
D. Item creation date, rounded to the nearest time period (e.g. day, hour, minute)
#card 
B
^1626790298797

82. There is a limit of 256 KB on the DynamoDB item size.  
A. True  
B. False
#card 
B  
The maximum item size in DynamoDB is 400 KB, which includes both attribute name binary length (UTF-8 length) and attribute value lengths (again binary length). The attribute name counts towards the size limit.
^1626790298807

83. You must provide the name of the DynamoDB table, along with the primary key of the item you want when using the GetItem operation.  
Answers  
A. True  
B. False
#card 
A  
DynamoDB provides four operations for basic create/read/update/delete (CRUD) functionality:  
• PutItem - create an item.  
• GetItem - read an item.  
• UpdateItem - update an item.  
• DeleteItem - delete an item.
Each of these operations require you to specify the primary key of the item you want to work with. For example, to read an item using GetItem, you must specify the partition key and sort key (if applicable) for that item.
^1626790298817

84. To create, update, and delete items in a DynamoDB table, use the following operations:  
• PutItem  
• UpdateItem  
• WriteItem  
• DeleteItem  
A. True  
B. False
#card 
B 
PutItem UpdateItem DeleteItem
^1626790298828

85. A single DynamoDB BatchGetItem request can retrieve up to 16 MB of data, which can contain as many as 25 items.  
A. True  
B. False
#card 
B  
BatchGetItem  
A single BatchGetItem operation can retrieve a maximum of 100 items. The total size of all the items retrieved cannot exceed 16 MB.
^1626790298837

86. DynamoDB BatchWriteItem can write up to 1 MB of data, consisting of up to 100 put or delete requests.  
A. True  
B. False
#card 
B
A single call to BatchWriteItem can write up to 16 MB of data, which can comprise as many as 25 put or delete requests.^1626790298847
