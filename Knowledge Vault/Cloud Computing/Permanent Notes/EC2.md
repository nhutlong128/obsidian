---
cards-deck: Obsidian::Cloud-Computing::Compute::EC2
tags: ec2, compute
---
### Metadata

-  Type: #permanent #compute
    Date written: #2021-06-23
    Source:  https://docs.aws.amazon.com/ec2, https://quizlet.com/411383274/aws-ec2-quiz-flash-cards/#, 
    Status: #wip 
    Keywords:  #cloudcomputing #aws #ec2
	Related:
	
### Notes
- [[EC2 Compute Type]]
- [[EC2 Provision Instance]]
- [[EC2 Location]]
- [[EC2 Type]]
- [[EC2 High Availability Mechanism]]
- [[EC2 Scalability Mechanism]]
- [[EC2 Storage]]
- [[EC2 Runtime Provided]]
- [[EC2 Security]]
- [[EC2 Optimize]]
- [[EC2 Fees charged]]
- [[EC2 Specific]]

### Questions

1. Which EC2 Purchasing Option can provide the biggest discount, but is not suitable for critical jobs or databases?
- Scheduled Instances
- Convertible Instances
- Dedicated Hosts
- Spot Instances
#card
Spot Instances
^1626789104377

2. Which network security tool can you use to control traffic in and out of EC2 Instances?
- Network Access Control List
- Identity and Management Access
- Security Groups
#card 
Security Groups
^1626789104388

3. How long can you reserve an EC2 Reserved Instance?
- 1 or 3 years
- 2 or 4 years
- 6 months or 1 year
- anytime between 1 and 3 years
#card 
1 or 3 years
^1626789104397

4. A company would like to deploy a high-performance computing (HPC) application on EC2. Which EC2 instance type should it choose?
- Compute Optimized
- Storage Optimized
- Memory Optimized
- General Purpose
#card 
Compute Optimized
^1626789104407

5. Which EC2 Purchasing Option should you use for an application you plan on running on a server continuously for 1 year?
- Reserved Instances
- Spot Instances
- On-demand Instances
- Convertible Instances
#card 
Reserved Instances
^1626789104416

6. You would like to make sure your EC2 instances have the highest performance while talking to each other as you're performing big data analysis. Which placement group should you choose?
- Cluster
- Spread
#card 
Cluster
^1626789104426

7. You plan on running an open-source MongoDB database year-round on EC2. Which instance launch mode should you choose?
- On-Demand
- Reserved Instances
- Spot Instances
#card 
Reserved Instances
^1626789104436

8. You are launching an EC2 instance in us-east-1 using this Python script snippet:
"ec2.create_instances(ImageId='ami-b23a5e7', MinCount=1, MaxCount=1)"
It works well, so you decide to deploy your script in us-west-1 as well. There, the script does not work and fails with "ami not found" error. What's the problem?
- AMI is region locked and the same ID cannot be used across regions
- The AMI needs to first be shared to another region. The same ID can then be used
#card 
AMI is region locked and the same ID cannot be used across regions
^1626789136095

9.  You would like to deploy a database technology and the vendor license bills you based on the physical cores and underlying network socket visibility. Which EC2 launch modes allow you to get visibility into them?
- Spot Instances
- Dedicated Hosts
- On-Demand
- Reserved Instances
#card 
Dedicated Hosts
^1626789104445

