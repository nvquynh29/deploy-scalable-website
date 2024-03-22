---
title : "Create Route Tables"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : "<b>3.5 </b>"
---
## Create Route Tables
1. Within **VPC** interface:
    - Select **Route tables**
    - Click on **Create route table**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_1.png)
2. Within **Create route table** interface:
    - Name it `todo-public-rtb`
    - Select VPC **todo-vpc**
    - Click on **Create route table**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_2.png)
3. Repeat the above steps to create 2 more route tables:
    - `todo-private-rtb-1`
    - `todo-private-rtb-2`

    After creating, we will have 3 route tables as shown in the image below:
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_3.png)
## Configure routes and subnet associations
The purpose of this step is to configure routing for resources located in the subnet.
1. Within **Route tables** interface:
    - Select **todo-public-rtb**
    - Select **Actions**
    - Select **Edit subnet associations**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_4.png)
2. Within **Edit subnet associations** interface:
    - Select subnets: **public-subnet-az-1** and **public-subnet-az-2**
    - Click on **Save associations**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_5.png)
3. Within **Route tables** interface:
    - Select **todo-public-rtb**
    - Select **Actions**
    - Select **Edit routes**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_6.png)
4. Within **Edit routes** interface:
    - Click on **Add route**
    - Add a route with the following configuration:
      - Destination: `0.0.0.0/0`
      - Target: Internet Gateway > `todo-igw`
    - Click on **Save changes**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_7.png)
5. Repeat the above steps with **todo-private-rtb-1** and **todo-private-rtb-2**, configuring as below:
    | Route table  | Subnet associations  | Route  |
    |:---|:---|:---|
    | todo-private-rtb-1  | private-subnet-az-1  | `0.0.0.0/0`: NAT Gateway > `todo-nat-gw-az-1`  |
    | todo-private-rtb-2  |  private-subnet-az-2 | `0.0.0.0/0`: NAT Gateway > `todo-nat-gw-az-2`  |
    - Configure route for **todo-private-rtb-1**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_8.png)
    - Configure route for **todo-private-rtb-2**
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_9.png)
6. Check configuration

    We can check whether the route table configuration is correct by looking at its detail
    ![Create Route Tables](../../../images/3-networking-security/vpc_create_rtb_10.png)
