---
title : "Configure Database"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : "<b>4.3 </b>"
---
## Configure Database
In this step, we will create the database and necessary tables. 

Our RDS database has been configured to not allow public access to increase security, it can only be accessed by resources in the same VPC. Therefore, we will use an EC2 instance in the same VPC to connect to and query the database.
 
We need to do this step manually because the source code does not have database migrations available. In fact, we would not have to do this step if we already had database migrations.

1. Within **Amazon RDS** interface:
    - Select database **todo-db**
    - Scroll down, select **Connectivity & Security** tab
    - Copy the endpoint with type **Writer** and save it to your text editor
    ![Configure Database](/images/4-database-deployment/rds_configure_db_1.png)
2. Access EC2:
    - Search keyword: `ec2`
    - Select **EC2** service
    ![Configure Database](/images/4-database-deployment/rds_configure_db_2.png)
    - Click **Launch instance**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_3.png)
3. Within **Launch an instance** interface:
    - Amazon Machine Image (AMI): **Amazon Linux 2 AMI**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_4.png)
    - Create new Key pair:
        - Key pair name: `configure-db-key`
        - Key pair type: **RSA**
    - Click **Create key pair**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_5.png)
    - Network settings:
        - VPC: **todo-vpc**
        - Subnet: **public-subnet-az-1**
        - Security group: **todo-ecs-sg**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_6.png)
{{% notice note %}}
We choose security group **todo-ecs-sg** because the database has been pre-configured to allow access from this security group.
{{% /notice %}}
4. Within **EC2** interface:
    - Select **Security Groups**
    - Select **todo-ecs-sg**
    - Select **Actions** then select **Edit inbound rules**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_7.png)
    - Add new inbound rule with type SSH, source **Anywhere-IPv4**
    - Click **Save rules**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_8.png)
5. Within **EC2** interface:
    - Select **Instances**
    - Select newly created EC2 instance
    - Click **Connect**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_9.png)
    - Leave all configurations as default, click **Connect**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_10.png)
6. Setup database:
    
After connecting to the EC2 instance, run the following commands:
```shell
sudo su
yum update -y
yum install mysql -y
```

Replace `<todo_db_write_endpoint>` with the endpoint you copied and then connect to the database with the following command:
```shell
mysql -h <todo_db_write_endpoint> -u admin -p
```

After entering the password, we will be able to connect to the database. Run the following commands to create the necessary tables:
```sql
CREATE DATABASE todos;
USE todos;
CREATE TABLE `todos` (
    `id` VARCHAR(40) PRIMARY KEY,
    `name` VARCHAR(255) NOT NULL,
    `description` VARCHAR(255) NULL,
    `status` BOOLEAN NOT NULL DEFAULT 0
);
```

If no errors occur, you have successfully configured the database.

7. Resource cleanup
    - Return to the EC2 interface and terminate the newly created EC2 instance
    ![Configure Database](/images/4-database-deployment/rds_configure_db_11.png)
    - Select **Security Groups**
    - Select **todo-ecs-sg**
    - Select **Actions** then select **Edit inbound rules**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_12.png)
    - Delete the inbound rule with type SSH
    - Click **Save rules**
    ![Configure Database](/images/4-database-deployment/rds_configure_db_13.png)
