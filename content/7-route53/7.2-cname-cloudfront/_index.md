---
title : "Alternate Domain Name"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : "<b>7.2 </b>"
---
To configure a domain name for CloudFront distribution, we need to have an SSL/TLS certificate attached to that domain name first. We can create this certificate using the Amazon Certificate Manager (ACM) service.
#### Configure CloudFront Alternate Domain Name
1. Request SSL/TLS certificate by ACM:
    - View your CloudFront distribution details
    - At the **General** tab, click **Edit**
    ![CloudFront Alternate Domain Name](../../../images/7-route53/route53_request_acm_1.png)
2. Within **Edit settings** interface:
    - Custom SSL certificate: **Request certificate**
    ![CloudFront Alternate Domain Name](../../../images/7-route53/route53_request_acm_2.png)
3. Within **Request certificate** interface:
    - Click **Next**
    ![CloudFront Alternate Domain Name](../../../images/7-route53/route53_request_acm_3.png)
    - Within **Request public certificate** interface:
      - Fully qualified domain name: Enter the domain name you want to choose for the Todo application. e.g. `todo.yourdomain.com`
    - Click **Request**
    ![CloudFront Alternate Domain Name](../../../images/7-route53/route53_request_acm_4.png)
4. Create Route 53 DNS record:
    - View your certificate details at **List certificates** page
    - Click **Create records in Route 53**
    ![CloudFront Alternate Domain Name](../../../images/7-route53/route53_request_acm_5.png)
    - Click **Create records**
    ![CloudFront Alternate Domain Name](../../../images/7-route53/route53_request_acm_6.png)
    Wait a moment until your certificate has status: **Issued**
    ![CloudFront Alternate Domain Name](../../../images/7-route53/route53_request_acm_7.png)
5. Configure CloudFront alternate domain name:
    - Return to the **Edit settings** interface of CloudFront distribution
    - **Custom SSL certificate** section:
      - Click the reload icon
      - Select the certificate you just created
    - **Alternate domain name (CNAME)** section:
      - Click **Add item**
      - Enter the domain name associated with your certificate
      - Scroll down and Click **Save changes**
    ![CloudFront Alternate Domain Name](../../../images/7-route53/route53_cloudfront_cname_1.png)
    - Return to the **Route 53 hosted zone** interface and Click **Create record** then configure:
      - Record name: Enter the subdomain associated with your certificate (e.g. `todo`)
      - Enable **Alias**
      - Route traffic to: **Alias to CloudFront distribution**
      - Select your CloudFront distribution
      - Click **Create records**
    ![CloudFront Alternate Domain Name](../../../images/7-route53/route53_cloudfront_cname_2.png)

    After creating this record, you have successfully configured the domain name for CloudFront distribution. When accessing the domain name you just configured, you will see the Todo website interface as shown in the image below:
    ![CloudFront Alternate Domain Name](../../../images/7-route53/route53_todo_app.png)
