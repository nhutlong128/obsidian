---
cards-deck: Obsidian::Cloud-Computing::Security::IAM
tags: iam, security
---
### Metadata

-  Type: #permanent #security
    Date written: #2021-06-22
    Source:  https://docs.aws.amazon.com/iam/index.html
	https://quizlet.com/411153047/aws-identity-and-access-management-quiz-flash-cards/
	https://quizlet.com/355252044/identity-and-access-management-and-security-flash-cards/
    Status: #wip 
    Keywords:  #cloudcomputing #aws #iam
	Related:
	
### Notes
- [[IAM User]] = One physical User
- [[IAM Group]]
- [[IAM Policy]]
- [[IAM Role]]
- [[IAM MFA]]
- [[IAM Security Tools]]
- [[IAM Identity Providers]] when dont need create new AWS users or when users have been managed outside AWS
- [[IAM Conditions]] - more restrict
- [[IAM Resource Based Policies]]
- [[IAM Permission Boundaries]]
### Questions

1. What is a proper definition of IAM Roles?
- An IAM entity that defines a set of permission for making AWS service requests, that will be used by AWS Services
- IAM Users in multiple Groups
- A password policy
- Permissions assgined to Users to perform actions
#card
An IAM entity that defines a set of permission for making AWS service requests, that will be used by AWS Services
^1626790755066

2. Which of the following is an IAM Security Tool?
- IAM Credentials Report
- IAM Root Account Manager
- IAM Service Report
- IAM Security Advisor
#card 
IAM Credentials Report
^1626790755077

3. Which answer is INCORRECT regarding IAM Users?
- IAM Users can belong to multi groups
- IAM Users dont have to belong to a group
- IAM Users can have policies assigned to them
- IAM Users access AWS with the root credentials
#card 
IAM Users access AWS with the root credentials
^1626790755087

4. Which of the following is an IAM best practice?
- Dont use the root user account
- Create several users for a physical person
- Share credentials so a colleague can perform a task for you
#card 
Dont use the root user account
^1626790755098

5. What are IAM Policies?
- AWS Services performable actions
- JSON documents to define Users, Groups, Roles' permissions
- Rules to set up a password for IAM Users
#card 
JSON documents to define ...
^1626790755110

6. Which principle should you apply regarding IAM Permissions?
- Grant most privilege
- Grant least privilege
- Grant permission if your employee asks you to
- Restrict root account permissions
#card 
Grant least privilege
^1626790755120

7. We need to gain access to a Role in another AWS account. How is it done?
- We should ask for them to create user for us
- We should ask for them to send us access key
- We should use the STS service to gain temporary credentials
#card 
We should use the STS service...
^1626790755131

8. You have a mobile application and would like to give your users access to their own personal space in Amazon S3. How do you achieve that?
- Generate IAM user credentials for each of your application's users
- Use Cognito Identity Federation
- Use SAML Identity Federation
- Use a Bucket Policy to make your bucket public
#card 
Use Cognito Identity Federation.
Cognito is made to federate mobile user accounts and provide them with their own IAM policy
^1626790755141

9. You have strong regulatory requirements to only allow fully internally audited AWS Services in production. You still want to allow your teams to experiment in development environments while services are being audited. How can you best set this up?
- Provide the Dev team with a completely independent AWS account
- Create an AWS Organization and create two Prod and Dev OU. Apply a SCP on Prod
- Apply a Global IAM Policy on your production account
- Create an AWS Config Rule
#card 
Create an AWS Organization and create two Prod and Dev OU...
^1626790755152

10. You have an on-premise active directory setup and would like to provide access for your on-premise users to the multiple accounts you have in AWS. The solution should scale to adding accounts in the future. What do you recommend?
- Setup the SAML 2.0 integration between each AWS account and your on-premise AD
- Setup AWS Single Sign-On
- Setup Web Identity Federation through Cognito
#card 
Setup AWS Single Sign-On. Because setup the SAML 2.0 integration between each AWS account and your on-premise AD means that you have to manually create each access for each relationship between AWS account and your on-premise AD => wont scale to adding accounts in the future
^1626790755163

11. Which AWS Directory Service allows you to proxy requests to your on-premise active directory?
- AD on EC2
- Managed Microsoft AD
- AD Connector
- Simple AD
#card 
AD Connector
^1626790755173

12. My EC2 Instance does not have the permissions to perform an API call PutObject on S3. What should I do?
- I should run 'aws configure' and insert my personal credentials, because I have access to PutObject on S3
- I should ask an administrator to attach a Policy to the IAM Role on my EC2 Instance that authorises it to do the API call
- I should export the environment variables with my credentials on the EC2 Instance
- I should use the EC2 Metadata API call
#card 
I should ask an administrator to attach a Policy to the IAM Role on my EC2 Instance that authorises it to do the API call. IAM roles are the right way to provide credentials and permissions to an EC2 instance
^1626790790161

13. I have an on-premise personal server that I'd like to use to perform AWS API calls
- I should run 'aws configure' and put my credentials there. Invalidate them when I'm done
- I should attach an EC2 IAM Role to my personal server
#card 
I should run 'aws configure' and put my credentials there. Invalidate them when I'm done. Even better would be to create a user specifically for that one on-premise server
^1626790790173

14. I need my colleagues help to debug my code. When he runs the application on his machine, it's working fine, whereas I get API authorisation exceptions. What should I do?
- Send him my AWS access key and secret key so he can replicate the issue on his machine
- Ask him to send me his credentials so I can start working
- Compare his IAM policy and my IAM policy in the policy simulator to understand the differences
- Ask him to create an EC2 server and puts his credentials there so I can run the application from the EC2 Instance
#card 
Compare his IAM policy and my IAM policy in the policy simulator to understand the differences
^1626790755184

15. To get the instance id of my EC2 machine from the EC2 machine, the best thing is to...
- Create an IAM role and attach it to my EC2 instance so I can perform a "describe" API call
- Query the user data at http://169.254.169.254/latest/user-data
- Query the meta data at http://169.254.169.254/latest/meta-data
- Query the meta data at http://254.169.254.169/latest/meta-data
#card 
Query the meta data at http://169.254.169.254/latest/meta-data. 169.254.169.254 is the Private IP.
^1626790755195

