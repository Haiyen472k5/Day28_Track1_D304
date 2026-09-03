# Bằng chứng chẩn đoán trong workflow

## Phạm vi

- Product: trợ lý AI soạn thảo báo cáo vận hành định kỳ.
- User: nhân viên vận hành.
- Workflow: tổng hợp dữ liệu thô → sinh bản nháp → đối soát số liệu.

## Bằng chứng định tính đã sử dụng

| Quan sát | Bước xuất hiện | Ý nghĩa chẩn đoán | Cách đo bổ sung trong pilot |
|---|---|---|---|
| Bản nháp có thể chứa chỉ số không truy xuất được về dữ liệu nguồn | Sinh bản nháp/đối soát | Readiness và tin cậy chưa đạt; thiếu validator và nguồn chuẩn | Đếm số chỉ số có/không có mã nguồn trong 5 báo cáo đầu |
| Người dùng phải kiểm tra và viết lại câu chữ dài dòng | Đối soát/chỉnh sửa | Người dùng chưa có Ability và workflow chưa có template/điểm bàn giao | Đo số đoạn sửa và phút chỉnh sửa mỗi báo cáo |
| AI nhận prompt tự do, tách khỏi bước chốt dữ liệu | Tổng hợp dữ liệu | Mollick chưa được thiết kế vào workflow; ranh giới người–AI chưa rõ | Ghi lại ai xác nhận nguồn, ai duyệt và ai xử lý ngoại lệ |

Đây là bằng chứng quan sát định tính được rút ra từ mô tả workflow và các ghi chú làm bài của nhóm; nhóm không tự tạo số liệu kết quả. Baseline định lượng sẽ được khóa sau khi có 5 mẫu báo cáo pilot.

## Mẫu log cần thu thập

| Mã báo cáo | Chỉ số có nguồn | Duyệt vòng đầu | Phút xử lý | Số đoạn viết lại | Ngoại lệ đã chuyển đúng owner | Người duyệt |
|---|---|---|---:|---:|---|---|
| R-01 | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot |
| R-02 | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot |
| R-03 | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot |
| R-04 | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot |
| R-05 | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot | Nhập sau pilot |
