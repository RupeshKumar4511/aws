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
```bash 

ssh -i <key-value-pair-file-path>
<br>
chmod 600 <key-value-pair-file-path> // to secure it

```