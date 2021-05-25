- If the function return error, Lambda will run it again two more times with one-minute between the first two attempt and two-minutes between the second and the third.
- Function errors includes [[Function Based Error]] and [[Runtime Based Error]] (timeout)
- If the age of events greater than 6 hours, it will be discarded. 
- Should configure Lambda to send an invocation record to another service for processing events that success or fail all attempts
- Lambda support two ways to send an invocation record of all attempts:
	- [[Dead Letter Queue - DLQ]]
	- [[Destination]]
- ![[Pasted image 20210524171539.png]]

Backlink: [[Asynchronous Invoke]]