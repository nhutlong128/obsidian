---
cards-deck: Obsidian::Cloud-Computing::Message::SQS
tags: sqs, message
---
### Metadata

-  Type: #permanent #message
    Date written: #2021-05-31  
    Source:  https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html
	https://quizlet.com/363204815/sqs-swf-sns-sts-flash-cards/
    Status: #wip 
    Keywords:  #cloudcomputing #aws #sqs
	Related:
	
### Notes
- [[SQS Messaging System Type]]
- [[SQS Message Consuming Mechanism]]
- [[SQS Provision Instance]]
- [[SQS High Availability Mechanism]]
- [[SQS Scaling Mechanism]]
- [[SQS Error Handling]]
- [[SQS Queue Type]]
- [[SQS Optimize]]
- [[SQS Security]]
- [[SQS Fees charged]]
- [[SQS Specific]]


### Questions

1. You are preparing for the biggest day of sale of the year, where your traffic will increase by 100x. You have already setup SQS standard queue. What should you do?
- Open a support ticket to pre-warm the SQS queue
- Enable auto scaling in the SQS queue
- Increase the capacity of the SQS queue
- Do nothing, SQS scales automatically
#card 
Do nothing, SQS scales automatically
^1626790649720

2. You would like messages to be processed by SQS consumers only after 5 minutes of being published to SQS. What should you do?
- Increase the DelaySeconds parameters
- Change the Visibility Timeout
- Enable Long Polling
- Use the extended SQS client
#card 
Increase the DelaySeconds parameters. Delay queues let you postpone the delivery of new messages to a queue for a number of seconds. If you create a delay queue, any messages that you send to the queue remain invisible to consumers for the duration of the delay period. The default (minimum) delay for a queue is 0 seconds. The maximum is 15 minutes
^1626790649730

3. Your consumers poll 10 messages at a time and finish processing them in 1 minute. You notice that your messages are processed twice, as other consumers also receive the messages. What should you do?
- Enable Long Polling
- Add delay to the messages when being produced
- Increase the Visibility Timeout
- Decrease the Visibility Timeout
#card 
Increase the Visibility Timeout. Immediately after a message is received, it remains in the queue. To prevent other consumers from processing the message again, Amazon SQS sets a visibility timeout, a period of time during which Amazon SQS prevents other consumers from receiving and processing the message. Increasing the timeout gives more time to the consumer to process that message and will prevent duplicate readings of the message
^1626790649740

4. You'd like your messages to be processed exactly once and in order. Which do you need?
- SQS Standard Queue
- SQS Dead Letter Queue
- SQS Delay Queue
- SQS FIFO Queue
#card 
SQS FIFO Queue
^1626790649750

5. You'd like to send a message to 3 different applications all using SQS. You should
- Use SQS Replication Feature
- Use SNS & SQS Fan out pattern
- Send messages individually to 3 SQS queues
#card 
Use SNS & SQS Fan out pattern
^1626790649761

6. How long messages can be kept in the Queue?
#card 
1 minute to 14 days. Default is 4 days
^1626790649772

7. What is SQS message size?
#card 
256KB
^1626790649782

8. What is SQS's visibility timeout?
#card 
-- A period of time, starting from the message is received until the timeout reached, during which Amazon SQS prevents other consumers from receiving and processing the message.  
--The default visibility timeout for a message is 30 second. The maximum visibility timeout is 12 hours
^1626790649793

9. What is ? SQS Standards
#card 
-- SQS will deliver your message at least once, but cannot guarantee the order in which the messages will be delivered.  
--SQS will deliver your message at least once, but cannot guarantee that it will not create duplicates of that message.
^1626790649803

10. SQS Delay Queues
#card 
Delay queues let you postpone the delivery of new messages to a queue for a number of seconds  
The minimum delay for a queue is 0 seconds. The maximum is 15 minutes
^1626790649812

11. _________ helps reduce the cost of using Amazon SQS by eliminating the number of empty responses
#card 
Long Polling
^1626790649823

12. What is Long Polling of SQS?
#card 
allows the SQS server to wait until a message is available in a queue before sending a response
^1626790649832

13. What is Amazon SQS Message Lifecycle?
#card 
1) A system that needs to send a message will select an Amazon SQS queue, and use SendMessage to send a new message to it.  
2) A different system that processes messages needs more messages to process, so it calls ReceiveMessage, and this message is returned.  
3) Once a message has been returned by ReceiveMessage, it will not be returned by any other ReceiveMessage until the visibility timeout has passed. This keeps multiple consumers from processing the same message at once.  
4) If the system that processes messages successfully finishes working with this message, it calls DeleteMessage, which removes the message from the queue so no one else will ever process it. If this system fails to process the message, then it will be read by another ReceiveMessage call as soon as the visibility timeout passes.  
5) If you have associated a Dead Letter Queue with a source queue, messages will be moved to the Dead Letter Queue after the maximum number of delivery attempts you specify have been reached.
^1626790649843

