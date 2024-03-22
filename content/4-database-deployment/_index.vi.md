---
title : "Cơ sở dữ liệu"
date : "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4. </b> "
---

#### Cơ sở dữ liệu

Trong phần này chúng ta sẽ cùng triển khai cơ sở dữ liệu bằng dịch vụ Amazon RDS đồng thời chuẩn bị một cơ sở dữ liệu và tạo các bảng cần thiết. Ngoài ra chúng ta sẽ lưu các thông tin cấu hình bằng chức năng Parameter Store thay vì lưu trực tiếp trong source code, giúp tăng tính bảo mật của hệ thống và giúp cho việc quản lý, thay đổi cấu hình dễ dàng hơn.

#### Nội dung

- [Tạo Subnet Group](4.1-subnet-group/)
- [Tạo Database](4.2-aurora/)
- [Cấu hình Database](4.3-configure-database/)
- [Tạo Parameters](4.4-parameter-store/)
