# 3 Tier Web Application Architecture Using Terraform and AWS


## Overview
This is a common cloud architecture: An internet-facing Application Load Balancer (ALB) forwards traffic to the web tier of EC2 instances. Those instances are running Nginx webservers that are configured to serve a React.js website and redirects API calls to the application tier’s internal-facing ALB. That internal ALB forwards that traffic to the Node.js application tier of EC2 instances. The application tier manipulates data in an Aurora MySQL multi-AZ database cluster and returns it to our web tier. Load balancing, health checks and autoscaling groups are created at each layer to maintain the availability of this architecture. Here is 
an example of this in the [AWS workshop](http://catalog.us-east-1.prod.workshops.aws/workshops/85cd2bb2-7f79-4e96-bdee-8078e469752a/en-US)

The problem comes in with the time it takes to do this: AWS says this workshop can **take around 3 hours**, maybe even longer if you're struggling with the tutorial.

                                

This won't do in a corporate environment and you'll need to use some sort of automation or infrastructure as code (IaC) tool like HashiCorp's Terraform to manage this process to make it faster.

**WITH 1 Click**