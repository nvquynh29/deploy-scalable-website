---
title : "Create Subnet Group"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : "<b>4.1 </b>"
---
## Create Subnet Group
A DB subnet group defines which subnets in a virtual private cloud (VPC) are designated for your database.

A DB subnet group has subnets in at least two Availability Zones in its AWS Region. The subnets in a DB subnet group are either public or private, depending on the configuration of their network ACLs and routing tables.

For security, the subnets in a DB subnet group are typically private.
If the database must be publicly accessible, all of the subnets in its DB subnet group must be public.
1. Within **AWS Management Console** interface:
    - Search keyword **RDS**
    - Select **RDS**
    ![Create Subnet Group](/images/4-database-deployment/rds_create_subnet_group_1.png)
2. Within **Amazon RDS** interface:
    - Select **Subnet groups**
    - Click on **Create DB subnet group**
    ![Create Subnet Group](/images/4-database-deployment/rds_create_subnet_group_2.png)
3. Within **Create DB subnet group** interface:
    - Name: `todo-db-subnet-group`
    - Description: `Subnet group for todo DB`
    - VPC: **todo-vpc**
4. Under **Add subnets** section:
    - Select availability zone: **ap-southeast-1a** and **ap-southeast-1b**
    ![Create Subnet Group](/images/4-database-deployment/rds_create_subnet_group_3.png)
    - Subnets: **private-subnet-az-1 (10.0.1.0/24)** and **private-subnet-az-2 (10.0.3.0/24)**
    ![Create Subnet Group](/images/4-database-deployment/rds_create_subnet_group_4.png)
    - Click on **Create**
