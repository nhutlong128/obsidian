### Metadata

-  Type: #permanent #integration
    Date written: #2021-05-31  
    Source:  https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html
    Status: #wip 
    Keywords:  #cloudcomputing #aws #sqs
	Related:
	
### Notes
- [[SQS]] support both [[Standard Queue]] and [[FIFO Queue]].
- [[SQS]] use [[Server-side encryption (SSE)]] to encrypt message in queues at rest.
- [[SQS]] offers common features such as [[Dead Letter Queue - DLQ]] and [[Cost Allocation Tag]]
- [[SQS]] provides [[Short-Long Polling]] for receiving messages from queue.
- When the message is received and processed from the consumer, to prevent other consumers get the message again due to distributed system of [[SQS]], [[Visibility Timeout]] set the message unavailable for the duration.
- When the message is first added to the queue, it can be hidden with the help of [[SQS Delay Queue]].
- To set the first added to the queue of one individual of message, use [[SQS Message Timers]].
- [[SQS Error Handling]] is to retry processing the message.
Backlink: [[Messaging & Integration]]