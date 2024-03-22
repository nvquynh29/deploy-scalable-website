---
title : "Create ALB"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : "<b>5.4 </b>"
---
#### Create ALB
1. Access **EC2**:
    - Search keyword: `ec2`
    - Select **EC2** service
    ![Create ALB](../../../images/5-ecs-service-deployment/ecs_setup_alb_1.png)
2. Create **Target group**:
    - Within EC2 interface, select **Target group**
    - Click **Create target group**
    ![Create ALB](../../../images/5-ecs-service-deployment/ecs_setup_alb_2.png)
3. Within **Create target group** interface:
    - Type: **IP address**
    - Target group name: `todo-ecs-tg`
    - Protocol: **HTTP**
    - Port: `5500`
    ![Create ALB](../../../images/5-ecs-service-deployment/ecs_setup_alb_3.png)
    - VPC: `todo-vpc`
    - Click **Next**
    ![Create ALB](../../../images/5-ecs-service-deployment/ecs_setup_alb_4.png)
4. Within **Register targets** interface:
    - Click **Remove**
    ![Create ALB](../../../images/5-ecs-service-deployment/ecs_setup_alb_5.png)
    - Click **Create target group**
    ![Create ALB](../../../images/5-ecs-service-deployment/ecs_setup_alb_6.png)
5. Within **EC2** interface:
    - Select **Load Balancers**
    - Click **Create load balancer**
    ![Create ALB](../../../images/5-ecs-service-deployment/ecs_setup_alb_7.png)
    - Click **Create** under **Application Load Balancer**
    ![Create ALB](../../../images/5-ecs-service-deployment/ecs_setup_alb_8.png)
6. Within **Create load balancer** interface:
    - Load balancer name: `todo-alb`
    - Scheme: **Internet-facing**
    ![Create ALB](../../../images/5-ecs-service-deployment/ecs_setup_alb_9.png)
    - **Network mapping**:
      - VPC: **todo-vpc**
      - Mappings: Select 2 public subnets **public-subnet-az-1** and **public-subnet-az-2**
    ![Create ALB](../../../images/5-ecs-service-deployment/ecs_setup_alb_10.png)
    - Security groups: **todo-alb-sg**
    - Listeners and routing:
      - Protocol: **HTTP**
      - Port: `80`
      - Default action: **todo-ecs-tg**
    ![Create ALB](../../../images/5-ecs-service-deployment/ecs_setup_alb_11.png)