16. Can you add an IAM role to an IAM group?  
A.) Yes  
B.) No  
C.) Yes, if there ten members in the group  
D.) Yes, if the group allows adding a role
#card 
B
^1626790755205

17. An IAM policy contains which of the following?  
A.) Username, Service name  
B.) Action, AZ  
C.) Action, Service name  
D.) Username, AZ
#card 
C
^1626790755215

18. What happens if you delete an IAM role that is associated with a running EC2 instance?  
A.) Any application running on the instance that is using the role will be denied access immediately  
B.) The application continues to use that role until the EC2 server is shut down 
C.) The application will have the access until the session is alive  
D.) The application will continue to have access
#card 
A
^1626790755225

19. Which is based on temporary security tokens?  
A.) Federation, Using AWS STS  
B.) EC2 Roles, Federation  
C.) Username/Password, Using AWS STS  
D.) EC2 Roles, Username/Password
#card 
A
^1626790755236

20. You want EC2 instances to give access without any username or password to S3 buckets. What is the easiest way of doing this?  
A.) By using a VPC S3 endpoint  
B.) By using a signed URL  
C.) By using roles  
D.) By sharing the keys between S3 and EC2
#card 
By using roles  
^1626790755247

21. An IAM policy takes which form?  
A.) Python script  
B.) Written in C language  
C.) JSON code  
D.) XML code
#card 
JSON code  
^1626790755258

22. If an administrator who has root access leaves the company, what should you do to protect your account?  
A.) Add MFA and delete the IAM accounts  
B.) Add MFA, change passwords, and rotate keys  
C.) Delete IAM accounts, rotate keys  
D.) Delete all EC2 instances created by the admin and rotate keys
#card 
B
^1626790755268

23. Using the shared security model, the customer is responsible for which of the following?  
A.) Patching the operating system and hypervisor  
B.) Maintaining the physical security of the data center  
C.) Fixing defective hardware  
D.) Patching the operating system and securing the data in the EC2 instaces
#card 
Patching the operating system and securing the data in the EC2 instaces
^1626790755279

24. In Amazon RDS, who is responsible for patching the database?  
A.) Customer  
B.) Amazon  
C.) In RDS, the database does not need to be patched  
D.) RDS does not fall under the shared security model
#card 
B
^1626790755289

25. CloudFront Origin Access Identity, CloudFront Signed URLs, CloudFront Signed Cookies, Public S3 buckets  
Which of the following options allows users to have secure access to private files located in S3?  
A.) 1, 4  
B.) 1, 2  
C.) 2, 3  
D.) 1, 2, 3
#card 
D
^1626790755299

26. Which statement best describes IAM?  
A.) IAM allows you to manage users' passwords only. AWS staff must create new users for your organization. This is done by raising a ticket  
B.) IAM allows you to manage users, groups, roles, and their corresponding level of access to the AWS platform  
C.) IAM allows you to manage permissions for your AWS resources only  
D.) IAM stands for Improvised Application Management, and it allows you to deploy and manage applications in the AWS cloud
#card 
IAM allows you to manage users, groups, roles, and their corresponding level of access to the AWS platform  
^1626790755310

27. What is the default level of access a newly created IAM user is granted?  
A.) Read only access to all AWS services  
B.) No access to any AWS services  
C.) Power user access to all AWS services  
D.) Administrator access to all AWS services
#card 
B
^1626790755322

28. Using SAML (Security Assertion Markup Language 2.0) you can give your federated users single sign-on (SSO) access to the AWS Management Console.  
A. True  
B. False
#card 
A
^1626790755333

29. What level of access does the "root" account have?  
A.) Read Only access  
B.) Power User access  
C.) Administrator Access  
D.) No Access
#card 
C
^1626790755344

30. What is an additional way to secure the AWS accounts of both the root account and new users alike?  
A.) Store the access ID and secret access key of all users in a publicly accessible plain text document on S3 of which only you and members of your organization know the address to  
B.) Implement MFA for all accounts  
C.) Configure the AWS Console so that you can only log in to it from your internal network IP address range  
D.) Configure the AWS Console so that you can only log in to it from a specific IP address range
#card 
B
^1626790755354

31. Power user access allows ____________  
A.) Full access to all AWS services and resources  
B.) Access to all AWS services except the management of groups and users within IAM  
C.) Users to inspect the source code of the AWS platform  
D.) Read Only access to all AWS services
#card 
B
^1626790755365

32. You have created a new AWS account for your company, and you have also configured MFA on the root account. You are about to create your new users. What strategy should you consider in order to ensure that there is good security on this account?  
A.) Give all users the same password so that if they forget their password they can just ask their co-workers  
B.) Restrict login to the corporate network only  
C.) Enact a strong password policy: user passwords must be changed every 45 days, with each password containing a combination of capital letters, lower case letters, numbers, and special symbols  
D.) Require users to only be able to log in using biometric authentication
#card 
C
^1626790755375

33. You have a client who is considering moving to AWS services and do not yet have an account. What is the first thing the company should do to set up an AWS account?  
A.) Set up an account using Cloud Search.  
B.) Set up an account using their company email address.  
C.) Set up an account via SQS.  
D.) Set up an account via SNS.
#card 
B
^1626790755386

34. Which of the following is not a component of IAM?  
A.) Users  
B.) Groups  
C.) Roles  
D.) Organizations Units
#card 
Organizations Units
^1626790755397

35. A ____________ is a document that provides a formal statement of one or more permissions.  
A.) Role  
B.) Policy  
C.) User  
D.) Group
#card 
B
^1626790755408

36. You are a solutions architect working for a large engineering company who are moving from legacy infrastructure to AWS. You have configured the company's first AWS account and you have set up IAM. Your company is based in Andorra, but there will be a small subsidiary operating out of South Korea, so that office will need its own AWS environment. Which of the following statements is true?  
A.) You will need to configure your policy documents regionally, however, your users are global  
B.) You will need to configure users and policy documents for each region respectively  
C.) You will need to configure your users regionally, however, your policy documents are global  
D.) You will need to configure user and policy documents only once as these are applied globally
#card 
D
^1626790755419

