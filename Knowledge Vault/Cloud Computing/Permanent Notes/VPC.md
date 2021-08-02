---
cards-deck: Obsidian::Cloud-Computing::Networking::VPC
tags: vpc, networking
---
## Metadata

-  Type: #permanent #networking
    Date written: #2021-07-01
    Source:  https://docs.aws.amazon.com/vpc
	https://quizlet.com/269100843/e1-c4-amazon-virtual-private-cloud-vpc-flash-cards/
	https://quizlet.com/412083376/aws-vpc-quiz-flash-cards/
    Status: #wip 
    Keywords:  #cloudcomputing #aws #vpc
	Related:
	
### Notes
- [[VPC CIDR]]
- Max [[VPC]] is 5 per [[Region]]
- For each [[VPC]]:
	- Min size: /28 = 16 IP Address
	- Max size: /16 = 65536 IP Address
- [[VPC Subnet]]
- [[VPC Internet Gateway]] helps [[VPC]] connect to the internet
- [[VPC Route Tables]] used to determine where network traffic from your subnet or gateway is directed
- [[NAT]]
- [[VPC NACL]]
- [[VPC Peering]] connect two [[VPC]] privately
- [[VPC Endpoints]]
- [[VPC Flow Logs]]
- [[VPC Bastion Hosts]]
- [[VPC Site to Site VPN]]
- [[VPC Endpoint Service (Private Link)]] ~ expose [[ELB]] to customer [[VPC]]
- [[VPC VPN CloudHub]] ~ similar to [[VPC Site to Site VPN]] but many customer VPNs connect to one VPC
- [[VPC Transit Gateway]]
- [[VPC Direct Connect]] ~ similar to [[VPC Site to Site VPN]] but private connection

### Questions

1. What does this CIDR correspond to? '10.0.4.0/28'
- 10.0.4.0 to 10.0.4.15
- 10.0.4.0 to 10.0.32.0
- 10.0.4.0 to 10.0.4.28
- 10.0.0.0 to 10.0.16.0
#card 
10.0.4.0 to 10.0.4.15
^1626790931441

2. You have a corporate network of size '10.0.0.0/8'  and a satellite office of size '192.168.0.0/16'. Which CIDR is acceptable for your AWS VPC if you plan on connecting your networks later on?
- 172.16.0.0/12
- 172.16.0.0/16
- 10.0.16.0/16
- 192.168.4.0/18
#card 
172.16.0.0/16. CIDR not should overlap, and the max CIDR size in AWS is /16
^1626790931454

3. You plan on creating a subnet and want it to have at least capacity for 28 EC2 instances. What's the minimum size you need to have for your subnet?
- /28
- /27
- /26
- /25
#card 
/26. perfect size (64 IP)
^1626790910782

4. You have set up an internet gateway in your VPC, but your EC2 instances still don't have access to the internet. What is NOT a possible issue?
- Route Tables are missing entries
- The security group does not allow network in
- The NACL does not allow network traffic out
#card 
The security group does not allow network in. security groups are stateful and if traffic can go out, then it can go back in
^1626790910793

5. You would like to provide internet access to your instances in private subnets with IPv4, while making sure this solution requires the least amount of administration and scales seamlessly. What should you use?
- NAT Instances with Source / Destination Check flag off
- NAT Gateway
- Egress Only Internet Gateway
#card 
NAT Gateway
^1626790910803

6. VPC Peering has been enabled between VPC A and VPC B, and the route tables have been updated for VPC A. Still, your instances cannot communicate. What is the likely issue?
- Check the NACL
- Check the route tables in VPC B
- Check the instance security groups
- Check if DNS Resolution is enabled
#card 
Check the route tables in VPC B. Route tables must be updated in both VPC that are peered
^1626790910814

7. You have set-up a direct connection between your Corporate Data Center and your VPC A. You need to access VPC B in another region from your Corporate Data Center as well. What should you do?
- Enable VPC Peering
- Use a Direct Connect Gateway
- Use a Direct Connect
- Setup a NAT gateway
#card 
This is the main use case of Direct Connect Gateways
^1626790910825

