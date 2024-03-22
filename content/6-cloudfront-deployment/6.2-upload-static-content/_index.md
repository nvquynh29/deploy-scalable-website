---
title : "Static content"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : "<b>6.2 </b>"
---
#### Upload
1. Copy the domain name of CloudFront distribution:
    - View details of the newly created CloudFront distribution
    - Select **General** tab
    - Copy the domain name
    ![Upload Static Content](../../../images/6-cloudfront-deployment/cloudfront_static_content_1.png)
2. Build frontend
    - Open file `simple-todo-app/frontend/.env`
    - Replace `<distribution domain name_https>` with the domain name you just copied (e.g. `https://d5g9rzkrknce9.cloudfront.net`) and update:
    ```
    REACT_APP_API_ENDPOINT=<distribution_domain_name_https>/api
    ```
    - Run the following command in the `simple-todo-app/frontend` folder, make sure your device has [NodeJS](https://nodejs.org/en) and [yarn](https://yarnpkg.com) installed:
    ```shell
    yarn
    yarn build
    ```

    After running this build command successfully, you will see a `build` folder, open the folder to prepare for the next step.
    ![Upload Static Content](../../../images/6-cloudfront-deployment/cloudfront_static_content_2.png)
3. Upload static content
  - Within S3 bucket **fcj-todo-bucket-1** interface click **Upload**
  ![Upload Static Content](../../../images/6-cloudfront-deployment/cloudfront_static_content_3.png)
  - Drag and drop all files in the build folder into the **Files and folders** section
  - Click **Upload**
  ![Upload Static Content](../../../images/6-cloudfront-deployment/cloudfront_static_content_4.png)
  After uploading, we will have files as shown in the image below:
  ![Upload Static Content](../../../images/6-cloudfront-deployment/cloudfront_static_content_5.png)