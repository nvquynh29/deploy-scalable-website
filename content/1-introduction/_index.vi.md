---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 1. </b> "
---

Trong bài lab này, chúng ta sẽ sử dụng những dịch vụ dưới đây của AWS

#### Virtual Private Cloud (VPC)

**Amazon Virtual Private Cloud (Amazon VPC)** là **“Đám mây Riêng tư Ảo”** là một mạng ảo tùy chỉnh nằm bên trong **AWS Cloud** và tách biệt với toàn bộ thế giới bên ngoài. Khái niệm này tương tự như việc thiết kế và triển khai một mạng độc lập riêng biệt hoạt động trong một trung tâm dữ liệu on-premise, loại hình vẫn còn rất phổ biến hiện nay tại nhiều nơi trên thế giới.

Bên trong VPC tùy chỉnh đó, bạn có toàn quyền kiểm kiểm soát môi trường mạng ảo của mình, nghĩa là vừa có khả năng khởi tạo và chạy các tài nguyên AWS, vừa có thể lựa chọn phạm vi địa chỉ IP, tạo các mạng con và cấu hình các bảng định tuyến và cổng kết nối mạng. Bạn có thể sử dụng cả IPv4 và IPv6 để truy cập an toàn và dễ dàng vào tài nguyên và ứng dụng trong VPC.

#### Amazon Relational Database Service (Amazon RDS)
**Amazon RDS** là dịch vụ cơ sở dữ liệu quan hệ dễ dàng quản lý, được tối ưu hoá để tiết kiệm chi phí. RDS rất đơn giản để thiết lập, vận hành và mở rộng tuỳ theo nhu cầu. RDS tự động hoá các tác vụ quản lý phổ biến chẳng hạn như khởi tạo, cấu hình, sao lưu và vá lỗi. RDS cho phép khách hàng tạo cơ sở dữ liệu mới chỉ trong vài phút và cung cấp tính linh hoạt để tuỳ chỉnh cơ sở dữ liệu đáp ứng với nhu cầu sử dụng. Khách hàng có thể tối ưu hóa hiệu suất với các tính năng như Multi-AZ với hai bản sao dự phòng có thể đọc hoặc đọc và ghi được tối ưu hóa,  đồng thời lựa chọn nhiều tùy chọn giá để quản lý chi phí hiệu quả.

#### Parameter Store
**Parameter Store** là một chức năng của AWS Systems Manager, cung cấp khả năng lưu trữ phân cấp, an toàn để quản lý configuration data và secrets. Bạn có thể lưu trữ dữ liệu như mật khẩu, địa chỉ cơ sở dữ liệu... dưới dạng văn bản thông thường hoặc dữ liệu được mã hóa. Bạn có thể tham chiếu các tham số này trong scripts, commands, hoặc cấu hình của dịch vụ khác bằng cách sử dụng Amazon Resource Name (ARN) của tham số.

#### Amazon Elastic Container Registry (ECR)
**Amazon Elastic Container Registry (Amazon ECR)** là dịch vụ lưu trữ container một cách bảo mật, có thể mở rộng và đáng tin cậy được quản lý bởi AWS. Amazon ECR hỗ trợ kho lưu trữ riêng tư với khả năng cấu hình quyển truy cập dựa trên tài nguyên bằng dịch vụ AWS IAM. Tính năng này cho phép bạn chỉ định những người dùng hoặc máy ảo EC2 nào có thể truy cập vào kho lưu trữ. ECR cho phép người dùng sử dụng CLI để quản lý, pull, push Docker images

#### Amazon Elastic Container Service (ECS)
**Amazon Elastic Container Service (Amazon ECS)** là dịch vụ điều phối container được quản lý hoàn toản bởi AWS. ECS giúp người dùng dễ dàng triển khai, quản lý và mở rộng quy mô của ứng dụng dưới dạng container. ECS là dịch vụ được quản lý hoàn toàn bởi AWS cho nên đã được tích hợp sẵn các best practices về cấu hình và vận hành ứng dụng. ECS có thể tích hợp với ECR và Docker một cách rất dễ dàng giúp cho việc triển khai ứng dụng trở nên thuận tiện hơn, người dùng chỉ cần tập trung vào việc phát triển ưng dụng còn phần triển khai đã được hỗ trợ bởi AWS.

