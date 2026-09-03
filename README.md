# Day 28 Track 01 — Dashboard Hành động cho Áp dụng AI v2

## 1. Thành viên và đóng góp

| Họ tên | MSSV | Phần phụ trách | Góp ý đã đưa cho nhóm bạn |
|---|---|---|---|
| Nguyễn Thị Hải Yến | 2A202601388 | ADKAR, tổng hợp vấn đề và memo | Đề nghị nhóm bạn phân biệt điểm nghẽn Desire/Ability với nhu cầu đào tạo; bổ sung hành động khi chỉ số xấu |
| Đồng Đại Huy | 2A202601901 | Mollick, phân chia người–AI và điểm bàn giao | Đề nghị nhóm bạn nêu rõ ai giữ quyền quyết định, ai kiểm chứng và cách chuyển người khi AI không chắc chắn |
| Lê Đình Việt | 2A202601528 | Gartner-Lite, readiness/governance và roadmap | Đề nghị nhóm bạn bổ sung data owner, nguồn dữ liệu, gate 30–60–90 và không rollout khi readiness chưa đạt |

Nhóm đã thực hiện kiểm tra chéo theo bốn trục của lab: phạm vi, framework, chỉ số và hành động. Tên nhóm đối tác không được lưu trong các tài liệu nguồn; nội dung góp ý và thay đổi sau phản biện được ghi trong [review/phan_bien_cheo.md](review/phan_bien_cheo.md).

## 2. Phạm vi

**Sản phẩm AI:** trợ lý soạn thảo báo cáo vận hành định kỳ. **Người dùng chính:** nhân viên vận hành. **Quy trình:** tổng hợp dữ liệu thô → sinh bản nháp báo cáo → đối soát số liệu.

## 3. Nguyên nhân gốc

Readiness chưa đạt: dữ liệu đầu vào chưa chuẩn hóa, số liệu chưa có nguồn truy vết và chưa có validator. Absorption chưa đạt: thiếu owner, điểm bàn giao và vòng phản hồi lỗi. Framework sử dụng: Gartner-Lite, Mollick và ADKAR. Bằng chứng là quan sát định tính trong workflow nhóm; baseline định lượng sẽ được khóa sau 5 báo cáo pilot.

## 4. Cách làm mới

Nguồn dữ liệu được khóa và gắn phiên bản; AI chỉ tính/viết từ số liệu đã xác nhận và phải gắn nguồn; validator và QA kiểm tra trước khi nhân viên vận hành duyệt. Khi AI không chắc chắn hoặc có chênh lệch, hệ thống đánh dấu và chuyển cho data owner/chủ báo cáo; AI không tự tạo số liệu và không tự phát hành.

## 5. Chỉ số

Dashboard v2 đo từ chất lượng sản phẩm đến workflow: tỷ lệ bản nháp được duyệt vòng đầu, thời gian từ khóa dữ liệu đến phê duyệt, tỷ lệ chỉ số truy xuất được nguồn, tỷ lệ nội dung phải viết lại và tỷ lệ ngoại lệ được chuyển đúng owner. Mỗi chỉ số có baseline, target, nguồn, owner và hành động khi xấu; số liệu thực tế được nhập trong sheet `Input_Log`.

## 6. Quyết định

**Tiếp tục pilot có điều kiện, chưa rollout rộng.** Chỉ mở rộng khi đạt ngưỡng chất lượng, hành vi và giá trị đã đặt ra. So với v1, nhóm đã thay metric activity bằng metric giá trị/workflow và bổ sung validator, điểm bàn giao, owner cùng gate quyết định; chi tiết ở [memo/memo_quyet_dinh.md](memo/memo_quyet_dinh.md).

## Cấu trúc bài nộp

```text
Day28_Track01_<Ten_Nhom>/
├── README.md
├── dashboard/
│   └── dashboard_hanh_dong_v2.xlsx
├── memo/
│   └── memo_quyet_dinh.md
├── v1/
│   └── dashboard_hanh_dong_v1.xlsx
├── evidence/
│   └── bang_chung_workflow.md
├── review/
│   └── phan_bien_cheo.md
└── workflow_roadmap.md
```
