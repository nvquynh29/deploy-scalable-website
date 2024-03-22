---
title : "Tạo Parameters"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : "<b>4.4 </b>"
---
## Tạo Parameters
1. Truy cập Parameter Store
    - Tìm kiếm từ khoá: `parameter store`
    - Chọn **Parameter Store**
    ![Create Parameters](../../../images/4-database-deployment/rds_parameter_store_1.png)
    - Bấm **Create parameter**
    ![Create Parameters](../../../images/4-database-deployment/rds_parameter_store_2.png)
2. Tạo parameter mới:
    - Name: `/todo/db-host`
    - Type: **SecureString**
    ![Create Parameters](../../../images/4-database-deployment/rds_parameter_store_3.png)
    - Value: DB writer endpoint mà bạn đã lưu ở bước trước
    - Bấm **Create parameter**
    ![Create Parameters](../../../images/4-database-deployment/rds_parameter_store_4.png)

3. Tạo các parameter còn lại
    Tạo các parameter dưới đây với Type là **SecureString**, thay `<database_password>` bằng mật khẩu database của bạn:
    | Name  |  Value |
    |:---|:---|
    | `/todo/db-port`  | `3306`  |
    | `/todo/db-user`  | `admin`  |
    | `/todo/db-pass`  | <database_password>  |
    | `/todo/db-name`  | `todos`  |

    Sau khi tạo xong, chúng ta sẽ có những parameter như dưới đây:
    ![Create Parameters](../../../images/4-database-deployment/rds_parameter_store_5.png)