10.  You are launching an application on EC2 and the whole process of installing the application takes about 30 minutes. You would like to minimize the total time for your instance to boot up and be operational to serve traffic. What do you recommend?
- Install the application using EC2 User Data
- Create an AMI after installing the application and launch from the AMI
- Use the EC2 Cluster Placement Group
- Provision an R4.xlarge instance type
#card 
Creating an AMI after installing the applications allows you to start more EC2 instances directly from that AMI, hence bypassing the need to install the application (as it's already installed)
^1626789104455

11. You are running a critical workload of three hours per week, on Monday. As a solutions architect, which EC2 Instance Launch Type should you choose to maximize the cost savings while ensuring the application stability?
- On-Demand Instances
- Reserved Instances
- Spot Instances
- Scheduled Reserved Instances
#card 
Scheduled Reserved Instances
^1626789104464

12.  Your instance in us-east-1a just got terminated, and the attached EBS volume is now available. Your colleague tells you he can't seem to attach it to your instance in us-east-1b.
- He's missing IAM permissions
- EBS volumes are region locked
- EBS volumes are AZ locked
#card 
EBS Volumes are AZ locked
^1626789104474

13. You would like to leverage EBS volumes in parallel to linearly increase performance, while accepting greater failure risks. Which RAID mode helps you in achieving that?
- RAID 0
- RAID 1
- RAID 5
- RAID 6
#card 
RAID 0
^1626789104493

14. Although EBS is already a replicated solution, your company SysOps advised you to use a RAID mode that will mirror data and will allow your instance to not be affected if an EBS volume entirely fails. Which RAID mode did he recommend to you?
- RAID 0
- RAID 1
#card 
RAID 1
^1626789104502

15. You would like to have the same data being accessible as an NFS drive cross AZ on all your EC2 instances. What do you recommend?
- Mount an EFS
- Mount an EBS
- Mount an Instance Store
#card 
Mount an EFS
^1626789104512

16. You would like to have a high-performance cache for your application that mustn't be shared. You don't mind losing the cache upon termination of your instance. Which storage mechanism do you recommend as a Solution Architect?
- Instance Store
- EBS
- EFS
#card 
Instance Store
^1626789104521

17. You are running a high-performance database that requires an IOPS of 210,000 for its underlying filesystem. What do you recommend?
- Use an EBS gp2 drive
- Use an EBS io1 drive
- Use an EC2 Instance Store
- Use EFS
#card 
Use an EBS io1 drive. Is running a DB on EC2 instance store possible? It is possible to run a database on EC2. It is also possible to use instance store, but there are some considerations to have. The data will be lost if the instance is stopped, but it can be restarted without problems. One can also set up a replication mechanism on another EC2 instance with instance store to have a standby copy. One can also have back-up mechanisms. It's all up to how you want to set up your architecture to validate your requirements. In this case, it's around IOPS, and we build an architecture of replication and back up around it.
^1626789104531

18. Load Balancers provide a
- static IPv4 we can use in our application
- static DNS name we can use in our application
- static IPv6 we can use in our application
#card 
static DNS name we can use in our application. The reason being that AWS wants your load balancer to be accessible using a static endpoint, even if the underlying infrastructure that AWS manages changes
^1626789104540

19. You are running a website with a load balancer and 10 EC2 instances. Your users are complaining about the fact that your website always asks them to re-authenticate when they switch pages. You are puzzled, because it's working just fine on your machine and in the dev environment with 1 server. What could be the reason?
- The application must have a bug
- The Load Balancer does not have stickiness enabled
- The EC2 instances log out users because they don't see their true IPs
#card 
The Load Balancer does nto have stickiness enabled. Stickiness ensures traffic is sent to the same backend instance for a client. This helps maintaining session data
^1626789104550

20. Your application is using an Application Load Balancer. It turns out your application only sees traffic coming from private IP which are in fact your load balancer's. What should you do to find the true IP of the clients connected to your website?
- Modify the front-end of the website so that the users send their IP in the requests
- Look into the X-Forwarded-For header in the backend
- Look into the X-Forwarded-Proto header in the backend
#card 
Look into the X-Forwarded-For header in the backend
^1626789104560

21. You quickly created an ELB and it turns out your users are complaining about the fact that sometimes, the servers just don't work. You realise that indeed, your servers do crash from time to time. How to protect your users from seeing these crashes?
- Enable Stickiness
- Enable Health Checks
- Enable SSL Termination
#card 
Enable Health Checks. Health checks ensure your ELB won't send traffic to unhealthy (crashed) instances
^1626789104569

22. You are designing a high performance application that will require millions of connections to be handled, as well as low latency. The best Load Balancer for this is
- Application Load Balancer
- Classic Load Balancer
- Network Load Balancer
#card 
Network Load Balancer
^1626789104579

23. Application Load Balancers handle all these protocols except
- HTTP
- HTTPS
- WebSocket
- TCP
#card 
TCP
^1626789104588

24. The application load balancer can route to different target groups based on all these except...
- Hostname
- Request Path
- Geography
- Source IP
#card 
Geography
^1626789104598

25. You are running at desired capacity of 3 and the maximum capacity of 3. You have alarms set at 60% CPU to scale out your application. Your application is now running at 80% capacity. What will happen?
- Nothing
- The desired capacity will go up to 4 and the maximum will stay at 3
- The desired capacity will go up to 4 and the maximum will stay at 4
#card 
Nothing. The capacity of your ASG cannot go over the maximum capacity you have allocated during scale out events
^1626789104608

26. I have an ASG and an ALB, and I setup my ASG to get health status of instances thanks to my ALB. One instance has just been reported unhealthy. What will happen?
- The ASG will keep the instance running and re-start the application
- The ASG will detach the EC2 instance from the group, and leave it running
- The ASG will terminate the EC2 Instance
#card 
The ASG will terminate the EC2 Instance. Because the ASG has been configured to leverage the ALB health checks, unhealthy instances will be terminated
^1626789104617

27. Your boss wants to scale your ASG based on the number of requests per minute your application makes to your database.
- You politely tell him it's impossible
- You create a CloudWatch custom metric and build an alarm on this to scale your ASG
- You enable detailed monitoring and use that to scale your ASG
#card 
You create a CloudWatch custom metric and build an alarm on this to scale your ASG. The metric "requests per minute" is not an AWS metric, hence it needs to be a custom metric
^1626789104627

28. Scaling an instance from an r4.large to an r4.4xlarge is called
- Horizontal Scalability
- Vertical Scalability
#card 
Vertical Scalability
^1626789104636

29. Running an application on an auto scaling group that scales the number of instances in and out is called
- Vertical Scalability
- Horizontal Scalability
#card 
Horizontal Scalability
^1626789104646

30. You would like to expose a fixed static IP to your end-users for compliance purposes, so they can write firewall rules that will be stable and approved by regulators. Which Load Balancer should you use?
- Application Load Balancer with Elastic IP attached to it
- Network Load Balancer
- Classic Load Balancer
#card 
Network Load Balancer. Network Load Balancers expose a public static IP, whereas an Application or Classic Load Balancer exposes a static DNS (URL)
^1626789104655

31. A web application hosted in EC2 is managed by an ASG. You are exposing this application through an Application Load Balancer. The ALB is deployed on the VPC with the following CIDR: 192.168.0.0/18. How do you configure the EC2 instance security group to ensure only the ALB can access the port 80?
- Open up the EC2 security group on port 80 to 0.0.0.0/0
- Open up the EC2 security group on port 80 to 192.168.0.0/18
- Open up the EC2 security on port 80 to the ALB's security group
- Load an SSL client certificate on the ALB
#card 
Open up the EC2 security on port 80 to the ALB's security group. This is the most secure way of ensuring only the ALB can access the EC2 instances. Referencing by security groups in rules is an extremely powerful rule and many questions at the exam rely on it. Make sure you fully master the concepts behind it!
^1626789104665

32. Your application load balancer is hosting 3 target groups with hostnames being users.example.com, api.external.example.com and checkout.example.com. You would like to expose HTTPS traffic for each of these hostnames. How do you configure your ALB SSL certificates to make this work?
- Use SNI
- Use a wildcard SSL certificate
- Use an HTTP to HTTPS redirect rule
- Use a security group SSL certificate
#card 
Use SNI. SNI (Server Name Indication) is a feature allowing you to expose multiple SSL certs if the client supports it.
^1626789104674

33. An ASG spawns across 2 availability zones. AZ-A has 3 EC2 instances and AZ-B has 4 EC2 instances. The ASG is about to go into a scale-in event. What will happen?
- The AZ-A will terminate an instance randomly
- The AZ-A will terminate the instance with the oldest launch configuration
- The AZ-B will terminate the instance with the oldest launch configuration
- The AZ-B will terminate an instance randomly
- The AZ-A will create an EC2 instance.
#card 
The AZ-B will terminate the instance with the oldest launch configuration. Make sure you remember the Default Termination Policy for ASG. It tries to balance across AZ first, and then delete based on the age of the launch configuration.
^1626789104683

34. The Application Load Balancers target groups can be all of these EXCEPT...
- EC2 Instances
- IP Addresses
- Lambda Functions
- Network Load Balancer
#card 
Network Load Balancer. 
^1626789104693

35. You are running an application in 3 AZ, with an Auto Scaling Group and a Classic Load Balancer. It seems that the traffic is not evenly distributed amongst all the backend EC2 instances, with some AZ being overloaded. Which feature should help distribute the traffic across all the available EC2 instances?
- Stickiness
- Cross Zone Load Balancing
- Target Group Routing Rules
- HTTPS Termination
#card 
Cross Zone Load Balancing
^1626789104702

36. Your Application Load Balancer (ALB) currently is routing to two target groups, each of them is routed to based on hostname rules. You have been tasked with enabling HTTPS traffic for each hostname and have loaded the certificates onto the ALB. Which ALB feature will help it choose the right certificate for your clients?
- TLS Termination
- Server Name Indication (SNI)
- SSL Security Policies
- Host Header
#card 
Server Name Indication (SNI)
^1626789104712

37. An application is deployed with an Application Load Balancer and an Auto Scaling Group. Currently, the scaling of the Auto Scaling Group is done manually and you would like to define a scaling policy that will ensure the average number of connections to your EC2 instances is averaging at around 1000. Which scaling policy should you use?
- Simple Scaling Policy
- Step Scaling Policy
- Target Tracking
- Scheduled Scaling
#card 
Target Tracking
^1626789104721

38. What is a service type of EC2
#card 
Infrastructure of Service
^1626789104731

39. Is EC2 bound to single Region or Availability Zone
#card 
Availability Zone
^1626789104740

40. What is the Load Balancer of EC2
#card 
Elastic Load Balancer
^1626789104750

41. What is the Auto Scaling of EC2
#card 
Auto Scaling Group
^1626789104759

42. How many ways are there to increase storage of EC2
#card 
Network-attached type: EBS, EFS
Hardware: EC2 Instance Store
^1626789104769

43. How many types are there of EC2
#card 
General Purpose
Compute optimized
Memory optimized
Storage optimized
Accelerated Computing (GPU)
^1626789104778

44. What is the cheapest purchasing option of EC2
#card 
EC2 Spot Instance
^1626789104787

45. What is the most expensive purchasing option of EC2
#card 
On-demand EC2
^1626789104797

46. How to filter any IP that has permission to access to EC2 Instance
#card 
EC2 Security Group help configure Firewall rules: Inbound and Outbound
^1626789104807

47. What is Elastic Network Interface of EC2
#card 
Represent Virtual Network Card in one VPC per Availability Zone
^1626789104817

48. What is Target Group of EC2
#card 
Is use to route requests to one or more registered targets. 
^1626789104827

49. You know that you need 24 CPUs for your production server. You also know that your compute capacity is going to remain fixed until next year, so you need to keep the production server up and running during that time. What pricing option would you go with?
A.) A spot instance  
B.) On-demand instance  
C.) Three-year reserved instance  
D.) One-year reserved instance
#card 
D
^1626789104837

