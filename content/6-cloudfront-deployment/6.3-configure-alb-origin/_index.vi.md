---
title : "Cấu hình ALB Origin"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : "<b>6.3 </b>"
---
#### Cấu hình ALB Origin
1. Tại giao diện **CloudFront Distribution**:
    - Chọn tab **Origin**
    - Bấm **Create origin**
    ![Configure ALB Origin](/images/6-cloudfront-deployment/cloudfront_alb_origin_1.png)
2. Tại giao diện **Create origin**:
    - Chọn **Origin domain**: `todo-alb`
    - Protocol: **HTTP**
    - Name `todo-app-backend`
    - Bấm **Create origin**
    ![Configure ALB Origin](/images/6-cloudfront-deployment/cloudfront_alb_origin_2.png)
3. Tại giao diện **CloudFront Distribution**:
    - Chọn tab **Behaviors**
    - Bấm **Create behavior**
    ![Configure ALB Origin](/images/6-cloudfront-deployment/cloudfront_alb_origin_3.png)
4. Tại giao diện **Create behavior**:
    - Path pattern: `/api/*`
    - Origin and origin groups: **todo-app-backend**
    - Viewer protocol policy: **Redirect HTTP to HTTPS**
    - Allowed HTTP methods: **GET, HEAD, OPTIONS, PUT, POST, PATCH, DELETE**
    ![Configure ALB Origin](/images/6-cloudfront-deployment/cloudfront_alb_origin_4.png)
    - Cache key and origin requests:
        - Cache policy: **CachingDisabled**
        - Origin request policy: **AllViewer**
    - Bấm **Create behavior**
    ![Configure ALB Origin](/images/6-cloudfront-deployment/cloudfront_alb_origin_5.png)
    Sau khi tạo thành công thì ta sẽ có các behavior như trong ảnh:
    ![Configure ALB Origin](/images/6-cloudfront-deployment/cloudfront_alb_origin_6.png)
5. Truy cập website bằng CloudFront Domain name:
    - Sao chép địa chỉ domain name của CloudFront distribution (VD: `https://d19141wkxl3uap.cloudfront.net`)
    - Truy cập tới địa chỉ này trên trình duyệt bạn sẽ thấy giao diện của website như sau:
    ![Configure ALB Origin](/images/6-cloudfront-deployment/cloudfront_alb_origin_7.png)