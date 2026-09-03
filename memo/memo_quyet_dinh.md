# Memo quyết định — Dashboard Hành động cho Áp dụng AI v2

## 1. Vấn đề và nguyên nhân gốc

Nhóm tập trung vào **trợ lý AI soạn thảo báo cáo vận hành định kỳ** cho **nhân viên vận hành**, trong workflow **tổng hợp dữ liệu thô → sinh bản nháp báo cáo → đối soát số liệu**. Vấn đề quan sát được là bản nháp có thể chứa chỉ số không truy xuất được về dữ liệu nguồn và diễn đạt dài dòng, khiến người dùng phải kiểm tra và viết lại.

Hai nguyên nhân gốc:

1. **Readiness chưa đạt:** dữ liệu đầu vào chưa có schema và nguồn chuẩn; chưa có validator để đối chiếu từng chỉ số với dữ liệu gốc.
2. **Absorption chưa đạt:** chưa có data owner/chủ báo cáo, điểm bàn giao và vòng phản hồi lỗi để duy trì cách làm mới.

## 2. Framework và bằng chứng

- **Gartner-Lite:** Direction đã rõ, nhưng Readiness và Absorption thiếu dữ liệu chuẩn, governance, owner và cơ chế học từ lỗi.
- **Mollick:** AI nằm ở vùng hỗ trợ; con người kiểm chứng, xử lý ngoại lệ, phê duyệt và chịu trách nhiệm cuối.
- **ADKAR:** người dùng nghẽn ở Awareness/Desire vì không biết giới hạn của AI và lo chịu trách nhiệm khi số liệu sai; Knowledge/Ability/Reinforcement cần được hỗ trợ ngay trong workflow.
- **Bằng chứng:** quan sát định tính trong workflow nhóm: AI nhận dữ liệu/prompt tự do, đầu ra có nguy cơ sinh chỉ số không có trong nguồn và người dùng phải viết lại câu chữ. Đây chưa phải số liệu định lượng; nhóm sẽ khóa baseline bằng 5 báo cáo đầu của pilot. Chi tiết ở [evidence/bang_chung_workflow.md](../evidence/bang_chung_workflow.md).

## 3. Thay đổi sau phản biện chéo

1. **Thay đổi cách đo:** v1 thiên về số báo cáo AI tạo và số người dùng; v2 chuyển sang tỷ lệ duyệt vòng đầu, thời gian xử lý, tỷ lệ truy xuất nguồn và tỷ lệ viết lại.
2. **Thay đổi cơ chế kiểm soát:** v2 thêm schema/nguồn dữ liệu đã khóa, validator, trích nguồn từng chỉ số, điểm bàn giao và quy tắc chuyển người khi AI không chắc chắn.
3. **Thay đổi cách triển khai:** v2 thêm owner và gate cho từng giai đoạn 30–60–90; chưa đạt ngưỡng thì sửa hoặc dừng, không rollout theo thời gian.

## 4. Quyết định

**Tiếp tục pilot có điều kiện; chưa rollout rộng.** Pilot chỉ chuyển sang mở rộng khi tỷ lệ chỉ số truy xuất nguồn đạt tối thiểu 95%, tỷ lệ duyệt vòng đầu đạt tối thiểu 80%, tỷ lệ nội dung phải viết lại không quá 20% và mọi ngoại lệ nghiêm trọng được chuyển đúng owner.

## 5. Lý do, bước tiếp theo và owner

- **0–30 ngày — Data owner + chủ quy trình:** khóa schema, nguồn dữ liệu, template, quyền truy cập; chọn một loại báo cáo và ghi baseline 5 mẫu.
- **31–60 ngày — Phụ trách AI + QA:** bật validator/trích nguồn, QA theo mẫu, hướng dẫn người dùng và ghi log lỗi/chuyển người.
- **61–90 ngày — Chủ nghiệp vụ:** đối chiếu target, kiểm tra governance và quyết định mở rộng, sửa rồi thử lại hoặc dừng.

Nếu chất lượng hoặc traceability dưới ngưỡng, dừng mở rộng và quay lại sửa nguồn dữ liệu/validator. Nếu đạt ngưỡng nhưng thời gian hoặc tỷ lệ viết lại chưa đạt, sửa workflow và thử lại pilot. Nếu các ngưỡng đều đạt, mở rộng có kiểm soát.