50. You are planning to run a database on an EC2 instance. You know that the database is pretty heavy on I/O. The DBA told you that you would need a minimum of 8,000 IOPS. What is the storage option you should choose?
A.) EBS Volume with magnetic hard drive  
B.) Store all the data files in the ephemeral storage of the server  
C.) EBS volume with provisioned IOPS  
D.) EBS volume with general-purpose SSD
#card 
C
^1626789104847

51. You are running your application on a bunch of on-demand servers. On weekends you have to kick off a large batch job, and you are planning to add capacity. The batch job you are going to run over the weekend can be restarted if it fails. What is the best way to secure additional compute resources?
A.) Use a spot instance  
B.) Use an on-demand instance  
C.) Use an on-demand instance plus PIOPS storage  
D.) Use an on-demand instance plus a general-purpose EBS volume
#card 
A
^1626789104856

52. You have a compliance requirement that you should own the entire physical hardware and not other customer should run any other instances on the physical hardware. What options should you choose?  
A.) Put the hardware inside the VPC so that no customers can use it  
B.) Use a dedicated instance  
C.) Reserve the EC2 instance for 1 year  
D.) Reserve the EC2 instance for 10 years
#card 
B
^1626789104867

53. You have created an instance in EC2, and you want to connect to it. What should you do to log in to the system for the first time?  
A.) Use the username/password combination to login to the server  
B.) Use the key-pair combination (private and public keys)  
C.) Use your cell phone to get a text message for secure login  
D.) Log in via the root user
#card 
B
^1626789104877

