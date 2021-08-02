There are 4 methods of encrypting objects in S3
- [[SSE-S3]]: encrypt using keys handled by AWS![[Pasted image 20210621220625.png]]
- [[KMS]]: encrypt using keys handled by AWS and customer
![[Pasted image 20210621220640.png]]
[[Pasted image 20210628002036.png]]
- [[CSE]]: Client Side Encryption using [[S3 SDK]] ![[Pasted image 20210628002102.png]]

From ML perspective, should use [[SSE-S3]] and [[KMS-AWS]]