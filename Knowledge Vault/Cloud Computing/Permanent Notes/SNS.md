---
cards-deck: Obsidian::Cloud-Computing::Message::SNS
tags: sns, message
---
### Metadata

-  Type: #permanent #message
    Date written: 2021-06-01 
    Source:  https://docs.aws.amazon.com/sns/latest/dg/welcome.html
    Status: #wip 
    Keywords:  #cloudcomputing #aws #sns
	Related:
	
### Notes
- [[SNS Messaging System Type]]
- [[SNS Message Consuming Mechanism]]
- [[SNS Provision Instance]]
- [[SNS High Availability Mechanism]]
- [[SNS Scaling Mechanism]]
- [[SNS Queue Type]]
- [[SNS Error Handling]] is dependent on error types to retry processing message or discard it.
- [[SNS Optimize]]
- [[SNS Security]]
- [[SNS Fees charged]]
- [[SNS Specific]]




### Questions

1. T/F: SNS can trigger lambda functions?
#card 
True. SNS can trigger lambda functions that are invoked with the payload of the message. The function receives the message payload as an input parameter and can manipulate the information in the message publish the message ot another sns topic or send hte message to other aws services.
^1626790679442

2. What is an SNS topic?
#card 
Allows the grouping of multiple recipients. A topic is an access point for allowing recipients to subscribe for identical copies of the same notification.
^1626790679453

3. T/F: Topics can have many different kinds of subscribers. I.E. mobile devices, sms, and email.
#card 
True. SNS autoformats the messages for the subscribers types.
^1626790679463

4. What is the simplest way to enable an S3 bucket to be able to send messages to your SNS topic?
#card 
Add a resource-based access control policy on the SNS topic.
^1626790679473

5. SNS message can be sent to different kinds of endpoints. What are supported endpoints?
#card 
HTTP/HTTPs, Email, Email-JSON, SQS, mobile app notifications, Lambda, SMS
^1626790679483

6. With ______________ and SNS, a full-environment monitoring solution can be created that notifies admins of alerts, capacity issues, downtime, etc
#card 
Cloudwatch
^1626790679494

7. What are the 3 SNS components?
#card 
Topic, subscription, publisher
^1626790679504

8. What is SNS Mobile Push?
#card 
Ability to send notifications to apps on mobile devices
^1626790679514

9. What is MPNS provider? Names?
#card 
Mobile Push Notification Services  
Amazon Device Messaging  
Apple Push Notification Service  
Google Cloud Messaging
^1626790679525

10. What is the flow for MPNS? What does SNS require from MPNS?
#card 
sns publisher -> SNS Topic -> MPNS Providers -> Mobile Device  
requires device tokens OR registration ids depending on the provider
^1626790679535

11. What API call can you make to grant access to your SNS topics to another AWS account?
#card 
AddPermission
^1626790679546

12. T/F EC2 or Lambda will use an IAM role to access SNS topics
#card 
True
^1626790679556

13. SNS Messages are typically ________-formatted _________________ pairs
#card 
JSON formatted Key-value pairs
^1626790679567

14. SNS Message headers help with message ______________
#card 
authenticity
^1626790679577

15. What is an SNS publisher? What are examples of SNS Publishers?
#card 
entity that triggers sending of a message  
AWS CLI  
AWS SDK  
AWS Services - s3 events, cloudwatch alarms, Lambda to publish to SNS
^1626790679588

16. SNS default TTL
#card 
4 weeks
^1626790679598

17. How long Subscription will be valid (not expire) if not confirmed. SNS
#card 
3 days
^1626790679608

18. Maximum length of the Topic Name SNS
#card 
256
^1626790679618

19. Maximum number of topics allowed per account SNS
#card 
100.000
^1626790679628

20. Maximum number of subscriptions per topic SNS
#card 
10 millions
^1626790679638

21. Maximum size of the message (except SMS) SNS
#card 
256 KB of text data, including XML, JSON and unformatted text.    
Each 64KB chunk of published data is billed as 1 request
^1626790679648

22. How many message filters can be applied to a topic
#card 
By default, 100 filter policies per account per region can be applied to a topic.
^1626790679659

23. Maximum size of the message - SMS SNS
#card 
Each SMS message can contain up to 140 bytes, and the character limit depends on the encoding scheme.
^1626790679669

24. What is Message Durablity of SNS
#card 
To prevent messages from being lost, all messages published to SNS are stored redundantly across multiple AZ.
^1626790679679

25. SNS vs SQS getting message method?
#card 
Both Messaging Service in AWS  
SNS - push 
SQS - Poll^1626790679690