54. What are the characteristics of AMI that are backed up by the instance store?  
- The data persist even after the instance reboot  
- The data is lost when the instance is shut down  
- The data persists when the instance is shut down  
- The data persists when the instance is terminated  
A.) 1, 2  
B.) 1, 4  
C.) 1, 3  
D.) 2
#card 
A
^1626789104887

55. How can you make a cluster of an EC2 instance?  
A.) By creating all the instances within a VPC  
B.) By creating all the instances in a public subnet  
C.) By creating all the instances in a private subnet  
D.) By creating a placement group
#card 
D
^1626789104897

56. You need to take a snapshot of the EBS volume. How long will the EBS remain unavailable?  
A.) The volume will be available immediately'  
B.) EBS magnetic drive will take more time than SSD volumes  
C.) It depends on the size of the EBS volume  
D.) It depends on the actual data stored in the EBS volume
#card 
A
^1626789104908

57. What are the different ways of making an EC2 server available to the public?  
A.) Create it inside a public subnet  
B.) Create it inside a private subnet and assign a NAT device  
C.) Attach an IPv6 address  
D.) Allocate that with a load balancer and expose the load balancer to the public
#card 
A
^1626789104918

58. The application workload changes constantly, and to meet that, you keep on changing the hardware type for the application server. Because of this, you constantly need to update the web server with the new IP address. How can you fix this problem?  
A.) Add a load balancer  
B.) Add an IPv6 IP address  
C.) Add an EIP to it  
D.)_Use a reserved EC2 instance
#card 
C
^1626789104929

