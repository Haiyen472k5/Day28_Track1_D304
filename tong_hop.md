# Bước 1:

Product:  trợ lý soạn thảo báo cáo vận hành
User:     nhân viên vận hành
Workflow: tổng hợp dữ liệu thô → sinh bản nháp báo cáo → đối soát số liệu
Problem:  vẫn phải viết lại do AI bịa chỉ số và hành văn lan man

**Một dòng phạm vi:** Xây dựng trợ lý AI soạn thảo báo cáo vận hành định kỳ cho nhân viên vận hành, tập trung giải quyết triệt để lỗi bịa đặt chỉ số và hành văn lan man trong quy trình sinh bản nháp và đối soát số liệu.


# Bước 2:

## Năm câu hỏi mở đầu

| **Trục** | **Nhận định**                                                                                           | **Mức** |
| --------------- | ---------------------------------------------------------------------------------------------------------------- | -------------- |
| Workflow        | AI chỉ nhận prompt tự do, tách rời bước chốt số liệu thô và duyệt báo cáo                         | Liên quan     |
| Con người     | Nhân viên mất lòng tin do AI bịa số, ngại dùng vì sửa còn lâu hơn viết tay                         | Liên quan     |
| Sẵn sàng      | Chưa có schema chuẩn hóa đầu vào; số liệu thô chưa được làm sạch trước khi đưa vào AI       | Liên quan     |
| Tin cậy        | Không có validator đối chiếu số liệu; AI tự sinh chỉ số mà không có trích nguồn dữ liệu gốc    | **GỐC** |
| Đo lường     | Chỉ đo số lượng báo cáo AI tạo ra; chưa đo tỷ lệ sai số và thời gian nhân viên phải viết lại | **GỐC** |

## Gartner-Lite

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

**Kết luận**: Direction đã tương đối rõ, nhưng Readiness và Absorption chưa đạt. Vì vậy, nhóm chỉ nên triển khai pilot nhỏ cho một loại báo cáo và một nhóm vận hành; chưa nên rollout rộng.

## Mollick — việc chia người–AI đã rõ chưa?

| Vùng | Nguyên tắc | Nội dung áp dụng cho phương án của nhóm |
| --- | --- | --- |
| **Người làm** | Giữ quyền quyết định | Nhân viên vận hành kiểm tra nội dung và số liệu; data owner xác nhận dữ liệu; chủ báo cáo xử lý ngoại lệ, phê duyệt và chịu trách nhiệm về bản cuối. |
| **AI hỗ trợ** | AI làm, người kiểm tra | AI chuẩn hóa dữ liệu, tạo bản nháp theo template, tóm tắt xu hướng và cảnh báo chênh lệch; nhân viên kiểm chứng trước khi sử dụng. |
| **AI tự động** | Chỉ với tác vụ rõ | Chỉ tự động các tác vụ lặp lại, rủi ro thấp như định dạng, sắp xếp hoặc tính toán từ dữ liệu đã xác nhận; không tự tạo số liệu và không tự phát hành báo cáo. |

**Mục đích**: Vấn đề của nhóm không chỉ là AI viết chưa tốt, mà còn là ranh giới công việc giữa người và AI chưa rõ. Theo Mollick, trợ lý AI nên nằm chủ yếu ở vùng **AI hỗ trợ, người kiểm tra**.

AI có thể tăng tốc việc tổng hợp, tính toán nháp và soạn thảo; con người vẫn phải kiểm chứng, xử lý ngoại lệ, phê duyệt và chịu trách nhiệm cuối cùng. Chỉ các tác vụ định dạng hoặc xử lý lặp lại, rủi ro thấp mới được tự động hóa.

## ADKAR — người dùng đang kẹt ở đâu?
| Bước                  | Nhận định                                                                                                         | Trạng thái  |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------- | --------------- |
| **A**wareness     | Chưa hiểu rõ ranh giới: AI chỉ hỗ trợ diễn đạt chứ không tính toán số liệu         | Nghẽn         |
| **D**esire        | Sợ chịu trách nhiệm khi báo cáo sai số; thà viết tay từ đầu còn hơn mất công rà soát sửa lỗi | Nghẽn         |
| **K**nowledge     | Chưa biết cách cấp context đầu vào chuẩn  và dùng prompt ràng buộc độ dài, format                    | Cần làm    |
| **A**bility       | Chưa có công cụ validator tự động đối chiếu số liệu nháp với file dữ liệu thô ngay khi viết         | Cần làm    |
| **R**einforcement | Chưa có cơ chế ghi nhận báo cáo chuẩn, chưa phạt/thưởng dựa trên tỷ lệ tiết kiệm thời gian thực tế | Cần làm<br /> |


**Kết luận:** đào tạo prompt là chưa đủ; cần khóa cứng số liệu (chống ảo giác), cơ chế đối soát tự động và quy định rõ trách nhiệm kiểm duyệt ngay tại workflow.



