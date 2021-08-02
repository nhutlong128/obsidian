---
cards-deck: Obsidian::Cloud-Computing::Networking::CloudFront
tags: cloudfront, networking
---
## Metadata

-  Type: #permanent #networking
    Date written: #2021-06-29
    Source:  https://docs.aws.amazon.com/cloudfront
    Status: #wip 
    Keywords:  #cloudcomputing #aws #cloudfront
	Related:
	
### Notes
- [[CDN]]
- [[Static Resource]] is cached on [[Edge Locations]] as [[Proxy]] all around the world
- [[CloudFront Origins]]
- [[CloudFront Signed URL]]
- [[CloudFront Signed Cookies]]
- [[CloudFront Price Classes]]
- [[CloudFront Multiple Origin]]
- [[CloudFront Field Level Encryption]]

![[Pasted image 20210629220546.png]]
![[Pasted image 20210629220600.png]]
![[Pasted image 20210629220614.png]]

### Questions

1. Which features allows us to distribute paid content from S3 securely, globally, if the S3 bucket is secured to only exchange data with CloudFront?
- Origin Access Identity
- S3 Pre-Signed URL
- CloudFront Signed URL
- CloudFront Distribution Invalidations
#card 
CloudFront Signed URL
^1626791210938

2. You are hosting highly dynamic content in Amazon S3 in us-east-1. Recently, there has been a need to make that data available with low latency in Singapore. What do you recommend using?
- CloudFront
- S3 Cross Region Replication
- S3 Pre-Signed URLs
#card 
S3 Cross Region Replication. S3 CRR allows you to replicate the data from one bucket in a region to another bucket in another region
^1626791210950

3. How can you ensure that only users who access our website through Canada are authorized in CloudFront?
- Set up a security group and attach it to CloudFront
- Use a Route 53 Latency record and attach it to CloudFront
- Use CloudFront Geo Restriction
#card 
Use CloudFront Geo Restriction
^1626791210961

4. You would like to provide your users access to hundreds of private files in your CloudFront distribution, which is fronting an HTTP web server behind an application load balancer. What should you use?
- CloudFront Signed URL
- CloudFront Signed Cookies
- CloudFront Origin Access Identity
- CloudFront HTTPS encryption
#card 
CloudFront Signed Cookies. Allows you to access many files
^1626791210973

5. You are creating an application that is going to expose an HTTP REST API. There is a need to provide request routing rules at the HTTP level. Due to security requirements, your application can only be exposed through the use of two static IPs. How can you create a solution that validates these requirements?
- Use Global Accelerator and an Application Load Balancer
- Use a Network Load Balancer and attach Elastic IPs to it
- Use an Application Load Balancer and attach Elastic IPs to it
- Use CloudFront with Elastic IP and an Application Load Balancer
#card 
Use Global Accelerator and an Application Load Balancer. Global Accelerator will provide us with the two static IP, and the ALB will provide use with the HTTP routing rules.^1626791210984
