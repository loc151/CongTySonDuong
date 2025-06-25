# Mô hình lưu trữ RIS/PACS
## Khái niệm:
- PACS (Picture Archiving and Communication System) là Hệ thống lưu trữ và truyền tải hình ảnh y tế
- Đây là 1 công nghệ quan trọng trong lĩnh vực y tế, giúp các bệnh viện và cơ sở khám chữa bệnh lưu trữ, truy xuất, quản lý và chia sẻ hình ảnh y khoa (X-quang, CT, MRI, siêu âm) một cách nhanh chóng và hiệu quả.

## Các thành phần chính:
- Thiết bị tạo ảnh y tế: máy chụp X-quang, CT, MRI, siêu âm, ...
- Hệ thống mạng: truyền tải dữ liệu hình ảnh giữa các thiết bị và máy chủ.
- Máy chủ lưu trữ: nơi lưu trữ hình ảnh theo chuẩn DICOM.
- Máy trạm chẩn đoán: nơi bác sĩ truy cập, phân tích và chẩn đoán hình ảnh.

## Mô hình: 
![image](https://github.com/user-attachments/assets/cd76edc0-97db-483b-aed3-27cca370affa)

## Giải thích:
### 1. Tương tác giữa HIS và PACS:
- HIS: là nơi quản lý toàn bộ thông tin bệnh nhân và đơn khám/chẩn đoán. HIS gửi yêu cầu chẩn đoán hình ảnh đến PACS và nhận lại kết quả hình ảnh sau khi quá trình chẩn đoán hoàn tất
- PACS: tiếp nhận lệnh từ HIS, kết nối với các thiết bị chẩn đoán, lưu trữ và gửi lại kết quả đã xử lý về HIS.

### 2. Quy trình xử lý hình ảnh tròn PACS:
- Reception (Tiếp nhận): Nhân viên lễ tân nhận đơn và chuyển vào hệ thống.
- Worklist (Danh sách công việc): Hệ thống tạo danh sách ca cần chụp cho các kỹ thuật viên.
- Capture (Chụp ảnh DICOM): Hình ảnh được ghi nhận từ thiết bị và chuyển lên PACS.
- Publication (Công bố kết quả): Bác sĩ hoặc quản lý duyệt và xuất kết quả.
- Clients (Người dùng): Bác sĩ truy cập và đọc hình ảnh qua phần mềm máy trạm.
- Preservation (Lưu trữ): Hình ảnh được bảo quản lâu dài để phục vụ theo dõi điều trị.

## Luồng, quy trình đảm bảo chất lượng: 
![image](https://github.com/user-attachments/assets/b3970637-7f07-48a8-b41b-00766e228963)

## Ứng dụng AI trong chẩn đoán hình ảnh:
![image](https://github.com/user-attachments/assets/194122f1-fcfd-440f-93f3-bf696fea492e)
![image](https://github.com/user-attachments/assets/14f0822d-f5a7-45d2-85ed-b08c9db51a96)

### Giải thích: Mô hình trên mô tả quy trình xử lý ảnh X-quang ngực bằng AI thông qua hệ thống Lunit INSIGHT, tích hợp với PACS và Lunit Gateway 
- Chụp ảnh (Imaging Modality): Khi bệnh nhân chụp X-quang ngực, thiết bị tạo ảnh sẽ gửi file DICOM đến hệ thống **PACS**
- Gửi ảnh đến Gateway: PACS tiếp tục chuyển file DICOM đến Lunit Gateway - cầu nối giữa PACS và hệ thống AI
- Ẩn danh và gửi đến AI: Gateway sẽ ẩn danh hoá dữ liệu (xoá thông tin cá nhân) rồi gửi ảnh đến Lunit INSIGHT - công cụ AI đặt trên cloud hoặc server nội bộ
- Phân tích và trả kết quả: Lunit INSIGHT phân tích ảnh và trả về file JPEG có đánh dấu bất thường (nếu có). Gateway sau đó tạo file DICOM SC (Secondary Capture) từ ảnh JPEG, giữ nguyên thông tin gốc.
- Trả kết quả về PACS: File DICOM SC được gửi trở lại PACS, nơi bác sĩ có thể xem ảnh gốc và ảnh đã phân tích AI song song 

## Trải nghiệm của bác sĩ về PACS:
![image](https://github.com/user-attachments/assets/fdfb7bc6-e30e-4314-8156-806733b89fa1)
![image](https://github.com/user-attachments/assets/b4c8c8c6-636b-45a5-b933-d80acbeac79b)
![image](https://github.com/user-attachments/assets/a04ebdf5-2c4e-4e47-90a1-fe48147cb557)

