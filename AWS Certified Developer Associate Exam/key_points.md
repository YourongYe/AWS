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
EBS are more flexible, since you can attach and detach it from instances, but is a little bit slower, as more suitable for general purpose.
