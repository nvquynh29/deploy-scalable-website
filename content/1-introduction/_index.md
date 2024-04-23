---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 1. </b> "
---

In this lab, we will use the following AWS services and features

#### Virtual Private Cloud (VPC)
**Amazon Virtual Private Cloud (Amazon VPC)** is a **Virtual Private Cloud**—a customized virtual network hosted within the AWS Cloud and isolated from the external world. This concept resembles the design and implementation of a distinct standalone network environment in an on-premise data center, a practice still widely employed across many countries.

Within this dedicated VPC, users possess comprehensive control over their virtual network environment. This control encompasses the initiation and operation of AWS resources, the ability to choose IP address ranges, establish network subnets, and configure routing tables and network gateways. Secure and convenient resource and application access within the VPC is facilitated through both IPv4 and IPv6 protocols.

#### Amazon Relational Database Service (Amazon RDS)
**Amazon RDS** is an easy to manage relational database service optimized for total cost of ownership. It is simple to set up, operate, and scale with demand. Amazon RDS automates the undifferentiated database management tasks, such as provisioning, configuring, backups, and patching. Amazon RDS enables customers to create a new database in minutes, and offers flexibility to customize databases to meet their needs. Customers can optimize performance with features, like Multi-AZ with two readable standbys, Optimized Writes and Reads, and choose from multiple pricing options to effectively manage costs.

#### AWS Systems Manager

**AWS Systems Manager** là trung tâm vận hành cho các ứng dụng và tài nguyên AWS, đồng thời là giải pháp quản lý toàn diện an toàn cho môi trường kết hợp và nhiều đám mây cho phép vận hành an toàn trên quy mô lớn.

**Parameter Store** is a capability of AWS Systems Manager, provides secure, hierarchical storage for configuration data management and secrets management. You can store data such as passwords, database connection strings,... as plain text or encrypted data. You can reference Systems Manager parameters in your scripts, commands, and configuration by Amazon Resource Name (ARN) of them.

#### Amazon Elastic Container Registry (ECR)
**Amazon Elastic Container Registry (Amazon ECR)** is an AWS managed container image registry service that is secure, scalable, and reliable. Amazon ECR supports private repositories with resource-based permissions using AWS IAM. This is so that specified users or Amazon EC2 instances can access your container repositories and images. ECR allows users to use CLI to manage, pull, push Docker images.

#### Amazon Elastic Container Service (ECS)
**Amazon Elastic Container Service (Amazon ECS)** is a fully managed container orchestration service that helps you easily deploy, manage, and scale containerized applications. As a fully managed service, Amazon ECS comes with AWS configuration and operational best practices built-in. It's integrated with both AWS and third-party tools, such as Amazon Elastic Container Registry and Docker. This integration makes it easier for teams to focus on building the applications, not the environment. You can run and scale your container workloads across AWS Regions in the cloud, and on-premises, without the complexity of managing a control plane.

#### Amazon CloudWatch
**CloudWatch** monitors resources and applications on AWS by collecting metrics over time. The service provides built-in dashboards for core services and allows users to create custom dashboards to visualize selected metrics. CloudWatch can integrate with many other services very easily. One of the most popular uses of CloudWatch is collecting application logs.

#### Elastic Load Balancing
**Elastic Load Balancing** automatically distributes income traffic to various targets, such as EC2 virtual machines, containers, or IP addresses in one or more availability zones. It monitors the access status of registered targets and only routes traffic to active targets. That's how load balancing can help the system know when to expand, reducing the amount of resources needed based on actual traffic.

#### Amazon Simple Storage Service (S3)
**Amazon Simple Storage Service (Amazon S3)** is an object storage service that offers industry-leading scalability, data availability, security, and performance. Customers of all sizes and industries can use Amazon S3 to store and protect any amount of data for a range of use cases, such as data lakes, websites, mobile applications, backup and restore, archive, enterprise applications, IoT devices, and big data analytics.

#### Amazon CloudFront
**Amazon CloudFront** is a web service that speeds up distribution of your static and dynamic web content, such as HTML, CSS Javascript, and image files, to your users. CloudFront speeds up web content delivery by:

- Using a global network of edge locations to serve content closer to users, reducing latency.
- Caching content at edge locations, so it's readily available for users without needing to go back to the origin server every time.
- Routing user requests through the AWS backbone for faster delivery.

This results in lower latency, higher data transfer rates, and improved reliability for your users.

#### Amazon Route 53
**Amazon Route 53** is a highly available and scalable Domain Name System (DNS) web service. You can use Route 53 to perform three main functions in any combination: domain registration, DNS routing, and health checking. Route 53 can integrate with many other AWS services, making deployment and configuration of web application domains very easy.
 
#### AWS Certificate Manager (ACM)
**AWS Certificate Manager (ACM)** handles the complexity of creating, storing, and renewing public and private SSL/TLS X.509 certificates and keys that protect your AWS websites and applications. SSL/TLS certificates enable web application servers to communicate with users via the HTTPS protocol, which is more secure than the HTTP protocol. Some modern browsers have decided that a web application is not secure enough if the server does not support the HTTPS protocol and now warn users if they visit those websites.
You can provide certificates for your integrated AWS services either by issuing them directly with ACM or by importing third-party certificates into the ACM management system. ACM certificates can secure singular domain names, multiple specific domain names, wildcard domains, or combinations of these. ACM wildcard certificates can protect an unlimited number of subdomains.