#### Amazon CloudWatch
**CloudWatch** giám sát các tài nguyên và ứng dụng trên AWS bằng cách thu thập số liệu theo thời gian. Dịch vụ này cung cấp sẵn các dashboard cho các dịch vụ cốt lõi và cho phép người dùng tạo các dashboard để trực quan hoá các số liệu đã chọn. CloudWatch có thể tích hợp với rất nhiều dịch vụ khác một cách rất dễ dàng. Một trong những ứng dụng phổ biến nhất của CloudWatch đó là thu thập log của ứng dụng.

#### Elastic Load Balancing
**Elastic Load Balancing** tự động phân phối lưu lượng truy cập đến nhiều mục tiêu khác nhau, chẳng hạn như máy ảo EC2, containers hoặc địa chỉ IP trong một hoặc nhiều vùng sẵn sàng. Nó giám sát tình trạng truy cập của các mục tiêu đã đăng ký và chỉ định tuyến lưu lượng truy cập đến các mục tiêu đang hoạt động. Nhờ vậy mà cân bằng tải có thể giúp hệ thống biết được khi nào cần mở rộng, giảm bớt lượng tài nguyên cần sử dụng dựa trên lưu lượng thực tế.

#### Amazon Simple Storage Service (S3)
**Amazon Simple Storage Service (Amazon S3)** là một dịch vụ lưu trữ dạng đối tượng cung cấp khả năng mở rộng, tính sẵn sàng, bảo mật và hiệu suất ở mức cao nhất. Khách hàng ở mọi quy mô và mọi ngành nghề đều có thể sử dụng S3 để lưu trữ và bảo vệ bất kỳ lượng dữ liệu nào cho nhiều trường hợp sử dụng, chẳng hạn như kho dữ liệu, trang web, ứng dụng di động, sao lưu và khôi phục, lưu trữ, ứng dụng doanh nghiệp, thiết bị IoT và phân tích dữ liệu lớn.

#### Amazon CloudFront
**Amazon CloudFront** là một dịch vụ giúp tăng tốc độ phân phối nội dung trang web tĩnh và động chẳng hạn như các tệp HTML, CSS, Javascript và hình ảnh cho người dùng của bạn. CloudFront tăng tốc độ phân phối nội dung bằng cách:
- Sử dụng hạ tầng toàn cầu của AWS để phân phối nội dung gần hơn với người dùng, giảm độ trễ
- Lưu nội dung vào bộ nhớ đệm tại các máy chủ gần người dùng, do đó nội dung này luôn có sẵn mà không cần phải quay lại máy chủ gốc để truy vấn
- Định tuyến các yêu cầu của người dùng thông qua hạ tầng mạng của AWS để phân phối nội dung nhanh hơn so với đường truyền internet

Những điều này giúp cho độ trễ của CloudFront thấp hơn, tốc độ truyền dữ liệu cao hơn và độ tin cậy được cải thiện hơn.

#### Amazon Route 53
**Amazon Route 53** là dịch vụ hệ thống tên miền (DNS) có tính sẵn sàng và khả năng mở rộng cao. Bạn có thể sử dụng Route 53 để đăng ký tên miền, cấu hình định tuyến DNS và kiểm tra tình trạng của hệ thống. Route 53 có thể tích hợp với rất nhiều dịch vụ khác của AWS giúp cho việc triển khai và cấu hình tên miền ứng dụng web trở nên rất dễ dàng.

#### AWS Certificate Manager (ACM)
**AWS Certificate Manager (ACM)** xử lý sự phức tạp của việc tạo, lưu và gia hạn chứng chỉ SSL/TLS X.509 công khai và riêng tư để bảo vệ các trang web và ứng dụng AWS. Chứng chỉ SSL/TLS giúp cho phép máy chủ của ứng dụng web giao tiếp với người dùng thông qua giao thức HTTPS bảo mật hơn so với giao thức HTTP. Một số trình duyệt hiện đại đã cho rằng ứng dụng web không đủ an toàn nếu như máy chủ không hỗ trợ giao thức HTTPS và hiện cảnh báo với người dùng nếu họ truy cập vào một trang web như vậy.
Người dùng có thể cung cấp chứng chỉ cho các dịch vụ AWS tích hợp của mình bằng cách cấp chúng trực tiếp với ACM hoặc bằng cách nhập chứng chỉ của bên thứ ba vào hệ thống quản lý ACM. Chứng chỉ ACM có thể bảo mật các tên miền đơn lẻ, nhiều tên miền cụ thể, miền ký tự đại diện hoặc kết hợp các tên miền này. Chứng chỉ ký tự đại diện ACM có thể bảo vệ số lượng tên miền phụ không giới hạn.