14. How is one payload of SQS billed?
#card 
The message payload can contain up to 256KB of text in any format. Each 64KB 'chunk' of payload is billed as 1 request.
^1626790649853

15. What is SQS message batch limit?
#card 
Messages can be sent, received or deleted in batches of up to 10 messages or 256KB. Batches cost the same amount as single messages.
^1626790649863

16. What is the Message maximum retention of SQS?
#card 
14 days
^1626790649873

17. What is message locking of SQS?
#card 
When a message is received, it becomes "locked" while being processed. This keeps other computers from processing the message simultaneously. If the message processing fails, the lock will expire and the message will be available again.
^1626790649883

18. What is DLQ of SQS?
#card 
Developers can handle stuck messages (messages that have not been successfully processed by a consumer) with Dead Letter Queues. When the maximum receive count is exceeded for a message it will be moved to the Dead Letter Queue (DLQ) associated with the original queue.
^1626790649893

19. What is SQS Design Pattern: Fanout?
#card 
Combine SQS with Simple Notification Service (SNS) to send identical copies of a message to multiple queues in parallel.
^1626790649903

20. What is SQS Design Pattern: Priority?
#card 
Use separate queues to provide prioritization of work.
^1626790649913

21. What is MAx visibility timeout of SQS?
#card 
12 hours
^1626790649923

22. What is Inflight message SQS?
#card 
A message is considered to be in flight after it's received from a queue by a consumer, but not yet deleted from the queue.
^1626790649933

23. Maximum number of inflight messages SQS?
#card 
120,000
^1626790649943

24. How do I handle reaching the maximum inflight messages SQS?
#card 
Delete them
^1626790649953

25. Amazon SQS standard queue ensures delivery of each message at least once.  
A. True  
B. False
#card 
True
^1626790649963

26. If you update the SQS delay value, the new value affects all messages in the queue.  
A. True  
B. False
#card 
B. If you update the value, the new value affects only messages enqueued after the update.
^1626790649973

27. You can delete a queue at any time, whether it is empty or not.  
A. True  
B. False
#card 
A
^1626790649983

28. SQS FIFO guarantees at least once delivery although there may be duplicate messages.  
A. True  
B. False
#card 
B. Standard queues provide at-least-once delivery, which means that each message is delivered at least once.  
FIFO queues provide exactly-once processing, which means that each message is delivered once and remains available until a consumer processes it and deletes it. Duplicates are not introduced into the queue.
^1626790649993

29. With SQS_________, when you retrieve messages from the queue, Amazon SQS samples a subset of the servers (based on a weighted random distribution) and returns messages from just those servers.  
A. short polling  
B. long polling  
C. delay queues  
D. None of the above
#card 
A. By default, Amazon SQS uses short polling, querying only a subset of its servers (based on a weighted random distribution), to determine whether any messages are available for a response.
^1626790650003

30. Amazon SQS assigns each queue you create an identifier called a__________, which includes the queue name and other components that Amazon SQS determines. Whenever you want to perform an action on a queue, you provide its __________.  
A. queue ID  
B. message ID  
C. queue URL  
D. None of the above
#card 
C. When you create a new queue, you must specify a queue name unique for your AWS account and region. Amazon SQS assigns each queue you create an identifier called a queue URL that includes the queue name and other Amazon SQS components. Whenever you want to perform an action on a queue, you provide its queue URL.
^1626790650013

31. Is the following a valid SQS queue URL?  
http://sqs.amazonaws.com/123456789012/sqs-queue2
#card 
False. http://sqs.us-east-1.amazonaws.com/123456789012/sqs-queue2
^1626790650023

32. The SQS message ID can be used to identify and delete a message.  
A. True  
B. False
#card 
Every time you receive a message from a queue, you receive a receipt handle for that message. This handle is associated with the action of receiving the message, not with the message itself. To delete the message or to change the message visibility, you must provide the receipt handle (not the message ID).
^1626790650033

33. Use this action with AttributeName setting to see approximate number of messages in an SQS queue:  
A. GetQueueAttributes with ApproximateNumberOfMessages  
B. GetQueueAttributes with ApproximateNumberOfMessagesNotVisible  
C. Either of the above  
D. None of the above
#card 
A
^1626790650044

34. Each SQS queue starts with a default setting of _______for the visibility timeout.  
A. 30 seconds  
B. 1 minute  
C. 30 minutes  
D. None of the above
#card 
A
^1626790650054

35. f your system doesn't call DeleteMessage for that message before the visibility timeout expires, the message again becomes visible.  
A. True  
B. False
#card 
A
^1626790650064

36. There is a _________limit for the number of inflight messages per standard queue.  
A. 1024  
B. 4096  
C. 20,000  
D. 120000
#card 
D
^1626790650074

