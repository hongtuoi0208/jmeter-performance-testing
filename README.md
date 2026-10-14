# BÁO CÁO KIỂM THỬ HIỆU NĂNG BẰNG APACHE JMETER

## 1. Giới thiệu

Apache JMeter là công cụ mã nguồn mở dùng để kiểm thử hiệu năng của website và ứng dụng. Công cụ cho phép mô phỏng nhiều người dùng gửi yêu cầu đến máy chủ, đồng thời thu thập các thông số như thời gian phản hồi, số lượng yêu cầu, tỷ lệ lỗi và thông lượng.

Trong bài thực hành này, em sử dụng Apache JMeter để kiểm thử hiệu năng website Apache JMeter tại địa chỉ https://jmeter.apache.org/.

## 2. Mục tiêu

- Làm quen với giao diện và cách sử dụng Apache JMeter.
- Xây dựng Test Plan để kiểm thử website bằng HTTP Request.
- Mô phỏng 50 người dùng ảo truy cập website.
- Thu thập và phân tích các chỉ số hiệu năng.
- Lưu trữ báo cáo và hình ảnh minh chứng trên GitHub.

## 3. Công cụ sử dụng

| Công cụ | Phiên bản hoặc mục đích |
|---|---|
| Apache JMeter | 5.6.3 |
| Java JDK | 21 |
| Visual Studio Code | Chỉnh sửa báo cáo |
| Git | Quản lý phiên bản |
| GitHub | Lưu trữ dự án |

## 4. Thiết lập kiểm thử

### 4.1. Cấu hình Thread Group

| Thông số | Giá trị |
|---|---:|
| Number of Threads (Users) | 50 |
| Ramp-up Period | 10 giây |
| Loop Count | 1 |
| Số yêu cầu dự kiến | 50 |

Thread Group được thiết lập với 50 người dùng ảo, thời gian khởi tạo người dùng là 10 giây và mỗi người dùng thực hiện một vòng lặp. Với một HTTP Request trong mỗi vòng lặp, số yêu cầu dự kiến là 50.

### 4.2. Cấu hình HTTP Request

| Thông số | Giá trị |
|---|---|
| Protocol | HTTPS |
| Server Name or IP | jmeter.apache.org |
| Method | GET |
| Path | / |

HTTP Request sử dụng phương thức GET để gửi yêu cầu đến trang chủ website.

### 4.3. Listener sử dụng

- **View Results Tree:** Hiển thị kết quả chi tiết của từng yêu cầu, bao gồm thông tin phản hồi từ máy chủ.
- **Summary Report:** Tổng hợp các chỉ số hiệu năng của lần kiểm thử.

## 5. Hình ảnh minh chứng

### 5.1. Tổng quan Test Plan

![Tổng quan Test Plan](screenshots/01-test-plan.png)

### 5.2. Cấu hình Thread Group

![Cấu hình 50 người dùng](screenshots/02-thread-group.png)

### 5.3. Cấu hình HTTP Request

![Cấu hình HTTP Request](screenshots/03-http-request.png)

### 5.4. Kết quả từng yêu cầu

![Kết quả View Results Tree](screenshots/04-test-results.png)

### 5.5. Báo cáo tổng hợp

![Kết quả Summary Report](screenshots/05-summary-report.png)

## 6. Kết quả kiểm thử

Bài kiểm thử được cấu hình với 50 người dùng ảo, Ramp-up Period là 10 giây và Loop Count bằng 1. Các chỉ số hiệu năng được lấy từ Summary Report sau khi thực thi Test Plan.

| STT | Chỉ số | Kết quả |
|---:|---|---:|
| 1 | Số người dùng ảo (Threads) | 50 |
| 2 | Ramp-up Period | 10 giây |
| 3 | Loop Count | 1 |
| 4 | Tổng số yêu cầu (Samples) | Chưa xác nhận |
| 5 | Thời gian phản hồi trung bình (Average) | Chưa xác nhận (ms) |
| 6 | Thời gian phản hồi nhỏ nhất (Min) | Chưa xác nhận (ms) |
| 7 | Thời gian phản hồi lớn nhất (Max) | Chưa xác nhận (ms) |
| 8 | Tỷ lệ lỗi (Error %) | Chưa xác nhận |
| 9 | Thông lượng (Throughput) | Chưa xác nhận |

**Lưu ý:** Cấu hình dự kiến tạo ra 50 yêu cầu nếu mỗi người dùng gửi một yêu cầu và tất cả các mẫu được thực thi. Kết quả thực tế cần được xác nhận bằng Summary Report.

### 6.1. Phân tích kết quả

Các chỉ số được sử dụng để đánh giá hiệu năng của website gồm:

- **Samples:** Tổng số yêu cầu đã thực hiện trong lần kiểm thử.
- **Average:** Thời gian phản hồi trung bình của các yêu cầu, tính bằng mili giây.
- **Min:** Thời gian phản hồi nhỏ nhất.
- **Max:** Thời gian phản hồi lớn nhất.
- **Error %:** Tỷ lệ yêu cầu xảy ra lỗi.
- **Throughput:** Thông lượng xử lý yêu cầu trong một đơn vị thời gian.

Thời gian phản hồi và tỷ lệ lỗi giúp đánh giá khả năng phản hồi của website trong điều kiện thử nghiệm. Thông lượng giúp quan sát số lượng yêu cầu được xử lý theo thời gian. Cần dựa trên số liệu thực tế để đưa ra nhận xét cụ thể, không thể kết luận giới hạn tải tối đa chỉ từ một lần kiểm thử.

## 7. Kết luận

Qua bài thực hành, em đã tìm hiểu cách sử dụng Apache JMeter để tạo Test Plan, thiết lập Thread Group, cấu hình HTTP Request và theo dõi kết quả bằng các Listener.

Việc mô phỏng 50 người dùng ảo giúp em thực hành quy trình kiểm thử hiệu năng và làm quen với các chỉ số như thời gian phản hồi, tỷ lệ lỗi và thông lượng. Báo cáo và hình ảnh minh chứng được quản lý bằng Git và lưu trữ trên GitHub.

## 8. Tài liệu tham khảo

- Apache JMeter: https://jmeter.apache.org/
- Apache JMeter User Manual: https://jmeter.apache.org/usermanual/

## 9. Repository GitHub

Link dự án: https://github.com/hongtuoi0208/jmeter-performance-testing