59. Can you attach an EBS volume to more than one EC2 instance at the same time?  
A.) Yes  
B.) No  
C.) If that EC2 volume is part of an AMI  
D.) Depends on which region
#card 
B
^1626789104939

60. You can add multiple volumes to an EC2 instance and then create your own RAID 5/RAID 10/RAID 0 configurations using those volumes.  
A.) True  
B.) False
#card 
A
^1626789104949

61. You can use the AWS Console to add a role to an EC2 instance after that instance has been created and powered up.  
A.) True  
B.) False
#card 
A
^1626789104958

62. Can you delete a snapshot of an EBS volume that is used as the root device of a registered AMI?  
A.) Yes  
B.) No  
C.) Only via the AWS CLI  
D.) Only via the AWS API
#card 
B
^1626789104968

63. To retrieve instance metadata or user data you will need to use which IP address?  
A.) http://127.0.0.1  
B.) http://10.0.0.1  
C.) http://192.168.0.254  
D.) http://169.254.169.254
#card 
D
^1626789104978

64. You can change the permissions to a role, even if that role is already assigned to an existing EC2 instance, and these changes will take effect immediately.  
A.) True  
B.) False
#card 
A
^1626789104988

65. Is it possible to perform actions on an existing EBS snapshot?  
A.) No  
B.) Yes, through the AWS APIs, CLI, and AWS Console  
C.) EBS does not have snapshot functionality  
D.) It depends on the region
#card 
B
^1626789104998

