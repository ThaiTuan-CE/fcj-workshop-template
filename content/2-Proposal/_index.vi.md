---
title: "Bản đề xuất"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---
# Hệ thống Nhà thông minh IoT trên nền tảng AWS

## Hệ thống giám sát nhà thông minh an toàn sử dụng công nghệ IoT và các dịch vụ đám mây AWS

---

# 1. Tóm tắt dự án

Dự án đề xuất xây dựng một hệ thống Nhà thông minh IoT sử dụng bo mạch phát triển ESP32-S3 kết hợp với các dịch vụ điện toán đám mây của AWS.

Hệ thống liên tục giám sát các điều kiện môi trường bao gồm nhiệt độ, độ ẩm, cường độ ánh sáng và trạng thái cửa. Dữ liệu từ các cảm biến được truyền bảo mật đến AWS IoT Core thông qua giao thức MQTT trên nền TLS 1.2 với cơ chế xác thực bằng chứng chỉ X.509.

AWS IoT Rules Engine xử lý dữ liệu telemetry nhận được và chuyển tiếp đến Amazon DynamoDB để lưu trữ. Khi hệ thống phát hiện cửa được mở, Amazon SNS sẽ tự động gửi email thông báo đến người dùng.

Kiến trúc được đề xuất là một giải pháp IoT gọn nhẹ, an toàn và có khả năng mở rộng, phù hợp cho các ứng dụng nhà thông minh cũng như mục đích học tập và nghiên cứu.

---

# 2. Phát biểu bài toán

## Thách thức hiện nay

Các hệ thống giám sát nhà ở truyền thống thường hoạt động cục bộ và thiếu khả năng quản lý tập trung.

Những hệ thống này thường chưa đáp ứng được các yêu cầu như:

- Giám sát từ xa theo thời gian thực.
- Xác thực thiết bị an toàn.
- Lưu trữ dữ liệu tập trung.
- Gửi thông báo tự động khi xảy ra sự kiện.
- Khả năng mở rộng trên nền tảng đám mây.

Khi số lượng thiết bị IoT ngày càng tăng, việc quản lý dữ liệu cảm biến và giám sát trạng thái hệ thống trở nên khó khăn hơn.

---

## Giải pháp đề xuất

Hệ thống Nhà thông minh IoT được đề xuất sử dụng các dịch vụ được quản lý của AWS nhằm cung cấp khả năng giao tiếp an toàn, lưu trữ dữ liệu tập trung và giám sát theo thời gian thực.

ESP32-S3 thu thập dữ liệu từ nhiều cảm biến và gửi các bản tin telemetry đến AWS IoT Core thông qua giao thức MQTT trên nền TLS.

AWS IoT Rules Engine tự động chuyển tiếp dữ liệu telemetry đến Amazon DynamoDB để lưu trữ lâu dài.

Khi cảm biến cửa phát hiện cửa mở, một IoT Rule khác sẽ gửi thông báo đến Amazon SNS để tự động gửi email cảnh báo đến người dùng đã đăng ký.

Ngoài ra, hệ thống còn hỗ trợ điều khiển relay từ xa thông qua các MQTT Command Topic.

---

# Lợi ích

Giải pháp đề xuất mang lại các lợi ích sau:

- Giao tiếp bảo mật bằng MQTT trên nền TLS 1.2.
- Xác thực thiết bị bằng chứng chỉ X.509.
- Lưu trữ dữ liệu telemetry tập trung.
- Gửi email thông báo tự động.
- Chi phí vận hành thấp.
- Kiến trúc đơn giản với các dịch vụ AWS được quản lý hoàn toàn.
- Dễ dàng mở rộng để tích hợp thêm các thiết bị Nhà thông minh trong tương lai.

---

# 3. Kiến trúc giải pháp

Hệ thống Nhà thông minh IoT bao gồm một thiết bị ESP32-S3 kết nối với nhiều cảm biến môi trường và các dịch vụ điện toán đám mây của AWS.

ESP32-S3 định kỳ thu thập dữ liệu telemetry và gửi các bản tin JSON đến AWS IoT Core.

AWS IoT Core xác thực thiết bị bằng chứng chỉ X.509 và IoT Policy trước khi chuyển tiếp dữ liệu đến AWS IoT Rules Engine.

AWS IoT Rules Engine lưu dữ liệu vào Amazon DynamoDB và gửi cảnh báo mở cửa thông qua Amazon SNS.

Kiến trúc tổng thể của hệ thống được minh họa như hình dưới đây.

![Smart Home IoT Architecture](/images/workshop/5.2/architec.jpg)

# Các dịch vụ AWS sử dụng

