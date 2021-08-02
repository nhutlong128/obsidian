---
cards-deck: Obsidian::Cloud-Computing::Compute::Lambda
tags: lambda, compute
---

### Metadata

-  Type: #permanent #compute
    Date written: #2021-05-21  
    Source:  https://docs.aws.amazon.com/lambda/index.html
    Status: #wip 
    Keywords:  #cloudcomputing #aws #lambda
	Related:
	
### Notes
- [[Lambda Compute Type]]
- [[Lambda Provision Instance]]
- [[Lambda Location]]
- [[Lambda Type]]
- [[Lambda High Availability Mechanism]]
- [[Lambda Scalability Mechanism]]
- [[Lambda Storage]]
- [[Lambda Runtime Provided]]
- [[Lambda Security]]
- [[Lambda Optimize]]
- [[Lambda Fees charged]]
- [[Lambda Specific]]

### Questions

1. How can you increase the CPU resources for your Lambda?
- Increase the configured CPU value
- Increase the configured timeout value
- Increase the configured memory value
- Increase the configured concurrency value
#card 
Increase the configured memory value
^1626789590971

2. How can additional code or content be provided for your Lambda?
- blocks
- layers
- aliases
- handlers
#card 
layers
^1626789590981

3. How can Step Functions call Lambdas?
- in sequence
- in parallel
- neither of these answers
- both of these answers
#card 
both of these answers
^1626789590990

4. Which AWS CLI command invokes a function?
- aws lambda invoke --function ReturnBucketName outputfile.txt
- aws lambda execute --function-name ReturnBucketName outputfile.txt
- aws lambda invoke --function-name ReturnBucketName outputfile.txt
- aws lambda execute --function ReturnBucketName outputfile.txt
#card 
aws lambda invoke --function-name ReturnBucketName outputfile.txt
^1626789590999

5. What adds tracing capabilities to a Lambda?
- AWS Trace
- CloudStack
- CloudTrail
- AWS X-Ray
#card 
AWS X-Ray
^1626789591009

6. You need to build a continuous integration/deployment pipeline for a set of Lambdas. What should you do?
- Create configuration files and deploy them using AWS CodePipeline.
- Create CloudFormation templates and deploy them using AWS CodeBuild
- Create configuration file and deploy using AWS CodeBuild
- Create CloudFormation templates and deploy them using AWS CodePipeline.
#card 
 Create CloudFormation templates and deploy them using AWS CodePipeline.
^1626789591018

7. What can you use to monitor function invocations?
- API Gateway
- S3
- SAS
- CLoudTrail
#card 
CloudTrail
^1626789591027

8. It is AWS best practice to enable Lambda logging by which of these methods.
- Use S3 metrics and CloudWatch alarms
- Create custom metrics within your Lambda code.
- Create custom metrics within your CloudWatch code
- Use Lambda metrics and CloudWatch alarms.
#card 
Use Lambda metrics and CloudWatch alarms.
^1626789591037

9. What may be provided for environment variables?
-  an SSL certificate
-  a bitmask
-  an AWS KMS key
-   an HTTP protocol
#card 
 an AWS KMS key
 
 10. Lambdas allow for running of what other things?
 - binaries
 - all of these answers
 - executables
 - Shell scripts
#card 
all of these answers
^1626789591046

11. In what style must you write Lambda code?
- MVC
- virtual
- stateless
- protocol
#card 
stateless
^1626789591055

12. How can a developer provide Lambda code?
- by uploading a .zip file
- all of these answers
- by editing inline
- from an S3 bucket
#card 
all of these answers
^1626789591064

13. You are performance-testing your Lambda to verify that you set the memory size adequately. Where do you verify the execution overhead?
- CLoudWatch logs
- DynamoDB logs
- S3 logs
- Lambda logs.
#card 
Lambda logs.
^1626789591073

14. What facilitates continuous delivery of Lambdas?
- CodeStack
- ElasticStack
-  Mobile Hub
- CodeDeploy
#card 
CodeDeploy
^1626789591083

15. How are computing resources allocated to Lambdas?
- proportionally
- equally
- periodically
- daily
#card 
proportionally. CPU power will be **allocated** proportionally to the memory.
^1626789591092

16. You can restrict the scope of a user's permissions by specifying which two items in an IAM policy?
- resources and users
- resources and conditions
- events and users
- events and conditions
#card 
resources and conditions
^1626789591102

