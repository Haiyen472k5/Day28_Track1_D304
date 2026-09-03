# Hồ sơ kiểm tra chéo và thay đổi v1 → v2

## Cách kiểm tra

Nhóm dùng checklist §4.6 của lab để kiểm tra chéo theo bốn trục: phạm vi, framework, chỉ số và hành động. Hồ sơ nguồn không ghi tên nhóm đối tác; vì vậy tài liệu này chỉ lưu lại nội dung góp ý và thay đổi đã áp dụng, không gán tên người/nhóm không có căn cứ.

## Góp ý cụ thể

| Trục | Góp ý phản biện | Thay đổi áp dụng trong v2 |
|---|---|---|
| Chỉ số | Số báo cáo tạo ra và số người dùng chỉ chứng minh activity, chưa chứng minh giá trị | Thay bằng tỷ lệ duyệt vòng đầu, thời gian xử lý, tỷ lệ truy xuất nguồn và tỷ lệ viết lại |
| Hành động | Chưa rõ AI sai thì ai xử lý và khi nào chuyển người | Bổ sung validator, data owner, QA, chủ báo cáo và quy tắc chuyển ngoại lệ |
| Roadmap | 30–60–90 dễ biến thành danh sách việc nếu không có cổng quyết định | Thêm gate hoàn thành và ba quyết định: mở rộng, sửa/thử lại hoặc dừng |

## Hai thay đổi dùng để chứng minh v2

1. **Metric thay đổi:** từ activity sang metric chất lượng/workflow có nguồn dữ liệu và hành động khi xấu.
2. **Workflow thay đổi:** thêm chuỗi nguồn → trích nguồn → validator/QA → chuyển người → phê duyệt → phản hồi, kèm owner tại từng điểm bàn giao.

## Kết luận sau kiểm tra

Giữ quyết định **tiếp tục pilot có điều kiện, chưa rollout rộng**. Bản v2 chỉ được xem là đạt gate mở rộng khi các ngưỡng trong dashboard đạt và dữ liệu log đủ để truy vết.