66. In addition to choosing the correct EBS volume type for your specific task, what else can be done to increase the performance of your volume?  
- Ensure that your EC2 instances are types that can be optimised with EBS  
- Never use HDD volumes, always ensure that SSDs are used  
- Schedule snapshots of HDD based volumes for period of low usage  
- Stripe volumes together in a RAID 0 configuration  
A.) 2, 3, 4  
B.) 1, 2  
C.) 1, 3, 4  
D.) 3, 4
#card 
C
^1626789105008

67. Can you move reserved instance from one region to another?  
A.) Yes  
B.) No  
C.) It depends on which region  
D.) Only in the US regions
#card 
B
^1626789105017

68. Which AWS CLI command should I use to create a snapshot of an EBS volume?  
A.) aws ec2 create-snapshot  
B.) aws ec2 fresh-snapshot  
C.) aws ec2 new-snapshot  
D.) aws ec2 deploy-snapshot
#card 
A
^1626789105027

69. You need to know both the private and public IP addresses of your EC2 instance. You should ____________  
A.) Retrieve the instance metadata from http://169.254.169.254/latest/meta-data/  
B.) Run IPCONFIG (windows) or IFCONFIG(linux)  
C.) Use the following command: aws ec2 displayIP  
D.) Retrieve the instance user data from http://169.254.169.254/latest/meta-data/
#card 
A
^1626789105037

70. Which of the following provide the lowest cost EBS options?  
- Provisioned IOPS (io1)  
- General Purpose (gp2)  
- Throughput Optimized (st1)  
- Cold (sc1)  
A.) 1, 3  
B.) 2, 4  
C.) 3, 4  
D.) 1, 2
#card 
C
^1626789105047

71. In order to enabled encryption at rest using EC2 and EBS, you must ____________  
A.) Configure encryption using the appropriate OS file system  
B.) Mount the EBS volume into S3 and then encrypt the bucket using an S3 policy  
C.) Configure encryption when creating the EBS volume  
D.) Configure encryption using X.509 certificates
#card 
C
^1626789105057

72. To help you manage your EC2 instances, you can assign your own metadata in the form of ____________  
A.) Tags  
B.) Certificates  
C.) Notes  
D.) Wildcards
#card 
A
^1626789105067

73. You have developed a new web application in the US-West-2 Region that requires six Amazon Elastic Compute Cloud (EC2) instances to be running at all times. US-West-2 comprises three Availability Zones (us-west-2a, us-west-2b, and us-west-2c). You need 100 percent fault tolerance: should any single Availability Zone in us-west-2 become unavailable, the application must continue to run. How would you make sure 6 servers are ALWAYS available? NOTE: each answer has 2 possible deployment configurations. Select the answer that gives TWO satisfactory solutions to this scenario.  
A.)  
Solution 1: us-west-2a with six EC2 instances, us-west-2b with six EC2 instances, and us-west-2c with no EC2 instances.  
Solution 2: us-west-2a with three EC2 instances, us-west-2b with three EC2 instances, and us-west-2c with three EC2 instances.  
B.)  
Solution 1: us-west-2a with three EC2 instances, us-west-2b with three EC2 instances, and us-west-2c with three EC2 instances.  
Solution 2: us-west-2a with four EC2 instances, us-west-2b with two EC2 instances, and us-west-2c with two EC2 instances.  
C.)  
Solution 1: us-west-2a with two EC2 instances, us-west-2b with two EC2 instances, and us-west-2c with two EC2 instances.  
Solution 2: us-west-2a with six EC2 instances, us-west-2b with six EC2 instances, and us-west-2c with no EC2 instances.  
D.)  
Solution 1: us-west-2a with three EC2 instances, us-west-2b with three EC2 instances, and us-west-2c with no EC2 instances.  
Solution 2: us-west-2a with three EC2 instances, us-west-2b with three EC2 instances, and us-west-2c with three EC2 instances.
#card 
A
^1626789105076

