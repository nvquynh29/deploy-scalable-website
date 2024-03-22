---
title : "Tạo Distribution"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : "<b>6.1 </b>"
---
#### Tạo S3 Bucket
1. Truy cập **S3**:
    - Tìm kiếm từ khoá: `s3`
    - Chọn **S3**
    ![Create S3 Bucket](../../../images/6-cloudfront-deployment/cloudfront_create_s3_1.png)
2. Tại giao diện **S3**:
    - Chọn **Buckets**
    - Bấm **Create bucket**
    ![Create S3 Bucket](../../../images/6-cloudfront-deployment/cloudfront_create_s3_2.png)
3. Tại giao diện **Create bucket**:
    - AWS Region: **Asia Pacific (Singapore) ap-southeast-1**
    - Bucket name: Điền tên bucket bạn muốn đặt (VD: `fcj-todo-bucket-1`)
    - Bấm **Create**
    ![Create S3 Bucket](../../../images/6-cloudfront-deployment/cloudfront_create_s3_3.png)

#### Tạo CloudFront Distribution
1. Truy cập **CloudFront**:
    - Tìm kiếm từ khoá: `cloudfront`
    - Chọn **CloudFront**
    ![Create CloudFront Distribution](../../../images/6-cloudfront-deployment/cloudfront_distribution_1.png)
2. Tại giao diện **CloudFront**:
    - Chọn **Distribution**
    - Bấm **Create distribution**
    ![Create CloudFront Distribution](../../../images/6-cloudfront-deployment/cloudfront_distribution_2.png)
3. Tại giao diện **Create distribution**:
    - Origin domain: Chọn S3 bucket vừa tạo
    - Name: `todo-app-frontend`
    - Origin access: **Origin access control settings (recommended)**
    - Bấm **Create new OAC**
    ![Create CloudFront Distribution](../../../images/6-cloudfront-deployment/cloudfront_distribution_3.png)
    - Giữ nguyên tất cả cấu hình rồi bấm **Create**
    ![Create CloudFront Distribution](../../../images/6-cloudfront-deployment/cloudfront_distribution_4.png)
    - Web Application Firewall: **Do not enable security protections**
    - Price class: **Use North America, Europe, Asia, Middle East, and Africa**
    ![Create CloudFront Distribution](../../../images/6-cloudfront-deployment/cloudfront_distribution_5.png)
    - Default root object: `index.html`
    - Bấm **Create distribution**
    ![Create CloudFront Distribution](../../../images/6-cloudfront-deployment/cloudfront_distribution_6.png)
4. Cập nhật S3 bucket policy:
    - Sau khi tạo xong distribution, bạn sẽ thấy một thông báo màu vàng yêu cầu cập nhật policy của S3 bucket.
    Bấm nút **Copy policy**
    ![Create CloudFront Distribution](../../../images/6-cloudfront-deployment/cloudfront_distribution_7.png)
    - Quay lại S3 bucket rồi chọn tab **Permissions**
    - Bấm **Edit** tại phần **Bucket policy**
    ![Create CloudFront Distribution](../../../images/6-cloudfront-deployment/cloudfront_distribution_8.png)
    - Dán nội dung policy vừa sao chép vào phần **Policy** rồi lưu lại
    ![Create CloudFront Distribution](../../../images/6-cloudfront-deployment/cloudfront_distribution_9.png)