37. The benefit/s of SQS long polling:  
A. Reduction of the number of empty responses  
B. Eliminates false empty responses  
C. Reduces resources required for polling queues  
D. All of the above
#card 
D. Long polling offers the following benefits:  
• Eliminate empty responses by allowing Amazon SQS to wait until a message is available in a queue before sending a response. Unless the connection times out, the response to the ReceiveMessage request contains at least one of the available messages, up to the maximum number of messages specified in the ReceiveMessage action.  
• Eliminate false empty responses by querying all—rather than a subset of—Amazon SQS servers.  
• Return messages as soon as they become available.
^1626790650085

38. Long polling occurs when the WaitTimeSeconds parameter of a ReceiveMessage call is set to 0.  
A. True  
B. False
#card 
B. You can enable long polling using the AWS Management Console by setting a Receive Message Wait Time to a value greater than 0
^1626790650095

39. You can use CreateQueue to create an SQS delay queue by setting the DelaySeconds attribute to any value between 0 and 900 (15 minutes).  
A. True  
B. False
#card 
A. Delay queues let you postpone the delivery of new messages to a queue for a number of seconds. If you create a delay queue, any message that you send to that queue remains invisible to consumers for the duration of the delay period. To create a delay queue, set the DelaySeconds attribute of the CreateQueue action to any value between 0 and 900 (15 minutes). To change an existing queue into a delay queue use the SetQueueAttributes action to set the queue's DelaySeconds attribute
^1626790650105

40. A dead letter queue is a queue that other (source) queues can target to send messages that for some reason could not be successfully processed. 
A. True  
B. False
#card 
A
^1626790650116

41. To specify a dead letter queue, you can use  
A. AWS Management Console  
B. Query API  
C. All of the above
#card 
C
^1626790650126

42. You must use the same AWS account and the same region to create the SQS queue which will be used as a dead letter queue and the other (source) queues that will send messages to the dead letter queue.  
A. True  
B. False
#card 
A
^1626790650136

43. The dead letter queue of a FIFO queue must also be a FIFO queue. Similarly, the dead letter queue of a standard queue must also be a standard queue.
#card 
True
^1626790650146

44. The metrics you configure with CloudWatch for your Amazon SQS queues are automatically collected and pushed to CloudWatch every _______.  
A. 30 seconds  
B. 1 minute  
C. 5 minutes  
D. 10 minutes
#card 
C
^1626790650156

45. The following SQS actions can be tracked with CloudTrail:  
A. AddPermission & RemovePermission  
B. CreateQueue & DeleteQueue  
C. SetQueueAttributes  
D. All of the above
#card 
D
^1626790650166

46. In almost all cases, SQS long polling is preferable to SQS short polling.  
A. True  
B. False
#card 
A. In almost all cases, Amazon SQS long polling is preferable to short polling. Long-polling requests let your queue consumers receive messages as soon as they arrive in your queue while reducing the number of empty ReceiveMessageResponse instances returned.  
Amazon SQS long polling results in higher performance at reduced cost in the majority of use cases. However, if your application expects an immediate response from a ReceiveMessage call, you might not be able to take advantage of long polling without some modifications to your application.
^1626790650176

47. You might receive a previously deleted SQS message from a standard queue again.  
A. True  
B. False
#card 
A  
For standard queues, under rare circumstances, you might receive a previously-deleted message a second time. This can happen in the rare situation when a DeleteMessage operation doesn't delete all copies of a message because one of the servers in the distributed Amazon SQS system isn't available at the time of deletion. This message copy can be delivered again. If you use standard queues, design your application to be idempotent (that is, no errors or inconsistencies occur if you receive a deleted message a second time).  
FIFO queues never introduce duplicate messages.
^1626790650186

48. You have a web application hosted in EC2 that consumes messages from an SQS queue and is integrated with SNS to send out an email to you once the process is complete. You received 5 orders but after a few hours, you saw more than 20 email notifications in your inbox.  
Which of the following could be the possible culprit for this issue?
#card 
The web application is not deleting the messages in the SQS queue after it has processed them.
^1626790650196

49. You run a website which accepts high-quality photos and turns them into a downloadable video montage. The website offers a free account and a premium account that guarantees faster processing. All requests by both free and premium members go through a single SQS queue and then processed by a group of EC2 instances which generate the videos. You need to ensure that the premium users who paid for the service have higher priority than your free members.  
How do you re-design your architecture to address this requirement?
#card 
Create an SQS queue for free members and another one for premium members. Configure your EC2 instances to consume messages from the premium queue first and if it is empty, poll from the free members' SQS queue.
^1626790650207

50. You developed a web application and deployed it on a fleet of EC2 instances, which is using Amazon SQS. The requests are saved as messages in the SQS queue which is configured with the maximum message retention period. However, after thirteen days of operation, the web application suddenly crashed and there are 10,000 unprocessed messages that are still waiting in the queue. Since you developed the application, you can easily resolve the issue but you need to send a communication to the users on the issue.  
What information will you provide and what will happen to the unprocessed messages?
#card 
Tell the users that the application will be operational shortly and all received requests will be processed after the web application is restarted.
^1626790650217




