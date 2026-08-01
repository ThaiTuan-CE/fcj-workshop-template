---
title: "Worklog Tuần 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---
### Mục tiêu tuần 2:

* Thiết lập môi trường AWS IoT Core cho hệ thống Smart Home IoT.
* Tìm hiểu cơ chế xác thực thiết bị bằng Certificate và IoT Policy.
* Thực hành giao tiếp MQTT thông qua MQTT Test Client.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                     | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | -------------- |
| 2   | - Tìm hiểu tổng quan về AWS IoT Core <br> - Nghiên cứu mô hình kết nối giữa thiết bị IoT và AWS Cloud                                                                                         | 22/06/2026   | 22/06/2026      | <https://docs.aws.amazon.com/iot/> |
| 3   | - Tạo **IoT Thing** trên AWS IoT Core <br> - Tìm hiểu Device Registry và quản lý thiết bị                                                                                                      | 23/06/2026   | 23/06/2026      | <https://docs.aws.amazon.com/iot/> |
| 4   | - Tạo **X.509 Certificate** <br> - Tạo **IoT Policy** và cấu hình quyền truy cập cho thiết bị                                                                                                  | 24/06/2026   | 24/06/2026      | <https://docs.aws.amazon.com/iot/> |
| 5   | - Gắn Certificate và IoT Policy vào IoT Thing <br> - Kiểm tra quá trình xác thực và phân quyền của thiết bị                                                                                   | 25/06/2026   | 25/06/2026      | <https://docs.aws.amazon.com/iot/> |
| 6   | - Thực hành sử dụng **MQTT Test Client** <br> - Publish và Subscribe các MQTT Topic <br> - Kiểm tra việc truyền nhận dữ liệu giữa các Topic                                                   | 26/06/2026   | 26/06/2026      | <https://docs.aws.amazon.com/iot/> |

### Kết quả đạt được tuần 2:

* Hiểu được vai trò của AWS IoT Core trong việc kết nối và quản lý các thiết bị IoT.

* Tạo thành công một **IoT Thing** để đại diện cho thiết bị trong hệ thống Smart Home.

* Tạo và quản lý các thông tin bảo mật cần thiết, bao gồm:
  * X.509 Certificate
  * Public Key
  * Private Key
  * IoT Policy

* Cấu hình và gắn thành công Certificate cùng IoT Policy cho IoT Thing.

* Hiểu được cơ chế xác thực và phân quyền của AWS IoT Core đối với thiết bị IoT.

* Thực hành thành công với **MQTT Test Client**, bao gồm:
  * Publish dữ liệu lên MQTT Topic.
  * Subscribe dữ liệu từ MQTT Topic.
  * Kiểm tra quá trình truyền nhận dữ liệu theo thời gian thực.
