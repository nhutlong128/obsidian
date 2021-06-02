### Metadata

-  Type: #permanent #integration
    Date written: 2021-06-01 
    Source:  https://docs.aws.amazon.com/sns/latest/dg/welcome.html
    Status: #wip 
    Keywords:  #cloudcomputing #aws #sns
	Related:
	
### Notes
- [[SNS]] is similar to [[SQS]]. If [[SQS]] is poll based method then [[SNS]] is push based method.
- [[SNS]] support [[Dead Letter Queue - DLQ]]
- [[SNS]] has two type queues like [[SQS]]:
	- [[Standard Queue]] and [[FIFO Queue]]. But [[FIFO Queue]] only supported by [[SQS]] consumer.
- [[SNS Error Handling]] is dependent on error types to retry processing message or discard it.
- [[SNS]] support [[MessageAttributes]] helping filter message and provide structured meta data for message.
Backlink: [[Messaging & Integration]]