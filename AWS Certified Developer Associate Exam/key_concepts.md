# AWS Availability Zones
- Each region has  many  availability  zones (usually  3,  min  is  2,  max  is  6).  
- Each availability  zone  (AZ)  is  one  or  more discrete  data  centers  with  redundant  power, networking,  and  connectivity
- They’re  separate  from  each  other,  so  that they’re  isolated  from  disasters
- They’re  connected  with  high  bandwidth, ultra-low  latency  networking

# IAM
- **Identity  and  Access  Management**,  Global  service
- Root  account created  by  default,  shouldn’t  be  used  or  shared
- Users or Groupscan be assigned JSON documents called policies. These policies define the permissionsof the users 
- In AWS you apply the **least privilege principle**

# IAM Policies Structure
- Effect: whether the statement allows or denies access (Allow, Deny)
- Principal: account/user/role to which this policy applied to
- Action: list of actions this policy allows or denies
- Resource: list of resources to which the actions applied to

# Multi Factor Authentication - MFA
- protect your Root Accounts and IAM users
- MFA = password you know + security device you own
- Main benefit of MFA: if a password is stolen or hacked, the account is not compromised
- MFA devices options: 
-   1. Virtual MFA device 
-   2. Universal 2nd Factor (U2F) Security Key
-   3. Hardware Key Fob MFA Device
-   4. Hardware Key Fob MFA Device for AWS GovCloud (US)

# IAM Roles
Means assign permissions to AWS services with IAM Roles to access other AWS services

# IAM Security Tools
- IAM Credentials Report (account-level)
- IAM Access Advisor (user-level)

 # EC2
 - EC2 represents Elastic Compute Cloud, also means Infrastructure as a Service
 - Common EC2 resources include:
   - Renting virtual machines (EC2) = instances
   - Distributing load across machines (ELB) = load balancer
- Configuration: 
  - Operating System (OS) => related to AMI options
  - compute power & cores (CPU)
  - random-access memory (RAM)
  - instance storage (disk)
  - Firewall rules: security group
  - Network card: speed of the card, Public IP address
  - Bootstrap script (configure at first launch): EC2 User Data

# EC2 User Data
- It is the script which will run only once at the instance first start
- It is used to automate boot tasks such as:
  - Installing updates
  - Installing software
  - Downloading common files from the internet
- Other things:
  - For example, you can write a bash script to launch a server on your instance
  - Bootstrapping means launching commands when a machine starts

# AMI
An AMI is a template that contains the software configuration (operating system, application server, and applications) required to launch your instance

# Key Pairs
- When we launch our instance, we will need to select a key pair
- It is used to log in to our instance
- Key pair file can only be downloaded once, so don't lose the file

# EC2 Instance Types
- naming convention: m5.2xlarge
  - m: instance class
  - 5: generation (version) (AWS improves them over time)
  - 2xlarge: size of the instance within the class
1. General Purpose
- Great for a diversity of workloads such as web servers or code repositories
- Balance between:
  - Compute
  - Memory
  - Networking
- For example, t2.micro is a free tier general purpose type of instance
2. Compute Optimized
- Great for compute-intensive tasks that require high performance processors:
  - Batch processing workloads
  - Media transcoding
  - High performance web servers
  - High performance computing (HPC)
  - Scientific modeling & machine learning
  - Dedicated gaming servers