37. Which of the following is not a feature of IAM?  
A.) IAM offers fine-grained access control to AWS resources  
B.) IAM integrates with existing active directory account single sign-on  
C.) IAM offers centralized control of your AWS account  
D.) IAM allows you to setup biometric authentication, so that no passwords are required
#card 
D
^1626790755429

38. A new employee has just started work, and it is your job to giver her administrator access to the AWS console. You have given her a user name, an access key ID, a secret access key, and you have generated a password for her. She is now able to log in to the AWS console, but she is unable to interact with any AWS services. What should you do next?  
A.) Grant her administrator access by adding her to the Administrators group  
B.) Require MFA for her user account  
C.) Ensure she is logging into the AWS console from the corporate network and not the normal internet  
D.) Tell her to log out and try logging back in
#card 
A
^1626790755439

39. You are a security administrator working for a hotel chain. You have a new member of staff who has started as a systems administrator, and she will need full access to the AWS console. You have created the user account and generated the access key id and the secret access key. You have moved this user into the group where the other administrators are, and you have provided the new user with their secret access key and their access key id. However, when she tries to log in to the AWS console, she cannot. Why might that be?  
  
A.) Your user is trying to log in from the AWS console from outside the corporate network. This is not possible  
B.) You cannot log into the AWS console using access key ID/secret access key pair. Instead, you must generate a password for the user and supply the user with the generated password and the company's unique AWS console login URL  
C.) You have not applied the "log into console" policy document to the user, you must apply this first so that they can login  
D.) You have not yet activated MFA for the user, so by default they will not be able to log in
#card 
B
^1626790755450

40. When you create a new user, that user ____________  
A.) Will be able to log in to the console anywhere in the world, using their access key ID and secret access key  
B.) Will be able to log in to the console only after MFA is enabled on their account  
C.) Will only be able to log in to the console in the region in which the user account was created  
D.) Will be able to interact with AWS using their access key ID and secret access key using the API, CLI, or the AWS SDKs
#card 
D
^1626790755460

41.   To save administration headaches, Amazon recommends that you leave all security groups in web facing subnets open on port 22 to 0.0.0.0/0 CIDR. That way, you can connect wherever you are in the world.  
A. True  
B. False
#card 
B
^1626790755471

42. You are a developer at a fast growing start up. Until now, you have used the root account to log in to the AWS console. However, as you have taken on more staff, you will now need to stop sharing the root account to prevent accidental damage to your AWS infrastructure. What should you do so that everyone can access the AWS resources they need to do their jobs? (Choose 2)  
A. Create individual user accounts with minimum necessary rights and tell the staff to log in to the console using the credentials provided.  
B. Create an additional AWS root account for each new user.  
C. Give your users the root account credentials so that they can also sign in.  
D. Create a customized sign in link such as "yourcompany.signin.aws.amazon.com/console" for your new users to use to sign in with.
#card 
A, D
^1626790755481

43. Every user you create in the IAM systems starts with ________.  
A. Partial Permissions  
B. No Permissions  
C. Full Permissions
#card 
B
^1626790755491

44. Which of the following methods will allow an application using an AWS SDK to be authenticated as a principal to access AWS Cloud services? (Choose 2 answers)  
A. Create an IAM user and store the user name and password for the user in the application's configuration.  
B. Create an IAM user and store both parts of the access key for the user in the application's configuration.  
C. Run the application on an Amazon EC2 instance with an assigned IAM role.  
D. Make all the API calls over an SSL connection.
#card 
B, C
^1626790755502

45. Which of the following are found in an IAM policy? (Choose 2 answers)  
A. Service Name  
B. Region  
C. Action  
D. Password
#card 
A, C
^1626790755513

46. Which of the following actions can be authorized by IAM? (Choose 2 answers)  
A. Installing ASP.NET on a Windows Server  
B. Launching an Amazon Linux EC2 instance  
C. Querying an Oracle database  
D. Adding a message to an Amazon Simple Queue Service (Amazon SQS) queue
#card 
B, D
^1626790755523

47. Which of the following are IAM security features? (Choose 2 answers)  
A. Password policies  
B. Amazon DynamoDB global secondary indexes  
C. MFA  
D. Consolidated Billing
#card 
A, C. Amazon DynamoDB global secondary indexes are a performance feature of Amazon DynamoDB; Consolidated Billing is an accounting feature allowing all bills to roll up under a single account. While both are very valuable features, neither is a security feature.
^1626790755534

48. Which of the following are benefits of using Amazon EC2 roles? (Choose 2 answers)  
A. No policies are required.  
B. Credentials do not need to be stored on the Amazon EC2 instance.  
C. Key rotation is not necessary.  
D. Integration with Active Directory is automatic.
#card 
B, C. Amazon EC2 roles must still be assigned a policy. Integration with Active Directory involves integration between Active Directory and IAM via SAML.
^1626790755544

49. Which of the following are based on temporary security tokens? (Choose 2 answers)  
A. Amazon EC2 roles  
B. MFA  
C. Root user  
D. Federation
#card 
A, D. Amazon EC2 roles provide a temporary token to applications running on the instance; federation maps policies to identities from other sources via temporary tokens.
^1626790755555

50. Your security team is very concerned about the vulnerability of the IAM administrator user accounts (the accounts used to configure all IAM features and accounts). What steps can be taken to lock down these accounts? (Choose 3 answers)  
A. Add multi-factor authentication (MFA) to the accounts.  
B. Limit logins to a particular U.S. state.  
C. Implement a password policy on the AWS account.  
D. Apply a source IP address condition to the policy that only grants permissions when the user is on the corporate network.  
E. Add a CAPTCHA test to the accounts.
#card 
A, C, D. Neither B nor E are features supported by IAM.
^1626790755565

51. You want to grant the individuals on your network team the ability to fully manipulate Amazon EC2 instances. Which of the following accomplish this goal? (Choose 2 answers)  
A. Create a new policy allowing EC2:* actions, and name the policy NetworkTeam.  
B. Assign the managed policy, EC2FullAccess, to a group named NetworkTeam, and assign all the team members' IAM user accounts to that group.  
C. Create a new policy that grants EC2:* actions on all resources, and assign that policy to each individual's IAM user account on the network team.  
D. Create a NetworkTeam IAM group, and have each team member log in to the AWS Management Console using the user name/ password for the group.
#card 
B, C. Access requires an appropriate policy associated with a principal. Response A is merely a policy with no principal, and response D is not a principal as IAM groups do not have user names and passwords. Response B is the best solution; response C will also work but it is much harder to manage.
^1626790755576

