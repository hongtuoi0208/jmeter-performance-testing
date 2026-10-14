# BÁO CÁO THỰC HÀNH KIỂM THỬ PHẦN MỀM BẰNG APACHE JMETER

## 1. Giới thiệu

Apache JMeter là công cụ mã nguồn mở được sử dụng để kiểm thử hiệu năng của ứng dụng, máy chủ và dịch vụ web. Công cụ cho phép mô phỏng nhiều người dùng gửi yêu cầu đến hệ thống và thu thập các chỉ số như thời gian phản hồi, số lượng yêu cầu và tỷ lệ lỗi.

Trong bài thực hành này, em sử dụng Apache JMeter phiên bản 5.6.3 để xây dựng và thực hiện một kịch bản kiểm thử HTTP đơn giản.

## 2. Mục tiêu

- Làm quen với giao diện và cách sử dụng Apache JMeter.
- Tạo Test Plan và Thread Group.
- Gửi yêu cầu HTTP đến một website.
- Theo dõi kết quả bằng View Results Tree.
- Tổng hợp và phân tích số liệu bằng Summary Report.
- Lưu kịch bản kiểm thử và báo cáo lên GitHub.

## 3. Công cụ sử dụng

| Công cụ | Phiên bản hoặc thông tin |
|---|---|
| Apache JMeter | 5.6.3 |
| Java | JDK 21 |
| Visual Studio Code | Môi trường chỉnh sửa README |
| Git | Quản lý phiên bản |
| GitHub | Lưu trữ và nộp bài |

## 4. Thiết lập kịch bản kiểm thử

Website được sử dụng trong bài thực hành là trang chủ Apache JMeter: https://jmeter.apache.org/

### 4.1. Cấu hình Thread Group

| Tham số | Giá trị |
|---|---|
| Name | Website Load Test |
| Number of Threads (users) | 3 |
| Ramp-up period | 3 giây |
| Loop Count | 1 |

Kịch bản mô phỏng 3 người dùng, mỗi người gửi một yêu cầu trong một vòng lặp.

### 4.2. Cấu hình HTTP Request

| Tham số | Giá trị |
|---|---|
| Name | Open JMeter Website |
| Protocol | HTTPS |
| Server Name or IP | jmeter.apache.org |
| Method | GET |
| Path | / |

HTTP Request được sử dụng để gửi yêu cầu GET đến trang chủ Apache JMeter.

### 4.3. Các thành phần theo dõi kết quả

- **View Results Tree:** Hiển thị chi tiết từng yêu cầu, mã phản hồi và nội dung phản hồi.
- **Summary Report:** Tổng hợp số lượng yêu cầu, thời gian phản hồi, tỷ lệ lỗi và thông lượng.

## 5. Hình ảnh minh họa

### 5.1. Cấu hình Test Plan

![Cấu hình Test Plan](screenshots/01-test-plan.png)

### 5.2. Cấu hình Thread Group

![Cấu hình Thread Group](screenshots/02-thread-group.png)

### 5.3. Cấu hình HTTP Request

![Cấu hình HTTP Request](screenshots/03-http-request.png)

### 5.4. Kết quả trong View Results Tree

![Kết quả kiểm thử](screenshots/04-test-results.png)

### 5.5. Báo cáo Summary Report

![Báo cáo tổng hợp](screenshots/05-summary-report.png)

## 6. Kết quả kiểm thử

Sau khi thực hiện kịch bản kiểm thử với 3 người dùng mô phỏng, thu được các kết quả sau:

| Chỉ số | Kết quả |
|---|---:|
| Samples | 3 |
| Average | 7504,67 ms |
| Min | 6527 ms |
| Max | 8462 ms |
| Error % | 0% |
| Throughput | Cần đối chiếu với Summary Report |

### 6.1. Phân tích kết quả

Cả 3 yêu cầu đều nhận được mã phản hồi HTTP `200 OK`. Các kết quả được cung cấp không ghi nhận lỗi, tương ứng với tỷ lệ lỗi 0%.

Thời gian phản hồi nhỏ nhất là 6527 ms, lớn nhất là 8462 ms và trung bình khoảng 7504,67 ms. Thời gian phản hồi giữa các yêu cầu có sự khác biệt.

Thông lượng cần được ghi nhận trực tiếp từ cột Throughput trong Summary Report của JMeter. Kết quả trên chỉ phản ánh lần kiểm thử nhỏ đã thực hiện, không đủ để kết luận về khả năng chịu tải tối đa của website.

## 7. Kết luận

Qua bài thực hành, em đã biết cách tạo một kịch bản kiểm thử HTTP bằng Apache JMeter, cấu hình số lượng người dùng mô phỏng và theo dõi kết quả thông qua View Results Tree và Summary Report.

Bài thực hành giúp em hiểu thêm cách thu thập, đọc và phân tích các chỉ số cơ bản trong kiểm thử hiệu năng phần mềm.

## 8. Tài liệu tham khảo

1. Apache JMeter Official Website: https://jmeter.apache.org/
2. Apache JMeter User Manual: https://jmeter.apache.org/usermanual/

## 9. Repository

GitHub: https://github.com/hongtuoi0208/jmeter-performance-testing
