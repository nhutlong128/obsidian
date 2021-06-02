- [[Server-side encryption (SSE)]] Using keys managed by [[KMS]] .
- [[Server-side encryption (SSE)]] only encrypts the body of a message
- [[Data key reuse perioid]] is the length of time SQS caching a data key before call [[KMS]] again.
- When [[SQS]] moves a message from encrypted source queue to an unecrypted [[Dead Letter Queue - DLQ]], the message remains **Encrypted**

Backlink: [[SQS]]