- [[Short-Long Polling]] for receiving messages from queue.
- When the message is received and processed from the consumer, to prevent other consumers get the message again due to distributed system, [[Visibility Timeout]] set the message unavailable for the duration.
- When the message is first added to the queue, it can be hidden with the help of [[SQS Delay Queue]].
- To set the first added to the queue of one individual of message, use [[SQS Message Timers]].
- [[Dead Letter Queue - DLQ]]
- [[Cost Allocation Tag]]
