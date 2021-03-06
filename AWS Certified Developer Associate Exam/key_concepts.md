# AWS Availability Zones
- Each region has  many  availability  zones (usually  3,  min  is  2,  max  is  6).  
- Each availability  zone  (AZ)  is  one  or  more discrete  data  centers  with  redundant  power, networking,  and  connectivity
- They’re  separate  from  each  other,  so  that they’re  isolated  from  disasters
- They’re  connected  with  high  bandwidth, ultra-low  latency  networking

# IAM
- **Identity  and  Access  Management**,  Global  service
- Root  account created  by  default,  shouldn’t  be  used  or  shared
- Users or Groups can be assigned JSON documents called policies. These policies define the permissions of the users 
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

# CLI
- Command Line Interface (where we can access AWS from the terminal)
- Username: access key
- Password: secret access key
- Different from EC2 Instance Connect

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

# AMI (Amazon Machine Image)
- An AMI is a template that contains the software configuration (operating system, application server, and applications) required to launch your instance
- You can launch EC2 instances from:  
  • A Public AMI: AWS provided  
  • Your own AMI: you make and maintain them yourself  
  • An AWS Marketplace AMI: an AMI someone else made (and potentially sells)  
- AMI are built for a specific region

# Key Pairs (aka Private Key File)
- When we launch our instance, we will need to select a key pair
- It is used to log in to our instance
- Key pair file can only be downloaded once, so don't lose the file

# EC2 Instance Types
- naming convention: m5.2xlarge
  - m: instance class
  - 5: generation (version) (AWS improves them over time)
  - 2xlarge: size of the instance within the class

**1. General Purpose**
- Great for a diversity of workloads such as web servers or code repositories
- Balance between:
  - Compute
  - Memory
  - Networking
- For example, t2.micro is a free tier general purpose type of instance
 
**2. Compute Optimized**
- Great for compute-intensive tasks that require high performance processors
- Use cases:
  - Batch processing workloads
  - Media transcoding
  - High performance web servers
  - High performance computing (HPC)
  - Scientific modeling & machine learning
  - Dedicated gaming servers

**3. Memory Optimized**
- Fast performance for workloads that process large data sets in memory
- Use cases:
  - High performance, relational/non-relational databases
  - Distributed web scale cache stores
  - In-memory databases optimized for BI (business intelligence)
  - Applications performing real-time processing of big unstructured data

**4. Storage Optimized**
- Great for storage-intensive tasks that require high, sequential read and write access to large data sets on local storage
- Use cases:
  - High frequency online transaction processing (OLTP) systems
  - Relational & NoSQL databases
  - Cache for in-memory databases (for example, Redis)
  - Data warehousing applications
  - Distributed file systems
 
# Security Groups
## Definition
- Fundamental of network security in AWS and acting as a “firewall” on EC2 instances
- Control how traffic is allowed into or out of our EC2 Instances
- Security groups only contain "allow" rules
- The rules can either by IP or by security group

## Good to know
- Accesssability
  - Can be attached to multiple instances
  - Locked down to a region / VPC combination
- Common sense
  - Does live “outside” the EC2 – if traffic is blocked the EC2 instance won’t see it
  - It’s good to maintain one separate security group for SSH access
- Error Msg related
  - If your application is not accessible (time out), then it’s a security group issue
  - If your application gives a “connection refused“ error, then it’s an application error or it’s not launched
- Default setting
  - All inbound traffic is blocked by default
  - All outbound traffic is authorised by default

## Ports to remember
• 22 = SSH (Secure Shell) - log into a Linux instance  
• 21 = FTP (File Transfer Protocol) – upload files into a file share  
• 22 = SFTP (Secure File Transfer Protocol) – upload files using SSH  
• 80 = HTTP – access unsecured websites   
• 443 = HTTPS – access secured websites  
• 3389 = RDP (Remote Desktop Protocol) – log into a Windows instance  

# Log into EC2 Instance
1. SSH(use terminal and use ssh commnad): Mac and Linux (key file needed)
2. Putty: all Windows version (key file needed, file conversion needed)
3. EC2 Instance Connect(from the AWS console): all applicable

# EC2 Instance Connect
- No need to use your key file that was downloaded
- The “magic” is that a temporary key is automatically uploaded onto EC2 by AWS
- Need to make sure the port 22 is still opened!

# EC2 Instances Purchasing Options
## EC2 On Demand
- Has the highest cost but no upfront payment
- short workload, predictable pricing
- for **short-term** and **un-interrupted workloads**, where you can't predict how the application will behave

## Reserved Instances
- Up to 72% discount compared to On-demand
- Reservation period: 1 year = + discount | 3 years = +++ discount (1 year **or** 3 year)
- Purchasing options: no upfront | partial upfront = + | All upfront = ++ discount
- For specific instance type only
- Recommended for **steady-state** usage applications (think database)

### Convertible Reserved Instance
- can change the EC2 instance type
- Up to 45% discount

### Scheduled Reserved Instances
- example – every Thursday between 3 and 6 pm
- Commitment for 1 year only

## Spot Instances
- discount of up to **90%**
- The MOST **cost-efficient** instances in AWS, **spot price fluctuates**
- you can “lose” at any point of time if your max price is less than the current spot price
- Useful for workloads that are resilient to failure
  - Batch jobs
  - Data analysis
  - Image processing
  - Any **distributed** workloads
  - Workloads with a flexible start and end time
- Not suitable for critical jobs or databases

