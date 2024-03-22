---
title : "Tạo NAT Gateways"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : "<b>3.4 </b>"
---
## Tạo NAT Gateways
1. Tại giao diện của **VPC**:
    - Chọn **NAT gateways**
    - Bấm **Create NAT gateway**
    ![Create NAT Gateways](../../../images/3-networking-security/vpc_create_natgw_1.png)
2. Tại giao diện **Create NAT gateway**:
    - Đặt tên là `todo-nat-gw-az-1`
    - Chọn subnet **public-subnet-az-1**
    - Bấm **Allocate Elastic IP**
    - Bấm **Create NAT gateway**
    ![Create NAT Gateways](../../../images/3-networking-security/vpc_create_natgw_2.png)
3. Lặp lại các bước trên để tạo thêm một NAT gateway nữa:
    - Đặt tên là `todo-nat-gw-az-2`
    - Chọn subnet **public-subnet-az-2**
    - Bấm **Allocate Elastic IP**
    - Bấm **Create NAT gateway**
    Sau khi tạo xong chúng ta sẽ có 2 NAT gateway như trong ảnh dưới đây:
    ![Create NAT Gateways](../../../images/3-networking-security/vpc_create_natgw_3.png)