---
title : "Create Subnets"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : "<b>3.2 </b>"
---
## Create Subnets
1. Within **VPC** interface:
    - Select **Subnets**
    - Click on **Create subnet**
    ![Create Subnets](../../../images/3-networking-security/vpc_create_subnets_1.png)
2. Within **Create subnet** interface:
    - Select **todo-vpc** VPC
    ![Create Subnets](../../../images/3-networking-security/vpc_create_subnets_2.png)
    - Create 4 subnets at the same time with configuration as shown in the following table:

    | Subnet name  | Availability zone  | IPv4 CIDR block |
    |:---|:---|:---|
    | `public-subnet-az-1`  | ap-southeast-1a  | `10.0.0.0/24`  |
    | `private-subnet-az-1`  | ap-southeast-1a  | `10.0.1.0/24`  |
    | `public-subnet-az-2`  | ap-southeast-1b  | `10.0.2.0/24`  |
    | `private-subnet-az-2`  | ap-southeast-1b  | `10.0.3.0/24`  |

    After creating, we will have subnets as shown in the following image:
    ![Create Subnets](../../../images/3-networking-security/vpc_create_subnets_3.png)
## Configure to automatically allocate public IPv4 addresses to 2 public subnets
1. Within **VPC** interface:
    - Select **Subnets**
    - Select **public-subnet-az-1**
    - Select **Actions**
    - Select **Edit subnet settings**
    ![Create Subnets](../../../images/3-networking-security/vpc_create_subnets_4.png)
2. Under **Auto-assign IP settings** section:
    - Select **Enable auto-assign public IPv4 address**
    - Click on **Save**
    ![Create Subnets](../../../images/3-networking-security/vpc_create_subnets_5.png)
3. Repeat the same process with **public-subnet-az-2**
    ![Create Subnets](../../../images/3-networking-security/vpc_create_subnets_6.png)
4. Check if the public subnets are configured correctly
    ![Create Subnets](../../../images/3-networking-security/vpc_create_subnets_7.png)