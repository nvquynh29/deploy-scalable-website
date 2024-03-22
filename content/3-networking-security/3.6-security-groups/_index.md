---
title : "Create Security Groups"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : "<b>3.6 </b>"
---
## Create Security Groups
1. Within **VPC** interface:
    - Select **Security groups**
    - Click on **Create security group**
    ![Create Security Groups](/images/3-networking-security/vpc_create_sg_1.png)
2. Within **Create security group** interface:
    - Security group name: `todo-alb-sg`
    - Description: `Allows HTTP access to ALB`
    - VPC: **todo-vpc**
    - In the **Inbound rules** configuration section, add a new rule as follows and then click **Create security group**
      - Type: **HTTP**
      - Source: **Anywhere-IPv4**
    ![Create Security Groups](/images/3-networking-security/vpc_create_sg_2.png)
3. Create additional security groups with the following configuration:
    - Security group name: `todo-ecs-sg`
    - Description: `Allows ALB access to ECS service`
    - VPC: **todo-vpc**
    - Inbound rule: 
      - Type: **Custom TCP**
      - Port: `5500`
      - Source: `todo-alb-sg`
      ![Create Security Groups](/images/3-networking-security/vpc_create_sg_3.png)
{{% notice note %}}
The port number is `5500` and not another number because the backend container runs on port 5500. We will configure it in the next steps.
{{% /notice %}}
    - Security group name: `todo-db-sg`
    - Description: `Allows RDS access to ECS service`
    - VPC: **todo-vpc**
    - Inbound rule: 
      - Type: **MySQL/Aurora**
      - Source: `todo-ecs-sg`
    ![Create Security Groups](/images/3-networking-security/vpc_create_sg_4.png)