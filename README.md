# 🏢 Tự động hóa xử lý request nội bộ với Power Automate  
# 🏢 Internal Request Automation with Power Automate  

## 📌 Giới thiệu | Introduction  

🇻🇳 Dự án này xây dựng một hệ thống **Power Automate Flow** để:  
- Xử lý tự động các request nội bộ (Xin nghỉ/ WFH, Yêu cầu IT, Hành chính...).  
- Giảm thiểu các tác vụ lặp đi lặp lại, tối ưu thời gian cho nhân viên.  
- Chuẩn hóa và lưu trữ dữ liệu để phục vụ **hệ thống báo cáo nội bộ** (Power BI, Excel).  

🇬🇧 This project demonstrates how to use **Microsoft Power Automate** to:  
- Automate handling of internal requests (Leave/ WFH, IT Support, Administrative...).  
- Eliminate repetitive manual tasks and improve employee efficiency.  
- Standardize and centralize data to support **internal reporting systems** (Power BI, Excel).  

---

## 🚀 Tính năng | Features  

- **Gửi form**: Nhân viên gửi request qua Microsoft Forms / Power Apps.  
- **Luồng phê duyệt tự động**: Hệ thống định tuyến đến quản lý hoặc phòng ban liên quan.  
- **Thông báo**: Email/Teams tới người phê duyệt và người gửi request.  
- **Theo dõi tập trung**: Tất cả dữ liệu được lưu SharePoint Online.  
- **Xử lý tác vụ lặp lại**: Tự động hóa các bước kiểm tra/ghi log, không cần thao tác thủ công.  
- **Chuẩn hóa dữ liệu**: Đảm bảo dữ liệu đầu ra thống nhất, hỗ trợ báo cáo chính xác.  

---

## 🛠️ Kiến trúc | Architecture  

1. **Trigger**: Nhân viên gửi request qua Forms/ Power Apps.  
2. **Flow xử lý**: Tự động phân loại request (Leave / IT / Other).  
3. **Phê duyệt**: Xác định người duyệt động từ AD/ SharePoint.  
4. **Lưu trữ & Chuẩn hóa**: Lưu dữ liệu vào SharePoint/ Dataverse theo format chuẩn.  
5. **Thông báo**: Gửi email/ Teams xác nhận và cập nhật trạng thái.  

---

## 📊 Ví dụ luồng xử lý | Example Flow  

```mermaid
flowchart TD
    A[Employee submits request] --> B{Request type?}
    B -->|Leave / WFH| C[Manager Approval]
    B -->|IT Request| D[IT Team Notification]
    B -->|Other| E[Admin Team Approval]
    C --> F[Log & Normalize Data]
    D --> F[Log & Normalize Data]
    E --> F[Log & Normalize Data]
    F --> G[Send confirmation + Feed Reporting System]
