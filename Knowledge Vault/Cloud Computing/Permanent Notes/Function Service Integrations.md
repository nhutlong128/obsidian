- Step functions [[Request a response]] and progress to the next state immediately after it gets HTTP response
- Step functions [[Run a Job]] and wait it for that job to complete
- Step functions call a service with a task token and [[Wait for a callback with a task token]]
- While waiting, if a task in a workflow get aborted and Step Functions dont have permission to cancel the corresponding integrated services. We will get additional charges.

Backlink: [[Step Functions]]