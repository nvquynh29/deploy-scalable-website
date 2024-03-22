---
title : "Cấu hình Database"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : "<b>4.3 </b>"
---
## Cấu hình Database
Ở bước này, chúng ta sẽ tạo cơ sở dữ liệu và các bảng cần thiết. 

RDS database của chúng ta đã được cấu hình không cho phép truy cập công khai để tăng tính bảo mật nên chỉ có thể truy cập được bằng các tài nguyên trong cùng VPC. Do đó chúng ta sẽ dùng một EC2 instance trong cùng VPC để kết nối đến và truy vấn database. Vì trong source code không có sẵn database migrations cho nên mới cần phải thực hiện bước này thủ công, trên thực tế chúng ta sẽ không phải thực hiện bước này nếu đã có database migrations.

1. Tại giao diện **Amazon RDS**:
    - Chọn database **todo-db**
    - Kéo xuống dưới, chọn tab **Connectivity & Security**
    - Copy endpoint có type là **Writer** và lưu lại
    ![Configure Database](/images/4-database-deployment/rds_configure_db_1.png)
2. Truy cập vào dịch vụ EC2:
    - Tìm kiếm từ khoá: `ec2`
    - Chọn dịch vụ **EC2**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_2.png)
    - Bấm **Launch instance**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_3.png)
3. Tại giao diện **Launch an instance**:
    - Amazon Machine Image (AMI): **Amazon Linux 2 AMI**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_4.png)
    - Tạo Key pair mới:
        - Key pair name: `configure-db-key`
        - Key pair type: **RSA**
    - Bấm **Create key pair**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_5.png)
    - Network settings:
        - VPC: **todo-vpc**
        - Subnet: **public-subnet-az-1**
        - Security group: **todo-ecs-sg**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_6.png)
{{% notice note %}}
Chúng ta chọn security group **todo-ecs-sg** vì database đã được cấu hình sẵn cho phép truy cập từ security group này.
{{% /notice %}}
4. Tại giao diện **EC2**:
    - Chọn **Security Groups**
    - Chọn **todo-ecs-sg**
    - Chọn **Actions** rồi chọn **Edit inbound rules**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_7.png)
    - Thêm inbound rule mới với type SSH, source **Anywhere-IPv4**
    - Bấm **Save rules**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_8.png)
5. Tại giao diện **EC2**:
    - Chọn **Instances**
    - Chọn EC2 instance vừa tạo
    - Bấm **Connect**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_9.png)
    - Giữ nguyên các cấu hình mặc định, bấm **Connect**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_10.png)
6. Cấu hình database:
    
Sau khi kết nối được đến EC2 instance, chạy các lệnh sau:
```shell
sudo su
yum update -y
yum install mysql -y
```

Thay `<todo_db_write_endpoint>` bằng endpoint bạn đã copy rồi kết nối đến database bằng lệnh sau:
```shell
mysql -h <todo_db_write_endpoint> -u admin -p
```

Sau khi nhập password, chúng ta sẽ kết nối được đến database. Chạy các lệnh sau để tạo các bảng cần thiết:
```sql
CREATE DATABASE todos;
USE todos;
CREATE TABLE `todos` (
    `id` VARCHAR(40) PRIMARY KEY,
    `name` VARCHAR(255) NOT NULL,
    `description` VARCHAR(255) NULL,
    `status` BOOLEAN NOT NULL DEFAULT 0
);
```

Nếu như không có lỗi gì xảy ra thì bạn đã cấu hình database thành công.

7. Dọn dẹp tài nguyên
    - Quay lại giao diện EC2 rồi terminate EC2 instance vừa tạo
    ![Configure Database](/images/4-database-deployment/rds_configure_db_11.png)
    - Chọn **Security Groups**
    - Chọn **todo-ecs-sg**
    - Chọn **Actions** rồi chọn **Edit inbound rules**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_12.png)
    - Xoá inbound rule có type là SSH
    - Bấm **Save rules**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_13.png)