52. Which is an operational process performed by AWS for data security?  
A. Advanced Encryption Standard (AES)-256 encryption of data stored on any shared storage device  
B. Decommissioning of storage devices using industry-standard practices  
C. Background virus scans of Amazon Elastic Block Store (Amazon EBS) volumes and Amazon EBS snapshots  
D. Replication of data across multiple AWS regions
#card 
B. All decommissioned magnetic storage devices are degaussed and physically destroyed in accordance with industry-standard practices.
^1626790755587

53. Secure wiping of Amazon EBS data when an Amazon EBS volume is unmounted  
You have launched a Windows Amazon Elastic Compute Cloud (Amazon EC2) instance and specified an Amazon EC2 key pair for the instance at launch. Which of the following accurately describes how to log in to the instance?  
A. Use the Amazon EC2 key pair to securely connect to the instance via Secure Shell (SSH).  
B. Use your AWS Identity and Access Management (IAM) user X. 509 certificate to log in to the instance.  
C. Use the Amazon EC2 key pair to decrypt the administrator password and then securely connect to the instance via Remote Desktop Protocol (RDP) as the administrator.  
D. A key pair is not needed. Securely connect to the instance via RDP.
#card 
C. The administrator password is encrypted with the public key of the key pair, and you provide the private key to decrypt the password. Then log in to the instance as the administrator with the decrypted password.
^1626790755598

54. You have launched a Windows Amazon Elastic Compute Cloud (Amazon EC2) instance and specified an Amazon EC2 key pair for the instance at launch. Which of the following accurately describes how to log in to the instance?  
A. Use the Amazon EC2 key pair to securely connect to the instance via Secure Shell (SSH).  
B. Use your AWS Identity and Access Management (IAM) user X. 509 certificate to log in to the instance.  
C. Use the Amazon EC2 key pair to decrypt the administrator password and then securely connect to the instance via Remote Desktop Protocol (RDP) as the administrator.  
D. A key pair is not needed. Securely connect to the instance via RDP.
#card 
C. The administrator password is encrypted with the public key of the key pair, and you provide the private key to decrypt the password. Then log in to the instance as the administrator with the decrypted password.
^1626790755609

55. A Database security group controls network access to a database instance that is inside a Virtual Private Cloud (VPC) and by default allows access from?  
A. Access from any IP address for the standard ports that the database uses is provided by default.  
B. Access from any IP address for any port is provided by default in the DB security group.  
C. No access is provided by default, and any access must be explicitly added with a rule to the DB security group.  
D. Access for the database connection string is provided by default in the DB security group.
#card 
C. By default, network access is turned off to a DB Instance. You can specify rules in a security group that allows access from an IP address range, port, or Amazon Elastic Compute Cloud (Amazon EC2) security group.
^1626790755620

56. Which encryption algorithm is used by Amazon Simple Storage Service (Amazon S3) to encrypt data at rest with Service-Side Encryption (SSE)?  
A. Advanced Encryption Standard (AES)-256  
B. RSA 1024  
C. RSA 2048  
D. AES-128
#card 
A. Amazon S3 SSE uses one of the strongest block ciphers available, 256-bit AES.
^1626790755631

57. How many access keys may an AWS Identity and Access Management (IAM) user have active at one time?  
A. 0  
B. 1  
C. 2  
D. 3
#card 
C. IAM permits users to have no more than two active access keys at one time.
^1626790755642

58. Which of the following is the name of the security model employed by AWS with its customers?  
A. The shared secret model  
B. The shared responsibility model  
C. The shared secret key model  
D. The secret key responsibility model
#card 
B. The shared responsibility model  
^1626790755652

59. Which of the following describes the scheme used by an Amazon Redshift cluster leveraging AWS Key Management Service (AWS KMS) to encrypt data-at-rest?  
A. Amazon Redshift uses a one-tier, key-based architecture for encryption.  
B. Amazon Redshift uses a two-tier, key-based architecture for encryption.  
C. Amazon Redshift uses a three-tier, key-based architecture for encryption.  
D. Amazon Redshift uses a four-tier, key-based architecture for encryption.
#card 
D. When you choose AWS KMS for key management with Amazon Redshift, there is a four-tier hierarchy of encryption keys. These keys are the master key, a cluster key, a database key, and data encryption keys.  
Amazon Redshift uses a four-tier, key-based architecture for encryption. The architecture consists of data encryption keys, a database key, a cluster key, and a master key. Data encryption keys encrypt data blocks in the cluster. Each data block is assigned a randomly-generated AES-256 key.
^1626790755663

60. Which of the following Elastic Load Balancing options ensure that the load balancer determines which cipher is used for a Secure Sockets Layer (SSL) connection?  
A. Client Server Cipher Suite  
B. Server Cipher Only  
C. First Server Cipher  
D. Server Order Preference
#card 
D. Elastic Load Balancing supports the Server Order Preference option for negotiating connections between a client and a load balancer. During the SSL connection negotiation process, the client and the load balancer present a list of ciphers and protocols that they each support, in order of preference. By default, the first cipher on the client's list that matches any one of the load balancer's ciphers is selected for the SSL connection. If the load balancer is configured to support Server Order Preference, then the load balancer selects the first cipher in its list that is in the client's list of ciphers. This ensures that the load balancer determines which cipher is used for SSL connection. If you do not enable Server Order Preference, the order of ciphers presented by the client is used to negotiate connections between the client and the load balancer.
^1626790755674

61. Which technology does Amazon WorkSpaces use to provide data security?  
A. Secure Sockets Layer (SSL)/ Transport Layer Security (TLS)  
B. Advanced Encryption Standard (AES)-256  
C. PC-over-IP (PCoIP)  
D. AES-128
#card 
C. Amazon WorkSpaces uses PCoIP, which provides an interactive video stream without transmitting actual data. 
An Amazon WorkSpace is a cloud-based virtual desktop that can act as a replacement for a traditional desktop. A WorkSpace is available as a bundle of operating system, compute resources, storage space, and software applications that allow a user to perform day-to-day tasks just like using a traditional desktop.
^1626790755685

