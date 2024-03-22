---
title : "Chuẩn bị"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---

## Chuẩn bị

AWS CLI là công cụ giao diện dòng lệnh giúp người dùng tương tác với các dịch vụ của AWS. Trong phần này chúng ta sẽ cùng cài đặt và cấu hình AWS CLI trên máy tính.

#### Cài đặt AWS CLI

Truy cập vào địa chỉ này để cài đặt AWS CLI phù hợp hệ điều hành của bạn: [Cài đặt AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html#getting-started-install-instructions)

#### Cấu hình AWS CLI
1. Tạo AWS access key
    - Truy cập vào dịch vụ **IAM**
    - Chọn **Users** trong phần sidebar
    - Chọn người dùng hiện tại
    - Chọn tab **Security credentials**
    - Kéo xuống phần **Access keys** rồi chọn **Create access key**
    ![IAM create access key](../../images/2-preparation/iam_create_access_key_1.png)
    - Chọn use case là **Command Line Interface (CLI)** rồi chọn **Next**
    ![IAM create access key](../../images/2-preparation/iam_create_access_key_2.png)
    - Các cấu hình còn lại để mặc định rồi tạo access key.
    Sau khi tạo xong bạn sẽ nhận được một cặp **Access key** và **Secret access key** như dưới đây.
    Hãy lưu các key này lại hoặc tải file CSV về máy tính của bạn để chuẩn bị cho bước tiếp theo.
    ![IAM create access key](../../images/2-preparation/iam_create_access_key_3.png)

2. Cấu hình AWS CLI

    Chạy lệnh sau để cấu hình AWS CLI. Phần **AWS Access Key ID** và **AWS Secret Access Key** thì điền key mà bạn vừa tạo. **Default region** thì đặt là `ap-southeast-1` (Singapore), **Default output format** là `json`
    ```shell
    aws configure
    ```
    Bạn có thể kiểm tra xem mình đã cấu hình đúng chưa bằng lệnh sau, nếu không có lỗi gì thì bạn đã cấu hình thành công.
    ```shell
    aws s3 ls
    ```