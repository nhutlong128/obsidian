---
cards-deck: Obsidian::Cloud-Computing::Monitoring::CloudWatch
tags: cloudwatch, monitoring
---
### Metadata

-  Type: #permanent #monitoring 
    Date written: #2021-07-01
    Source:  https://docs.aws.amazon.com/iam/index.html
    Status: #wip 
    Keywords:  #cloudcomputing #aws #cloudwatch
	Related:
	
### Notes
- [[CloudWatch Metrics]]
- [[CloudWatch Dashboards]]
- [[CloudWatch Logs]]
- [[CloudWatch Alarms]]
- [[CloudWatch Events]]

### Questions

1. We'd like to have CloudWatch Metrics for EC2 at a 1 minute rate. What should we do?
- Enable Custom Metrics
- Enable High Resolution
- Enable Basic Monitoring
- Enable Detailed Monitoring
#card 
Enable Basic Monitoring is default and 5 minutes rate. Enable Detailed Monitoring. This is a paid offering and gives you EC2 metrics at a 1 minute rate
^1626790853282


2. High Resolution Custom Metrics can have a minimum resolution of
- 1 second
- 10 seconds
- 30 seconds
- 1 minute
#card 
1 second
^1626790853293

3. Your CloudWatch alarm is triggered and controls an ASG. The alarm should trigger 1 instance being deleted from your ASG, but your ASG has already 2 instances running and the minimum capacity is 2. What will happen?
- One instance will be deleted and the ASG capacity and minimum will go to 1
- The alarm will remain in "ALARM" state but never decrease the number of instances in my ASG
- The alarm will be detached from my ASG
- The alarm will go in OK state
#card 
The alarm will remain in "ALARM" state but never decrease the number of instances in my ASG. The number of instances in an ASG cannot go below the minimum, even if the alarm would in theory trigger an instance termination
^1626790853304

4. An Alarm on a High Resolution Metric can be triggered as often as
- 1 second
- 10 seconds
- 30 seconds
- 1 minute
#card 
10 seconds
^1626790853314

5. You have made a configuration change and would like to evaluate the impact of it on the performance of your application. Which service do you use?
- CloudWatch
- CloudTrail
#card 
CloudWatch
^1626790853325

6. Someone has terminated an EC2 instance in your account last week, which was hosting a critical database. You would like to understand who did it and when, how can you achieve that?
- Look at the CloudWatch Metrics
- Look at the CloudWatch Alarms
- Look at the CloudWatch Events
- Look at CloudTrail
#card 
CloudTrail helps audit the API calls made within your account, so the database deletion API call will appear here (regardless if made from the console, the CLI, or an SDK)
^1626790853336

7. You would like to ensure that over time, none of your EC2 instances expose the port 84 as it is known to have vulnerabilities with the OS you are using. What can you do to monitor this?
- Setup CloudWatch Metrics
- Setup CloudTrail trails
- Setup Config Rules
- Create AWS Lambda cron job
#card 
Setup Config Rules
^1626790853347

8. You would like to evaluate the compliance of your resource's configurations over time. Which technology do you choose?
- CloudWatch
- CloudTrail
- Config
#card 
Config^1626790853357