62. As a Solutions Architect, how should you architect systems on AWS?  
A. You should architect for least cost.  
B. You should architect your AWS usage to take advantage of Amazon Simple Storage Service's (Amazon S3) durability.  
C. You should architect your AWS usage to take advantage of multiple regions and Availability Zones.  
D. You should architect with Amazon Elastic Compute Cloud (Amazon EC2) Auto Scaling to ensure capacity is available when needed.
#card 
C. Distributing applications across multiple Availability Zones provides the ability to remain resilient in the face of most failure modes, including natural disasters or system failures.
^1626790755696

63. Which security scheme is used by the AWS Multi-Factor Authentication (AWS MFA) token?  
A. Time-Based One-Time Password (TOTP)  
B. Perfect Forward Secrecy (PFC)  
C. Ephemeral Diffie Hellman (EDH)  
D. Split-Key Encryption (SKE)
#card 
A. A virtual MFA device uses a software application that generates six-digit authentication codes that are compatible with the TOTP standard, as described in RFC 6238.
^1626790755707

64. DynamoDB tables may contain sensitive data that needs to be protected. Which of the following is a way for you to protect DynamoDB table content? (Choose 2 answers)  
A. DynamoDB encrypts all data server-side by default so nothing is required.  
B. DynamoDB can store data encrypted with a client-side encryption library solution before storing the data in DynamoDB.  
C. DynamoDB obfuscates all data stored so encryption is not required.  
D. DynamoDB can be used with the AWS Key Management Service to encrypt the data before storing the data in DynamoDB.  
E. DynamoDB should not be used to store sensitive information requiring protection.
#card 
B, D  
Amazon DynamoDB does not have a server-side feature to encrypt items within a table. You need to use a solution outside of DynamoDB such as a client-side library to encrypt items before storing them, or a key management service like AWS Key Management Service to manage keys that are used to encrypt items before storing them in DynamoDB.
^1626790755718

65. You have launched an Amazon Linux Elastic Compute Cloud (Amazon EC2) instance into EC2-Classic, and the instance has successfully passed the System Status Check and Instance Status Check. You attempt to securely connect to the instance via Secure Shell (SSH) and receive the response, "WARNING: UNPROTECTED PRIVATE KEY FILE," after which the login fails. Which of the following is the cause of the failed login?  
A. You are using the wrong private key.  
B. The permissions for the private key are too insecure for the key to be trusted.  
C. A security group rule is blocking the connection.  
D. A security group rule has not been associated with the private key.
#card 
B. If your private key can be read or written to by anyone but you, then SSH ignores your key.
^1626790755729

66. Which of the following public identity providers are supported by Amazon Cognito Identity?  
A. Amazon  
B. Google  
C. Facebook  
D. All of the above
#card 
D
^1626790755740

67. Which feature of AWS is designed to permit calls to the platform from an Amazon Elastic Compute Cloud (Amazon EC2) instance without needing access keys placed on the instance?  
A. AWS Identity and Access Management (IAM) instance profile  
B. IAM groups  
C. IAM roles  
D. Amazon EC2 key pairs
#card 
A. An instance profile is a container for an IAM role that you can use to pass role information to an Amazon EC2 instance when the instance starts.
^1626790755751

68. Which of the following Amazon Virtual Private Cloud (Amazon VPC) elements acts as a stateless firewall?  
A. Security group  
B. Network Access Control List (ACL)  
C. Network Address Translation (NAT) instance  
D. An Amazon VPC endpoint
#card 
B  
A network ACL is an optional layer of security for your Amazon VPC that acts as a firewall for controlling traffic in and out of one or more subnets. You might set up network ACLs with rules similar to your security groups in order to add an additional layer of security to your Amazon VPC.
^1626790755762

69. Which of the following is the most recent version of the AWS digital signature calculation process?  
A. Signature Version 1  
B. Signature Version 2  
C. Signature Version 3  
D. Signature Version 4
#card 
D. The Signature Version 4 signing process describes how to add authentication information to AWS requests. For security, most requests to AWS must be signed with an access key (Access Key ID and Secret Access Key). If you use the AWS Command Line Interface (AWS CLI) or one of the AWS Software Development Kits (SDKs), those tools automatically sign requests for you based on credentials that you specify when you configure the tools. However, if you make direct HTTP or HTTPS calls to AWS, you must sign the requests yourself.
^1626790755773

70. Which of the following is the name of the feature within Amazon Virtual Private Cloud (Amazon VPC) that allows you to launch Amazon Elastic Compute Cloud (Amazon EC2) instances on hardware dedicated to a single customer?  
A. Amazon VPC-based tenancy  
B. Dedicated tenancy  
C. Default tenancy  
D. Host-based tenancy
#card 
B. Dedicated instances are physically isolated at the host hardware level from your instances that aren't dedicated instances and from instances that belong to other AWS accounts.
^1626790755784

71. Which of the following describes how Amazon Elastic MapReduce (Amazon EMR) protects access to the cluster?  
A. The master node and the slave nodes are launched into an Amazon Virtual Private Cloud (Amazon VPC).  
B. The master node supports a Virtual Private Network (VPN) connection from the key specified at cluster launch.  
C. The master node is launched into a security group that allows Secure Shell (SSH) and service access, while the slave nodes are launched into a separate security group that only permits communication with the master node.  
D. The master node and slave nodes are launched into a security group that allows SSH and service access.
#card 
C. Amazon EMR starts your instances in two Amazon Elastic Compute Cloud (Amazon EC2) security groups, one for the master and another for the slaves. The master security group has a port open for communication with the service. It also has the SSH port open to allow you to securely connect to the instances via SSH using the key specified at startup. The slaves start in a separate security group, which only allows interaction with the master instance. By default, both security groups are set up to prevent access from external sources, including Amazon EC2 instances belonging to other customers. Because these are security groups in your account, you can reconfigure them using the standard Amazon EC2 tools or dashboard.
^1626790755794

