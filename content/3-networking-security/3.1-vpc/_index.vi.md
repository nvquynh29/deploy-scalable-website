---
title : "Tạo VPC"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : "<b>3.1 </b>"
---
## Tạo VPC
1. Tại giao diện của **AWS Management Console**:
    - Search từ khoá **VPC**
    - Chọn **VPC**
    ![Create VPC](../../../images/3-networking-security/vpc_create_vpc_1.png)
2. Tại giao diện của **VPC**:
    - Chọn **Your VPCs**
    - Bấm **Create VPC**
    ![Create VPC](../../../images/3-networking-security/vpc_create_vpc_2.png)
3. Các thông tin cấu hình:
    - Resource: **VPC only**
    - Name tag: `todo-vpc`
    - IPv4 CIDR: `10.0.0.0/16`

    Các cấu hình còn lại giữ nguyên mặc định rồi bấm **Create VPC**
    ![Create VPC](../../../images/3-networking-security/vpc_create_vpc_3.png)
4. Sau khi VPC trở trên khả dụng:
    - Chọn **Actions**
    - Bấm **Edit VPC settings**
    ![Create VPC](../../../images/3-networking-security/vpc_create_vpc_4.png)
    - Check vào ô **Enable DNS hostname**
    - Bấm **Save**
    ![Create VPC](../../../images/3-networking-security/vpc_create_vpc_5.png)