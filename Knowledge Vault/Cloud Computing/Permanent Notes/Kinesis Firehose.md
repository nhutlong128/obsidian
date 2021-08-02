- Is similar to [[Kinesis Streams]], if [[Kinesis Streams]] is for Real Time and managed then [[Kinesis Firehose]] is near real time and fully managed
- Fully Managed Service
- Sources: [[Kinesis Firehose PUT API]], [[Kinesis Agent]], [[Kinesis Streams]], [[CloudWatch]]
- Load streams into [[S3]], [[Redshift]], [[ElasticSearch]], [[Splunk]]
- Near Real Time (1 minute latency minimum for non full batches)
- Automatic Scaling
- Data conversion from CSV/JSON to Parquet/ORC & Data compression only for [[S3]]
- Data Transformation with the help of [[Lambda]]

![[Pasted image 20210622215723.png]]
![[Pasted image 20210622215752.png]]