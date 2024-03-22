---
title : "Create VPC"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : "<b>3.1 </b>"
---
## Create VPC
1. Within the **AWS Management Console** interface:
    - Search keyword **VPC**
    - Select **VPC**
    ![Create VPC](../../../images/3-networking-security/vpc_create_vpc_1.png)
2. Within the **VPC** interface:
    - Select **Your VPCs**
    - Click on **Create VPC**
    ![Create VPC](../../../images/3-networking-security/vpc_create_vpc_2.png)
3. Configuration fields:
    - Resource: **VPC only**
    - Name tag: `todo-vpc`
    - IPv4 CIDR: `10.0.0.0/16`

    Keep the remaining configurations as default and then click on **Create VPC**
    ![Create VPC](../../../images/3-networking-security/vpc_create_vpc_3.png)
4. After your VPC become available:
    - Select **Actions**
    - Click on **Edit VPC settings**
    ![Create VPC](../../../images/3-networking-security/vpc_create_vpc_4.png)
    - Check the checkbox **Enable DNS hostname**
    - Click on **Save**
    ![Create VPC](../../../images/3-networking-security/vpc_create_vpc_5.png)