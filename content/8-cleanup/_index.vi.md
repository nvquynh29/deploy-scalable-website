---
title : "Dọn dẹp tài nguyên"
date : "`r Sys.Date()`" 
weight : 8 
chapter : false
pre : " <b> 8. </b> "
---

#### Dọn dẹp tài nguyên
1. RDS:
    - Xoá RDS database (xoá từng instance trước khi xoá database)
    - Xoá database subnet group
2. Parameter Store:
    - Xoá các parameter
3. Route 53:
    - Xoá toàn bộ record của Hosted zone trừ 2 records mặc định
    - Xoá hosted zone
4. CloudFront:
    - Disable CloudFront distribution
    - Xoá CloudFront distribution
5. ACM:
    - Xoá chứng chỉ SSL/TLS tại region `us-east-1`
6. S3:
    - Xoá toàn bộ file trong S3 bucket
    - Xoá S3 bucket
7. EC2:
    - Xoá Load balancer
    - Xoá Target group
8. ECR:
    - Xoá ECR repository
9. ECS:
    - Xoá ECS service
    - Xoá ECS cluster
    - Xoá task definition
10. VPC:
    - Xoá NAT gateways
    - Xoá elastic IPs
    - Xoá VPC
11. CloudWatch:
    - Xoá CloudWatch log groups
12. IAM:
    - Xoá roles: `todo-ecs-task-role` và `ecsTaskExecutionRole`
    - Xoá IAM access key