8. Which are the only two services that have a **Gateway Endpoint** instead of an Interface Endpoint as a VPC endpoint?
- Amazon S3 & Amazon SQS
- Amazon S3 & DynamoDB
- Amazon SQS & DynamoDB
#card 
Amazon S3 & DynamoDB. these two services have a Gateway endpoint (remember it), all the other ones have an interface endpoint (powered by Private Link - means a private IP)
^1626790910836

9. Your company has created a REST API that it will sell to hundreds of customers as a SaaS. Your customers are on AWS and are using their own VPC. You would like to allow your customers to access your SaaS without going through the public internet while ensuring your infrastructure is not left exposed to network attacks. What do you recommend?
- Create a VPC endpoint
- Create a VPC Peering connection
- Create a PrivateLink
- Create a Classic Link
#card 
Create a PrivateLink
^1626790910846

10. Your company has several on-premise sites across the USA. These sites are currently linked using a private connection, but your private connection provider has been recently quite unstable, making your IT architecture partially offline. You would like to create a backup connection that will use the public internet to link your on-premise sites, that you can failover in case of issues with your provider. What do you recommend?
- Site-to-Site VPN
- Direct Connect
- VPN CloudHub
- PrivateLink
#card 
VPN CloudHub
^1626790910857

11. What is the minimum size subnet that you can have in an Amazon VPC?  
A. /24  
B. /26  
C. /28  
D. /30
#card 
C. /28  
^1626790910867

12. You are a solutions architect working for a large travel company that is migrating its existing server estate to AWS. You have recommended that they use a custom Amazon VPC, and they have agreed to proceed. They will need a public subnet for their web servers and a private subnet in which to place their databases. They also require that the web servers and database servers be highly available and that there be a minimum of two web servers and two database servers each.  
How many subnets should you have to maintain high availability?    
A. 2  
B. 3  
C. 4  
D. 1
#card 
C
^1626790910878

13. Which of the following is an optional security control that can be applied at the subnet layer of a VPC?  
A. Network ACL  
B. Security Group  
C. Firewall  
D. Web application firewall
#card 
A
^1626790910888

14. What is the maximum size IP address range that you can have in an Amazon VPC?  
A. /16  
B. /24  
C. /28  
D. /30
#card 
A
^1626790910900

15. You create a new subnet and then add a route to your route table that routes traffic out from that subnet to the Internet using an IGW.  
What type of subnet have you created?   
A. An internal subnet  
B. A private subnet  
C. An external subnet  
D. A public subnet
#card 
A
^1626790910911

16. What happens when you create a new Amazon VPC?  
A. A main route table is created by default.  
B. Three subnets are created by default—one for each Availability Zone.  
C. Three subnets are created by default in one Availability Zone.  
D. An IGW is created by default.
#card 
A main route table is created by default.  
^1626790910921

17. You create a new VPC in US-East-1 and provision three subnets inside this Amazon VPC.  
Which of the following statements is true?  
A. By default, these subnets will not be able to communicate with each other; you will need to create routes.  
B. All subnets are public by default.  
C. All subnets will be able to communicate with each other by default.  
D. Each subnet will have identical CIDR blocks.
#card 
C
^1626790910932

18. How many IGWs can you attach to an Amazon VPC at any one time?  
A. 1  
B. 2  
C. 3  
D. 4
#card 
A
^1626790910944

19. What aspect of an Amazon VPC is stateful?  
A. Network ACLs  
B. Security groups  
C. Amazon DynamoDB  
D. Amazon S3
#card 
B
^1626790910955

20. You have created a custom Amazon VPC with both private and public subnets. You have created a NAT instance and deployed this instance to a public subnet. You have attached an EIP address and added your NAT to the route table. Unfortunately, instances in your private subnet still cannot access the Internet.  
What may be the cause of this?  
  A. Your NAT is in a public subnet, but it needs to be in a private subnet.  
