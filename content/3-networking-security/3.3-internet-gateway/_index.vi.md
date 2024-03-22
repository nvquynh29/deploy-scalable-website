---
title : "Tạo Internet Gateway"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : "<b>3.3 </b>"
---
## Tạo Internet Gateway
1. Tại giao diện của **VPC**:
    - Chọn **Internet gateways**
    - Bấm **Create internet gateway**
    ![Create Internet Gateway](../../../images/3-networking-security/vpc_create_igw_1.png)
2. Tại giao diện **Create internet gateway**:
    - Đặt tên là `todo-igw`
    - Bấm **Create internet gateway**
    ![Create Internet Gateway](../../../images/3-networking-security/vpc_create_igw_2.png)
3. Sau khi tạo xong internet gateway:
    - Chọn **Actions**
    - Chọn **Attach to VPC**
    ![Create Internet Gateway](../../../images/3-networking-security/vpc_create_igw_3.png)
    - Chọn **todo-vpc**
    - Bấm **Attach internet gateway**
    ![Create Internet Gateway](../../../images/3-networking-security/vpc_create_igw_4.png)
    Sau khi attach thành công internet gateway vào VPC thì nó sẽ có trạng thái là **Attached**
    ![Create Internet Gateway](../../../images/3-networking-security/vpc_create_igw_5.png)