---
title : "Tạo Hosted Zone"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : "<b>7.1 </b>"
---
#### Tạo Hosted Zone
1. Truy cập **Route 53**:
    - Tìm kiếm từ khoá: `route 53`
    - Chọn dịch vụ **Route 53**
    ![Create Hosted Zone](/images/7-route53/route53_hosted_zone_1.png)
2. Tại giao diện **Route 53**:
    - Chọn **Hosted zones**
    - Bấm **Create hosted zone**
    ![Create Hosted Zone](/images/7-route53/route53_hosted_zone_2.png)
3. Tại giao diện **Create hosted zone**:
    - Domain name: Điền domain name của bạn
    - Type: **Public hosted zone**
    - Bấm **Create hosted zone**
    ![Create Hosted Zone](/images/7-route53/route53_hosted_zone_3.png)
4. Cấu hình name servers:
    Để tích hợp domain của bạn với Route 53 thì bạn cần trỏ các DNS record có type **NS** vào các name server của AWS.
    ![Create Hosted Zone](/images/7-route53/route53_hosted_zone_4.png)
    Bạn có thể làm điều này bằng cách truy cập và trang quản lý DNS của nhà cung cấp domain của bạn.
    
    Ví dụ về cấu hình:
    ![Create Hosted Zone](/images/7-route53/route53_hosted_zone_5.png)
5. Kiểm tra cấu hình name servers:
    Việc cấu hình name servers có thể sẽ mất thời gian để cập nhật. Hãy đợi vài phút trước khi thực hiện các bước dưới đây.
    - Truy cập vào địa chỉ: [DNS Checker](https://dnschecker.org)
    - Chọn tab: **DNS Lookup**
    - Tại phần **Enter any Valid URL**: Nhập địa chỉ domain của bạn (VD: `yourdomain.com`)
    - Record type: **NS**
    - Bấm **Lookup DNS**
    ![Create Hosted Zone](/images/7-route53/route53_dns_lookup_1.png)
    Kết quả khi bạn cấu hình thành công:
    ![Create Hosted Zone](/images/7-route53/route53_dns_lookup_2.png)