B. Your NAT should be behind an Elastic Load Balancer.  
C. You should disable source/destination checks on the NAT.  
D. Your NAT has been deployed on a Windows instance, but your other instances are Linux. You should redeploy the NAT onto a Linux instance.
#card 
C
^1626790910966

21. Which of the following will occur when an Amazon Elastic Block Store (Amazon EBS)- backed Amazon EC2 instance in an Amazon VPC with an associated EIP is stopped and started? (Choose 2 answers)  
A. The EIP will be dissociated from the instance.  
B. All data on instance-store devices will be lost.  
C. All data on Amazon EBS devices will be lost.  
D. The ENI is detached.  
E. The underlying host for the instance is changed.
#card 
B, E
^1626790910976

22. How many VPC Peering connections are required for four VPCs located within the same AWS region to be able to send traffic to each of the others?  
A. 3  
B. 4  
C. 5  
D. 6
#card 
D
^1626790910987

23. Which of the following AWS resources would you use in order for an EC2-VPC instance to resolve DNS names outside of AWS?  
A. A VPC peering connection  
B. A DHCP option set  
C. A routing rule  
D. An IGW
#card 
B
^1626790910998

24. Which of the following is the Amazon side of an Amazon VPN connection? 
A. An EIP  
B. A CGW  
C. An IGW  
D. A VPG
#card 
D
^1626790911009

25. What is the default limit for the number of Amazon VPCs that a customer may have in a region?    
A. 5  
B. 6  
C. 7  
D. There is no default maximum number of VPCs within a region.
#card 
A
^1626790911020

26. You are responsible for your company's AWS resources, and you notice a significant amount of traffic from an IP address in a foreign country in which your company does not have customers. Further investigation of the traffic indicates the source of the traffic is scanning for open ports on your EC2-VPC instances.  
Which one of the following resources can deny the traffic from reaching the instances?  
A. Security group  
B. Network ACL  
C. NAT instance  
D. An Amazon VPC endpoint
#card 
B
^1626790911032

27. Which of the following is the security protocol supported by Amazon VPC
A. SSH  
B. Advanced Encryption Standard (AES)  
C. Point-to-Point Tunneling Protocol (PPTP)  
D. IPsec
#card 
D
^1626790911043

28. Which of the following Amazon VPC resources would you use in order for EC2-VPC instances to send traffic directly to Amazon S3?  
A. Amazon S3 gateway  
B. IGW  
C. CGW  
D. VPC endpoint
#card 
D
^1626790911054

29. What properties of an Amazon VPC must be specified at the time of creation? (Choose 2 answers)  
A. The CIDR block representing the IP address range  
B. One or more subnets for the Amazon VPC  
C. The region for the Amazon VPC  
D. Amazon VPC Peering relationships
#card 
A, C
^1626790911065

30. Which Amazon VPC feature allows you to create a dual-homed instance?  
A. EIP address  
B. ENI  
C. Security groups  
D. CGW
#card 
B
^1626790911076

31. You have created a VPC with two subnets. The web servers are running in a public subnet and the database server is running in a private subnet. You need to download an operating system patch to update the database server. How are you going to download the patch?  
A.) By attaching an Internet Gateway to the private subnet temporarily  
B.) By using a NAT gateway  
C.) By using peering to another VPC  
D.) By changing the security group of the database server and allowing Internet access
#card 
B
^1626790911088

32. What is the maximum size of the CIDR block you can have for a VPC?  
A.) 16  
B.) 32  
C.) 28  
D.) 10
#card 
A
^1626790911099

33. How many IP addresses are reserved by AWS for internal purposes in a CIDR block that you can't use?  
A.) 2  
B.) 3  
C.) 4  
D.) 5
#card 
D
^1626790911111

34. You have a web server and an app server running. You often reboot your app server for maintenance activities. Every time you reboot your app server, you need to update the connect string for the web server since the IP address of the app server changes. How do you fix this issue?  
A.) Allocate and IPv6 IP address to the app server  
B.) Allocate an Elastic Network Interface to the app server  
C.) Allocate an elastic IP address to the app server  
D.) Run a script to change the connection
#card 
C
^1626790911123

