- **Concurrency** is the number of requests that your function is serving at any given time. 
- When your function is invoked, Lambda provisions an instance of it to process the event. 
- When the function code finishes running, it can handle another request. 
- If the function is invoked again while a request is still being processed, another instance is provisioned, increasing the function's concurrency. This works with the help of [[Lambda Function Scaling]]
- Has two types of [[concurrency controls]]

Backlink: [[Lambda]]