72. To help prevent data loss due to the failure of any single hardware component, Amazon Elastic Block Storage (Amazon EBS) automatically replicates EBS volume data to which of the following?  
A. Amazon EBS replicates EBS volume data within the same Availability Zone in a region.  
B. Amazon EBS replicates EBS volume data across other Availability Zones within the same region.  
C. Amazon EBS replicates EBS volume data across Availability Zones in the same region and in Availability Zones in one other region.  
D. Amazon EBS replicates EBS volume data across Availability Zones in the same region and in Availability Zones in every other region.
#card 
A  
When you create an Amazon EBS volume in an Availability Zone, it is automatically replicated within that Availability Zone to prevent data loss due to failure of any single hardware component. An EBS Snapshot creates a copy of an EBS volume to Amazon S3 so that copies of the volume can reside in different Availability Zones within a region.
^1626790755805

73. For implementing security features, which of the following would you choose (Choose all that apply)?  
A. Username/password  
B. MFA  
C. Using multiple S3 buckets  
D. Login using the root user
#card 
A, B
^1626790755816

74. You want EC2 instances to give access without any username or password to S3 buckets. What is the easiest way of doing this?  
A. By using a VPC S3 endpoint  
B. By using a signed URL  
C. By using roles  
D. By sharing the keys between S3 and EC2
#card 
C
^1626790755827

75. Using the shared security model, the customer is responsible for which of the following? (Choose two.)  
A. The security of the data running inside the database hosted in EC2  
B. Maintaining the physical security of the data center  
C. Making sure the hypervisor is patched correctly  
D. Making sure the operating system is patched correctly
#card 
A, D. The customer is responsible for the security of anything running on the hypervisor, and therefore the operating system and the security of data are the customer's responsibility.
^1626790755837

76. In Amazon RDS, who is responsible for patching the database?  
A. Customer.  
B. Amazon.  
C. In RDS you don't have to patch the database.  
D. RDS does not come under the shared security model.
#card 
B. RDS does come under a shared security model. Since it is a managed service, the patching of the database is taken care of by Amazon.
^1626790755848

77. What statements correctly describe security groups within a VPC? (Select three)  
A. default security group only permit inbound traffic  
B. security groups are stateful firewalls  
C. only allow rules are supported  
D. allow and deny rules are supported  
E. security groups are associated to network interfaces
#card 
B, C, E
^1626790755859

78. What three items are required to configure a security group rule?  
A. Protocol type  
B. VPC name  
C. Port number  
D. Source IP  
E. Destination IP  
F. description
#card 
A, C, D
^1626790755869

79. What two source IP address types are permitted in a security group rule?  
A. Only CIDR blocks with /16 subnet mask  
B. Source IP address 0.0.0.0/0  
C. Single source IP address with /24 subnet mask  
D. Security group id  
E. IPv6 address with /64 prefix length
#card 
B, D
^1626790755880

80. What protocols must be enabled for remote access to Linux-based and Windows-based EC2 instances?  
A. SSH, ICMP, Telnet  
B. SSH, HTTP, RDP  
C. SSH, HTTP, SSL  
D. SSH, RDP, ICMP
#card 
D
^1626790755891

81. Distinguish network ACLs from security groups within a VPC? (Select three)  
A. ACL filters at the subnet level  
B. ACL is based on deny rules only  
C. ACL is applied to instances and subnets  
D. ACL is stateless  
E. ACL supports a numbered list for filtering
#card 
A, D, E
^1626790755902

82. What happens to the security permissions of a tenant when an IAM role is granted? (Select two)  
A. Tenant inherits only permissions assigned to the IAM role temporarily  
B. Add security permissions of the IAM role to existing permissions  
C. Previous security permissions are no longer in effect  
D. Previous security permissions are deleted unless reconfigured  
E. Tenant inherits only read permissions assigned to the IAM role.
#card 
A, C
^1626790755912

83. Where are IAM permissions granted to invoke and execute a Lambda function for S3 access? (Select two)  
A. S3 bucket  
B. EC2 instance  
C. Lambda function  
D. IAM role  
E. Event mapping
#card 
A, D
^1626790755923

84. You have some developers working on code for an application and they require temporary access to AWS cloud up to an hour. What is the easiest web-based solution from AWS to provide access and minimize security exposure?  
A. ACL  
B. Security group  
C. IAM group  
D. STS  
E. EFS
#card 
D
^1626790755934

85. What two methods are used to request temporary credentials based on AWS Security Token Service (STS)?  
A. Web identity Federation  
B. LDAP  
C. IAM identity  
D. Dynamic ACL  
E. Private key rotation
#card 
A, C. AWS Identity and Access Management (IAM) supports identity federation, which enables external identities, such as users in your corporate directory, to sign in to the AWS Management Console via single sign-on (SSO).
^1626790755944

86. What two components are required for enabling SAML authentication requests to AWS Identity and Access Management (IAM)?  
A. Access keys  
B. Sessiontoken  
C. SSO  
D. Identity provider (IdP)  
E. SAML provider entity
#card 
D, E. Security Assertion Markup Language (SAML) is an open standard that allows identity providers (IdP) to pass authorization credentials to service providers (SP). ... SAML is the link between the authentication of a user's identity and the authorization to use a service.
^1626790755954

87. What are the two reasons for deploying Origin Access Identity (OAI) when enabling CloudFront?  
A. Prevent users from deleting objects in S3 buckets  
B. Mitigate distributed denial of service attacks (DDoS)  
C. Prevent users from accessing objects with Amazon S3 URL  
D. Prevent users from accessing objects with CloudFront URL  
E. Replace IAM for internet-based customer authentication
#card 
B, C
^1626790755965

88. What solutions are recommended to mitigate DDoS attacks? (Select three)
A. Host-based firewall  
B. Elastic load balancer  
C. WAF  
D. SSL/TLS  
E. Bastion host  
F. NAT gateway
#card 
B, C, E
^1626790755976

89. What features are required to prevent users from bypassing AWS CloudFront security? (Select three)  
A. Bastion host  
B. Signed URL  
C. IP whitelist  
D. Signed cookies  
E. Origin access identity (OAI)
#card 
B, D, E
^1626790755986

