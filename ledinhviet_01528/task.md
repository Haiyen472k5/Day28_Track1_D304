# Gartner-Lite — Đánh giá mức sẵn sàng của tổ chức

## Phạm vi đánh giá

**Sản phẩm AI:** Trợ lý soạn thảo báo cáo vận hành định kỳ.  
**Người dùng chính:** Nhân viên vận hành.  
**Quy trình:** Tổng hợp dữ liệu thô → sinh bản nháp báo cáo → đối soát số liệu.  
**Vấn đề quan sát được:** Nhân viên vẫn phải viết lại báo cáo vì AI bịa chỉ số và diễn đạt lan man.

## Đánh giá theo Gartner-Lite

| Trục | Hạng mục | Nhận định | Kết quả |
|---|---|---|---|
| **Direction** | Vấn đề và người dùng | Vấn đề, người dùng và ba bước trong workflow đã được xác định cụ thể. | **ĐẠT** |
| **Direction** | Giá trị kỳ vọng | Giá trị cần tạo là giảm thời gian viết lại, giảm sai lệch số liệu và tăng tỷ lệ bản nháp được duyệt ngay vòng đầu. | **ĐẠT** |
| **Direction** | Phạm vi AI | AI chỉ nên tổng hợp và tạo bản nháp; không được tự tạo số liệu hoặc tự phê duyệt báo cáo. | **ĐẠT CÓ ĐIỀU KIỆN** |
| **Readiness** | Dữ liệu | Dữ liệu thô chưa có schema đầu vào thống nhất, chưa được làm sạch và chưa gắn nguồn để truy vết từng chỉ số. | **THIẾU** |
| **Readiness** | Governance và quyền truy cập | Chưa có quy tắc về nguồn dữ liệu được phép dùng, phân quyền theo vai trò, lưu vết phiên bản và xử lý dữ liệu nhạy cảm. | **THIẾU** |
| **Readiness** | Kiểm soát chất lượng | Chưa có validator đối chiếu số liệu AI sinh với dữ liệu gốc, ngưỡng sai số, bộ mẫu QA hoặc bước chuyển người khi AI không chắc chắn. | **THIẾU — NGUYÊN NHÂN GỐC** |
| **Readiness** | Kỹ năng | Nhân viên chưa có hướng dẫn chuẩn về cách cung cấp dữ liệu, kiểm tra số liệu và rút gọn nội dung do AI tạo. | **THIẾU** |
| **Readiness** | Nguồn lực | Chưa xác nhận ngân sách, năng lực tích hợp dữ liệu và thời gian dành cho QA trong giai đoạn pilot. | **CẦN XÁC NHẬN** |
| **Absorption** | Owner | Chưa chỉ định data owner, người chịu trách nhiệm chất lượng bản nháp và người quyết định khi có sai lệch. | **THIẾU — NGUYÊN NHÂN GỐC** |
| **Absorption** | Hỗ trợ vận hành | Chưa có hướng dẫn tại workflow, kênh hỗ trợ hoặc quy trình xử lý ngoại lệ để người dùng áp dụng cách làm mới. | **THIẾU** |
| **Absorption** | Học từ lỗi | Chưa có cơ chế ghi nhận lỗi bịa số, nội dung phải viết lại, nguyên nhân và hành động khắc phục để cải thiện hệ thống. | **THIẾU** |
| **Absorption** | Đo lường và duy trì | Hiện mới quan tâm số lượng báo cáo được tạo; chưa đo tỷ lệ sai số, tỷ lệ viết lại, thời gian xử lý và tỷ lệ duyệt vòng đầu. | **THIẾU** |

## Bằng chứng trong workflow

- Nhân viên phải viết lại báo cáo do AI bịa chỉ số và hành văn lan man: đây là dấu hiệu trực tiếp cho thấy kiểm soát chất lượng chưa đáp ứng.
- AI đang nhận dữ liệu/prompt tự do, tách rời bước chốt số liệu và duyệt báo cáo: chưa có nguồn chuẩn để đối chiếu đầu ra.
- Nhóm chưa xác định validator, owner chất lượng và cơ chế ghi nhận lỗi: tổ chức chưa đủ khả năng hấp thụ và duy trì cách làm mới.

## Nguyên nhân gốc

1. **Readiness chưa đạt:** dữ liệu đầu vào chưa chuẩn hóa và chưa có cơ chế kiểm chứng từng chỉ số với nguồn gốc, nên đầu ra sai khó được phát hiện sớm.
2. **Absorption chưa đạt:** thiếu owner và vòng phản hồi lỗi, nên các lỗi bịa số hoặc viết lan man chỉ được sửa thủ công ở cuối quy trình thay vì trở thành dữ liệu cải tiến.

## Kết luận và quyết định

**Direction đã tương đối rõ, nhưng Readiness và Absorption chưa đạt. Vì vậy, nhóm chỉ nên triển khai pilot nhỏ cho một loại báo cáo và một nhóm vận hành; chưa nên rollout rộng.**

Pilot chỉ được chuyển sang giai đoạn mở rộng khi đáp ứng đủ các điều kiện sau:

1. Có schema dữ liệu đầu vào, nguồn dữ liệu được phê duyệt và data owner.
2. Mọi chỉ số trong bản nháp đều truy vết được về dữ liệu gốc; có validator và QA theo mẫu.
3. Có người chịu trách nhiệm duyệt cuối, quy trình chuyển người khi AI không chắc chắn và kênh báo lỗi.
4. Có log để đo tỷ lệ sai số, tỷ lệ nội dung phải viết lại, thời gian hoàn thành và tỷ lệ duyệt ngay vòng đầu.
5. Cuối pilot, nhóm ra một trong ba quyết định dựa trên các chỉ số đã thống nhất: **mở rộng, sửa rồi thử lại, hoặc dừng**.
