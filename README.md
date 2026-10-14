# Báo cáo thực hành Apache JMeter

## 1. Mục tiêu
- Tìm hiểu công cụ kiểm thử hiệu năng Apache JMeter.
- Xây dựng kịch bản kiểm thử HTTP.
- Thực hiện kiểm thử với nhiều người dùng mô phỏng.
- Đọc và phân tích kết quả kiểm thử.

## 2. Công cụ sử dụng
- Apache JMeter 5.6.3
- Java JDK 21
- Visual Studio Code
- Git và GitHub

## 3. Kịch bản kiểm thử
- Website: https://jmeter.apache.org/
- Protocol: HTTPS
- Method: GET
- Path: /
- Number of Threads: 3
- Ramp-up Period: 3 giây
- Loop Count: 1

## 4. Quy trình thực hiện
1. Tạo Test Plan.
2. Tạo Thread Group với 3 người dùng mô phỏng.
3. Thêm HTTP Request để gửi yêu cầu GET đến website.
4. Thêm View Results Tree để kiểm tra từng yêu cầu.
5. Thêm Summary Report để tổng hợp kết quả.
6. Chạy kiểm thử và ghi nhận số liệu.

## 5. Hình ảnh minh họa

### 5.1. Cấu hình Test Plan
![Cấu hình Test Plan](screenshots/01-test-plan.png)

### 5.2. Cấu hình Thread Group
![Cấu hình Thread Group](screenshots/02-thread-group.png)

### 5.3. Cấu hình HTTP Request
![Cấu hình HTTP Request](screenshots/03-http-request.png)

### 5.4. Kết quả View Results Tree
![Kết quả kiểm thử](screenshots/04-test-results.png)

### 5.5. Kết quả Summary Report
![Báo cáo tổng hợp](screenshots/05-summary-report.png)

## 6. Kết quả kiểm thử

Điền số liệu sau khi chạy kiểm thử:

| Chỉ số | Kết quả thực tế |
|---|---|
| Samples | [Điền kết quả] |
| Average | [Điền kết quả] ms |
| Min | [Điền kết quả] ms |
| Max | [Điền kết quả] ms |
| Error % | [Điền kết quả] |
| Throughput | [Điền kết quả] |

### Nhận xét
Dựa trên kết quả thu được, đánh giá thời gian phản hồi và tỷ lệ lỗi của các yêu cầu. Kết quả chỉ phản ánh kịch bản kiểm thử nhỏ đã thực hiện, không đại diện cho khả năng chịu tải tối đa của website.

## 7. Kết luận
Qua bài thực hành, em đã biết cách tạo và chạy một kịch bản kiểm thử HTTP bằng Apache JMeter, đồng thời biết cách sử dụng View Results Tree và Summary Report để đọc kết quả.

## 8. Tài liệu tham khảo
- Apache JMeter: https://jmeter.apache.org/
- Apache JMeter User Manual: https://jmeter.apache.org/usermanual/
