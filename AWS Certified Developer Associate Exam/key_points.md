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
`chmod 0400 EC2Tutorial.pem`
