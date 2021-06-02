- [[Short Polling]]: [[SQS]] samples a subset of servers (based on weighted random distribution) to get the messages
- [[Long Polling]]: After [[WaitTimeSecond]], [[SQS]] start [[Long Polling]] by get all the messages of servers.
- [[Long Polling]]: reduce false empty response (when [[Short Polling]] cant get the response message)
Backlink: [[SQS]]