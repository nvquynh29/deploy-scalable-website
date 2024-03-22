---
title : "Alternate Domain Name"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : "<b>7.2 </b>"
---
Để cấu hình được tên miền cho CloudFront distribution thì chúng ta cần phải có một chứng chỉ SSL/TLS gắn với tên miền đó trước. Chúng ta có thể tạo chứng chỉ này bằng dịch vụ Amazon Certificate Manager (ACM).
#### Cấu hình CloudFront Alternate Domain Name
1. Yêu cầu chứng chỉ SSL/TLS bằng ACM:
    - Xem chi tiết CloudFront distribution của bạn
    - Tại tab **General**, bấm **Edit**
    ![CloudFront Alternate Domain Name](/images/7-route53/route53_request_acm_1.png)
2. Tại giao diện **Edit settings**:
    - Custom SSL certificate: **Request certificate**
    ![CloudFront Alternate Domain Name](/images/7-route53/route53_request_acm_2.png)
3. Tại giao diện **Request certificate**
    - Bấm **Next**
    ![CloudFront Alternate Domain Name](/images/7-route53/route53_request_acm_3.png)
    - Tại giao diện **Request public certificate**:
      - Fully qualified domain name: Điền tên miền bạn muốn chọn cho Todo application. VD: `todo.yourdomain.com`
    - Bấm **Request**
    ![CloudFront Alternate Domain Name](/images/7-route53/route53_request_acm_4.png)
4. Tạo Route 53 DNS record:
    - Xem chi tiết chứng chỉ của bạn tại phần **List certificates**
    - Bấm **Create records in Route 53**
    ![CloudFront Alternate Domain Name](/images/7-route53/route53_request_acm_5.png)
    - Bấm **Create records**
    ![CloudFront Alternate Domain Name](/images/7-route53/route53_request_acm_6.png)
    Đợi một chút cho đến khi chứng chỉ của bạn có trạng thái là: **Issued**
    ![CloudFront Alternate Domain Name](/images/7-route53/route53_request_acm_7.png)
5. Cấu hình CloudFront alternate domain name:
    - Quay lại giao diện **Edit settings** của CloudFront distribution
    - Tại phần **Custom SSL certificate**:
      - Bấm biểu tượng reload
      - Chọn chứng chỉ bạn vừa tạo
    - Tại phần **Alternate domain name (CNAME)**:
      - Bấm **Add item**
      - Điền tên miền gắn với chứng chỉ của bạn
      - Kéo xuống dưới và bấm **Save changes**
    ![CloudFront Alternate Domain Name](/images/7-route53/route53_cloudfront_cname_1.png)
    - Quay lại giao diện **Route 53 hosted zone** rồi bấm **Create record** sau đó cấu hình:
      - Record name: Điền sub domain gắn với chứng chỉ của bạn (VD: `todo`)
      - Bật **Alias**
      - Route traffic to: **Alias to CloudFront distribution**
      - Chọn CloudFront distribution của bạn
      - Bấm **Create records**
    ![CloudFront Alternate Domain Name](/images/7-route53/route53_cloudfront_cname_2.png)

    Sau khi tạo xong record này, bạn đã cấu hình thành công domain name cho CloudFront distribution. Khi truy cập đến tên miền bạn vừa cấu hình, bạn sẽ thấy giao diện của website Todo như trong ảnh dưới đây:
    ![CloudFront Alternate Domain Name](/images/7-route53/route53_todo_app.png)
