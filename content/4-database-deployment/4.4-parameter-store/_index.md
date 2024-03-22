---
title : "Create Parameters"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : "<b>4.4 </b>"
---
## Create Parameters
1. Access Parameter Store
    - Search keyword: `parameter store`
    - Select **Parameter Store**
    ![Create Parameters](/images/4-database-deployment/rds_parameter_store_1.png)
    - Click **Create parameter**
    ![Create Parameters](/images/4-database-deployment/rds_parameter_store_2.png)
2. Create new parameter:
    - Name: `/todo/db-host`
    - Type: **SecureString**
    ![Create Parameters](/images/4-database-deployment/rds_parameter_store_3.png)
    - Value: DB writer endpoint that you saved in the previous step
    - Click **Create parameter**
    ![Create Parameters](/images/4-database-deployment/rds_parameter_store_4.png)

3. Create the remaining parameters
    Create the following parameters with Type as **SecureString**, replace `<database_password>` with your database password:
    | Name  |  Value |
    |:---|:---|
    | `/todo/db-port`  | `3306`  |
    | `/todo/db-user`  | `admin`  |
    | `/todo/db-pass`  | <database_password>  |
    | `/todo/db-name`  | `todos`  |

    After creation, we will have the following parameters:
    ![Create Parameters](/images/4-database-deployment/rds_parameter_store_5.png)