35. To connect your corporate data center to AWS, you need at least which of the following components?  
1. Internet gateway  
2. Virtual private gateway  
3. NAT gateway  
4. Customer gateway  
A.) 1, 3  
B.) 1, 2  
C.) 3, 4  
D.) 2, 4
#card 
D
^1626790911133

36. You want to explicitly "deny" certain traffic to the instance running in your VPC. How do you achieve this?  
A.) Using a security group  
B.) Adding an entry in the route table  
C.) By putting the instance in a private subnet  
D.) Using a Network ACL
#card 
D
^1626790911144

37. You have created a web server in the public subnet, and now anyone can access the web server from the internet. You want to change this behavior and just have the load balancer talk with the web server and no one else. How do you achieve this?  
A.) By removing the internet gateway  
B.) By adding the load balancer in the route table  
C.) By allowing the load balancer access in the NACL of the public subnet  
D.) By modifying the security group of the instance and just having the load balancer talk with the web server
#card 
D
^1626790911155

38. How can your VPC talk with DynamoDB directly?  
A.) By using a direct connection  
B.) By using a VPN connection  
C.) By using a VPN endpoint  
D.) By using an instance in the public subnet
#card 
C
^1626790911166

39. The local route table in the VPC allows which of the following?  
A.) All the instances running in different subnets within a VPC can communicate to each other  
B.) Only traffic to the internet can be routed  
C.) Multiple VPCs can talk with each other  
D.) An instance can use the local route and talk to the Internet
#card 
A
^1626790911176

40. What happens to the EIP address when you stop and start an instance?  
A.) The EIP is released to the pool and you need to re-attach it  
B.) The EIP is released temporarily during the stop and start  
C.) The EIP remains associated with the instance  
D.) The EIP is available for any other customer
#card 
C
^1626790911187

41. An application load balancer must be deployed into at least two subnets.  
A.) True  
B.) False
#card 
A
^1626790911198

42. You can accelerate your application by adding a second Internet gateway to your VPC.  
A.) True  
B.) False
#card 
B
^1626790911208

43. At which of the following levels can VPC Flow Logs be created?  
1. Security group level  
2. VPC level  
3. Subnet level  
4. Network ACL level  
5. Network interface level  
6. Instance level  
A.) 1, 4, 6  
B.) 2, 4, 5  
C.) 1, 2, 4  
D.) 2, 3, 5
#card 
D
^1626790911219

44. To save administration headaches, Amazon recommend that you leave all security groups in web facing subnets open on port 22 to 0.0.0.0/0 CIDR, that way you can connect where ever you are in the world.  
A.) True  
B.) False
#card 
B
^1626790911229

45. Security groups act like a firewall at the instance level, whereas ____________ are an additional layer of security that act at the subnet level. 
A.) DB security groups  
B.) Network ACL  
C.) Route table  
D.) VPC security group
#card 
B
^1626790911240

46. How many Internet gateways can be attached to your custom VPC?  
A.) 1  
B.) 2  
C.) 3  
D.) 1 per availability zone
#card 
A
^1626790911250

47. What is the purpose of an Egress-only Internet gateway?  
1. Allows VPC based IPv6 traffic to communicate to the Internet  
2. Prevents IPv6 traffic accessing the Internet by utilizing security groups  
3. Prevents IPv6 based Internet resources initiating a connection into a VPC  
4. Allows instance communication over IPv4 or IPv6 to access the internet  
A.) 1, 3  
B.) 2, 4  
C.) 1, 4  
D.) 2, 3
#card 
A
^1626790911261

48. When you create a new security group all outbound traffic is allowed by default.  
A.) True  
B.) False
#card 
A
^1626790911272

49. By default, instances in new subnets in a custom VPC can communicate with each other across AZs.  
A.) True  
B.) False
#card 
A
^1626790911282