- AWS IoT Core
- AWS IoT Rules Engine
- Amazon DynamoDB
- Amazon Simple Notification Service (Amazon SNS)
- AWS Identity and Access Management (AWS IAM)
- Amazon CloudWatch

---

# Thành phần phần cứng

- Bo mạch phát triển ESP32-S3
- Cảm biến nhiệt độ và độ ẩm DHT11
- Cảm biến ánh sáng LDR
- Cảm biến cửa từ
- Module Relay

---

# 4. Triển khai kỹ thuật

## Các giai đoạn triển khai

Dự án được chia thành bốn giai đoạn chính.

### Giai đoạn 1

Phân tích yêu cầu và thiết kế kiến trúc hệ thống.

### Giai đoạn 2

Cấu hình AWS IoT Core, bao gồm tạo IoT Thing, chứng chỉ X.509, IoT Policy và kiểm thử MQTT.

### Giai đoạn 3

Phát triển chương trình nhúng cho ESP32-S3, bao gồm kết nối Wi-Fi, giao tiếp MQTT trên nền TLS, thu thập dữ liệu telemetry và điều khiển relay.

### Giai đoạn 4

Tích hợp hệ thống với nền tảng đám mây, kiểm thử, đánh giá hệ thống và hoàn thiện tài liệu.

---

# Yêu cầu kỹ thuật

### Phần mềm

- Visual Studio Code
- PlatformIO
- AWS Management Console

### Dịch vụ AWS

- AWS IoT Core
- Amazon DynamoDB
- Amazon SNS
- AWS IAM

### Ngôn ngữ lập trình

- C++
- Arduino Framework

### Giao thức truyền thông

- MQTT trên nền TLS 1.2

---

# 5. Kế hoạch thực hiện

| Tuần | Công việc |
|------|-----------|
| Tuần 1 | Phân tích yêu cầu và nghiên cứu AWS |
| Tuần 2 | Cấu hình AWS IoT Core và môi trường phát triển |
| Tuần 3 | Phát triển firmware và cấu hình các dịch vụ Cloud |
| Tuần 4 | Tích hợp ESP32-S3 với AWS IoT Core |
| Tuần 5 | Tối ưu kiến trúc hệ thống và firmware |
| Tuần 6 | Kiểm thử toàn bộ hệ thống |
| Tuần 7 | Hoàn thiện tài liệu và chuẩn bị báo cáo, trình bày |

---

# 6. Dự toán chi phí

Dự án ưu tiên sử dụng các dịch vụ thuộc AWS Free Tier nhằm giảm thiểu chi phí vận hành.

Chi phí vận hành dự kiến ở mức rất thấp vì:

- Số lượng bản tin AWS IoT Core không nhiều.
- Amazon DynamoDB chỉ lưu trữ dữ liệu telemetry có kích thước nhỏ.
- Amazon SNS chỉ gửi thông báo khi xảy ra sự kiện.
- Amazon CloudWatch chỉ được sử dụng để theo dõi log và giám sát hệ thống.

Chi phí phần cứng bao gồm:

- Bo mạch ESP32-S3
- Cảm biến DHT11
- Cảm biến ánh sáng LDR
- Cảm biến cửa từ
- Module Relay

---

# 7. Đánh giá rủi ro

## Các rủi ro có thể xảy ra

- Mất kết nối Wi-Fi.
- Gián đoạn giao tiếp MQTT.
- Cảm biến hoạt động không chính xác.
- Cấu hình AWS sai.
- Email thông báo bị chậm.

---

## Biện pháp giảm thiểu

- Tự động kết nối lại Wi-Fi khi mất kết nối.
- Tự động kết nối lại MQTT.
- Kiểm tra và xác thực dữ liệu cảm biến.
- Áp dụng nguyên tắc phân quyền tối thiểu (Least Privilege) trong AWS IAM.
- Kiểm thử AWS IoT Rules trước khi triển khai chính thức.

---

# 8. Kết quả mong đợi

Sau khi hoàn thành, hệ thống Nhà thông minh IoT sẽ cung cấp các chức năng sau:

- Giao tiếp bảo mật giữa ESP32-S3 và AWS IoT Core.
- Giám sát nhiệt độ, độ ẩm, ánh sáng và trạng thái cửa theo thời gian thực.
- Điều khiển relay từ xa thông qua MQTT.
- Gửi email cảnh báo tự động khi cửa được mở.
- Lưu trữ dữ liệu telemetry tập trung trên Amazon DynamoDB.
- Kiến trúc có khả năng mở rộng để tích hợp thêm các thiết bị Nhà thông minh trong tương lai.

Dự án cũng là một ví dụ thực tiễn về việc tích hợp hệ thống nhúng với các dịch vụ điện toán đám mây AWS trong các ứng dụng Internet of Things (IoT).