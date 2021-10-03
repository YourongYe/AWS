# How to choose an AWS Region?
- Compliance with  data  governance  and  legal requirements:  data  never  leaves  a  region  without your  explicit  permission 
- Proximity to  customers:  reduced  latency
- Available  services within  a  Region:  new  services and  new  features  aren’t  available  in  every  Region
- Pricing:  pricing  varies  region  to  region  and  is transparent  in  the  service  pricing  page

# How can users access AWS ?
- AWS Management Console (protected by password + MFA)
- AWS Command Line Interface (CLI): protected by access keys
- AWS Software Developer Kit (SDK) - for code: protected by access keys (Eg. boto3)

# What is the difference between EBS and SSD in AWS?
- SSD are faster because there's no network latency, but you can't detach it from an instance and attach it to another. 
- EBS are more flexible, since you can attach and detach it from instances, but is a little bit slower, as more suitable for general purpose.

# What does Security Group do?
They regulate:
- Access to Ports
- Authorised IP ranges – IPv4 and IPv6
- Control of inbound network (from other to the instance)
- Control of outbound network (from the instance to other)
- Example: port 80 only allows IP address range: 0.222.222.0 - 0.333.333.0

# Why am I getting "UNPROTECTED PRIVATE KEY FILE" warning when SSH to EC2 on Mac/LInux?
Because when you first download the file, the access permission of the file is 0644, which is too open, so it will treat it as a bad permission private key file.   
## How to do with it?
We need to change the access permission of the file using the command:
`chmod 0400 EC2Tutorial.pem` to change the acess permission of the key file.   
And then ssh into the EC2 again using the command: `ssh -i EC2Tutorial.pem <username>@<public IP address of the EC2>`

# How can we access AWS from our EC2 Instance?
1. Go to AWS console and choose the instance you want to log in
2. Connect to the instance from the console (make sure the SSH security port 22 is open to all)
3. Now we are in the EC2 Instance Connect (terminal)
4. Create a policy that has readonly permission to AWS IAM and then attche this policy to a new defined role
5. Then in the instance page, attch this role to this EC2 instance
6. Go back to EC2 Instance Connect, and try command: `aws iam list-users`, and now you can see the user details

**Attention**: never use AWS credentials to log into AWS from your EC2 instance, cus others can access the instance and will be able to see it.

# How to copy volume across AZ or Regions?
1. Create a snaptshot from an EBS volume
## To another Region
2. Copy that snapshot to another region
3. Create a volume in an AZ from this copied snapshot

## To another AZ
2. Create a volume in antoher AZ from this snapshot


# How can we create our own AMI?
1. Launch a new instance
2. Configuring this instance with all the initial setup
3. Create an AMI from this instance (all the setup on this instance (including user data script) will be backedup as a new AMI), this will also create EBS snapshots
4. Next time, when we want to launch instance with the same setup, just choose our own AMI during the configuration and then launch it
