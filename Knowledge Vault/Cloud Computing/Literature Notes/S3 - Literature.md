### Metadata

-  Type: #literature #storage
    Date written: [[2021-05-17, Mon]]  
    Source:  https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html
    Status: #done  
    Keywords:  #cloudcomputing #aws #s3
	
### Notes
- S3 is a **global service** as seen at the top right but buckets are created in a specific region. This helps reduce **latency**. Bucket names must be **unique globally** and no two buckets in AWS S3 have the same name.
- S3 supports Object Lock: store objects using a write-once-read-many (WORM) model to help you prevent objects from being delected or overwritten for a fixed amount of time or indefinitely
- Instead of manually setting up the storage classes for each individual objects, S3 also provides an option to set up **Life Cycle Rules** that will automatically change the storage class of objects under a bucket after a specific interval of time.
- In S3 Bucket versioning, new versions are created with `standard storage `even if the previous versions were under some other storage class.
- **Write once read many** (**WORM**) describes a [data storage device](https://en.wikipedia.org/wiki/Data_storage_device "Data storage device") in which information, once written, cannot be modified. This [write protection](https://en.wikipedia.org/wiki/Write_protection "Write protection") affords the assurance that the [data](https://en.wikipedia.org/wiki/Data "Data") cannot be tampered with once it is written to the device.
- S3 also allows replicating objects to a different bucket for backup or some other purposes. Objects can be replicated to bucket with the same region (SRR) or to some other region (CRR).
- For S3 replication, it is mandatory we **set up an IAM role** to allow S3 to put objects to the destination bucket. Also, **bucket versioning** for destination bucket must be **enabled**.
- While S3 Replication, We can also change **the storage class** of the replicated objects in the destination bucket. Another option we can enable is **replication time control** (RTC). Additional charges per GB are charged but 99.99% data is copied within 15 mins.
- **Read after write consistency** for new objects — means that if we request new objects right after creation, S3 might return 404 but eventually the objects become available.
- **Eventual Consistency** for objects overwrites — If an object is retrieved right after the update, S3 might return the old copy or the new one but never a partially updated object.

##### Security
- Server-Side — Unencrypted data is uploaded on S3 and encrypted first before physically stored by S3 and decrypted on access. The keys used for encryption are managed by the S3 service. S3 also provides options for the client to use its own encryption keys in this case as well.
- Client-Side — Data is encrypted at clients' end and uploaded to S3 in encrypted form. The client is responsible for key management in this case.

##### Monitoring
- You can use the following automated monitoring tools to watch Amazon S3 and report when something is wrong:
	-   **Amazon CloudWatch Alarms** – Watch a single metric over a time period that you specify, and perform one or more actions based on the value of the metric relative to a given threshold over a number of time periods. The action is a notification sent to an Amazon Simple Notification Service (Amazon SNS) topic or Amazon EC2 Auto Scaling policy. CloudWatch alarms do not invoke actions simply because they are in a particular state. The state must have changed and been maintained for a specified number of periods. For more information, see [Monitoring metrics with Amazon CloudWatch](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cloudwatch-monitoring.html).
    
	-   **AWS CloudTrail Log Monitoring** – Share log files between accounts, monitor CloudTrail log files in real time by sending them to CloudWatch Logs, write log processing applications in Java, and validate that your log files have not changed after delivery by CloudTrail. For more information, see [Logging Amazon S3 API calls using AWS CloudTrail](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cloudtrail-logging.html).
	- You can use the Amazon S3 Event Notifications feature to receive notifications when certain events happen in your S3 bucket:
		- Amazon S3 can publish notifications for the following events:
			- **New object created events**
			- **Object removal events**
			- **Restore object events**
			- **Reduced Redundancy Storage (RRS) object lost events**
			- **Replication events**
		- Amazon S3 supports the following destinations where it can publish events:
			- SNS
			- SQS
			- AWS Lambda

##### Analysis
- You can use analytics and insights in Amazon S3 to understand, analyze, and optimize your storage usage.
	- Storage Class Analysis
		- When selecting data export you specify a destination bucket and optional destination prefix where the file is written. You can export the data to a destination bucket in a different account. The destination bucket must be in the same region as the bucket that you configure to be analyzed.
		- You must create a bucket policy on the destination bucket to grant permissions to Amazon S3 to verify what AWS account owns the bucket and to write objects to the bucket in the defined location.
	- S3 Storage Lens
		- Amazon S3 Storage Lens aggregates your usage and activity metrics and displays the information in the account snapshot on the Amazon S3 console home (**Buckets**) page, interactive dashboards, or through a metrics export that you can download in CSV or Parquet format.
	- X-Ray
		- AWS X-Ray supports trace context propagation for Amazon S3, so you can view end-to-end requests as they travel through your entire application.
	
##### Optimize
- Using Caching for Frequently Accessed Content
	- CloudFront
	- ElastiCache
	- Elemental MediaStore
- Timeouts and Retries for Latency-Sensitive Applications
		-  If an application generates high request rates (typically sustained rates of over 5,000 requests per second to a small number of objects), it might receive HTTP 503 _slowdown_ responses. If these errors occur, each AWS SDK implements automatic retry logic using exponential backoff. If you are not using an AWS SDK, you should implement retry logic when receiving the HTTP 503 error.
		-  Amazon S3 automatically scales in response to sustained new request rates, dynamically optimizing performance. While Amazon S3 is internally optimizing for a new request rate, you will receive HTTP 503 request responses temporarily until the optimization completes.
		-  When you make large variably sized requests (for example, more than 128 MB), we advise tracking the throughput being achieved and retrying the slowest 5 percent of the requests. When you make smaller requests (for example, less than 512 KB), where median latencies are often in the tens of milliseconds range, a good guideline is to retry a GET or PUT operation after 2 seconds. If additional retries are needed, the best practice is to back off. For example, we recommend issuing one retry after 2 seconds and a second retry after an additional 4 seconds.
- Horizontal Scaling and Request Parallelization for High Throughput
	- Amazon S3 is a very large distributed system. To help you take advantage of its scale, we encourage you to horizontally scale parallel requests to the Amazon S3 service endpoints.
	- For high-throughput transfers, Amazon S3 advises using applications that use multiple connections to GET or PUT data in parallel. For example, this is supported by [Amazon S3 Transfer Manager](https://docs.aws.amazon.com/sdk-for-java/v1/developer-guide/examples-s3-transfermanager.html) in the AWS Java SDK, and most of the other AWS SDKs provide similar constructs. For some applications, you can achieve parallel connections by launching multiple requests concurrently in different application threads, or in different application instances.
	-  As a general rule, when you download large objects within a Region from Amazon S3 to [Amazon EC2](https://docs.aws.amazon.com/ec2/index.html), we suggest making concurrent requests for byte ranges of an object at the granularity of 8–16 MB. Make one concurrent request for each 85–90 MB/s of desired network throughput. To saturate a 10 Gb/s network interface card (NIC), you might use about 15 concurrent requests over separate connections. You can scale up the concurrent requests over more connections to saturate faster NICs, such as 25 Gb/s or 100 Gb/s NICs.
	-  If your application issues requests directly to Amazon S3 using the REST API, we recommend using a pool of HTTP connections and re-using each connection for a series of requests. Avoiding per-request connection setup removes the need to perform TCP slow-start and Secure Sockets Layer (SSL) handshakes on each request.
- Using Amazon S3 Transfer Acceleration to Accelerate Geographically Disparate Data Transfers
	- [Configuring fast, secure file transfers using Amazon S3 Transfer Acceleration](https://docs.aws.amazon.com/AmazonS3/latest/userguide/transfer-acceleration.html) is effective at minimizing or eliminating the latency caused by geographic distance between globally dispersed clients and a regional application using Amazon S3. Transfer Acceleration uses the globally distributed edge locations in CloudFront for data transport.