17.  What does Lambda logging include?
- logging streams
- rotating streams
- logging events
- advancing log groups
#card 
logging streams
^1626789591111

18.  What can AWS Amplify NOT do for a Lambda?
- create a Lambda
- assign an IAM role
- delete a Lambda
- be an event source
#card
be an event source
^1626789591121

19. How do you author a Lambda in a programming language that AWS does not support?
- Create a Lambda function with a custom runtime and reference the function in your Lambda
- Create a Lambda layer with a custom runtime and reference the layer in your lambda
- You cannot use Lambda in this situation
- Create a Lambda function with a custom runtime
#card 
Create a Lambda layer with a custom runtime and reference the layer in your lambda
^1626789591131

20.  What are listed downstream resources based on?
- the execution policy
- the Lambda configuration
- the Lambda nodes
- the IAM user
#card 
the Lambda configuration. A downstream resources is An **AWS** service, such as DynamoDB tables or Amazon S3 buckets, that Lambda function calls once it is triggered
^1626789591141

21. Which is an equivalent and valid tag for a pair of Lambdas?
- department:Sales,department:Sales
- department:Sales,department:sales
- aws:demo;aws:demo
- aws:demo;aws:DEMO
#card 
department:Sales,department:sales (tag key and tag value is case sensitive)
^1626789591150

22. Outbound connections from Lambdas must be ___
- neither of these answers
- UDP/IP
- TCP/IP
- both of these answers
#card 
both of these answers
^1626789591160

23. How are CloudWatch actions configured?
- automatically
- none of these answers
- manually
- ad hoc
#card 
manually
^1626789591170

24. You are testing your stream-based application and the associated Lambda. AWS best practice advises you to test by varying what?
- stream and record sizes
- stream and shard sizes
- batch and record sizes
- batch and shard sizes
#card 
batch and record sizes
^1626789591179

25. You need to make your Lambda available to services in multiple VPCs. What do you do?
- Place each subnet in a VPC. Associate all subnets to your Lambda.
- Place all subnets in a VPC. Associate all subnets to your Lambda.
- Configure your Lambda to be available to multiple VPCs.
- Configure all application VPCs to be peered.
#card 
Configure all application VPCs to be peered.
^1626789591188

26. How is the cost associated with Lambda function calculated?
- number of function calls
- amount of code run
- compute time
- amount of infrastructure used
#card 
compute time
^1626789591197

27. What is the fastest way to get started with Lambda?
- Author a Lambda from scratch.
- Use a blueprint.
- Use a .zip deployment package.
- Use the serverless app repository.
#card 
Use a blueprint.
^1626789591206

28.  Where is the disk space allocated for Lambda functions?
- /tmp
- /default
- /temp
- /ds
#card 
/tmp
^1626789591216

29. How do you stop a running Lambda that is stuck in a recursive loop?
- Delete the function.
- Set the function concurrent execution limit to 0 while you update the code.
- Reset the function.
- Set the function concurrent execution limit to 100 while you update the code.
#card 
Set the function concurrent execution limit to 0 while you update the code.
^1626789591225

30. What is AWS best practice for Lambda configuration?
- Overprovision memory to run your functions faster and reduce your costs. Do not overprovision your function timeout settings.
- Overprovision memory and your function timeout settings to run your functions faster and reduce your costs.
- Do not overprovision memory. Overprovision your function timeout settings to run your functions faster and reduce costs.
- Do not overprovision memory. Do not overprovision your function timeout settings to run your functions faster and reduce costs.
#card 
Overprovision memory to run your functions faster and reduce your costs. Do not overprovision your function timeout settings.
^1626789591234

31. Basic Lambda permissions include permissions for what?
- removing log groups
- none of these answers
- creating log groups
- updating log groups
#card 
updating log groups
^1626789591243

32.  How are environment variables stored?
- DynamoDB tables
- key-value pairs
- S3 buckets
- none of these answers
#card 
key-value pairs
^1626789591252

33. You need to use a Lambda to provide backend logic to your website. Which service do you use to make your Lambda available to your website?
- S3
- API Gateway
- X-Ray
- DynamoDB
#card 
API Gateway
^1626789591261

34. You are creating a Lambda to trigger on change to files in an S3 bucket. Where should you put the bucket name?
- in the Lambda function code
- in a Lambda environment variable
- in the Lambda tags
- in another S3 bucket
#card
in a Lambda environment variable
^1626789591270

