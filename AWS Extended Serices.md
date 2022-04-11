# Elastic Beanstalk

A smarter way of getting your code / application to run on EC2 instances with scalability. It often comes with EC2 instances, S3 and load balancer.

If we choose to manually deploy it on EC2 instances:
1. Manual configuration
2. Manual code deployment
3. Manual set up for AMIs when scaling
4. Manual monitoring


However, if we use EB:

1. Easy configuration and deployment 
2. Aggregated monitoring even your application runs on multiple instances.

## Structure:

An application, many application versions, two environments: test environment and production environment.

Actual files and your code are stored in S3 buckets.  

# Lambda (Function as a service)

You provide some code and lambda will run it for you without any configuration needed. 

Scalability: it automatically run your code on as many servers as needed. 

# Virtual Private Cloud (VPC)

Structure: it contains a subnet  or subnets that can group your resources with given rules. Like a private network only for your server. Increase safety.

# CloudWatch

For monitoring and alarms. 

Logs can be set up in EC2 instances. 

# CloudFront 

A content delivery network. Aim to reduce latency around the world. 

Allows us to serve(send and fetch) files globally with very fast connections. It serves your content from the location that is closest to your users. 

Structure: distribution of your content. Set up your original location (such as S3), and edge locations.

# Simple Queue Service (SQS)
Message queue, can set up to trigger lambda. Normally a lambda is tied with a trigger (sqs, sns, event rules)

