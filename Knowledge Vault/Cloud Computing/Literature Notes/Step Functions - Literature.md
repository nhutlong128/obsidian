### Metadata

-  Type: #literature #compute
    Date written: [[2021-05-20, Thu]]  
    Source:  https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html
    Status: #wip 
    Keywords:  #cloudcomputing #aws #stepfunctions
	
### Notes
- Step Functions has two workflow types. 
	- Standard workflows have exactly-once workflow execution and can run for up to one year. 
		- 2,000 per second execution rate
		- 4,000 per second state transition rate
		- Priced per state transition
		- Shows execution history and visual debugging
	- Express workflows have at-least-once workflow execution and can run for up to five minutes.
		- 100,000 per second execution rate
		- Nearly unlimited state transition rate
		- Priced per number and duration of executions
		- Sends execution history to [Amazon CloudWatch](https://aws.amazon.com/cloudwatch/)

- Step Functions integrates with multiple AWS services. To combine Step Functions with these services, use the following service integration patterns:
	- Request a response
		- Call a service, and let Step Functions progress to the next state after it gets an HTTP response.
	- Run a job
		- Call a service, and have Step Functions wait for a job to complete.
	- Wait for a callback with a task token
		- Call a service with a task token, and have Step Functions wait until the task token returns with a callback.

- A state machine is defined by the states it contains and the relationships between them.
	```python
	{ "Comment": "A Hello World example of the Amazon States Language using a Pass state", "StartAt": "HelloWorld", "States": { "HelloWorld": { "Type": "Pass", "Result": "Hello World!", "End": true } } }
	```
- The following rules apply to states within a state machine:
	- States can occur in any order within the enclosing block, but the order in which they're listed doesn't affect the order in which they're run. The contents of the states determines this order.
	- Within a state machine, there can be only one state that's designated as the `start` state, designated by the value of the `StartAt` field in the top-level structure. This state is the one that is executed first when the execution starts
	- Any state for which the `End` field is `true` is considered an `end` (or `terminal`) state. Depending on your state machine logic—for example, if your state machine has multiple branches of execution—you might have more than one `end` state.
	- If your state machine consists of only one state, it can be both the `start` state and the `end` state.
- State Type:
	- Pass
		- A `Pass` state (`"Type": "Pass"`) passes its input to its output, without performing work. `Pass` states are useful when constructing and debugging state machines.
		- Here is an example of a `Pass` state that injects some fixed data into the state machine, probably for testing purposes.
			```python
			"No-op": { "Type": "Pass", "Result": { "x-datum": 0.381018, "y-datum": 622.2269926397355 }, "ResultPath": "$.coords", "Next": "End" }
			```
		- Suppose the input to this state is the following
			```python
			{ "georefOf": "Home" }
			```
		- Then the output
			```python
			{ "georefOf": "Home", "coords": { "x-datum": 0.381018, "y-datum": 622.2269926397355 } }
			```
	- Task
		- A `Task` state (`"Type": "Task"`) represents a single unit of work performed by a state machine.
		- All work in your state machine is done by _tasks_. A task performs work by using an activity or an AWS Lambda function, or by passing parameters to the API actions of other services.
		- It's a good practice to set a timeout value and a heartbeat interval for long-running activities. This can be done by specifying the timeout and heartbeat values, or by setting them dynamically.
			- ### Static timeout and heartbeat notification
			- ### Dynamic task timeout and heartbeat notification
		- The following task types are supported:
			- Activity
				- Activities represent workers (processes or threads), implemented and hosted by you, that perform a specific task. They are supported only by Standard Workflows, not Express Workflows.
				- You must create activities with Step Functions (using a [CreateActivity](https://docs.aws.amazon.com/step-functions/latest/apireference/API_CreateActivity.html), API action, or the [Step Functions console](https://console.aws.amazon.com/states/home?region=us-east-1#/)) before their first use.
			- Lambda
				- Lambda tasks execute a function using AWS Lambda. To specify a Lambda function, use the ARN of the Lambda function in the `Resource` field.
			- Supported AWS Services
				- When you reference a connected resource, Step Functions directly calls the API actions of a supported service. Specify the service and action in the `Resource` field.
				- To create a synchronous connection to a connected resource, append `.sync` to the `APIname` entry in the ARN. For more information
	- Choice
		- A `Choice` state (`"Type": "Choice"`) adds branching logic to a state machine.
		- A **comparison** – Two fields that specify an input variable to compare, the type of comparison, and the value to compare the variable to. Choice Rules support comparison between two variables. Within a Choice Rule, the value of Variable can be compared with another value from the state input by appending `Path` to name of supported comparison operators.
		-  A **`Next` field** – The value of this field must match a state name in the state machine.
		-  Example
			```python
			{ "Variable": "$.foo", "NumericEquals": 1, "Next": "FirstMatchState" }
			```
	- Wait
		- A `Wait` state (`"Type": "Wait"`) delays the state machine from continuing for a specified time. You can choose either a relative time, specified in seconds from when the state begins, or an absolute end time, specified as a timestamp.
	- Succeed
		- A `Succeed` state (`"Type": "Succeed"`) stops an execution successfully. The `Succeed` state is a useful target for `Choice` state branches that don't do anything but stop the execution.
	- Fail
		- A `Fail` state (`"Type": "Fail"`) stops the execution of the state machine and marks it as a failure, unless it is caught by a `Catch` block.
	- Parallel
		- The `Parallel` state (`"Type": "Parallel"`) can be used to create parallel branches of execution in your state machine.
	- Map
		- The `Map` state (`"Type": "Map"`) can be used to run a set of steps for each element of an input array. While the `[Parallel](https://docs.aws.amazon.com/step-functions/latest/dg/amazon-states-language-parallel-state.html)` state executes multiple branches of steps using the same input, a `Map` state will execute the same steps for multiple entries of an array in the state input.

- Transitions
	```python
	"SomeState" : { ..., "Next" : "NextState" }
	```
- Paths
	- a _path_ is a string beginning with `$` that you can use to identify components within JSON text.
	- A _reference path_ is a path whose syntax is limited in such a way that it can identify only a single node in a JSON structure:
		```python
		{ "foo": 123, "bar": \["a", "b", "c"\], "car": { "cdr": true } }
		```
		
		```python
		$.foo => 123 $.bar => \["a", "b", "c"\] $.car.cdr => true
		```
- Error Handling
	- ### Handling a failure using Retry
		- ### Complex retry scenarios
			```python
			"X": { "Type": "Task", "Resource": "arn:aws:states:us-east-1:123456789012:task:X", "Next": "Y", "Retry": \[ { "ErrorEquals": \[ "ErrorA", "ErrorB" \], "IntervalSeconds": 1, "BackoffRate": 2.0, "MaxAttempts": 2 }, { "ErrorEquals": \[ "ErrorC" \], "IntervalSeconds": 5 } \], "Catch": \[ { "ErrorEquals": \[ "States.ALL" \], "Next": "Z" } \] }
			```
	- ### Handling a failure using Catch
			```python
			{ "Comment": "A Hello World example of the Amazon States Language using an AWS Lambda function", "StartAt": "HelloWorld", "States": { "HelloWorld": { "Type": "Task", "Resource": "arn:aws:lambda:us-east-1:123456789012:function:FailFunction", "Catch": \[ { "ErrorEquals": \["HandledError"\], "Next": "fallback" } \], "End": true }, "fallback": { "Type": "Pass", "Result": "Hello, AWS Step Functions!", "End": true } } }
			```
		- 