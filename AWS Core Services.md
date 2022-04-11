# Elastic Cloud Compute (EC2)

Think of it as a Virtual Machine. You can run an application or your own code on this scalable virtual machine in the cloud.

Cloud computing: means a computing service that operates in remote data servers around the world, not in-house.

Elastic: means it scales up and down automatically, without you having to do anything manually. 

## Basic Unit of EC2

An EC2 instance: An instance is a computer, or let's say a virtual server with no specified operating system. 

## Amazon Machine Image

When we configure an instance on AWS, AMI is the first thing to decide and set up. It is the operating system we select for our instance and it comes along with some preinstalled applications. 

- Update Operating System  
Amazon security group takes care of the update of these available operating systems. It is important to keep them up to date to avoid security issues. 

Once an instance is created, Amazon won't update your instance's software, you need to deal with it on your own. 

## Amazon MarketPlace

Provides some other software that you want to configure on your instance. E.g. MongoDB, Firewall, etc. 


### Choose an instance Type

The specs of your instance. For example, the number of CPUs, the amount of RAM, and the network performance. 

Different families, different user cases to choose from. 


### Auto Scaling Group

You can set up your own rules to automatically scale up or down. Once we're done set up an instance, we can choose the number of instances with the same configuration. 


### Elastic Block Storage

Compared to S3, EBS is specialised for EC2 instances, but S3 is more like storing and serving independent files. 

Independent from your EC2 instances: means you can choose to retain it when you terminate your EC2 instances. 

### Security Group

A light firewall between different services or different instances. 
It controls which IP addresses your instance can talk to and which IP addresses can access your instance.



# Simple Storage Service (S3)

AWS cloud storage service. 

Basic structure: bucket as a unit, where you can store different files.

Configuration: access permission, users, URL etc.

You can host a static website using S3.

Maximum file size: 5TB


# Relational Database Service (RDS)

You can select from different database types including: MySQL, PostgresSQL, Oracle, etc.

Amazon manages the database for you:
1. Scheduled automated backups
2. Software updates
3. Infrastructure (easy to configure, no need to worry about security patches)

Route53 for URLs (solution for DNS management)

DNS: domain name system. Think of it as the internet's phonebook. It matches human-readable domain names to IP addresses, connecting you to the correct website. 

Configure Route53: means that you choose how you expose your AWS resources to users.