90. What is the advantage of resource-based policies for cross-account access?  
A. Trusted account permissions are not replaced  
B. Trusted account permissions are replaced  
C. Resource-based policies are easier to deploy  
D. Trusting account manages all permissions
#card 
A. Identity-based policies are attached to an IAM user, group, or role. These policies let you specify what that identity can do (its permissions).  
Resource-based policies are attached to a resource. For example, you can attach resource-based policies to Amazon S3 buckets, Amazon SQS queues, and AWS Key Management Service encryption keys.
^1626790755996

91. Select three requirements for configuring a Bastion host?  
A. EIP  
B. SSH inbound permission  
C. Default route  
D. CloudWatch logs group  
E. VPN  
F. Auto-Scaling
#card 
A, B, D
^1626790756007

92. What rule must be added to the security group assigned to a mount target instance that enables EFS access from an EC2 instance?  
A. Type = EC2, protocol = IP, port + 2049, source = remote security group id  
B. Type = EC2, protocol = EFS, port = 2049, source= 0.0.0.0/0  
C. Type = NFS, protocol = UDP, port = 2049, source = remote security group ID  
D. Type=NFSv4, protocol = UDP, port = 2049, source = remote security group id
#card 
C
^1626790756017

93.   What are the two advantages of customer-managed encryption keys (CMK)?  
A. Create and rotate encryption keys  
B. AES-128 cipher for data at rest  
C. Audit encryption keys  
D. Encrypts data in-transit for server-side encryption only
#card 
A, C
^1626790756027

94. What feature is not available with AWS Trusted Advisor?  
A. Cost optimization  
B. Infrastructure best practices  
C. Vulnerability assessment  
D. Monitor application metrics
#card 
C
^1626790756037

95. What is required to Ping from a source instance to a destination instance?
A. Network ACL: not required Security Group: allow ICMP outbound on source/destination EC2 instances  
B. Network ACL: allow ICMP inbound/outbound on source/destination subnets Security group: not required  
C. Network ACL: allow ICMP inbound/outbound-on source/destination subnets Security group: allow ICMP outbound on source EC2 instance Security Group: allow ICMP inbound on destination EC2 instance  
D. Network ACL: allow TCP inbound/outbound on source/destination subnets Security Group: allow TCP and ICMP inbound on source EC2 instance
#card 
C
^1626790756047

96. What two steps are required to grant cross-account permissions between AWS accounts?  
A. Create an IAM user  
B. Attach a trust policy to S3  
C. Create a transitive policy  
D. Attach a trust policy to the role  
E. Create an IAM role
#card 
D, E
^1626790756058

97. You have configured a security group to allow ICMP, SSH and RDP inbound and assigned the security group to all instances in a subnet. There is no access to any Linux-based or Windows-based instances and you cannot Ping any instances. The network ACL for the subnet is configured to allow all inbound traffic to the subnet. What is the most probably cause? 
A. On-premises firewall rules  
B. Security group and network ACL outbound rules  
C. Security group outbound rules  
D. Bastion host required
#card 
C
^1626790756068

98. What three techniques provide authentication security on S3 volumes?  
A. Bucket policies  
B. Network ACL  
C. Identity and Access Management (IAM)  
D. Encryption  
E. AES256
#card 
A, B, C
^1626790756079

99. What statement correctly describes support for AWS encryption of S3 objects?  
A. Tenants manage encryption for server-side encryption of S3 objects  
B. Amazon manages encryption for server-side encryption of S3 objects  
C. Client-side encryption of S3 objects is not supported  
D. S3 buckets are encrypted only  
E. SSL is only supported with Glacier storage
#card 
B
^1626790756089

100. What authentication method provides Federated Single Sign-On (SSO) for cloud applications?  
A. ADS  
B. ISE  
C. Radius  
D. Tacacs  
E. SAML
#card 
E
^1626790756100

101. Based on the Amazon security model, what infrastructure configuration and associated security is the responsibility of tenants and not Amazon AWS? (Select two)  
A. Dedicated cloud server  
B. Hypervisor  
C. Operating system level  
D. Application level  
E. Upstream physical switch
#card 
C, D
^1626790756111

102. What security authentication is required before configuring or modifying EC2 instances? (select three)  
A. Authentication at the operating system level  
B. EC2 instance authentication with asymmetric keys  
C. Authentication at the application level  
D. Telnet username and password  
E. SSH/RDP session connection
#card 
A, B, E
^1626790756121

103. What feature is part of Amazon Trusted Advisor?  
A. Security compliance  
B. Troubleshooting tool  
C. EC2 configuration tool  
D. Security certificates
#card 
A
^1626790756131

104. What AWS feature is recommended for optimizing data security?  
A. Multi-factor authentication  
B. Username and encrypted password  
C. Two-factor authentication  
D. SAML  
E. Federated LDAP
#card 
A
^1626790756141

105. What IAM class enables an EC2 instance to access a file object in an S3 bucket?  
A. User  
B. Root  
C. Role  
D. Group
#card 
C
^1626790756152

106. What are three recommended solutions that provide protection and mitigation from distributed denial of service (DDoS) attacks?  
A. Security groups  
B. CloudWatch  
C. Encryption  
D. WAF  
E. Data replication  
F. Auth-Scaling
#card 
A, B, D
^1626790756163

107. What are three recommended best practices when configuring Identity and Access Management (IAM)security services?  
A. Lock or delete your root access keys when not required  
B. IAM groups are not recommended for storage security  
C. Create an IAM user with administrator privileges  
D. Share your password and/or access keys with members of your group only  
E. Delete any AWS account where the access keys are unknown
#card 
A, C, E
^1626790756173

108. What two features create security zones between EC2 instances within a VPC?  
A. Security groups  
B. Virtual Security Gateway  
C. Network ACL  
D. WAF
#card 
A, B. Check Point Security Gateway for Amazon Web Services delivers a security cloud computing platform that enables customers to deploy flexible multilayer security in the cloud. It extends the latest security technology to Amazon's cloud, protects assets in the cloud from attacks, and enable security connectivity. Based on the latest Check Point GAiA 64-bit operating system, it also enforces a consistent security policy across the organization by protecting data between the corporate network and Amazon Virtual Private Cloud and inspects data entering and leaving the private subnet in the Amazon's VPC. Check Point Software Blade architecture meets an organization's cloud security needs with flexible and manageable security options; the Firewall, IPS, Application Control, Antivirus and Anti-Bot Software Blades protect services in the public cloud from unauthorized access and attacks. The Application Control Software Blade helps prevent application layer denial of service attacks and protects your cloud services.
^1626790756184