50. Which statements are true for security groups?  
1. Security groups evaluate all rules before deciding whether to allow traffic  
2. Security groups support both "allow" and "deny" rules  
3. Security groups operate at the subnet level  
4. Security groups support only "allow" rules  
5. Security groups process rules in numbered order when deciding to allow traffic  
6. Security groups operate at the instance level  
A.) 2, 5, 6  
B.) 1, 4, 6  
C.) 1, 2, 3  
D.) 3, 4, 6
#card 
B
^1626790911293

51. Which statement is true?  
A.) Security groups are stateless and Network ACLs are stateful  
B.) Security groups are stateful and Network ACLs are stateless  
C.) Both security groups and Network ACLs are stateful  
D.) Both security groups are Network ACLs are stateless
#card 
B
^1626790911303

52. In a default VPC, all EC2 instances are assigned 2 IP addresses at launch. What are they?  
A.) An elastic and public IP address  
B.) A public and private IP address  
C.) An IPv6 and an elastic IP address  
D.) A public and a secret IP address
#card 
B
^1626790911314

53. You are permitted to conduct your own vulnerability scans on your own VPC without alerting AWS first?  
A.) True  
B.) False
#card 
A
^1626790911324

54. A VPN connection consists of which of the following components?  
1. Cross connect  
2. Customer gateway  
3. Virtual private gateway  
4. Direct connect gateway  
A.) 2, 3  
B.) 1, 4  
C.) 1, 3  
D.) 2, 4
#card 
A
^1626790911335

55. Having just created a new VPC and launching an instance into its public subnet, you realize that you have forgotten to assign a public IP to the instance during creation. What is the simplest way to make your instance reachable from the outside world?  
A.) Create an Elastic IP address and associate it with your instance  
B.) Associate the private IP of your instance to the public IP of the Internet gateway  
C.) Nothing - by default all instances deployed into any public subnet will automatically receive a public IP  
D.) Create an Elastic IP and new network interface. Associated the Elastic IP to the new network interface and the new network interface to your instance
#card 
A
^1626790911346

56. Select the incorrect statement.  
A.) In Amazon VPC, an instance retains its private IP  
B.) You may only have 1 Internet gateway per VPC  
C.) In Amazon VPC, an instance does not retain its private IP  
D.) It is possible to have private subnets in a VPC
#card 
C
^1626790911357

57. A subnet can span multiple AZ  
A.) True  
B.) False
#card 
B
^1626790911367

58. When you create a custom VPC, which of the following are created automatically?  
1. NAT Gateway  
2. Route table  
3. Access Control List  
4. Security Group  
5. Subnets  
6. Internet gateway  
A.) 2, 3, 4  
B.) 1, 3, 4  
C.) 1, 5, 6  
D.) 1, 3, 5
#card 
A
^1626790911378

59. By default, how many VPCs am I allowed in each AWS region?  
A.) 1  
B.) 2  
C.) 5  
D.) 6
#card 
C
^1626790911388

60. Which of the following allows you to SSH or RDP into an EC2 instance located in a private subnet?  
A.) NAT instance  
B.) NAT gateway  
C.) Bastion host  
D.) Internet gateway
#card 
C
^1626790911399

61. You have five VPCs in a 'hub and spoke' configuration, with VPC 'A' in the center and individually paired with VPCs 'B', 'C', 'D', and 'E', which make up the 'spokes'. There are no other VPC connections. Which of the following VPCs can VPC 'B' communicate with directly?  
A.) VPCs 'C', 'D', and 'E'  
B.) VPC 'A'  
C.) VPCs 'A' and 'E'  
D.) VPCs 'A' and 'C'
#card 
B
^1626790911410

62. When peering VPCs, you may peer your VPC only with another VPC in your same AWS account.  
A.) True  
B.) False
#card 
B
^1626790911421

63. Which of the following is a chief advantage of using VPC endpoints to connect your VPC to services such as S3?  
A.) VPC endpoints require public IP addresses, offering rapid connectivity from the public internet  
B.) Traffic between your VPC and the other service does not leave the Amazon network  
C.) VPC endpoints are dedicated hardware devices that cannot be accessed without the correct IAM credentials  
D.) VPC endpoints offer a faster path through the public internet than you can realize with a NAT instance
#card 
B^1626790911431
