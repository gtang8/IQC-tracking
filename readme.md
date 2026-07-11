#
[英文](./readme_en.md) / [中文](./readme_cn.md) / [Tiếng Việt](./readme_vn.md) 

---

# Generic IQC Incoming Inspection & Tracking System

# 通用 IQC 进料检验与追踪系统

# Hệ thống Theo dõi và Kiểm tra Đầu vào IQC Đa dụng

---

## 🇨🇳 中文简介 (Chinese)

这是一个**无需部署后端服务器的纯离线 IQC 进料检验管理工具**。通过浏览器 `LocalStorage` 存储和创新的 **JSON Smart Merge（智能双向合并引擎）** 技术，完美实现了在没有局域网的环境下，通过简单的文件导入导出，完成“检验员制单 ➔ 离线文件流转 ➔ 主管审批 ➔ 数据闭环”的全套合规工作流。特别适合网络受限的工厂车间或中小型制造企业。

### ✨ 主要功能特点

1. **零部署与纯离线架构**：单 HTML 文件结构，无需安装任何数据库或 Node/Python 环境，下载双击即可运行。数据完全保存在本地浏览器中。
2. **智能测试频率拦截 (红绿灯机制)**：系统根据内置的供应商评级（如A/B级免检期长、C级监控期短），自动判定来料是否需要强制化学测试，并能智能关联有效期内的主报告，自动锁死防篡改。
3. **动态物理检验模板与 AQL 防呆**：根据选择的“物料大类/细类”，弹窗会自动加载对应的检验规范与标准参数。内嵌 AQL 防呆逻辑（输入 Ac 接收数，自动计算并显示 Re 拒收数）。
4. **双角色权限物理隔离**：
* **检验员模式（默认）**：仅可录入数据和初步判定，无法看到审批区域与打印按钮。
* **主管模式（隐藏通道）**：双击页面顶部主标题并输入专属密码（开源演示密码为 `123456`），即可解锁隐蔽的主管审批区及终版报告打印权限。


5. **Smart Merge 离线协同引擎**：检验员导出“待批准”JSON给主管，主管批复后导出“已批准”JSON发回。导入时系统会自动精准识别记录 ID 替换状态，不覆盖本地其他无关数据。
6. **合规级 A4 PDF 打印排版**：专为国际大厂（如 Hasbro, Mattel）外审要求设计的打印样式，输入框尺寸在打印态被严格物理固化，防止内容溢出引发的格式错乱。

---

## 🇬🇧 English Introduction

This is a **serverless, fully offline IQC (Incoming Quality Control) Inspection & Tracking Tool**. Utilizing browser `LocalStorage` and an innovative **JSON Smart Merge Engine**, it achieves a seamless closed-loop workflow: "Inspector Entry ➔ Offline File Relay ➔ Supervisor Approval ➔ Data Sync" entirely without an active network or shared database. It is perfectly suited for network-restricted factory floors or Small and Medium Enterprises (SMEs).

### ✨ Key Features

1. **Zero Deployment & 100% Offline**: A single HTML file structure requires no database, Node.js, or Python environment. Just double-click to run. All data is securely stored in the local browser.
2. **Smart Test Frequency Interception**: Automatically determines whether incoming materials require mandatory testing based on the supplier's risk level rating. It smartly links to existing valid historical reports and locks fields to prevent tampering.
3. **Dynamic Templates & AQL Poka-Yoke**: Automatically loads specific physical inspection criteria and test standards based on material categories. Built-in AQL logic automatically calculates Rejection (Re) limits once Acceptance (Ac) numbers are entered.
4. **Dual-Role Privilege Isolation**:
* **Inspector Mode (Default):** Only allows data entry and preliminary judgment; hides approval areas and print buttons.
* **Supervisor Mode (Hidden Trigger):** Double-clicking the main title and entering a password (demo password: `123456`) unlocks the hidden approval interface and PDF printing privileges.


5. **Smart Merge Offline Collaboration**: Inspectors export "Pending Approval" JSONs to supervisors; supervisors approve and send back "Approved" JSONs. The system precisely matches record IDs to merge statuses without overwriting other local data.
6. **Audit-Ready A4 PDF Printing**: CSS print media rules strictly lock text box heights to prevent pagination glitches, ensuring inspection reports look professional and meet strict international audit standards.

---

## 🇻🇳 Giới thiệu tiếng Việt (Vietnamese)

Đây là một **công cụ quản lý kiểm tra đầu vào IQC hoàn toàn ngoại tuyến, không cần triển khai máy chủ (serverless)**. Thông qua lưu trữ `LocalStorage` của trình duyệt và công nghệ **JSON Smart Merge (Gộp thông minh hai chiều)**, hệ thống hiện thực hóa quy trình làm việc khép kín: "Nhân viên kiểm tra tạo đơn ➔ Chuyển tiếp tập tin ngoại tuyến ➔ Quản lý phê duyệt ➔ Đồng bộ dữ liệu" mà không cần mạng LAN. Rất thích hợp cho các phân xưởng bị hạn chế mạng hoặc các doanh nghiệp sản xuất vừa và nhỏ.

### ✨ Các tính năng chính

1. **Chạy ngoại tuyến & Không cần cài đặt**: Cấu trúc chỉ với một tệp HTML, không cần cài đặt bất kỳ cơ sở dữ liệu hay môi trường backend nào. Chỉ cần nhấp đúp để chạy. Dữ liệu được bảo mật hoàn toàn trong trình duyệt cục bộ.
2. **Đánh giá chặn tần suất thông minh**: Tự động xác định xem vật liệu đến có cần phải kiểm tra bắt buộc hay không dựa trên cấp độ rủi ro của nhà cung cấp. Nó liên kết thông minh với các báo cáo lịch sử còn hiệu lực và khóa các trường để tránh làm sai lệch.
3. **Mẫu kiểm tra động & Chống lỗi AQL**: Tự động tải các quy cách và tiêu chuẩn kiểm tra vật lý tương ứng dựa trên loại vật liệu. Tích hợp logic chống lỗi AQL (Nhập số nhận Ac, tự động tính số từ chối Re).
4. **Cách ly quyền hạn hai vai trò**:
* **Chế độ nhân viên kiểm tra (Mặc định):** Chỉ có thể nhập dữ liệu và phán đoán sơ bộ, không thể thấy khu vực phê duyệt và nút in.
* **Chế độ Quản lý (Kích hoạt ẩn):** Nhấp đúp vào tiêu đề chính và nhập mật khẩu (mật khẩu demo: `123456`) để mở khóa khu vực phê duyệt ẩn và quyền in báo cáo PDF.


5. **Cộng tác ngoại tuyến Smart Merge**: Nhân viên kiểm tra xuất JSON "Chờ phê duyệt" cho quản lý; quản lý phê duyệt và xuất JSON "Đã phê duyệt" gửi lại. Khi nhập tệp, hệ thống sẽ nhận diện chính xác ID để thay thế trạng thái mà không ghi đè lên các dữ liệu cục bộ khác.
6. **In báo cáo PDF chuẩn A4 kiểm toán**: Các quy tắc CSS khi in (Print Media) được thiết kế đặc biệt để khóa chặt kích thước các ô nhập liệu, ngăn ngừa tình trạng tràn trang, đảm bảo báo cáo kiểm tra tuân thủ các tiêu chuẩn đánh giá quốc tế khắt khe.