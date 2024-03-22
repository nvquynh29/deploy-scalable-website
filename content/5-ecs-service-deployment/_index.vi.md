---
title : "ECS Service"
date : "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

#### ECS Service

Trong phần này chúng ta sẽ cùng triển khai cơ sở dữ liệu bằng dịch vụ Amazon RDS đồng thời chuẩn bị một cơ sở dữ liệu và tạo các bảng cần thiết. Ngoài ra chúng ta sẽ lưu các thông tin cấu hình bằng chức năng Parameter Store thay vì lưu trực tiếp trong source code, giúp tăng tính bảo mật của hệ thống và giúp cho việc quản lý, thay đổi cấu hình dễ dàng hơn.

#### Nội dung

- [Tạo ECR Repository](5.1-setup-ecr/)
- [Tạo IAM Role](5.2-iam-role/)
- [Tạo Task Definition](5.3-ecs-task-definition/)
- [Tạo ALB](5.4-setup-alb/)
- [Triển khai ECS Service](5.5-deploy-ecs-service/)