74. When creating a new security group, all inbound traffic is allowed by default.  
A.) True  
B.) False
#card 
B
^1626789105086

75. Placement Groups can be created across 2 or more Availability Zones.  
A.) True  
B.) False
#card 
A
^1626789105096

76. What are the two underlying hypervisors for EC2?  
- EXS  
- Nitro  
- Hyper-V  
- Xen  
A.) 1, 4  
B.) 3, 4  
C.) 2, 3  
D.) 2, 4
#card 
D
^1626789105106

77. Amazon's EBS volumes are ____________  
A.) Not suitable for databases  
B.) Object based storage  
C.) Block based storage  
D.) Encrypted by deafult
#card 
C
^1626789105115

78. If an Amazon EBS volume is an additional partition (ie not the root volume), can I detach it without stopping the instance?  
A.) No, you will need to stop the instance  
B.) No, it is not possible to detach once it has been attached  
C.) Yes, although it may take some time  
D.) Yes, it will become detached immediately
#card
C
^1626789105125

79. The use of a cluster placement group is ideal ____________  
A.) Your fleet of EC2 instances requires low latency and high network throughput across multiple availability zones  
B.) Your fleet of EC2 instances requires high network throughput and low latency within a single availability zone  
C.) When you need to distribute content on a CDN network  
D.) When you need to deploy EC2 instances that require high disk IO
#card 
B
^1626789105135

80. Can a placement group be deployed across multiple AZs?  
A.) Yes  
B.) No  
C.) Only in us-east-1  
D.) Yes, but only using the AWS API
#card 
A
^1626789105144

81. Individual instances are provisioned in...  
A.) Regions  
B.) AZs  
C.) Edge Locations  
D.) Global
#card 
B
^1626789105154

82. You are consulting to a mid-sized company with a predominantly Mac & Linux desktop environment. In passing they comment that they have over 30TB of unstructured Word and spreadsheet documents of which 85% of these documents don't get accessed again after about 35 days. They wish that they could find a quick and easy solution to have tiered storage to store these documents in a more cost effective manner without impacting staff access. What options can you offer them?  
- Migrate documents to File Gateway presented as iSCSI and make use of lifecycles using IA storage  
- Migrate documents to File Gateway presented as NFS and make use of life-cycle using Infrequent Access storage  
- Migrate the document store to S3 storage and make use of life-cycle using Infrequent Access storage  
- Migrate documents to EFS storage and make use of life-cycle using Infrequent Access storage  
A.) 2, 4  
B.) 1, 3  
C.) 1, 4  
D.) 2, 3
#card 
A
^1626789105163

83. EBS Snapshots are backed up to S3 in what manner?  
A.) Incrementally  
B.) Exponentially  
C.) Decreasingly  
D.) EBS Snapshots are not stored in S3
#card 
A
^1626789105173

84. If you terminated an EC2 instance, would that EBS root volume persist?  
A.) Only if you specify (using the AWS Console or CLI) that it should do so  
B.) It depends on the region in which the EC2 instance is provisioned  
C.) Yes  
D.) No
#card 
A^1626789105183

85. You have provisioned an 8TB gp2 EBS volume and you are running out of IOPS. What is NOT a way to increase performance?
- Increase the EBS volume size
- Mount EBS volumes in RAID 0
- Change to an io1 volume type
#card 
Increase the EBS volume size. EBS IOPS peaks at 16,000 IOPS. or equivalent 5334 GB.
^1626789104483