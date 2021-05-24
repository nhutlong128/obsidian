### Metadata

-  Type: #permanent #compute
    Date written: #2021-05-21  
    Source:  
    Status: #wip 
    Keywords:  #cloudcomputing #aws #lambda
	References: [[Lambda - Literature]]
	Related:
	
### Notes
- Lambda is a compute services running our code without provisioning and managing services.
- Lambda should be used for doing "light task"
- Lambda has 3 [[Lambda events]] to be triggered to run
- Lambda has 2 types of [[Lambda deployment packages]]
- We can contain more additional code with [[Lambda Layer]] or use [[Lambda Layer]] as running environment 
- [[Lambda Concurrency]] is the number of Lambda function instances running at any given time.
- By default, **Lambda** owns its **[[VPC]]**, which isn't connected to your account's default [[VPC]]. When Lambda is put to a [[VPC]] in user acount, the function in Lambda can't access the internet unless user account's default [[VPC]] provide access. 
- When you put a function to a [[VPC]], Lambda creates a network interface for each subnet in your function's VPC configuration. This process can take about a minute.
- To establish a private connection between VPC and Lambda using [[PrivateLink]]
- To use Lambda efficiently, should [[monitor Lambda]] to optimize if needed.
- Error Analysis
### Questions



Backlink: [[Compute]]