35. What action is needed before you can test a Lambda?
- Deploy the Lambda
- Export the function
- none of these answers
- Configure a test event
#card 
Configure a test event
^1626789591280

36. What kind of packages can you use with Node.js for Lambdas?
- Fleece
- NPM
- Pod
#card 
NPM
^1626789591289

37. Lambdas are monitored by default using which service?
- CloudTrail
- CloudWatch
- CloudFormation
- LogWatch
#card 
CloudWatch
^1626789591298

38. What can trigger a Lambda function execution?
- a table definition
- queue isolation
- STS Write
- an SNS topic
#card 
an SNS topic
^1626789591307

39. You need to set an S3 event trigger on your Lambda to respond when data is added to your bucket from another S3 bucket. Which event type do you configure?
- POST
- "All object create events"
- PUT
- COPY
#card 
PUT
^1626789591316

40. To make Lambdas more testable, it is AWS best practice to separate which of these?
- Lambda configuration from logging code
- Lambda handler from logging code
- Lambda handler from core logic
- Lambda configuration from core logic
#card 
Lambda handler from core logic
^1626789591326

41. You have a Lambda function that will process data for 25 minutes before successfully completing. The code is working fine in your machine, but in AWS Lambda it just fails with a "timeout" issue after 3 seconds. What should you do?
- Set the timeout to 25 minutes
- Set the memory to 3GB
- Run your code somewhere else than Lambda - the maximum timeout is 15 minutes
#card 
Run your code somewhere else than Lambda - the maximum timeout is 15 minutes
^1626789591335

42. You'd like to have a dynamic DB_URL variable loaded in your Lambda code
- Place it in the environment variables
- Place it in the code zip file
- Place it in the code itself
#card 
Place it in the environment variables
^1626789591344

43. What setting is used to limit concurrency of a lambda function
#card 
Reserved Concurrency
^1626789591353

44. What error is thrown if the lambda concurrency limit is exceeded
#card 
ThrottleError
^1626789591362

45. What capability enables warm lambdas
#card 
Provisioned Concurrency
^1626789591371

46. How are dependencies included in lambda
#card 
included in zip file
^1626789591380

47. What are the memory limits / region of Lambda
#card 
128mb - 3008 mb
^1626789591390

48. What is the memory limit for environment variables
#card 
4kb
^1626789591399

49. What is the disk capacity for /tmp
#card 
512mb
^1626789591408

50. What are the zip / unzip limits
#card 
50 / 250mb
^1626789591417

51. When using CloudFormation where should the code of Lambda go
#card 
S3 in a zip file
^1626789591426

52. How can lambda be integrated with an ALB
#card 
With a target group
^1626789591436

53. Lambda writes all output to S3.
#card 
False
^1626789591445

54. Print and logging statements in Lambda write to:
#card 
Cloudwatch Logs
^1626789591455

55. How does Lambda scale automatically?
#card 
Lambda scales OUT automatically - each time your function is triggered, a new, separate instance of that function is started. There are limits, but these can be adjusted on request.
^1626789591464

56. What service can be used to help resolve an issue with a lambda function?
#card 
X-Ray
^1626789591473

57. What does AWS X-Ray do?
#card 
AWS X-Ray helps you debug Lambda.
^1626789591483

58. Each time a Lambda function is triggered....
#card 
Each time a Lambda function is triggered, an isolated instance of that function is invoked. Multiple triggers result in multiple concurrent invocations, one for each time it is triggered
^1626789591493

59. Serverless computing is about eliminating servers.
#card 
False. Serverless computing is about shifting most of the the responsibility for infrastructure and operation of the infrastructure to a vendor so that you can focus more on the business services, not how to manage the infrastructure that they run on.
^1626789591502

60. From which services does Lambda read events?
#card 
Kinesis  
Dynamo DB  
SQS
^1626789591511

61. Name three AWS services which support hyper-threading on one or more virtual CPUs.
#card 
Lambda, EC2, ECS
^1626789591521

62. Lambda scales in response to what?
#card 
to events
^1626789591530

63. What defines which AWS resources your function can access?
#card 
An execution role defines which AWS resources your function can access.
^1626789591539

64. What is used to tell the Lambda service which events have permission to invoke the Lambda function?
#card 
A resource policy is used to tell the Lambda service which events have permission to invoke the Lambda function.
^1626789591549