## Dedicated Hosts
- Can address **compliance requirements**
- Can use your **existing server-bound software licenses**.
- More expensive
- Useful for software that have complicated licensing model
- for companies that have strong regulatory or compliance needs
- **Physical** server with EC2 instance capacity fully dedicated to your use.

# EBS Volume
## Define
- An EBS (Elastic Block Store) Volume is a network drive you can attach to your instances while they run
- Think of them as a **“network USB stick”**
## Features
- It allows your instances to persist data, even after their termination
- **They can only be mounted to one instance at a time** (at the CCP level)
- They are bound to a specific availability zone
- To move a volume across AZ or Region, you first need to snapshot it
- Have a provisioned capacity (size in GBs, and IOPS)
## Billing
- You get billed for all the provisioned capacity
- You can increase the capacity of the drive over time
- (size in GBs, and IOPS) in/out
## Delete on Termination attribute
- Controls the EBS behaviour when an EC2 instance terminates
- By default, the root EBS volume is deleted (attribute enabled)
- By default, any other attached EBS volume is not deleted (attribute disabled)

## EBS Volume Types
- EBS Volumes are characterized in Size | Throughput | IOPS (I/O Ops Per Sec)
- Only gp2/gp3 and io1/io2 can be used as boot volumes (root volume)
### General Purpose SSD (gp2/gp3)
- Cost effective storage, low-latency
- System boot volumes, Virtual desktops, Development and test environments
- 1 GiB - 16 TiB
### Provisioned IOPS (PIOPS) SSD (io1/io2)
- Critical business applications with sustained IOPS performance
- Or applications that need more than **16,000 IOPS**
- Great for databases workloads (sensitive to storage perf and consistency)
- Supports EBS Multi-attach
### Hard Disk Drives (HDD)
- **Cannot** be a boot volume
- Throughput Optimized HDD (st1): Max throughput 500 MiB/s – max IOPS 500
- Cold HDD (sc1): Max throughput 250 MiB/s – max IOPS 250

## EBS Multi-Attach – io1/io2 family
- Attach the same EBS volume to multiple EC2 instances in the same AZ
- Each EC2 instance has full read/write permissions.
- Use case:
  - Achieve higher application availability in clustered Linux applications (ex: Teradata)
  - Applications must manage concurrent write operations

# EBS Snapshots
- Make a **backup** (snapshot) of your EBS volume
- Not necessary to detach volume from EC2 instance to do snapshot, but recommended
- Exists at **Region** level, not linked to a specific AZ
- Can copy snapshots across **AZ or Region**

# EC2 Instance Store (VS EBS)
## Define
- EBS volumes are network drives with good but “**limited**” performance
- If you need a high-performance **hardware disk**, use EC2 Instance Store
## Feature
- Better I/O performance
- EC2 Instance Store lose their storage if they’re stopped (ephemeral)
- Good for buffer / cache / scratch data / **temporary content**
- Risk of data loss if hardware fails
- Backups and Replication are your responsibility

# EFS – Elastic File System
## Define
- Managed NFS (network file system) that can be mounted on many EC2
- EFS can provide access for EC2 instances in multi-AZ
- Highly available, scalable, expensive (3x gp2), pay per use
## Features
- Uses **NFSv4.1 protocol**
- Use cases: content management, web serving, data sharing, Wordpress
- **Only** Compatible with **Linux** based AMI (not Windows)

# EBS vs EFS – Elastic File System
## EBS Summary
- EBS volumes…
  - can be attached to **only one instance** at a time
  - are locked at the Availability Zone (AZ) level
  - gp2: IO increases if the disk size increases
  - io1: can increase IO independently
- To migrate an EBS volume across AZ
  - Take a snapshot
  - Restore the snapshot to another AZ
  - EBS backups should be done while detached
## EFS Summary
- Can be mounting to many many of instances across AZ at a time
- EFS share website files (WordPress)
- Only for Linux Instances (POSIX)
- EFS has a higher price point than EBS
- Can leverage EFS-IA(Infrequent Access) for cost savings
- **Remember: EFS vs EBS vs Instance Store**

# Elastic Load Balancer?
- a managed load balancer
- Health Checks: They enable the load balancer to know if instances it forwards traffic to are available to reply to requests

## Classic Load Balancers (v1 **deprecated**)
- Supports TCP (Layer 4), HTTP & HTTPS (Layer 7)
- Health checks are TCP or HTTP based
- **Fixed hostname** XXX.region.elb.amazonaws.com

## Application Load Balancer (v2)
- Application load balancers is Layer 7 (HTTP)
- ALB can **route** to multiple **target groups**
- Load balancing to multiple applications on the same machine (ex: containers)
- **In comparison, we’d need multiple Classic Load Balancer per application**
- ALB are a great fit for micro services & container-based application (example: Docker & Amazon ECS)
- Health checks are at the target group level
### Routing methods
- Routing based on path in URL (example.com/users & example.com/posts)
- Routing based on hostname in URL (one.example.com & other.example.com)
- Routing based on Query String, Headers (example.com/users?id=123&order=false)
### Good to know
- Fixed hostname (XXX.region.elb.amazonaws.com)
- The application servers don’t see the IP of the client directly
- The true IP of the client is inserted in the header **X-Forwarded-For**

## Network Load Balancer (v2)
- Network load balancers (Layer 4) (low level)
  - Forward TCP & UDP traffic to your instances
  - Handle millions of request per seconds
  - Less latency
- NLB has one static IP per AZ, and supports assigning Elastic IP (helpful for whitelisting specific IP)
- NLB are used for **extreme performance**, TCP or UDP traffic
- Not in the AWS free tier
