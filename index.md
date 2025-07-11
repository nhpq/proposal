---
layout: default
title: Proposal
---
# 🎓 Proposal  
## Tối ưu hóa tính sẵn sàng và hiệu suất hệ thống Web trên nền tảng AWS
> **Giải pháp phân phối tải động, tự mở rộng và đảm bảo uptime cho hệ thống Web**

---

### 📄 Thông tin sinh viên  
- **Họ và tên:** Nguyễn Hà Phú Quý  
- **MSSV:** 2180601278  
- **Email:** phuquy3816@gmail.com  
- **Trường:** Đại học Công nghệ TP.HCM (HUTECH)  
- **Ngày thực hiện:** 09/07/2025  

---

### 📄 Executive Summary  
Đề tài này tập trung vào việc xây dựng hệ thống Web có khả năng **tự động mở rộng** và **phân phối tải truy cập** thông minh thông qua dịch vụ **Auto Scaling Group (ASG)** và **Application Load Balancer (ALB)** trên nền tảng AWS. Mục tiêu là đảm bảo hệ thống vẫn hoạt động ổn định khi có nhiều người dùng truy cập đồng thời, từ đó đạt được **High Availability** và **tối ưu chi phí vận hành**.

---

### ✅ Key Features  
- Cân bằng tải giữa nhiều EC2 instance  
- Tự động scale-in / scale-out theo CPU hoặc traffic  
- Cấu hình Health Check và bảo vệ chống lỗi server  
- Monitoring bằng CloudWatch  
- Hỗ trợ triển khai CI/CD cơ bản  

---

### 💼 Business Benefits  
- Giảm thiểu downtime do lỗi máy chủ  
- Phân phối tải giúp tăng hiệu năng  
- Tiết kiệm chi phí vận hành  
- Dễ dàng mở rộng cho hệ thống thật  

---

### 🏗️ Solution Architecture  
**Các thành phần chính:**  
- **ALB**: Phân phối request người dùng đến các EC2 instance  
- **Auto Scaling Group**: Tự động tạo/xóa EC2 khi traffic thay đổi  
- **EC2 Instance**: Chạy Web App (demo login)  
- **Launch Template**: Định nghĩa cấu hình EC2  
- **CloudWatch**: Theo dõi CPU, phản hồi và cảnh báo  

---

### 🔧 Technical Implementation  
- Tạo Launch Template cho EC2  
- Cấu hình Auto Scaling Group (Min: 1, Max: 3)  
- Cấu hình Application Load Balancer  
- Gắn target group và health check  
- Deploy Web App (có form login demo) lên EC2  
- Truy cập ALB để test phân phối tải  
- Dùng CloudWatch để theo dõi hoạt động scaling  

---

### 📅 Timeline & Milestones  

| Tuần | Nội dung |
|------|----------|
| 1    | Thu thập yêu cầu, dựng kiến trúc |
| 2    | Tạo Launch Template, EC2 Image |
| 3    | Cấu hình ASG và ALB |
| 4    | Deploy Web App và test cân bằng tải |
| 5    | Tối ưu scale-in/out, thêm CloudWatch |
| 6    | Kiểm thử nhiều người dùng |
| 7    | Viết báo cáo và xử lý rủi ro |
| 8    | Nộp đề tài và trình bày kết quả |

---

### 💰 Budget Estimation  

| Hạng mục                         | Chi phí ước tính (vận hành 1 tháng)          |
|----------------------------------|---------------------------------------------|
| **EC2 t2.micro**                 | Miễn phí nếu còn trong Free Tier (750h/tháng) |
| **EC2 t3.micro** *(hết Free Tier)* | ~8 USD/tháng (~200.000đ)                  |
| **Application Load Balancer (ALB)** | ~18–20 USD/tháng (~450.000đ)              |
| **CloudWatch Logs & Alarms**     | ~1–2 USD/tháng (~25.000–50.000đ)           |
| **Data Transfer (10GB outbound)**| ~0.90 USD (~20.000đ)                       |

**👉 Tổng chi phí ước tính nếu vận hành thực tế 1 tháng:**  
**~700.000 – 800.000đ**

---

### ⚠️ Risk Assessment  

| Rủi ro                      | Mức độ     | Hướng xử lý                          |
|-----------------------------|------------|--------------------------------------|
| Cấu hình sai ALB hoặc ASG   |    Trung bình |    Kiểm tra log, rollback               |
| EC2 không phản hồi kịp      |    Thấp       |    Dùng AMI chuẩn, bật health check     |
| Quá giới hạn Free Tier      |    Thấp       |    Giới hạn thời gian test              |
| Scaling không diễn ra đúng  |    Trung bình |    Dùng CloudWatch log để debug         |

---

### 🎯 Expected Outcomes  
- Truy cập website từ ALB sẽ dẫn đến các EC2 khác nhau  
- Khi có nhiều user truy cập cùng lúc, ASG sẽ tự scale-out  
- Web hoạt động ổn định ngay cả khi 1 EC2 bị lỗi (High Availability)  
- Báo cáo chi tiết về kiến trúc, cấu hình, chi phí và rủi ro  
