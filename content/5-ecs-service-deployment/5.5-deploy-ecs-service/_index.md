---
title : "Deploy ECS Service"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : "<b>5.5 </b>"
---
#### Deploy ECS Service
1. Within **todo-ecs-cluster** interface:
    - Select **Services** tab
    - Click **Create**
    ![Deploy ECS Service](../../../images/5-ecs-service-deployment/ecs_deploy_service_1.png)
2. Within **Create service** interface:
    - Environment:
      - Compute options: **Launch type**
    ![Deploy ECS Service](../../../images/5-ecs-service-deployment/ecs_deploy_service_2.png)
    - Application type: **Service**
    - Task definition:
      - Family: **todo-ecs-task-definition**
      - Service name: `todo-ecs-service`
      - Service type: **Replica**
      - Desired tasks: `2`
    ![Deploy ECS Service](../../../images/5-ecs-service-deployment/ecs_deploy_service_3.png)
    - VPC: **todo-vpc**
    - Subnets: **private-subnet-az-1** and **private-subnet-az-2**
    - Security group:
      - Use an existing security group
      - Select **todo-ecs-sg**
    ![Deploy ECS Service](../../../images/5-ecs-service-deployment/ecs_deploy_service_4.png)
    - Load balancing:
      - Load balancer type: **Application Load Balancer**
      - Container: **todo-app 5500:5500**
      - Load balancer: Select **Use an existing security group** then select **todo-alb**
      - Health check grace period: `10`
    ![Deploy ECS Service](../../../images/5-ecs-service-deployment/ecs_deploy_service_5.png)
      - Listener: Select **Use an existing listener** then select **80:HTTP**
      - Target group: Select **Use an existing target group** then select **todo-ecs-tg**
    ![Deploy ECS Service](../../../images/5-ecs-service-deployment/ecs_deploy_service_6.png)
    - Service auto scaling:
      - Select **Use service auto scaling**
      - Minimum number of tasks: `1`
      - Maximum number of tasks: `3`
      - Scaling policy type: **Target tracking**
      - Policy name: `avg-cpu-scaling-policy`
      - ECS service metric: **ECSServiceAverageCPUUtilization**
      - Target value: `70`
    ![Deploy ECS Service](../../../images/5-ecs-service-deployment/ecs_deploy_service_7.png)
    
    Leave other configurations as default and then click **Create**.
    ![Deploy ECS Service](../../../images/5-ecs-service-deployment/ecs_deploy_service_8.png)
3. Access ECS service:
    - After deployment is complete, the ECS service will have a status as shown in the image below:
    ![Deploy ECS Service](../../../images/5-ecs-service-deployment/ecs_deploy_service_9.png)
    - Return to the **Load balancers** interface and copy the DNS name of **todo-alb**:
    ![Deploy ECS Service](../../../images/5-ecs-service-deployment/ecs_deploy_service_10.png)

    Access this address in your browser and you will see the following result:
    ```json
    {"message":"Welcome to the Todo API"}
    ```
