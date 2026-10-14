# BÁO CÁO THỰC HÀNH KIỂM THỬ HIỆU NĂNG BẰNG APACHE JMETER

## 1. Giới thiệu

Apache JMeter là công cụ mã nguồn mở được sử dụng để kiểm thử hiệu năng của website và ứng dụng. Công cụ cho phép mô phỏng nhiều người dùng truy cập hệ thống, gửi yêu cầu và thu thập các thông số như thời gian phản hồi, số lượng yêu cầu và tỷ lệ lỗi.

Trong bài thực hành này, em sử dụng Apache JMeter để kiểm thử hiệu năng website Apache JMeter tại địa chỉ https://jmeter.apache.org/.

## 2. Mục tiêu

- Làm quen với giao diện và cách sử dụng Apache JMeter.
- Xây dựng Test Plan để gửi yêu cầu HTTP đến website.
- Mô phỏng 50 người dùng ảo truy cập website.
- Thu thập và phân tích kết quả kiểm thử.
- Sử dụng Git và GitHub để lưu trữ bài thực hành, báo cáo và ảnh minh chứng.

## 3. Công cụ sử dụng

| Công cụ | Phiên bản hoặc mục đích |
|---|---|
| Apache JMeter | 5.6.3 |
| Java JDK | 21 |
| Visual Studio Code | Chỉnh sửa README và quản lý dự án |
| Git | Quản lý phiên bản |
| GitHub | Lưu trữ mã nguồn và báo cáo |

## 4. Cấu hình kiểm thử

### 4.1. Cấu hình Thread Group

| Thông số | Giá trị |
|---|---:|
| Number of Threads (Users) | 50 |
| Ramp-up Period | 10 giây |
| Loop Count | 1 |
| Số yêu cầu dự kiến | 50 |

Thread Group được cấu hình để mô phỏng 50 người dùng ảo. Thời gian Ramp-up là 10 giây, nghĩa là JMeter khởi tạo người dùng trong khoảng thời gian này. Mỗi người dùng thực hiện một vòng lặp.

### 4.2. Cấu hình HTTP Request

| Thông số | Giá trị |
|---|---|
| Protocol | HTTPS |
| Server Name or IP | jmeter.apache.org |
| Method | GET |
| Path | / |

HTTP Request sử dụng phương thức GET để gửi yêu cầu truy cập trang chủ website.

### 4.3. Các Listener sử dụng

- **View Results Tree:** Quan sát kết quả từng yêu cầu và thông tin phản hồi từ máy chủ.
- **Summary Report:** Tổng hợp số lượng mẫu, thời gian phản hồi, tỷ lệ lỗi và thông lượng.

## 5. Hình ảnh minh chứng

### 5.1. Tổng quan Test Plan

![Tổng quan Test Plan](screenshots/01-test-plan.png)

### 5.2. Cấu hình Thread Group với 50 người dùng

![Cấu hình Thread Group](screenshots/02-thread-group.png)

### 5.3. Cấu hình HTTP Request

![Cấu hình HTTP Request](screenshots/03-http-request.png)

### 5.4. Kết quả từng yêu cầu

![Kết quả View Results Tree](screenshots/04-test-results.png)

### 5.5. Báo cáo tổng hợp Summary Report

![Kết quả Summary Report](screenshots/05-summary-report.png)

## 6. Kết quả kiểm thử

Các chỉ số dưới đây cần được cập nhật theo Summary Report thực tế sau lần chạy 50 người dùng.

| Chỉ số | Kết quả |
|---|---|
| Tổng số yêu cầu (Samples) | Điền số liệu thực tế |
| Thời gian phản hồi trung bình (Average) | Điền số liệu thực tế (ms) |
| Thời gian phản hồi nhỏ nhất (Min) | Điền số liệu thực tế (ms) |
| Thời gian phản hồi lớn nhất (Max) | Điền số liệu thực tế (ms) |
| Tỷ lệ lỗi (Error %) | Điền số liệu thực tế |
| Thông lượng (Throughput) | Điền số liệu thực tế |

### 6.1. Nhận xét kết quả

Sau khi thực hiện kiểm thử, em sử dụng Summary Report để đánh giá khả năng phản hồi của website.

- **Samples:** Cho biết tổng số yêu cầu đã được thực hiện.
- **Average:** Cho biết thời gian phản hồi trung bình của các yêu cầu.
- **Min và Max:** Thể hiện thời gian phản hồi nhỏ nhất và lớn nhất.
- **Error %:** Cho biết tỷ lệ yêu cầu xảy ra lỗi.
- **Throughput:** Thể hiện số lượng yêu cầu được xử lý trong một đơn vị thời gian.

Thông qua các chỉ số trên, có thể đánh giá sơ bộ khả năng phản hồi của website trong lần kiểm thử. Tuy nhiên, kết quả chỉ phản ánh điều kiện thử nghiệm tại thời điểm chạy và không đủ để kết luận về giới hạn tải tối đa của hệ thống.

## 7. Kết luận

Qua bài thực hành, em đã làm quen với Apache JMeter, biết cách tạo Test Plan, cấu hình Thread Group, gửi yêu cầu HTTP và sử dụng các Listener để thu thập kết quả.

Việc mô phỏng 50 người dùng giúp em hiểu rõ hơn cách kiểm thử hiệu năng và cách phân tích những chỉ số cơ bản như thời gian phản hồi, tỷ lệ lỗi và thông lượng. Báo cáo cùng hình ảnh minh chứng được lưu trữ trên GitHub để thuận tiện cho việc kiểm tra và đánh giá.

## 8. Tài liệu tham khảo

- Trang chủ Apache JMeter: https://jmeter.apache.org/
- Tài liệu hướng dẫn Apache JMeter: https://jmeter.apache.org/usermanual/
- Kho lưu trữ bài thực hành: https://github.com/hongtuoi0208/jmeter-performance-testing

## 9. Repository GitHub

Link GitHub: https://github.com/hongtuoi0208/jmeter-performance-testing
