- By default, **Lambda** owns its **[[VPC]]**, which isn't connected to your account's default [[VPC]]. When Lambda is put to a [[VPC]] in user acount, the function in Lambda can't access the internet unless user account's default [[VPC]] provide access. 
- When you put a function to a [[VPC]], Lambda creates a network interface for each subnet in your function's VPC configuration. This process can take about a minute.
- To establish a private connection between VPC and Lambda using [[PrivateLink]]

Backlink: [[Lambda]]