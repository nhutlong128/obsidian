---
cards-deck: Obsidian::Cloud-Computing::Compute::ECS
tags: ecs, compute
---
### Metadata

-  Type: #permanent #compute
    Date written: #2021-06-23
    Source:  https://docs.aws.amazon.com/ecs
    Status: #wip 
    Keywords:  #cloudcomputing #aws #ecs
	Related:
	
### Notes
- [[ECS Compute Type]]
- [[ECS Provision Instance]]
- [[ECS Location]]
- [[ECS Type]]
- [[ECS High Availability Mechanism]]
- [[ECS Scalability Mechanism]]
- [[ECS Storage]]
- [[ECS Runtime Provided]]
- [[ECS Security]]
- [[ECS Optimize]] (Not done)
- [[ECS Fees charged]] (Not done)
- [[ECS Specific]]

### Questions

1. Does ECS support any other container types?
#card 
**No. Docker is the only container platform supported at this time.**
^1626789673407

2. In ECS, I want to launch containers. Why do I have to launch Tasks?
#card 
**Tasks allow you to define a set of containers that you would like to be placed together (or part of the same placement decision), their properties, and how they may be linked**.  
Tasks **include all the information that Amazon ECS needs to make the placement decision**.
^1626789673417

3. Does Amazon ECS support batch jobs?
#card 
Yes. You can use Amazon ECS Run task to run one or more tasks once. Run task starts the task on an instance that meets the task's requirements including CPU, memory and ports.
^1626789673427

4. Can I use my own scheduler with Amazon ECS?
#card 
ECS provides Blox, a collection of open source projects for container management and orchestration.
^1626789673437

5. Does Amazon ECS support retrieving Docker images from a private or internal source?
#card 
Yes. Customers can configure their container instances to access a private Docker image registry within a VPC or a registry that's accessible outside a VPC such as Amazon ECR.
^1626789673446

6. What is needed on each EC2 instance in a ECS Cluster?
#card 
Docker and an ECS agent
^1626789673456

7. What does the ECS agent do?
#card 
Installed on each EC2 instance.  
**Manages containers (Start, stop,etc)**  
**Communicates with Docker Daemon**  
**Sends utilization information to ECS service**
^1626789673466

8. How do Containers, Tasks, the ECS Service and Clusters related?
#card 
Container definition is contained in a task definition  
A Task definition is run by the ECS Service  
The ECS Service runs tasks on instances in the Cluster  
Container Definition=>Task Definition=>Service=>Cluster
^1626789673475

9. What is the ECS Task Placement Strategy?
#card 
**Algorithm for selecting instances for task placement or tasks for termination (when scaling down a task count)** for EC2 launch types.  
**Tasks can be balanced for availability or packed for efficiency**.
^1626789673485

10. What task placement strategy types are available of ECS?
#card 
binpack - least available CPU or memory (minimizes the number of instances in use)  
random - place tasks randomly
spread - place tasks evenly based on specified values. Accepted values are key-value pairs, instanceId or host.
^1626789673494

11. What is the ECS Task placement constraints?
#card 
A _task placement constraint_ is a rule that is considered during task placement.
^1626789673504

12. What is a Task constraint strategy and what options are available?
#card 
**distinctInstance** - **Place each task on a different container instance**.  
**memberOf** - **Place tasks on container instances that satisfy an expression (e.g. AZ, Compute type or custom attribute)**. Can be specified/used when running a task, creating a service or create/updating a task definition.
^1626789673513

13. Can ECS tasks be grouped together?
#card 
**Yes**, **task groups** can be used to group tasks for things like spread placement. A **task can belong to only on task group**.
^1626789673523

14. How can you maintain a specified number of instances of a task definition simultaneously in an ECS Cluster?
#card 
This is done via a ECS **service**.
^1626789673533

15. What does a Service do in an ECS Cluster?
#card 
Amazon ECS Service **allows you to run and maintain a specified number of instances of a task definition simultaneously in an Amazon ECS cluster**.
^1626789673543

16. How can you distribute traffic across the tasks that are associated with a service?
#card 
You can **place the service behind a load balancer**.
^1626789673552

17. What service schedule strategies are supported with the ECS Scheduler?
#card 
1) **replica** - The replica scheduling strategy **places and maintains the desired number of tasks across your cluster(default is across AZs)**  
2) **daemon** - The daemon scheduling strategy **deploys exactly one task on each active container instance that meets all of the task placement constraints that you specify in your cluster**. Not supported with Fargate types.
^1626789673562

18. What is ECS Optimized AMI?
#card 
ECS optimized AMI (Amazon Linux - ECS optimized) include the ECS container agent and hence don't need separate installation
^1626789673571

19. Does doing ECS Service Auto Scaling means that our cluster will get bigger?
#card 
No,for this we can do Cluster Auto Scaling,  
through Capacity Provider.
^1626789673581

20. What is the difference between ECS Service Auto Scaling and Cluster Auto Scaling?
#card 
ECS Cluster Auto Scaling will make Clustter bigger.
^1626789673590

21. Which ECS config must you enable in /etc/ecs/ecs.config to allow your ECS tasks to endorse IAM roles?
#card 
ECS_ENABLE_TASK_IAM_ROLE
^1626789673599

22. You are looking to push Docker images into ECR with your AWS CodePipeline and CodeBuild. The last step fails with an authorization issue. What is the issue?
#card 
Double check your IAM permissions for CodeBuild service (Note: Any permissions issues against ECR is most likely due to IAM policies)
^1626789673609

23. You are looking to run multiple instances of the same application on the same EC2 instance and expose it with a load balancer. The application is available as a Docker container. You should use
#card 
Application Load Balancer + ECS (because it uses the dynamic port feature)
^1626789673618

24. You are running a web application on ECS, the Docker image is stored on ECR, and trying to launch two containers of the same type on EC2. The first container starts, but the second one doesn't. You have checked and there's enough CPU and RAM available on the EC2 instance. What's the problem?
#card 
The host port is defined in the task definition.(To enable random host port, set host port = 0 (or empty), which allows multiple containers of the same type to launch on the same instance)
^1626789673627

25. You have started an EC2 instance and it's not registered with the ECS cluster. What's NOT a reason for this issue?
#card 
The security groups on the EC2 instance are misconfigured.(security groups do not matter when an instance registers with the ECS service)
^1626789673636

26. You would like to run 4 ECS services on your ECS cluster, which need access to various services. What is the best practice?
#card 
Create 4 ECS task roles and attach them to the relevant ECS task definition.
^1626789673645

27. Which task cluster placement is the MOST cost-efficient?
#card 
binpack^1626789673655
