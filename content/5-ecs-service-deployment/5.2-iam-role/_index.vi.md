---
title : "Tạo IAM Role"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : "<b>5.2 </b>"
---
## Tạo IAM Role
1. Truy cập IAM:
    - Tìm kiếm với từ khoá `iam`
    - Chọn service **IAM**
    ![Create ECS Task Role](../../../images/5-ecs-service-deployment/ecs_task_role_1.png)
2. Tại giao diện **IAM**:
    - Chọn **Roles**
    - Chọn **Create role**
    ![Create ECS Task Role](../../../images/5-ecs-service-deployment/ecs_task_role_2.png)
3. Tại giao diện **Create role**:
    - Chọn type **AWS service**
    - Tìm kiếm với từ khoá `elastic`
    - Chọn **Elastic Container Service**
    ![Create ECS Task Role](../../../images/5-ecs-service-deployment/ecs_task_role_3.png)
    - Chọn use case **Elastic Container Service Task**
    - Bấm **Next**
    ![Create ECS Task Role](../../../images/5-ecs-service-deployment/ecs_task_role_4.png)
    - Tại bước 2 (Add permissions) tìm kiếm `AmazonRDSDataFullAccess` và chọn policy này
    - Bấm **Next**
    ![Create ECS Task Role](../../../images/5-ecs-service-deployment/ecs_task_role_5.png)
    - Tại bước 3:
      - Role name: `todo-ecs-task-role`
      - Description: `Allow RDS access to ECS tasks`
      - Bấm **Create role**
    ![Create ECS Task Role](../../../images/5-ecs-service-deployment/ecs_task_role_6.png)
