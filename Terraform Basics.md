# Introduction

A tool to automate the deployment of infrastructure across multiple providers in the public and private cloud.

# Infrastructure as Code

Definition

Use software to do the infrastructure configuration. 

The environment set up by software will be consistent and predictable. 


# Core concepts:
1. You define your infrastructure using coding, instead of manually setting it up.
2.  The code should be stored and version controlled (source controlled).
3. Two ways of defining your infrastructure in code: declarative and imperative. 
4. Idempotent and consistency

# Declarative:
Means we just declare what we need and let the software to figure out how to implement it. 

# Idempotent:
It won't do the same thing again if you assigned the same tasks for twice. 
In other words, if you run the same configuration code again, because the existing environment already has the same configuration, so it won’t configure it again, and so nothing will change.

 => (Terraform is declarative and idempotent.)


Benefits of using Infrastructure as Code (IaC)

1. Automated deployment of the infrastructure
2. Consistent environment (manual configuration may not achieve)
3. Repeatable process (once you write the code, it is repeatable)
4. Reusable components (DRY principle.)
5. Documented architecture (you have all your configuration noted and documented during this process, easier for back-checking if something goes wrong)

