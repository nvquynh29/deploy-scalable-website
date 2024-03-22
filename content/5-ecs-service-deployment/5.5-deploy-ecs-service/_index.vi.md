---
title : "Triển khai ECS Service"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : "<b>5.5 </b>"
---
#### Triển khai ECS Service
1. Tại giao diện **todo-ecs-cluster**:
    - Chọn tab **Services**
    - Bấm **Create**
    ![Deploy ECS Service](/images/5-ecs-service-deployment/ecs_deploy_service_1.png)
2. Tại giao diện **Create service**:
    - Environment:
      - Compute options: **Launch type**
    ![Deploy ECS Service](/images/5-ecs-service-deployment/ecs_deploy_service_2.png)
    - Application type: **Service**
    - Task definition:
      - Family: **todo-ecs-task-definition**
      - Service name: `todo-ecs-service`
      - Service type: **Replica**
      - Desired tasks: `2`
    ![Deploy ECS Service](/images/5-ecs-service-deployment/ecs_deploy_service_3.png)
    - VPC: **todo-vpc**
    - Subnets: **private-subnet-az-1** và **private-subnet-az-2**
    - Security group:
      - Use an existing security group
      - Chọn **todo-ecs-sg**
    ![Deploy ECS Service](/images/5-ecs-service-deployment/ecs_deploy_service_4.png)
    - Load balancing:
      - Load balancer type: **Application Load Balancer**
      - Container: **todo-app 5500:5500**
      - Load balancer: Chọn **Use an existing security group** rồi chọn **todo-alb**
      - Health check grace period: `10`
    ![Deploy ECS Service](/images/5-ecs-service-deployment/ecs_deploy_service_5.png)
      - Listener: Chọn **Use an existing listener** rồi chọn **80:HTTP**
      - Target group: Chọn **Use an existing target group** rồi chọn **todo-ecs-tg**
    ![Deploy ECS Service](/images/5-ecs-service-deployment/ecs_deploy_service_6.png)
    - Service auto scaling:
      - Chọn **Use service auto scaling**
      - Minimum number of tasks: `1`
      - Maximum number of tasks: `3`
      - Scaling policy type: **Target tracking**
      - Policy name: `avg-cpu-scaling-policy`
      - ECS service metric: **ECSServiceAverageCPUUtilization**
      - Target value: `70`
    ![Deploy ECS Service](/images/5-ecs-service-deployment/ecs_deploy_service_7.png)
    
    Các cấu hình khác để mặc định rồi bấm **Create**.
    ![Deploy ECS Service](/images/5-ecs-service-deployment/ecs_deploy_service_8.png)
3. Truy cập ECS service:
    - Sau khi triển khai xong, ECS service sẽ có trạng thái như trong ảnh dưới đây:
    ![Deploy ECS Service](/images/5-ecs-service-deployment/ecs_deploy_service_9.png)
    - Quay lại giao diện **Load balancers** rồi sao chép DNS name của **todo-alb**:
    ![Deploy ECS Service](/images/5-ecs-service-deployment/ecs_deploy_service_10.png)

    Truy cập địa chỉ này trên trình duyệt bạn sẽ thấy kết quả như sau:
    ```json
    {"message":"Welcome to the Todo API"}
    ```
