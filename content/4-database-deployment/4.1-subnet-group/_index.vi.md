---
title : "Tạo Subnet Group"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : "<b>4.1 </b>"
---
## Tạo Subnet Group
Database subnet group được dùng để nhóm những subnet được chỉ định dành cho database. Khi khởi tạo, database chỉ có thể thuộc trong một trong các subnet của subnet group.

Một subnet group có các subnet ở ít nhất hai vùng sẵn sàng trong region của subnet group đó. Các subnet trong subnet group có thể là public hoặc private, tùy thuộc vào cấu hình Network ACL và route table của chúng.

Để bảo mật, các subnet trong subnet group thường là private subnet. Nếu cơ sở dữ liệu phải có thể truy cập công khai thì tất cả các subnet trong subnet group của nó phải là public subnet.
1. Tại giao diện **AWS Management Console**:
    - Search từ khoá **RDS**
    - Chọn **RDS**
    ![Create Subnet Group](../../../images/4-database-deployment/rds_create_subnet_group_1.png)
2. Tại giao diện của **Amazon RDS**:
    - Chọn **Subnet groups**
    - Bấm **Create DB subnet group**
    ![Create Subnet Group](../../../images/4-database-deployment/rds_create_subnet_group_2.png)
3. Tại giao diện **Create DB subnet group**:
    - Name: `todo-db-subnet-group`
    - Description: `Subnet group for todo DB`
    - VPC: **todo-vpc**
4. Tại phần **Add subnets**:
    - Chọn availability zone: **ap-southeast-1a** và **ap-southeast-1b**
    ![Create Subnet Group](../../../images/4-database-deployment/rds_create_subnet_group_3.png)
    - Subnets: **private-subnet-az-1 (10.0.1.0/24)** và **private-subnet-az-2 (10.0.3.0/24)**
    ![Create Subnet Group](../../../images/4-database-deployment/rds_create_subnet_group_4.png)
    - Bấm **Create**
