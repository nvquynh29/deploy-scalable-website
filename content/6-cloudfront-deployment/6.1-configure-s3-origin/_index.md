---
title : "Create Distribution"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : "<b>6.1 </b>"
---
#### Create S3 Bucket
1. Access **S3**:
    - Search keyword: `s3`
    - Select **S3** service
    ![Create S3 Bucket](/images/6-cloudfront-deployment/cloudfront_create_s3_1.png)
2. Within **S3** interface:
    - Select **Buckets**
    - Click **Create bucket**
    ![Create S3 Bucket](/images/6-cloudfront-deployment/cloudfront_create_s3_2.png)
3. Within **Create bucket** interface:
    - AWS Region: **Asia Pacific (Singapore) ap-southeast-1**
    - Bucket name: Enter the name you want to set (e.g. `fcj-todo-bucket-1`)
    - Click **Create**
    ![Create S3 Bucket](/images/6-cloudfront-deployment/cloudfront_create_s3_3.png)

#### Create CloudFront Distribution
1. Access **CloudFront**:
    - Search keyword: `cloudfront`
    - Select **CloudFront**
    ![Create CloudFront Distribution](/images/6-cloudfront-deployment/cloudfront_distribution_1.png)
2. Within **CloudFront** interface:
    - Select **Distribution**
    - Click **Create distribution**
    ![Create CloudFront Distribution](/images/6-cloudfront-deployment/cloudfront_distribution_2.png)
3. Within **Create distribution** interface:
    - Origin domain: Select the S3 bucket you just created
    - Name: `todo-app-frontend`
    - Origin access: **Origin access control settings (recommended)**
    - Click **Create new OAC**
    ![Create CloudFront Distribution](/images/6-cloudfront-deployment/cloudfront_distribution_3.png)
    - Leave all configurations as default then **Create**
    ![Create CloudFront Distribution](/images/6-cloudfront-deployment/cloudfront_distribution_4.png)
    - Web Application Firewall: **Do not enable security protections**
    - Price class: **Use North America, Europe, Asia, Middle East, and Africa**
    ![Create CloudFront Distribution](/images/6-cloudfront-deployment/cloudfront_distribution_5.png)
    - Default root object: `index.html`
    - Click **Create distribution**
    ![Create CloudFront Distribution](/images/6-cloudfront-deployment/cloudfront_distribution_6.png)
4. Update S3 bucket policy:
    - After creating the distribution, you will see a yellow message asking to update the S3 bucket policy.
    Click the **Copy policy** button
    ![Create CloudFront Distribution](/images/6-cloudfront-deployment/cloudfront_distribution_7.png)
    - Go back to the S3 bucket and select the **Permissions** tab
    - Click **Edit** in the **Bucket policy** section
    ![Create CloudFront Distribution](/images/6-cloudfront-deployment/cloudfront_distribution_8.png)
    - Paste the copied policy content into the **Policy** section and save it
    ![Create CloudFront Distribution](/images/6-cloudfront-deployment/cloudfront_distribution_9.png)
