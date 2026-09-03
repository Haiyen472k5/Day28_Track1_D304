# Workflow và lộ trình triển khai

## AS-IS

```text
Dữ liệu thô chưa chuẩn hóa
        ↓
Prompt tự do / nguồn không khóa
        ↓
AI sinh bản nháp và có thể tự hoàn thiện số liệu
        ↓
Nhân viên kiểm tra lại toàn bộ, viết lại câu chữ
        ↓
Chủ báo cáo duyệt nhưng chưa có log lỗi/owner rõ
```

Điểm nghẽn chính là số liệu khó truy vết, không có validator và không có điểm bàn giao rõ ràng.

## TO-BE

```text
Data owner khóa nguồn + schema + phiên bản
        ↓
AI chuẩn hóa/tính nháp từ số liệu đã xác nhận
        ↓
AI tạo bản nháp theo template, gắn nguồn từng chỉ số
        ↓
Validator đối chiếu + QA theo mẫu
        ↓
Nhân viên vận hành kiểm tra nội dung và cảnh báo
        ↓
Chủ báo cáo xử lý ngoại lệ và phê duyệt
        ↓
Log lỗi, phản hồi và cập nhật nguồn/template
```

### Quyền hạn và điểm bàn giao

| Điểm | AI | Con người chịu trách nhiệm | Điều kiện chuyển tiếp |
|---|---|---|---|
| Nguồn → AI | Đọc/chuẩn hóa nguồn được cấp quyền | Data owner | Nguồn, thời gian, phiên bản và công thức đã xác nhận |
| AI → nhân viên | Tạo bản nháp, gắn nguồn, đánh dấu thiếu/chênh lệch | Nhân viên vận hành | Có nguồn cho từng chỉ số; cảnh báo không bị ẩn |
| Đối soát → duyệt | So sánh và đánh dấu sai lệch | Chủ báo cáo | Mọi cảnh báo đã xử lý hoặc chuyển đúng owner |

## Lộ trình 30–60–90

| Giai đoạn | Mục tiêu | Việc chính | Owner | Gate hoàn thành |
|---|---|---|---|---|
| 0–30 ngày | Chứng minh vấn đề | Chọn một loại báo cáo; khóa schema, nguồn, template; chỉ định data owner; ghi baseline 5 mẫu | Data owner + chủ quy trình | Có nguồn chuẩn, owner, log và baseline |
| 31–60 ngày | Chứng minh chất lượng | Bật validator/trích nguồn; QA theo mẫu; hướng dẫn người dùng; ghi tỷ lệ truy xuất, viết lại, duyệt vòng đầu và chuyển ngoại lệ | Phụ trách AI + QA | Traceability ≥95%, ngoại lệ có owner, log đủ để phân tích |
| 61–90 ngày | Quyết định mở rộng | So sánh target; kiểm tra governance, quyền truy cập và năng lực vận hành; chốt phương án | Chủ nghiệp vụ | Mở rộng nếu đạt; sửa/thử lại hoặc dừng nếu không đạt |

## Quy tắc khi AI không chắc chắn

- Không tìm thấy chỉ số trong nguồn: ghi “chưa có dữ liệu nguồn”, không tự điền.
- Hai nguồn khác nhau: đánh dấu chênh lệch và chuyển data owner.
- Công thức chưa rõ: cảnh báo, không tự diễn giải.
- Câu chữ quá dài: đề xuất bản rút gọn, nhân viên quyết định.
- Không có bằng chứng cho nguyên nhân: ghi “giả thuyết cần xác minh”.
- Dữ liệu nhạy cảm/sai quyền: dừng xử lý và báo owner hệ thống.
