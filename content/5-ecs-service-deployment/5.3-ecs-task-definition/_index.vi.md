---
title : "Tạo Task Definition"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : "<b>5.3 </b>"
---
AWS Fargate là công nghệ mà người dùng có thể sử dụng với Amazon ECS để chạy container mà không cần phải quản lý máy chủ hoặc cluster Amazon EC2. Với AWS Fargate, người dùng không còn phải cung cấp, đặt cấu hình hoặc thay đổi quy mô các cụm máy ảo để chạy container. Điều này loại bỏ nhu cầu chọn loại máy chủ, quyết định thời điểm mở rộng quy mô cụm của người dùng hoặc tối ưu hóa việc đóng gói cụm.
#### Tạo ECS Cluster
1. Truy cập ECS:
    - Tìm kiếm với từ khoá `ecs`
    - Chọn service **Elastic Container Service**
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_1.png)
2. Tại giao diện **ECS**:
    - Chọn **Clusters**
    - Bấm **Create cluster**
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_2.png)
3. Tại giao diện **Create cluster**:
    - Cluster name: `todo-ecs-cluster`
    - Infrastructure: `AWS Fargate (serverless)`
    - Bấm **Create**
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_3.png)
#### Tạo ECS Task Definition
1. Tại giao diện **ECS**:
    - Chọn **Task definitions**
    - Bấm **Create new task definition**
    - Chọn **Create new task definition**
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_4.png)
2. Tại giao diện **Create new task definition**:
    - Task definition family: `todo-ecs-task-definion`
    - Launch type: **AWS Fargate**
    - Operating system/Architecture: Tuỳ theo kiến trúc Docker image của bạn
    {{% notice note %}}
  Bước này bạn cần phải chọn đúng kiến trúc Docker image, nếu không bạn sẽ không thể triển khai ECS service được. Để biết Docker image của bạn có kiến trúc **amd** hay **arm** hãy chạy lệnh sau: `docker inspect todo:latest | grep Architecture`. Nếu kết quả là **arm64** thì hãy chọn kiến trúc **Linux/ARM64**, còn nếu không thì hãy chọn **Linux/X86_64**
    {{% /notice %}}

    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_5.png)
    - CPU: **.5 vCPU**
    - Memory: **1GB**
    - Task role: **todo-ecs-task-role**
    - Task execution role: **Create new role**
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_6.png)
    - Phần **Container-1**:
      - Name: `todo-app`
      - Image URI: ECR image URI
      - Container port: `5500`
      - Port name: `todo-server-port`
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_7.png)
    - Phần **Environment variables**:
      Bạn có thể lấy được ARN của một parameter trong Parameter Store, bằng cách xem chi tiết 
      của parameter đó như trong ảnh:
      ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_8.png)

      Thêm các biến môi trường như trong bảng dưới đây:
      | Key  | Value type  | Value  |
      |:---|:---|:---|
      | `DB_HOST`  | ValueFrom  | ARN của parameter `/todo/db-host`  |
      | `DB_PORT`  | ValueFrom  | ARN của parameter `/todo/db-port`  |
      | `DB_USER`  | ValueFrom  | ARN của parameter `/todo/db-user`  |
      | `DB_PASS`  | ValueFrom  | ARN của parameter `/todo/db-pass`  |
      | `DB_NAME`  | ValueFrom  | ARN của parameter `/todo/db-name`  |
      
      Sau khi thêm tất cả các biến thì chúng ta sẽ được như trong ảnh sau:
      ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_definition_9.png)

    Sau khi cấu hình xong hết thì bấm **Create**.

#### Cấu hình IAM policy cho ECS Task Execution Role
1. Tại giao diện ECS Task definitions:
    - Xem thông tin của task definition **todo-ecs-task-definition**
    - Bấm vào **ecsTaskExecutionRole** để xem chi tiết role đó
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_execution_role_1.png)
2. Thêm policy cho ECS Task Execution Role
    - Kéo xuống phía dưới rồi chọn **Add permissions**
    - Chọn **Create inline policy**
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_execution_role_2.png)
3. Tại giao diện **Create policy**
    - Chọn **JSON**
    - Dán đoạn IAM policy sau vào **Policy editor**, sửa `<aws_account_id>` 
    thành AWS account ID của bạn (12 chữ số) rồi bấm **Next**
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
    - Bấm **Create policy**
    ![Create ECS Task Definition](../../../images/5-ecs-service-deployment/ecs_task_execution_role_4.png)
