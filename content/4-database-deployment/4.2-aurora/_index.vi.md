---
title : "Tạo Database"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : "<b>4.2 </b>"
---
## Tạo Database
1. Tại giao diện **Amazon RDS**:
    - Chọn **Databases**
    - Bấm **Create database**
    ![Create Database](/images/4-database-deployment/rds_create_db_1.png)
2. Tại giao diện **Create database** cấu hình như sau:
    - Creation method: **Standard create**
    - Engine options: **Aurora (MySQL Compatible)**
    - Engine Version: **Aurora MySQL 3.04.1**
    - Templates: **Dev/Test**
    ![Create Database](/images/4-database-deployment/rds_create_db_2.png)
    - DB cluster identifier: `todo-db`
    - Credentials Settings:
      - Master password: Đặt mật khẩu cho database của bạn (VD: `password`)
    ![Create Database](/images/4-database-deployment/rds_create_db_3.png)
    - Instance configuration:
      - DB instance class: **Burstable classes (includes t classes)**
      - DB type: **db.t3.medium**
    - Availability & durability: **Create an Aurora Replica or Reader node in a different AZ (recommended for scaled availability)**
    ![Create Database](/images/4-database-deployment/rds_create_db_4.png)
    - Connectivity:
      - VPC: **todo-vpc**
      ![Create Database](/images/4-database-deployment/rds_create_db_5.png)
      - DB subnet group: **todo-db-subnet-group**
      - Public access: **No**
      - VPC security group:
        - Chọn **Choose existing**
        - Chọn **todo-db-sg**
      ![Create Database](/images/4-database-deployment/rds_create_db_6.png)
  
    Sau khi cấu hình xong thì bấm **Create database**.

    Khi tạo cơ sở dữ liệu thành công, giao diện sẽ giống như trong ảnh dưới đây:
    ![Create Database](/images/4-database-deployment/rds_create_db_7.png)
 