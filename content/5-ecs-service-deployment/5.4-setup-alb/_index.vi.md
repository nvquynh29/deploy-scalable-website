---
title : "Tạo ALB"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : "<b>5.4 </b>"
---
#### Tạo ALB
1. Truy cập **EC2**:
    - Tìm kiếm với từ khoá: `ec2`
    - Chọn **EC2**
    ![Create ALB](/images/5-ecs-service-deployment/ecs_setup_alb_1.png)
2. Tạo **Target group**:
    - Tại giao diện EC2, chọn **Target group**
    - Bấm **Create target group**
    ![Create ALB](/images/5-ecs-service-deployment/ecs_setup_alb_2.png)
3. Tại giao diện **Create target group**:
    - Type: **IP address**
    - Target group name: `todo-ecs-tg`
    - Protocol: **HTTP**
    - Port: `5500`
    ![Create ALB](/images/5-ecs-service-deployment/ecs_setup_alb_3.png)
    - VPC: `todo-vpc`
    - Bấm **Next**
    ![Create ALB](/images/5-ecs-service-deployment/ecs_setup_alb_4.png)
4. Tại giao diện **Register targets**:
    - Bấm **Remove**
    ![Create ALB](/images/5-ecs-service-deployment/ecs_setup_alb_5.png)
    - Bấm **Create target group**
    ![Create ALB](/images/5-ecs-service-deployment/ecs_setup_alb_6.png)
5. Tại giao diện **EC2**:
    - Chọn **Load Balancers**
    - Bấm **Create load balancer**
    ![Create ALB](/images/5-ecs-service-deployment/ecs_setup_alb_7.png)
    - Bấm **Create** ở phần **Application Load Balancer**
    ![Create ALB](/images/5-ecs-service-deployment/ecs_setup_alb_8.png)
6. Tại giao diện **Create load balancer**:
    - Load balancer name: `todo-alb`
    - Scheme: **Internet-facing**
    ![Create ALB](/images/5-ecs-service-deployment/ecs_setup_alb_9.png)
    - **Network mapping**:
      - VPC: **todo-vpc**
      - Mappings: Chọn 2 public subnets **public-subnet-az-1** và **public-subnet-az-2**
    ![Create ALB](/images/5-ecs-service-deployment/ecs_setup_alb_10.png)
    - Security groups: **todo-alb-sg**
    - Listeners and routing:
      - Protocol: **HTTP**
      - Port: `80`
      - Default action: **todo-ecs-tg**
    ![Create ALB](/images/5-ecs-service-deployment/ecs_setup_alb_11.png)