109. What AWS service provides vulnerability assessment services to tenants within the cloud?  
A. Amazon WAF  
B. Amazon Inspector  
C. Amazon Cloud Logic  
D. Amazon Trusted Advisor
#card 
B. Amazon Inspector is an automated security assessment service that helps improve the security and compliance of applications deployed on AWS. Amazon Inspector automatically assesses applications for vulnerabilities or deviations from best practices.
^1626790756195

110. What are two primary differences between AD Connector and Simple AD for cloud directory services?  
A. Simple AD requires an on-premises ADS directory  
B. Simple AD is fully managed and setup in minutes  
C. AD connector requires an on-premises ADS directory  
D. Simple AD is more scalable than AD Connector  
E. Simple AD provides enhanced integration with IAM
#card 
B, C. AD Connector is a dual Availability Zone proxy service that connects AWS apps to your on-premises directory. ... This account is used by AWS to enable seamless domain join, single sign-on (SSO), and AWS Applications (WorkSpaces, WorkDocs, and WorkMail) functionality.
^1626790756206

111. You are deploying an application on Amazon EC2, which must call AWS APIs. What method should you use to securely pass credentials to the application?  
A. Pass API credentials to the instance using Instance userdata.  
B. Store API credentials as an object in Amazon S3.  
C. Embed the API credentials into your application.  
D. Assign I AM roles to the EC2 Instances.
#card 
C
^1626790756217

112. The security policy of an organization requires an application to encrypt data before writing to the disk. Which solution should the organization use to meet this requirement?  
A. AWS KMS API  
B. AWS Certificate Manager  
C. API Gateway with STS  
D. 1AM Access Key
#card 
A. You can use roles to delegate access to users, applications, or services that don't normally have access to your AWS resources. It is not a good practice to use IAM credentials for a production based application. A good practice however, is to use IAM Roles.
^1626790756227

113. A retailer exports data daily from its transactional databases into an S3 bucket in the Sydney region. The retailer's Data Warehousing team wants to import this data into an existing Amazon Redshift cluster in their VPC at Sydney. Corporate security policy mandates that data can only be transported within a VPC.  
What combination of the following steps will satisfy the security policy?  
Choose 2 answers from the options given below.  
A. Enable Amazon Redshift Enhanced VPC Routing.  
B. Create a Cluster Security Group to allow the Amazon Redshift cluster to access Amazon S3.  
C. Create a NAT gateway in a public subnet to allow the Amazon Redshift cluster to access Amazon S3.  
D. Create and configure an Amazon S3 VPC endpoint.
#card 
A, D. Amazon Redshift Enhanced VPC Routing provides VPC resources, the access to Redshift.  
Redshift will not be able to access the S3 VPC endpoints without enabling Enhanced VPC routing, so one option is not  
to support the scenario if another is not selected. NAT instance (the proposed answer) cannot be reached by Redshift without enabling Enhanced VPC Routing.
^1626790756238

114. A company is using a Redshift cluster to store their data warehouse. There is a requirement from the Internal IT Security team to encrypt data for the Redshift database. How can this be achieved?  
A. Encrypt the EBS volumes of the underlying EC2 Instances.  
B. Use AWSKMS Customer Default master key.  
C. Use SSL/TLS for encrypting the data.  
D. Use S3 Encryption.
#card 
B. Amazon Redshift uses a hierarchy of encryption keys to encrypt the database. You can use either AWS Key Management Service (AWS KMS) or a hardware security module (HSM) to manage the top-level encryption keys in this hierarchy. The process that Amazon Redshift uses for encryption differs depending on how you manage keys.
^1626790756249

115. There is a requirement for Block-level storage to store 500GB of data. Data Encryption is also required. Which of the following can be used in such a case?  
A. AWS EBS Volumes  
B. AWS S3  
C. AWS Glacier  
D. AWS EFS
#card 
AWS EBS is a Block-level storage service.  
Options B and C are incorrect since they are Object-level storage services.  
Option D is incorrect since this is a File-level storage service.
^1626790756259

116. There is a requirement for EC2 Instances in a private subnet to access an S3 bucket. It is required that the traffic does not traverse to the Internet. Which of the following can be used to fulfill this requirement?  
A. VPC Endpoint  
B. NAT Instance  
C. NAT Gateway  
D. Internet Gateway
#card 
A VPC endpoint enables you to privately connect your VPC to supported AWS services and VPC endpoint services powered by PrivateLink without requiring an internet gateway, NAT device, VPN connection, or AWS Direct Connect connection. Instances in your VPC do not require public IP addresses to communicate with resources in the service. Traffic between your VPC and the other service does not leave the Amazon network.
^1626790756270

117. A company hosts 5 web servers in AWS. They want to ensure that Route53 can be used to route user traffic to random web servers when they request for the underlying web application. Which routing policy should be used to fulfill this requirement?  
A. Simple  
B. Weighted  
C. Multivalue Answer  
D. Latency
#card 
C. If you want to route traffic approximately randomly to multiple resources such as web servers, you can create one multivalue answer record for each resource and, optionally, associate an Amazon Route 53 health check with each record. For example, suppose you manage an HTTP web service with a dozen web servers that each have their own IP address, no one web server could handle all of the traffic, but if you create a dozen multivalue answer records, Amazon Route 53 responds to DNS queries with up to eight healthy records in response to each DNS query. Amazon Route 53 gives different answers to different DNS resolvers. If a web server becomes unavailable after a resolver caches a response, client software can try another IP address in the response.  Simple routing policy - Use for a single resource that performs a given function for your domain, for example, a web server that serves content for the example.com website.  
Latency routing policy - Use when you have resources in multiple locations and you want to route traffic to the resource that provides the best latency.  
Weighted routing policy - Use to route traffic to multiple resources in proportions that you specify.  
Multivalue answer routing policy - Use when you want Route 53 to respond to DNS queries with up to eight healthy records selected at random.^1626790756280
