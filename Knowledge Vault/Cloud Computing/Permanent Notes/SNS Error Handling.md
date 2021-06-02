- If the message failed due to [[SNS Client Side Error]]. SNS wont retry delivering  message, it will discard the message or send it to [[Dead Letter Queue - DLQ]]:
	- SQS Consumer deletes queue
	- SNS dont have permission to deliver message to SQS
- If the message failed due to [[SNS Server Side Error]]. SNS will try retry delivering message again and again until reach a number of times, then it will discard the mssage or send it to [[Dead Letter Queue - DLQ]]:
	- SQS Consumer is unavailable
	- SQS fails to consume SNS valid message
Backlink: [[SNS]]