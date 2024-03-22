---
title : "Create ECR Repository"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : "<b>5.1 </b>"
---
Please download the source code below and extract it to prepare for the next steps:

{{%attachments title="Source code" style="green" pattern="simple-todo-app.zip"/%}}

## Create ECR Repository
1. Access ECR:
    - Search keyword: `ecr`
    - Select **Elastic Container Registry**
    ![Create ECR Repository](/images/5-ecs-service-deployment/ecs_setup_ecr_1.png)
2. Within **Amazon Elastic Container Registry** interface:
    - Select **Repositories**
    - Click **Create Registry**
    ![Create ECR Repository](/images/5-ecs-service-deployment/ecs_setup_ecr_2.png)
3. Within **Create Registry** interface:
    - Visibility settings: **Public**
    - Registry name: `todo`
    ![Create ECR Repository](/images/5-ecs-service-deployment/ecs_setup_ecr_3.png)
4. Push Docker image to ECR:
    - Select **Repositories** in the **Public registry** section
    - Select repository **todo** then click **View push commands**
    ![Create ECR Repository](/images/5-ecs-service-deployment/ecs_setup_ecr_4.png)
    - In the `simple-todo-app` folder run the following command:
    ```shell
    cd backend
    ```
    - Run commands on the ECR interface one by one.
{{% notice note %}}
Make sure Docker on your computer is turned on before running these commands.
{{% /notice %}}
    
    After running these commands, we will have a Docker image on the ECR repository as shown in the image:
    ![Create ECR Repository](/images/5-ecs-service-deployment/ecs_setup_ecr_5.png)
5. Check Docker image:
    - Within the ECR interface, select **Repositories** under the **Public registry** section and then select **todo**
    ![Create ECR Repository](/images/5-ecs-service-deployment/ecs_setup_ecr_6.png)
    Click the **Copy URI** button to copy the address of this image.
    Save this address because we will need it in the next steps.