65. What makes it easy to grant access to the Lambda function across AWS accounts?
#card 
Resource policies make it easy to grant access to the Lambda function across AWS accounts.
^1626789591558

66. When is a Lambda Function policy created?
#card 
A Lambda Function policy is created when you add a trigger to a Lambda function.
^1626789591567

67. A Lambda Function Policy is also called a what?
#card 
A Lambda Function Policy is also called a Resource Policy.
^1626789591576

68. True/False: Does a resource policy have to be chosen or created when you create a Lambda function?
#card 
False. A resource policy does not have to be chosen or created when you create a Lambda function.
^1626789591586

69. True/False: Can a Resource Policy give Amazon S3 permission to trigger a Lambda function?
#card 
True: A Resource Policy can give Amazon S3 permission to trigger a Lambda function.
^1626789591595

70. True/False: Can a Resource policy give Lambda permission to write data to a DynamoDB table?
#card 
False: A Resource policy can not give Lambda permission to write data to a DynamoDB table. An Execution Role would give Lambda permission to write data to a DynamoDB table.
^1626789591604

71. True/False: Can a Resource Policy grant access to the Lambda function across AWS accounts?
#card 
True. A Resource Policy grant access to the Lambda function across AWS accounts.
^1626789591613

72. True/False: Does a Resource Policy Determine what Lambda is allowed to do?
#card 
False. An Execution Role determines what Lambda is allowed to do.
^1626789591622

73. What is a function or resource policy used for?
#card 
A function or resource policy determines who is allowed in and is used to tell the Lambda service which events have permission to invoke the Lambda function.
^1626789591631

74. Would you use a Resource Policy or an Execution role to grant access to the Lambda function across AWS accounts?
#card 
You would use a Resource Policy to grant access to the Lambda function across AWS accounts.
^1626789591641

75. True/False: Does an Execution Role have to be chosen or created when you create a Lambda function?
#card 
True: An Execution Role has to be chosen or created when you create a Lambda function.
^1626789591650

76. What does an Execution Role control?
#card 
An Execution Role controls what Lambda is allowed to do, such as writing to a DynamoDB table.
^1626789591659

77. The event sources or triggers can be categorized into 4 types. What are the 4 types of event sources?
#card 
the 4 types of event sources are:  
Data Store.  
Endpoint.  
Repositiories.  
Message Services.
^1626789591668

78. What is an example of a Data Store event source?
#card 
If it stores data that you want to track changes to, it's a potential event source. So for example, Amazon S3, Amazon DynamoDB, and Amazon Kinesis Data Streams are all data stores.
^1626789591677

79. What are Endpoint event sources?
#card 
These are AWS services that emit events and invoke Lambda. For example, when you ask Alexa to do something, she's emitting an event that triggers a Lambda function.
^1626789591686

80. What is an example of a Repository event source?
#card 
Repositories hold information and can trigger Lambda when certain actions occur—like triggering a Lambda function based on a specific action recorded in Amazon CloudWatch. Or automatically triggering your CI/CD build process when you commit code to your AWS CodeCommit repository.
^1626789591696

81. What is an example of a Message Services event source?
#card 
An example of a Message Services event source is something being published to an Amazon SNS topic. SES, SNS, SQS, Cron Events
^1626789591705

82. How are errors handled differently, between stream and queue polling?
#card 
With stream, errors in a shard block further processing, because events in each shard from the stream need to be processed in order. With queue, errors are returned to the queue or go to a dead letter queue.
^1626789591714

83. True/False: When invoking a Lambda function programmatically, you must specify the invocation type.
#card 
True: When invoking a Lambda function programmatically, you must specify the invocation type.
^1626789591724

84. Which invocation type should you use for batch processing?
#card 
Asynchronous events. This model makes sense for things that are batch processes. With an async event, Lambda will automatically retry the invoke twice more on your behalf. You also have the option to enable a dead letter queue (or DLQ) on your Lambda function.
^1626789591733

85. Which three services use the polling model?
#card 
DynamoDB streams, Kinesis Data Streams and SQS use the polling model.
^1626789591743

86. Best practice: Write functions to take advantage of what kind of start?
#card 
Write functions to take advantage of a warm start.
^1626789591752

87. Best Practice: What kind of start should be minimized?
#card 
Write functions to minimize Cold Starts. Note that enabling VPC with Lambda increases the cold start time.
^1626789591761

88. Is enabling VPC with Lambda increases the cold start time?
#card 
Yes
^1626789591770
