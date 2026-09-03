# Mollick — Việc chia người–AI đã rõ chưa?

## Phương án của nhóm

```text
Product: Trợ lý AI soạn thảo báo cáo vận hành định kỳ
User: Nhân viên vận hành
Workflow: Tổng hợp dữ liệu thô → sinh bản nháp báo cáo → đối soát số liệu
Problem: Bản nháp có thể chứa chỉ số không có trong dữ liệu nguồn và
         diễn đạt dài dòng, khiến nhân viên phải kiểm tra và viết lại.
```

## Phân chia người–AI

| Vùng | Nguyên tắc | Nội dung áp dụng cho phương án của nhóm |
| --- | --- | --- |
| **Người làm** | Giữ quyền quyết định | Nhân viên vận hành kiểm tra nội dung và số liệu; data owner xác nhận dữ liệu; chủ báo cáo xử lý ngoại lệ, phê duyệt và chịu trách nhiệm về bản cuối. |
| **AI hỗ trợ** | AI làm, người kiểm tra | AI chuẩn hóa dữ liệu, tạo bản nháp theo template, tóm tắt xu hướng và cảnh báo chênh lệch; nhân viên kiểm chứng trước khi sử dụng. |
| **AI tự động** | Chỉ với tác vụ rõ | Chỉ tự động các tác vụ lặp lại, rủi ro thấp như định dạng, sắp xếp hoặc tính toán từ dữ liệu đã xác nhận; không tự tạo số liệu và không tự phát hành báo cáo. |

## Áp dụng vào workflow

| Bước | AI được làm | Con người phải làm |
| --- | --- | --- |
| **1. Tổng hợp dữ liệu thô** | Chuẩn hóa tên cột, định dạng; phát hiện dữ liệu thiếu, trùng hoặc bất thường; tính toán nháp từ nguồn được cấp quyền. | Xác nhận nguồn dữ liệu, khoảng thời gian, công thức và tính đúng của chỉ số. |
| **2. Sinh bản nháp báo cáo** | Soạn báo cáo theo template, tóm tắt xu hướng và gắn nguồn cho từng chỉ số. | Kiểm tra số liệu, nhận định, văn phong và mức độ phù hợp với tình hình thực tế. |
| **3. Đối soát số liệu** | So sánh bản nháp với dữ liệu nguồn và đánh dấu chênh lệch. | Kiểm tra lại từng chênh lệch, xử lý ngoại lệ và phê duyệt bản cuối. |

## Quy tắc khi AI không chắc chắn

- Nếu không tìm thấy chỉ số trong dữ liệu nguồn: AI phải ghi **“chưa có dữ liệu nguồn”**, không tự điền số.
- Nếu các nguồn có số liệu khác nhau: AI phải đánh dấu chênh lệch và chuyển cho data owner.
- Nếu AI đề xuất nguyên nhân nhưng không có bằng chứng: chỉ ghi là **giả thuyết cần xác minh**.
- Nếu văn phong quá dài hoặc lệch template: AI đánh dấu phần cần sửa; nhân viên vận hành quyết định bản diễn đạt cuối.
- AI không được tự xử lý ngoại lệ, tự kết luận số liệu đúng hoặc tự gửi báo cáo.

## Kết luận

Vấn đề của nhóm không chỉ là AI viết chưa tốt, mà còn là ranh giới công việc giữa người và AI chưa rõ. Theo Mollick, trợ lý AI nên nằm chủ yếu ở vùng **AI hỗ trợ, người kiểm tra**.

AI có thể tăng tốc việc tổng hợp, tính toán nháp và soạn thảo; con người vẫn phải kiểm chứng, xử lý ngoại lệ, phê duyệt và chịu trách nhiệm cuối cùng. Chỉ các tác vụ định dạng hoặc xử lý lặp lại, rủi ro thấp mới được tự động hóa.

## Bằng chứng nhóm cần bổ sung

Nhóm cần bổ sung bằng chứng thực tế, chẳng hạn so sánh bản nháp AI với dữ liệu nguồn, xem lịch sử chỉnh sửa hoặc phỏng vấn nhân viên vận hành. Không nên tự tạo số liệu.
