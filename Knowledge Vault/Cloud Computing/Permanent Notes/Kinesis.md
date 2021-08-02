---
cards-deck: Obsidian::Cloud-Computing::Analytics::Kinesis
tags: kinesis, analytics
---
### Metadata

-  Type: #permanent #analytics
    Date written: #2021-06-22
    Source:  https://aws.amazon.com/vi/kinesis/
    Status: #wip 
    Keywords:  #cloudcomputing #aws #kinesis
	Related:
	
### Notes
- [[Kinesis]] is a managed atlernative to [[Kafka]]
- [[Kinesis Streams]] low latency streaming
- [[Kinesis Analytics]] real-time analytics on streams using SQL
- [[Kinesis Firehose]] load streams into storage, data warehouse
- [[Kinesis Video Streams]] streaming video in real-time

![[Pasted image 20210622214451.png]]
![[Pasted image 20210622215847.png]]
![[Pasted image 20210622221731.png]]

### Questions

##### You have a Kinesis stream usually receiving 5MB/s of data and sending out 8 MB/s of data. You have provisioned 6 shards. Some days, your traffic spikes up to 2 times and you get a throughput exception. You should
- Enable Kinesis replication
- Add more shards
- Use SQS as a buffer to Kinesis
#card 
Add more shards. Each shard allows for 1MB/s incoming and 2MB/s outgoing of data

##### You are sending a clickstream for your users navigating your website, all the way to Kinesis. It seems that the users data is not ordered in Kinesis, and the data for one individual user is spread across many shards. How to fix that problem?
- There are too many shards, you should only use 1 shard
- You should use a partition key that represents the identity of the user
- You shouldn't use multiple consumers, only one and it should re-order data
#card 
You should use a partition key that represents the identity of the user

##### We'd like to perform real time analytics on streams of data. The most appropriate product will be
- SQS
- SNS
- Kinesis
#card 
Kinesis

##### We'd like for our big data to be loaded near real time to S3 or Redshift. We'd like to convert the data along the way. What should we use?
- SQS & Lambda
- SNS & HTTP Endpoint
- Kinesis Streams & Kinesis Firehose
#card 
Kinesis Streams & Kinesis Firehose. This is a perfect combo of technology for loading data near real-time in S3 and Redshift