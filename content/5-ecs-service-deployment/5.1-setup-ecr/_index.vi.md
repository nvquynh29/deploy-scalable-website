---
title : "Tạo ECR Repository"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : "<b>5.1 </b>"
---
Hãy tải về source code dưới đây và giải nén để chuẩn bị cho các bước tiếp theo:

{{%attachments title="Source code" style="green" pattern="simple-todo-app.zip"/%}}

## Tạo ECR Repository
1. Truy cập ECR:
    - Tìm kiếm với từ khoá: `ecr`
    - Chọn **Elastic Container Registry**
    ![Create ECR Repository](../../../images/5-ecs-service-deployment/ecs_setup_ecr_1.png)
2. Tại giao diện **Amazon Elastic Container Registry**:
    - Chọn **Repositories**
    - Bấm **Create Registry**
    ![Create ECR Repository](../../../images/5-ecs-service-deployment/ecs_setup_ecr_2.png)
3. Tại giao diện **Create Registry**:
    - Visibility settings: **Public**
    - Registry name: `todo`
    ![Create ECR Repository](../../../images/5-ecs-service-deployment/ecs_setup_ecr_3.png)
4. Push Docker image to ECR:
    - Chọn **Repositories** trong phần **Public registry**
    - Chọn repository **todo** rồi bấm **View push commands**
    ![Create ECR Repository](../../../images/5-ecs-service-deployment/ecs_setup_ecr_4.png)
    - Tại folder `simple-todo-app` chạy lệnh sau:
    ```shell
    cd backend
    ```
    - Chạy lần lượt các lệnh trên giao diện của ECR.
{{% notice note %}}
Đảm bảo Docker trên máy tính của bạn đang bật trước khi chạy các lệnh này.
{{% /notice %}}
    
    Sau khi chạy xong các lệnh này chúng ta sẽ có một Docker image trên ECR repository như trong ảnh:
    ![Create ECR Repository](../../../images/5-ecs-service-deployment/ecs_setup_ecr_5.png)
5. Kiểm tra Docker image:
    - Tại giao diện ECR, chọn **Repositories** dưới phần **Public registry** rồi chọn **todo**
    ![Create ECR Repository](../../../images/5-ecs-service-deployment/ecs_setup_ecr_6.png)
    Bấm nút **Copy URI** để sao chép địa chỉ của image này.
    Hãy lưu lại địa chỉ này vì chúng ta sẽ cần dùng đến nó ở các bước tiếp theo.