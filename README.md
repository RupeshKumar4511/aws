# cloud 
Cloud is computer resources over the internet.

# cloud computing : 
It is on demand delivery of services over the internet.

# Public Cloud : 
Virtual machines can be provided to any users who have account with aws/azure/GCP.

# Private Cloud : 
Organizations buy and maintains their own servers (virtual machines and other resources).

# Mixed Cloud (Public + Private) : 
We can also create Private Cloud inside Public cloud. 

# Why Public Cloud is so popular ?
Two main reason : 
<br>
1. To get rid of mentainance of entire setup of servers.
<br>
2. Cost Efficient.

# How AWS is better than others ?
Because AWS is the one who intially started this cloud concept. 

# Main Disadvantage of Public Cloud : 
Security Concerns
<br>
Server Downtime
<br>
Network Requirement

# AWS IAM (Identity and Access Management)
IAM solves the problem of authentication and authorization using their policy.

# Why we need Users, Policies, Groups and Roles : 
Users : Admins create users for their organization. 
<br>
Policies : Policies are attached with user account which provides the user some access to resoursces.
<br>

Groups : Instead of creating multiple users and attaching policies, admins can create groups like Group of ["Developer","QA Engineer", "DB-Admins","others"] and each of them have their own policies. When a new employee comes to an organization the DevOps engineer just check the employee is "Developer" or "QA Engineer" or  "DB-Admins" or "others" and create account and put him into groups. 

<br>

Role : In AWS IAM, a Role is an identity that grants temporary permissions to access AWS resources. 
<br>
Unlike a user, a role:
<br>
Does not have a username or password
<br>
Is assumed by services, users, or applications
<br>
Provides temporary security credentials
<br>
Roles are commonly used to:
<br>
Allow an EC2 instance to access S3
<br>
Let one AWS account access resources in another account
<br>
Give applications secure access without storing keys
<br>
Github Repo : https://github.com/iam-veeramalla/aws-devops-zero-to-hero/tree/main/day-2

# EC2 instance 
EC2 stands for Elastic Cloud Compute. It is a service offered by AWS which provides virtual servers which is elastic in nature.
<br>
Compute means we are requesting Virtual Servers (CPU,RAM,Disks)
<br>
Cloud : service over the internet. 
<br>
Elastic : It means this service can be scale up and down.
<br>
Advantages : 
<br>
No need to upgrade unlike in physical server.
<br>
no need to manage unlike in physical server.
<br>
There are 5 diff types of EC2 instance : 
<br>
1. General Purpose : Mostly used.
<br>
2. Compute Optimized : Used for ML model, gaming servers.
<br>
3. Memory Optimized : Used for big data analytics.
<br>
4. Storage Optimized 
<br>
5. Accelated Optimized : Integrated with GPUs,AI-chips

# How to login on EC2 instance : 
Open Gitbash 
<br>

```bash 

ssh -i <key-value-pair-file-path> ubuntu@<public-ipv4>
<br>
chmod 600 <key-value-pair-file-path> // to secure it

```

<br>
Github Repo : https://github.com/iam-veeramalla/aws-devops-zero-to-hero/tree/main/day-3

# Virtual Private Cloud : 
A VPC (Virtual Private Cloud) is our own private network inside AWS.
<br>
It lets us create an isolated environment where we can launch and manage AWS resources (like EC2, RDS, etc.) with full control over:
<br>
IP address ranges
<br>
Subnets (public and private)
<br>
Routing (route tables, gateways)
<br>
Network security (security groups, NACLs)
<br>
All configuration of VPC is setup by the devops engineer of an organization.
<br>
Size of VPC is defined by the IP address range. And further this IP address range can be divided into subnets for different subprojects inside a project of an organization.
<br>
Example : If an user wants to access application which is hosted on VPC then firstly it pass the Internet gatway of the VPC and then it passes to the public subnet inside VPC then there will be a load balancer attached to public subnet which has target group and takes the request to particular application through route table (router) and then request to needs to pass security groups before reaching to particular application. 
<br>
If an application needs to download a package from the public internet (google.com) then <b>NAT gatway</b> is used to mask the ip address of private virtual machines and application with load balance ip addr or router ip addrerss.
<br>
VPC flow logs contains all the logs of requests. 
<br>
Github Repo : https://github.com/iam-veeramalla/aws-devops-zero-to-hero/tree/main/day-4
<br>
Security Groups and NACL(Network Access Control List) are very crucial for our application because these are last point of security. Security Groups are implemented at instance level and NACL implemented at subnet level.
<br>
There are two concepts in Security Groups : 
<br>
1. Inbound Traffic  : Request comming into ec2 instance from outside. 
<br>
2. Outbound Traffic : Request outgoing from ec2 instance to public network like google. 
<br>
By default when we create an ec2 instance then it provides default VPC because it assigns a security groups to our instance which deny every incoming request and allow every outgoing request except traffic on port 25. 
<br>
NACL : A Network Access Control List is a stateless firewall that controls inbound and outbound traffic at the subnet level. It operates at the IP address level and can allow or deny traffic based on rules that you define. NACLs provide an additional layer of network security for your VPC. Here we define which traffic will be denied or allowed.
<br>
When we create a VPC on aws then aws will automatically create internet gatway, NACL with default configuration and route table.
<br>
Github Repo : https://github.com/iam-veeramalla/aws-devops-zero-to-hero/tree/main/day-5
