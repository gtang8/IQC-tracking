#
[英文](./readme_en.md) / [中文](./readme_cn.md) 
---

# Phiên bản tiếng Việt: Sổ tay Hướng dẫn Thao tác Tiêu chuẩn Hệ thống Theo dõi và Kiểm tra Đầu vào IQC Mattel

Hệ thống này áp dụng mô hình làm việc "cách ly vật lý hai vai trò" và "chuyển tiếp tập tin ngoại tuyến". **Nhân viên kiểm tra** và **Quản lý chất lượng** thao tác độc lập trên máy tính của từng người, thông qua việc xuất/nhập tập tin JSON để luân chuyển chứng từ và gộp dữ liệu.

---

## 👨‍🔧 Phần 1: Hướng dẫn Thao tác cho Nhân viên Kiểm tra IQC (Tạo đơn, Bổ sung kết quả Hóa học & Phán đoán sơ bộ Vật lý)

### Bước 1: Nhập dữ liệu hàng đến và Đánh giá thông minh [Tần suất kiểm tra hóa học]

1. Mở trang web hệ thống, điền thông tin phiếu giao hàng tại khu vực [1. Nhập lô hàng đến mới & Đánh giá chặn thông minh].
2. **Nhập nhanh**: Khi nhập "Mã nhà cung cấp" hoặc "Tên nhà cung cấp", hệ thống sẽ tự động khớp và hiển thị [Cấp độ nhà cung cấp Mattel].
3. Lần lượt chọn "Phân loại lớn vật liệu" và "Loại vật liệu chi tiết".
4. Sau khi điền xong, phía dưới hệ thống sẽ tự động hiện **kết quả đánh giá đèn giao thông về kiểm tra hóa học**:
* 🚨 **Thẻ đỏ (Bắt buộc kiểm tra)**: Thể hiện vật liệu đã đến chu kỳ kiểm tra hóa học (ví dụ: đã quá hạn 12 tháng/6 tháng), hoặc thuộc vật liệu bắt buộc kiểm tra mỗi lô của nhà cung cấp không được chỉ định.
* 🔒 **Thẻ xanh (Không cần kiểm tra)**: Thể hiện báo cáo kiểm tra hóa học vẫn còn hiệu lực, hệ thống tự động khóa ô nhập và tự động hiển thị ngày, mã số của báo cáo hóa học đạt yêu cầu trước đó.


5. Sau khi xác nhận chính xác, nhấp vào **[💾 Lưu lô hàng]**. Chứng từ sẽ tự động được đưa vào sổ quản lý bên dưới.

### Bước 2: Bổ sung nhanh thông tin báo cáo [Kiểm tra hóa học]

Trong thực tế, các vật liệu "Bắt buộc kiểm tra" thẻ đỏ thường chưa có báo cáo thử nghiệm hóa học ngay khi nhập kho. Hệ thống hỗ trợ cập nhật nhanh trong sổ quản lý:

1. Khi phòng thí nghiệm phát hành báo cáo hóa học, hãy tìm lô tương ứng trong danh sách sổ quản lý.
2. **Nhấp đúp** vào ô **[Ngày báo cáo hóa học]** của hàng đó, ô này sẽ biến thành bộ chọn lịch, chọn ngày xong nhấn phím `Enter` để lưu.
3. **Nhấp đúp** vào ô **[Mã báo cáo hóa học]** của hàng đó, nhập mã báo cáo (VD: C-2026-XXXX) xong nhấn phím `Enter` để lưu.
4. *Lời nhắc đồng bộ thông minh: Nếu vật liệu này có các đơn hàng tiếp theo đến, chỉ cần bạn cập nhật báo cáo hóa học của lô chính, các bản ghi của đơn hàng tiếp theo sẽ tự động đồng bộ, cập nhật và khóa lại, không cần nhập lại.*

### Bước 3: Nhập dữ liệu đo lường thực tế và Phán đoán sơ bộ [Kiểm tra Vật lý]

