---
title : "Create NAT Gateways"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : "<b>3.4 </b>"
---
## Create NAT Gateways
1. Within **VPC** interface:
    - Select **NAT gateways**
    - Click on **Create NAT gateway**
    ![Create NAT Gateways](/images/3-networking-security/vpc_create_natgw_1.png)
2. Within **Create NAT gateway** interface:
    - Name it `todo-nat-gw-az-1`
    - Select subnet **public-subnet-az-1**
    - Click on **Allocate Elastic IP**
    - Click on **Create NAT gateway**
    ![Create NAT Gateways](/images/3-networking-security/vpc_create_natgw_2.png)
3. Repeat the above steps to create another NAT gateway:
    - Name it `todo-nat-gw-az-2`
    - Select subnet **public-subnet-az-2**
    - Click on **Allocate Elastic IP**
    - Click on **Create NAT gateway**
    
    After creation, we will have 2 NAT gateways as shown in the image below:
    ![Create NAT Gateways](/images/3-networking-security/vpc_create_natgw_3.png)