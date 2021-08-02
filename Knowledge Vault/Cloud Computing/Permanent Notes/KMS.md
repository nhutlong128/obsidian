---
cards-deck: Obsidian::Cloud-Computing::Security::KMS
tags: kms, security
---
### Metadata

-  Type: #permanent #security
    Date written: #2021-06-22
    Source:  https://docs.aws.amazon.com/iam/index.html
    Status: #wip 
    Keywords:  #cloudcomputing #aws #iam
	Related:
	
### Notes
- [[KMS Key Type]]
- [[KMS Customer Master Keys (CMK) Types]]
- [[KMS ]] can only encrypting up to 4KB

### Questions

1. What is the Key Type of RSA & ECC?
#card 
Asymmetric
^1626791456128

2. What is the Key Type of AES-256?
#card 
Symmetric
^1626791456139

3. The limit of size that KMS can only encrypting
#card 
4KB
^1626791456150

4. In server side encryption, only the encryption happens on the server. Where does the decryption happen?
- The Server
- The Client
#card 
The Server. In server side encryption, the decryption also happens on the server (in AWS, we wouldn't be able to decrypt the data ourselves as we can't have access to the corresponding encryption key)
^1626791456162

5. In client side encryption, the server must know our encryption scheme to accept the data
- True
- False
#card 
With client side encryption, the server does not need to know any information about the encryption being used, as the server won't perform any encryption or decryption tasks
^1626791456173

6. We need to create User Keys in KMS before using the encryption features for EBS, S3, etc...
- True
- False
#card 
False. we can use the AWS Managed Service Keys in KMS, therefore we don't need to create our own keys
^1626791456183

7. We'd like our Lambda function to have access to a database password. We should
- Embed it in the code
- Have it as a plaintext environment variable
- Have it as an encrypted environment variable and decrypt it at runtime
#card 
Have it as an encrypted environment variable and decrypt it at runtime
^1626791456194

8. We would like to audit the values of an encryption value over time
- We should use KMS versoning feature
- We should use S3
- We should use SSM Parameter Store
#card 
SSM Parameter Store has versioning and audit of values built-in directly
^1626791456205

9. Under the shared responsibility model, what are you responsible for in RDS?
- Security Group Rules
- OS patching
- Database Patching
- Underlying Hardware Security
#card 
Security Group Rules^1626791456216
