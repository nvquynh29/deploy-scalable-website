---
title : "Tạo Route Tables"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : "<b>3.5 </b>"
---
## Tạo Route Tables
1. Tại giao diện của **VPC**:
    - Chọn **Route tables**
    - Bấm **Create route table**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_1.png)
2. Tại giao diện **Create route table**:
    - Đặt tên là `todo-public-rtb`
    - Chọn VPC **todo-vpc**
    - Bấm **Create route table**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_2.png)
3. Lặp lại các bước trên để tạo thêm 2 route table nữa:
    - `todo-private-rtb-1`
    - `todo-private-rtb-2`

    Sau khi tạo xong chúng ta sẽ có 3 route tables như trong ảnh dưới đây:
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_3.png)
## Cấu hình route table và subnet associations
Mục đích của bước này là để cấu hình định tuyến cho các tài nguyên nằm trong subnet.
1. Tại giao diện **Route tables**:
    - Chọn **todo-public-rtb**
    - Chọn **Actions**
    - Chọn **Edit subnet associations**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_4.png)
2. Tại giao diện **Edit subnet associations**:
    - Chọn các subnet: **public-subnet-az-1** và **public-subnet-az-2**
    - Bấm **Save associations**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_5.png)
3. Tại giao diện **Route tables**:
    - Chọn **todo-public-rtb**
    - Chọn **Actions**
    - Chọn **Edit routes**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_6.png)
4. Tại giao diện **Edit routes**:
    - Bấm **Add route**
    - Thêm route với thông tin như sau:
      - Destination: `0.0.0.0/0`
      - Target: Internet Gateway > `todo-igw`
    - Bấm **Save changes**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_7.png)
5. Lặp lại các bước trên với **todo-private-rtb-1** và **todo-private-rtb-2**, cấu hình như sau:
    | Route table  | Subnet associations  | Route  |
    |:---|:---|:---|
    | todo-private-rtb-1  | private-subnet-az-1  | `0.0.0.0/0`: NAT Gateway > `todo-nat-gw-az-1`  |
    | todo-private-rtb-2  |  private-subnet-az-2 | `0.0.0.0/0`: NAT Gateway > `todo-nat-gw-az-2`  |
    - Cấu hình route cho **todo-private-rtb-1**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_8.png)
    - Cấu hình route cho **todo-private-rtb-2**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_9.png)
6. Kiểm tra cấu hình

    Chúng ta có thể kiểm tra cấu hình route table đã đúng chưa bằng cách xem thông tin của nó
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_10.png)
