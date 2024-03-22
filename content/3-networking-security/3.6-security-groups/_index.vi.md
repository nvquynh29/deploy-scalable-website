---
title : "Tạo Security Groups"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : "<b>3.6 </b>"
---
## Tạo Security Groups
1. Tại giao diện **VPC**:
    - Chọn **Security groups**
    - Bấm **Create security group**
    ![Create Security Groups](/images/3-networking-security/vpc_create_sg_1.png)
2. Tại giao diện **Create security group**:
    - Security group name: `todo-alb-sg`
    - Description: `Allows HTTP access to ALB`
    - VPC: **todo-vpc**
    - Tại phần cấu hình **Inbound rules** thêm rule mới như sau rồi bấm **Create security group**
      - Type: **HTTP**
      - Source: **Anywhere-IPv4**
    ![Create Security Groups](/images/3-networking-security/vpc_create_sg_2.png)
3. Tạo thêm các security group với cấu hình như sau:
    - Security group name: `todo-ecs-sg`
    - Description: `Allows ALB access to ECS service`
    - VPC: **todo-vpc**
    - Inbound rule: 
      - Type: **Custom TCP**
      - Port: `5500`
      - Source: `todo-alb-sg`
      ![Create Security Groups](/images/3-networking-security/vpc_create_sg_3.png)
{{% notice note %}}
Port number là `5500` mà không phải số khác là bởi vì container backend chạy trên port 5500. Chúng ta sẽ cùng cấu hình nó ở các bước tiếp theo.
{{% /notice %}}
    - Security group name: `todo-db-sg`
    - Description: `Allows RDS access to ECS service`
    - VPC: **todo-vpc**
    - Inbound rule: 
      - Type: **MySQL/Aurora**
      - Source: `todo-ecs-sg`
    ![Create Security Groups](/images/3-networking-security/vpc_create_sg_4.png)