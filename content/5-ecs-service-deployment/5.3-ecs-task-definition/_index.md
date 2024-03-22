---
title : "Create Task Definition"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : "<b>5.3 </b>"
---
#### Create ECS Cluster
AWS Fargate is a technology that you can use with Amazon ECS to run containers without having to manage servers or clusters of Amazon EC2 instances. With AWS Fargate, you no longer have to provision, configure, or scale clusters of virtual machines to run containers. This removes the need to choose server types, decide when to scale your clusters, or optimize cluster packing.
1. Access ECS:
    - Search keyword: `ecs`
    - Select **Elastic Container Service**
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_1.png)
2. Within **ECS** interface:
    - Select **Clusters**
    - Click **Create cluster**
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_2.png)
3. Within **Create cluster** interface:
    - Cluster name: `todo-ecs-cluster`
    - Infrastructure: `AWS Fargate (serverless)`
    - Click **Create**
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_3.png)
#### Create ECS Task Definition
1. Within **ECS** interface:
    - Select **Task definitions**
    - Click **Create new task definition**
    - Select **Create new task definition**
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_4.png)
2. Within **Create new task definition** interface:
    - Task definition family: `todo-ecs-task-definion`
    - Launch type: **AWS Fargate**
    - Operating system/Architecture: Depending on your Docker image architecture
    {{% notice note %}}
  In this step, you need to choose the right Docker image architecture, otherwise you will not be able to deploy the ECS service. To see if your Docker image has an **amd** or **arm** architecture, run the following command: `docker inspect todo:latest | grep Architecture`. If the result is **arm64** then select the architecture **Linux/ARM64**, otherwise select **Linux/X86_64**
    {{% /notice %}}

    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_5.png)
    - CPU: **.5 vCPU**
    - Memory: **1GB**
    - Task role: **todo-ecs-task-role**
    - Task execution role: **Create new role**
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_6.png)
    - Section **Container-1**:
      - Name: `todo-app`
      - Image URI: ECR image URI
      - Container port: `5500`
      - Port name: `todo-server-port`
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_7.png)
    - Section **Environment variables**:
      You can get the ARN of a parameter in the Parameter Store by viewing the details
      of that parameter as shown in the picture:
      ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_8.png)

      Add environment variables as shown in the table below:
      | Key  | Value type  | Value  |
      |:---|:---|:---|
      | `DB_HOST`  | ValueFrom  | ARN of parameter `/todo/db-host`  |
      | `DB_PORT`  | ValueFrom  | ARN of parameter `/todo/db-port`  |
      | `DB_USER`  | ValueFrom  | ARN of parameter `/todo/db-user`  |
      | `DB_PASS`  | ValueFrom  | ARN of parameter `/todo/db-pass`  |
      | `DB_NAME`  | ValueFrom  | ARN of parameter `/todo/db-name`  |
      
      After adding all the variables, we will get something like in the following image:
      ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_9.png)

    After completing the configuration, click **Create**.

#### Configure IAM policy for ECS Task Execution Role
1. Within ECS Task definitions interface:
    - View details of task definition **todo-ecs-task-definition**
    - Click **ecsTaskExecutionRole** to see details of this role
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_execution_role_1.png)
2. Add policy for ECS Task Execution Role:
    - Scroll down and select **Add permissions**
    - Select **Create inline policy**
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_execution_role_2.png)
3. Within **Create policy** interface:
    - Select **JSON**
    - Paste the following IAM policy into the **Policy editor**, replace `<aws_account_id>`
    with your AWS account ID (12 digits) then Click **Next**
    ```json
    {
      "Version": "2012-10-17",
      "Statement": [
        {
          "Effect": "Allow",
          "Action": [
            "ssm:GetParameters",
            "kms:Decrypt"
          ],
          "Resource": [
            "arn:aws:ssm:ap-southeast-1:<aws_account_id>:parameter/*",
            "arn:aws:kms:ap-southeast-1:<aws_account_id>:key/*"
          ]
        }
      ]
    }
    ```
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_execution_role_3.png)
    - Policy name: `ssm-parameter-store-read-only-region-singapore-policy`
    - Click **Create policy**
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_execution_role_4.png)