1. Nhấp vào nút **[⏳ Chờ kiểm tra]** ở góc ngoài cùng bên phải của chứng từ tương ứng trong sổ quản lý để mở cửa sổ kiểm tra vật lý.
2. Hệ thống đã **tự động khớp các hạng mục kiểm tra vật lý và quy cách chuẩn** dựa trên loại vật liệu chi tiết bạn đã chọn.
3. Nhập lần lượt "Số mẫu", "Số lỗi" và "Dữ liệu đo lường thực tế" vào bảng.
* *Lời nhắc chống lỗi: Sau khi nhập Ac (Số nhận) ở phần trên, hệ thống sẽ tự động tính toán Re (Số từ chối).*


4. Cuộn xuống dưới bảng, tại phần **[📊 Quyết định sơ bộ của nhân viên kiểm tra]**, chọn kết luận kiểm tra vật lý (Đạt / Không đạt).
5. Bổ sung mô tả bất thường tại hiện trường vào ô **[📝 Ghi chú của nhân viên kiểm tra]** ở dưới cùng.
6. Nhấp vào **[💾 Chỉ lưu dữ liệu]** ở dưới cùng. Lúc này trạng thái sổ quản lý sẽ chuyển thành màu xanh xám `[⏳ Chờ phê duyệt]`.

### Bước 4: Đóng gói gửi duyệt (Gửi cho Quản lý)

1. Ở bên trái danh sách sổ quản lý, **tích chọn** các chứng từ cần gửi duyệt (có thể chọn nhiều dòng cùng lúc).
2. Nhấp vào nút **[📤 Trích xuất Xuất [Dòng JSON đã chọn] để cộng tác]** phía trên sổ quản lý.
3. Hệ thống sẽ tự động tải xuống một tập tin với định dạng tên `待批准-NămThángNgày-GiờPhútGiây.json`.
4. Gửi tập tin này cho Quản lý chất lượng qua WeChat, DingTalk hoặc Email.

### Bước 5: Nhận phê duyệt và In báo cáo

1. Sau khi nhận được tệp phê duyệt gửi lại từ Quản lý, nhấp vào **[📥 Nhập/Gộp JSON thông minh]** ở góc trên bên phải trang và chọn tệp để tải lên.
2. Hệ thống sẽ tự động gộp kết quả phê duyệt vào sổ quản lý của bạn mà không làm mất dữ liệu gốc, trạng thái chứng từ liên quan sẽ chuyển sang màu xanh lá cây hiển thị `[✅ Đã phê duyệt]`.
3. Nhấp đúp vào sổ quản lý để mở cửa sổ kiểm tra vật lý của chứng từ đó, cuộn xuống dưới cùng, nhấp vào nút **[🖨️ In Báo cáo Phê duyệt Cuối cùng (In PDF)]** để in trực tiếp.
* *Lời nhắc in: Hệ thống đã khóa bố cục, khung ghi chú của nhân viên kiểm tra sẽ tự động cố định ở độ cao tiêu chuẩn 8 dòng, tránh bị lỗi in ấn. Tệp PDF được lưu sẽ tự động lấy mã số của báo cáo vật lý đó làm tên.*



---

## 👨‍💼 Phần 2: Hướng dẫn Thao tác cho Quản lý Chất lượng (Phê duyệt và Gửi lại)

Việc phê duyệt của quản lý cần được thực hiện trong "Chế độ Quản lý" chuyên dụng để mở khóa quyền chỉnh sửa và in ấn cao nhất.

### Bước 1: Mở khóa chế độ Quản lý ẩn

