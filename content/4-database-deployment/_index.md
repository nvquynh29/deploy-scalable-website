---
title : "Database Deployment"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

## Database Deployment

In this section we will deploy the database using the Amazon RDS service, prepare a database and create some necessary tables. In addition, we will save configuration information using the Parameter Store feature instead of saving it directly in the source code, helping to increase the security of the system and making management, change configuration data easier.

#### Contents

- [Create Subnet Group](4.1-subnet-group/)
- [Create Database](4.2-aurora/)
- [Configure Database](4.3-configure-database/)
- [Create Parameters](4.4-parameter-store/)
