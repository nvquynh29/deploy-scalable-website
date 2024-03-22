---
title : "Configure ALB Origin"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : "<b>6.3 </b>"
---
#### Configure ALB Origin
1. Within **CloudFront Distribution** interface:
    - Select **Origin** tab
    - Click **Create origin**
    ![Configure ALB Origin](../../../images/6-cloudfront-deployment/cloudfront_alb_origin_1.png)
2. Within **Create origin** interface:
    - Select **Origin domain**: `todo-alb`
    - Protocol: **HTTP**
    - Name: `todo-app-backend`
    - Click **Create origin**
    ![Configure ALB Origin](../../../images/6-cloudfront-deployment/cloudfront_alb_origin_2.png)
3. Within **CloudFront Distribution** interface:
    - Select **Behaviors** tab
    - Click **Create behavior**
    ![Configure ALB Origin](../../../images/6-cloudfront-deployment/cloudfront_alb_origin_3.png)
4. Within **Create behavior** interface:
    - Path pattern: `/api/*`
    - Origin and origin groups: **todo-app-backend**
    - Viewer protocol policy: **Redirect HTTP to HTTPS**
    - Allowed HTTP methods: **GET, HEAD, OPTIONS, PUT, POST, PATCH, DELETE**
    ![Configure ALB Origin](../../../images/6-cloudfront-deployment/cloudfront_alb_origin_4.png)
    - Cache key and origin requests:
        - Cache policy: **CachingDisabled**
        - Origin request policy: **AllViewer**
    - Click **Create behavior**
    ![Configure ALB Origin](../../../images/6-cloudfront-deployment/cloudfront_alb_origin_5.png)
    After successful creation, we will have behaviors as shown in the image:
    ![Configure ALB Origin](../../../images/6-cloudfront-deployment/cloudfront_alb_origin_6.png)
5. Access our website using CloudFront Domain name:
    - Copy the domain name address of CloudFront distribution (e.g. `https://d19141wkxl3uap.cloudfront.net`)
    - After visit this address on your browser, you will see the website interface as follows:
    ![Configure ALB Origin](../../../images/6-cloudfront-deployment/cloudfront_alb_origin_7.png)
