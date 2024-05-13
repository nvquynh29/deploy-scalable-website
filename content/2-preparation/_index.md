---
title : "Preparation"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2. </b> "
---

## Preparation

AWS CLI is a command line interface tool that helps users interact with AWS services. In this section we will install and configure the AWS CLI on our computer.

#### Install AWS CLI

Access this address to install the AWS CLI that is appropriate for your operating system: [Install AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html#getting-started-install-instructions)

#### Configure AWS CLI
1. Create AWS access key
    - Access **IAM** service
    - Select **Users** in the sidebar
    - Select current user
    - Scroll down to the **Access keys** section and select **Create access key**
    ![IAM create access key](/images/2-preparation/iam_create_access_key_1.png)
    - Select the use case as **Command Line Interface (CLI)** and select **Next**
    ![IAM create access key](/images/2-preparation/iam_create_access_key_2.png)
    - Leave the remaining configurations as default and then create an access key.
    After creating, you will receive a pair of **Access key** and **Secret access key** as below.
    Save these keys or download the CSV file to your computer to prepare for the next step.
    ![IAM create access key](/images/2-preparation/iam_create_access_key_3.png)

2. Configure AWS CLI

    Run the following command to configure the AWS CLI. Leave **AWS Access Key ID** and **AWS Secret Access Key** as your keys. **Default region** is set to `ap-southeast-1` (Singapore), **Default output format** is `json`
    ```shell
    aws configure
    ```
    You can check if you have configured correctly with the following command, if there are no errors then you have configured successfully.
    ```shell
    aws s3 ls
    ```
