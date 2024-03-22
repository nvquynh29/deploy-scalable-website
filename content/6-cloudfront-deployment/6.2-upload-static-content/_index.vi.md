---
title : "Nội dung tĩnh"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : "<b>6.2 </b>"
---
#### Tải lên nội dung tĩnh
1. Sao chép domain name của CloudFront distribution:
    - Xem chi tiết CloudFront distribution vừa tạo
    - Chọn tab **General**
    - Sao chép domain name
    ![Upload Static Content](/images/6-cloudfront-deployment/cloudfront_static_content_1.png)
2. Build frontend
    - Mở file `simple-todo-app/frontend/.env`
    - Thay `<distribution_domain_name_https>` bằng domain name bạn vừa sao chép (VD: `https://d5g9rzkrknce9.cloudfront.net`) rồi cập nhật:
    ```
    REACT_APP_API_ENDPOINT=<distribution_domain_name_https>/api
    ```
    - Chạy lệnh sau tại folder `simple-todo-app/frontend`, hãy đảm bảo rằng máy bạn đã cài [NodeJS](https://nodejs.org/en) và [yarn](https://yarnpkg.com):
    ```shell
    yarn
    yarn build
    ```

    Sau khi chạy lệnh build này thành công bạn sẽ thấy một folder `build`, hãy mở folder sẵn để chuẩn bị cho bước tiếp theo.
    ![Upload Static Content](/images/6-cloudfront-deployment/cloudfront_static_content_2.png)
3. Tải lên nội dung tĩnh
  - Tại giao diện của S3 bucket **fcj-todo-bucket-1** bấm **Upload**
  ![Upload Static Content](/images/6-cloudfront-deployment/cloudfront_static_content_3.png)
  - Kéo thả toàn bộ file trong folder build vào phần **Files and folders**
  - Bấm **Upload**
  ![Upload Static Content](/images/6-cloudfront-deployment/cloudfront_static_content_4.png)
  Sau khi upload xong ta sẽ có các file như trong ảnh dưới:
  ![Upload Static Content](/images/6-cloudfront-deployment/cloudfront_static_content_5.png)