---
title : "CloudFront"
date : "`r Sys.Date()`" 
weight : 6 
chapter : false
pre : " <b> 6. </b> "
---

#### CloudFront

Trong phần này chúng ta sẽ cùng triển khai CloudFront để cache lại các nội dung tĩnh của website giúp giảm thời gian tải trang đi đáng kể đồng thời cấu hình **Cache behavior** để điều hướng request đến đúng target frontend hoặc backend.

#### Nội dung

- [Tạo Distribution](6.1-configure-s3-origin/)
- [Nội dung tĩnh](6.2-upload-static-content/)
- [Cấu hình ALB Origin](6.3-configure-alb-origin/)
