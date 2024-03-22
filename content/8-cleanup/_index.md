---
title : "Clean Up"
date : "`r Sys.Date()`" 
weight : 8 
chapter : false
pre : " <b> 8. </b> "
---

#### Resource Clean Up
1. RDS:
    - Delete RDS database (delete each instance before deleting the database)
    - Delete database subnet group
2. Parameter Store:
    - Delete parameters
3. Route 53:
    - Delete all records of the Hosted zone (except 2 default records)
    - Delete hosted zone
4. CloudFront:
    - Disable CloudFront distribution
    - Delete CloudFront distribution
5. ACM:
    - Delete the SSL/TLS certificate in region `us-east-1`
6. S3:
    - Empty S3 bucket
    - Delete S3 bucket
7. EC2:
    - Delete Load balancer
    - Delete Target group
8. ECR:
    - Delete ECR repository
9. ECS:
    - Delete ECS service
    - Delete ECS cluster
    - Delete task definition
10. VPC:
    - Delete NAT gateways
    - Delete Elastic IPs
    - Delete VPC
11. CloudWatch:
    - Delete CloudWatch log groups
12. IAM:
    - Delete roles: `todo-ecs-task-role` và `ecsTaskExecutionRole`
    - Delete IAM access key