1. Sau khi mở trang web hệ thống, di chuyển chuột đến tiêu đề lớn ở giữa trên cùng của trang **"Hệ thống Theo dõi và Kiểm tra Đầu vào IQC Mattel"**.
2. **Nhấp đúp nhanh** vào tiêu đề lớn đó, hệ thống sẽ hiện ra hộp thoại mật khẩu xác thực.
3. Nhập mật khẩu dành riêng cho quản lý: `ABC123456`, nhấn OK.
4. Sau khi xác thực thành công, bên cạnh tiêu đề sẽ xuất hiện huy hiệu màu đỏ `[Chế độ Quản lý đã kích hoạt]`, nghĩa là quyền phê duyệt và in ấn của bạn đã được mở khóa hoàn toàn.

### Bước 2: Nhập và Xem xét Phiếu kiểm tra

1. Sau khi nhận được tệp `待批准-xxx.json` từ nhân viên kiểm tra, nhấp vào **[📥 Nhập/Gộp JSON thông minh]** ở góc trên cùng bên phải của trang để tải tệp đó lên.
2. Tìm các chứng từ có trạng thái `[⏳ Chờ phê duyệt]` trong sổ quản lý bên dưới, nhấp vào chứng từ đó để mở cửa sổ kiểm tra vật lý.
3. Kiểm tra xem thông tin báo cáo "Kiểm tra hóa học" ở phần trên đã đầy đủ chưa, xem xét dữ liệu đo lường vật lý thực tế, kết quả phán đoán sơ bộ và thông tin ghi chú.

### Bước 3: Điền ý kiến phê duyệt và Ký duyệt

1. Cuộn xuống khu vực màu xanh lá cây ở dưới cùng của cửa sổ kiểm tra **【✍️ Khu vực Phê duyệt Cuối cùng của Quản lý IQC】**.
2. Điền ý kiến xét duyệt, lý do đặc cách (AOD) hoặc hướng dẫn trả hàng của bạn vào ô **[Ghi chú phê duyệt]** (Ô này nằm ở trên cùng để dễ dàng nhập các đoạn văn dài).
3. Chọn **[Kết luận phê duyệt]** ở bên dưới (Đồng ý nhận / Đặc cách nhận / Từ chối trả hàng).
4. Xác nhận **[Chữ ký điện tử của Quản lý]** (Trưởng phòng QC / Trưởng phòng QA) và **[Ngày phê duyệt]**.
5. Nhấp vào **[💾 Chỉ lưu dữ liệu]** ở dưới cùng để hoàn tất phê duyệt.

### Bước 4: Gửi lại dữ liệu đã phê duyệt

1. Trong sổ quản lý, tích chọn các chứng từ bạn vừa phê duyệt xong (trạng thái đã chuyển sang màu xanh lá cây `[✅ Đã phê duyệt]`, v.v.).
2. Nhấp vào nút **[📤 Trích xuất Xuất [Dòng JSON đã chọn] để cộng tác]** phía trên sổ quản lý.
3. Hệ thống sẽ tự động tải xuống tệp có tên `已批准-NămThángNgày-GiờPhútGiây.json`.
4. Gửi tệp này cho nhân viên kiểm tra qua WeChat hoặc Email để nhân viên kiểm tra nhập vào máy tính của họ nhằm hoàn thành quy trình khép kín.

### Bước 5: Sao lưu toàn bộ dữ liệu phòng ngừa rủi ro (Thực hiện hàng tuần)

Để tránh mất dữ liệu do bộ nhớ cache của trình duyệt bị xóa, quản lý cần thường xuyên sao lưu toàn bộ hệ thống:

1. Nhấp vào nút **[📤 Xuất bản sao lưu JSON]** ở góc trên cùng bên phải trang.
2. Hệ thống sẽ tải xuống tệp tổng thể chứa toàn bộ sổ quản lý lịch sử, tất cả chứng từ và danh mục nhà cung cấp, với tên là `Mattel_Integrated_DB_Backup_NămThángNgày_GiờPhútGiây.json`.
3. Vui lòng lưu tệp này trên ổ đĩa mạng chung của công ty hoặc USB được mã hóa. Nếu cần đổi máy tính, chỉ cần nhập tệp này vào hệ thống trống để khôi phục toàn bộ dữ liệu chỉ trong một giây.

