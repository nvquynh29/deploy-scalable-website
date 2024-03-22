---
title : "Create Hosted Zone"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : "<b>7.1 </b>"
---
#### Create Hosted Zone
1. Access **Route 53**:
    - Search keyword: `route 53`
    - Select **Route 53** service
    ![Create Hosted Zone](/images/7-route53/route53_hosted_zone_1.png)
2. Within **Route 53** interface:
    - Select **Hosted zones**
    - Click **Create hosted zone**
    ![Create Hosted Zone](/images/7-route53/route53_hosted_zone_2.png)
3. Within **Create hosted zone** interface:
    - Domain name: Enter your domain
    - Type: **Public hosted zone**
    - Click **Create hosted zone**
    ![Create Hosted Zone](/images/7-route53/route53_hosted_zone_3.png)
4. Configure name servers:
    To integrate your domain with Route 53, you need to point DNS records with type **NS** to AWS name servers.
    ![Create Hosted Zone](/images/7-route53/route53_hosted_zone_4.png)
    You can do this by visiting your domain provider's DNS management page.
    
    Configuration example:
    ![Create Hosted Zone](/images/7-route53/route53_hosted_zone_5.png)
5. Check the name servers configuration:
    Name server configuration may take time to update. Wait a few minutes before performing the steps below.
    - Access this URL: [DNS Checker](https://dnschecker.org)
    - Select tab: **DNS Lookup**
    - In the **Enter any Valid URL** section: Enter your domain address (e.g. `yourdomain.com`)
    - Record type: **NS**
    - Click **Lookup DNS**
    ![Create Hosted Zone](/images/7-route53/route53_dns_lookup_1.png)
    Result when you successfully configure:
    ![Create Hosted Zone](/images/7-route53/route53_dns_lookup_2.png)
