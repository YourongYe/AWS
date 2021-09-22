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
we will assign permissions to AWS services with IAM Roles to access other AWS services
