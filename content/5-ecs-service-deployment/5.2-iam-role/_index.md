---
title : "Create IAM Role"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : "<b>5.2 </b>"
---
## Create IAM Role
1. Access IAM:
    - Search keyword: `iam`
    - Select **IAM** service
    ![Create ECS Task Role](/images/5-ecs-service-deployment/ecs_task_role_1.png)
2. Within **IAM** interface:
    - Select **Roles**
    - Select **Create role**
    ![Create ECS Task Role](/images/5-ecs-service-deployment/ecs_task_role_2.png)
3. Within **Create role** interface:
    - Select type **AWS service**
    - Search keyword: `elastic`
    - Select **Elastic Container Service**
    ![Create ECS Task Role](/images/5-ecs-service-deployment/ecs_task_role_3.png)
    - Select use case **Elastic Container Service Task**
    - Click **Next**
    ![Create ECS Task Role](/images/5-ecs-service-deployment/ecs_task_role_4.png)
    - In step 2 (Add permissions) search for `AmazonRDSDataFullAccess` and select this policy
    - Click **Next**
    ![Create ECS Task Role](/images/5-ecs-service-deployment/ecs_task_role_5.png)
    - Step 3:
      - Role name: `todo-ecs-task-role`
      - Description: `Allow RDS access to ECS tasks`
      - Click **Create role**
    ![Create ECS Task Role](/images/5-ecs-service-deployment/ecs_task_role_6.png)
