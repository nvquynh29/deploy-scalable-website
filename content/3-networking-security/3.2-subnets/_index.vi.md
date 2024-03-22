---
title : "Tạo Subnets"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : "<b>3.2 </b>"
---
## Tạo Subnets
1. Tại giao diện của **VPC**:
    - Chọn **Subnets**
    - Bấm **Create subnet**
    ![Create Subnets](../../../images/3-networking-security/vpc_create_subnets_1.png)
2. Tại giao diện **Create subnet**:
    - Chọn **todo-vpc** VPC
    ![Create Subnets](../../../images/3-networking-security/vpc_create_subnets_2.png)
    - Tạo cùng lúc 4 subnets với cấu hình như trong bảng sau:

    | Subnet name  | Availability zone  | IPv4 CIDR block |
    |:---|:---|:---|
    | `public-subnet-az-1`  | ap-southeast-1a  | `10.0.0.0/24`  |
    | `private-subnet-az-1`  | ap-southeast-1a  | `10.0.1.0/24`  |
    | `public-subnet-az-2`  | ap-southeast-1b  | `10.0.2.0/24`  |
    | `private-subnet-az-2`  | ap-southeast-1b  | `10.0.3.0/24`  |

    Sau khi tạo xong chúng ta sẽ có các subnet như trong hình:
    ![Create Subnets](../../../images/3-networking-security/vpc_create_subnets_3.png)
## Cấu hình tự động cấp phát địa chỉ IPv4 công khai cho 2 public subnets
1. Tại giao diện của **VPC**:
    - Chọn **Subnets**
    - Chọn **public-subnet-az-1**
    - Chọn **Actions**
    - Chọn **Edit subnet settings**
    ![Create Subnets](../../../images/3-networking-security/vpc_create_subnets_4.png)
2. Tại phần **Auto-assign IP settings**:
    - Chọn **Enable auto-assign public IPv4 address**
    - Bấm **Save**
    ![Create Subnets](../../../images/3-networking-security/vpc_create_subnets_5.png)
3. Làm tương tự với **public-subnet-az-2**
    ![Create Subnets](../../../images/3-networking-security/vpc_create_subnets_6.png)
4. Kiểm tra xem các public subnets đã cấu hình đúng chưa
    ![Create Subnets](../../../images/3-networking-security/vpc_create_subnets_7.png)