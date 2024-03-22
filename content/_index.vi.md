---
title : "Triển khai trang hệ thống có khả năng mở rộng với CloudFront, ECS Fargate"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---

# Triển khai trang hệ thống có khả năng mở rộng với CloudFront, ECS Fargate

#### Tổng quan
Trong bài lab này, chúng ta sẽ triển khai một ứng dụng web đơn giản lên AWS sử dụng các service như CloudFront, Elastic Container Service (ECS), Amazon RDS, Route53. Website được triển khai theo cách này giúp tăng tính sẵn sàng, và khả năng mở rộng mà không cần phải quản lý máy chủ vật lý nào.


#### Sơ đồ kiến trúc
![Architecture Diagram](../../../images/architecture_diagram.svg)

#### Nội dung

1. [Giới thiệu](1-introduce/)
2. [Chuẩn bị](2-preparation/)
3. [Mạng vào bảo mật](3-networking-security/)
4. [Triển khai cơ sở dữ liệu](4-database-deployment/)
5. [Triển khai ECS Service](5-ecs-service-deployment/)
6. [Triển khai CloudFront](6-cloudfront-deployment/)
7. [Cấu hình Route53](7-route53/)
8. [Dọn dẹp tài nguyên](8-cleanup/)
