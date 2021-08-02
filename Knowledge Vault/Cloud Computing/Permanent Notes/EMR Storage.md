Three option:
- [[HDFS]] ~ Default ~ Performance standpoint for processing data on memory => Lost if shutdown
- [[EMRFS]]: Access [[S3]] as if it were [[HDFS]]
	- [[EMRFS Consistent View]] for [[S3 Consistency]]
	- Use [[DynamoDB]] to track [[S3 Consistency]]
- [[EBS]] for [[HDFS]]