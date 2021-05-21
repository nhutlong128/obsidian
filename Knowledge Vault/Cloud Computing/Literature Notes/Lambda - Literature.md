## Metadata

-  Type: #literature #compute
    Date written: #2021-05-19
    Source:  https://docs.aws.amazon.com/lambda/latest/
    Status: #done
    Keywords:  #cloudcomputing #aws #lambda
	
### Notes
- When you invoke a function synchronously, Lambda runs the function and waits for a response. When the function completes, Lambda returns the response from the function's code with additional data, such as the version of the function that was invoked. To invoke a function synchronously with the AWS CLI, use the `invoke` command.
	- Invoke sync from:
		- AWS CLI
- For asynchronous invocation, Lambda places the event in a queue and returns a success response without additional information. A separate process reads events from the queue and sends them to your function. To invoke a function asynchronously, set the invocation type parameter to `Event`.
	```python3

	aws lambda invoke --function-name my-function  --invocation-type Event --payload '{ "key": "value" }' response.json

	```
	- Invoke async from:
		- AWS CLI
		- SNS
		- S3
	- Sending invocation record to:
		- SQS
		- SNS
		- Lambda
		- Event Bridge
	- As an alternative to an [on-failure destination](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html#invocation-async-destinations), you can configure your function with a dead-letter queue to save discarded events for further processing. A dead-letter queue acts the same as an on-failure destination in that it is used when an event fails all processing attempts or expires without being processed. However, a dead-letter queue is part of a function's version-specific configuration, so it is locked in when you publish a version.
		- If you don't have a queue or topic, create one. Choose the target type that matches your use case.
			- SQS
			- SNS
- For event source mapping: An event source mapping is an AWS Lambda resource that reads from an event source and invokes a Lambda function. You can use event source mappings to process items from a stream or queue in services that don't invoke Lambda functions directly. 
	- Lambda provides event source mappings for the following services.
		- DynamoDB
		- Kinesis
		- MQ
		- Kafka
		- SQS
	- You can also configure the event source mapping to send an invocation record to another service when it discards an event batch. Lambda supports the following [destinations](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html#invocation-async-destinations) for event source mappings:
		- SQS
		- SNS
- You deploy your Lambda function code using a _deployment package_. Lambda supports two types of deployment packages:
	-   A .zip file archive that contains your function code and its dependencies. Lambda provides the operating system and runtime for your function.
	-   A container image that is compatible with the [Open Container Initiative (OCI)](https://opencontainers.org/) specification. You add your function code and dependencies to the image. You must also include the operating system and a Lambda runtime.
- A **Lambda _layer_** is a** .zip file** archive that can contain additional code or other content. A layer can contain libraries, a [custom runtime](https://docs.aws.amazon.com/lambda/latest/dg/runtimes-custom.html), data, or configuration files.
	- Layers provide a convenient way to package libraries and other dependencies that you can use with your Lambda functions. Using layers reduces the size of uploaded deployment archives and makes it faster to deploy your code. Layers also promote code sharing and separation of responsibilities so that you can iterate faster on writing business logic.
	- You can include up to five layers per function. Layers count towards the standard Lambda [deployment size quotas](https://docs.amazonaws.cn/en_us/lambda/latest/dg/gettingstarted-limits.html). When you include a layer in a function, the contents are extracted to the `/opt` directory in the execution environment.
- **Concurrency** is the number of requests that your function is serving at any given time. When your function is invoked, Lambda provisions an instance of it to process the event. When the function code finishes running, it can handle another request. If the function is invoked again while a request is still being processed, another instance is provisioned, increasing the function's concurrency.
- A Lambda function's execution role is an AWS Identity and Access Management (IAM) role that grants the function permission to access AWS services and resources.
- When you connect a function to a VPC, Lambda creates an [elastic network interface](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_ElasticNetworkInterfaces.html) for each subnet in your function's VPC configuration. This process can take about a minute.
- While Lambda creates a network interface, you can't perform additional operations that target the function, such as [creating versions](https://docs.aws.amazon.com/lambda/latest/dg/configuration-versions.html) or updating the function's code. For new functions, you can't invoke the function until its state changes from `Pending` to `Active`
- If you use Amazon Virtual Private Cloud (Amazon VPC) to host your AWS resources, you can establish a connection between your VPC and Lambda. You can use this connection to invoke your Lambda function without crossing the public internet.

##### Security
- ## Encryption in transit : Lambda API endpoints only support secure connections over HTTPS. When you manage Lambda resources with the AWS Management Console,AWS SDK, or the Lambda API, all communication is encrypted with Transport Layer Security (TLS).
- ## Encryption at rest : You can use environment variables to store secrets securely for use with Lambda functions. Lambda always encrypts environment variables at rest.
- AWS Identity and Access Management (IAM) is an AWS service that helps an administrator securely control access to AWS resources. IAM administrators control who can be _authenticated_ (signed in) and _authorized_ (have permissions) to use Lambda resources. IAM is an AWS service that you can use with no additional charge.

##### Monitoring
- CloudWatch
- CloudTrail
- X-Ray

