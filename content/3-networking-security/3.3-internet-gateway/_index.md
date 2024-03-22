---
title : "Create Internet Gateway"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : "<b>3.3 </b>"
---
## Create Internet Gateway
1. Within **VPC** interface:
    - Select **Internet gateways**
    - Click on **Create internet gateway**
    ![Create Internet Gateway](/images/3-networking-security/vpc_create_igw_1.png)
2. Within **Create internet gateway** interface:
    - Name it `todo-igw`
    - Click on **Create internet gateway**
    ![Create Internet Gateway](/images/3-networking-security/vpc_create_igw_2.png)
3. After creating the internet gateway:
    - Select **Actions**
    - Select **Attach to VPC**
    ![Create Internet Gateway](/images/3-networking-security/vpc_create_igw_3.png)
    - Select **todo-vpc**
    - Click on **Attach internet gateway**
    ![Create Internet Gateway](/images/3-networking-security/vpc_create_igw_4.png)
    After successfully attaching the internet gateway to the VPC, the state will be **Attached**
    ![Create Internet Gateway](/images/3-networking-security/vpc_create_igw_5.png)