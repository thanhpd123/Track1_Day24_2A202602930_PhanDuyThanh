# Track 1 — Day 24 — CS9 Workshop: AI Economics / ROI / Pricing (bài nhóm)

Bài nhóm **3201** của buổi Day 24, Track 1 — AI Product Management. Câu hỏi cả buổi: **sản phẩm AI này có lãi không, bán giá bao nhiêu và có đáng bỏ tiền làm không?**

## File trong repo

| File | Là gì |
|---|---|
| `Nhom3201_CS9.xlsx` | Bài nhóm (file Excel nộp trên VLearn) |

## Đề bài nhóm chọn

Các thành viên ngồi chung bàn nhưng không có dự án chung, nên theo runbook nhóm chọn 1 trong 3 đề bài giả định và dùng xuyên suốt buổi:

> **Đề bài 1 — SổSạch:** trợ lý AI đọc hoá đơn đầu vào cho văn phòng kế toán dịch vụ.
> **1 việc** = 1 hoá đơn đầu vào được đọc, đối chiếu mã số thuế và nhập vào phần mềm kế toán.
> **Khách trả tiền:** văn phòng kế toán dịch vụ. **Điểm cần chú ý:** chi phí người kiểm tra lớn; văn phòng lớn thấy đắt.

Mọi số ở sheet 1–3 lấy đúng từ đề; cột "Nguồn / lý do" ghi rõ "Đề bài 1, Trang X". Giá token và tỷ giá là dữ liệu bài tập (trang 9 của đề), không phải báo giá nhóm tự kiểm chứng.

## Nội dung các sheet

| Sheet | Nội dung |
|---|---|
| `0_Đầu vào` | 6 đầu vào đánh dấu "Chưa" (dùng đề giả định, không có số đo thật) và ghi nguồn thay thế |
| `A_Tài chính căn bản` | Ba báo cáo tài chính (Trợ Lý Xanh): kết quả kinh doanh, cân đối kế toán, lưu chuyển tiền tệ, câu hỏi 1–4, bài mua hay thuê máy chủ. Mọi ô kiểm tra "Đạt" |
| `1_Chi phí mỗi việc` | Claude Haiku 4.5, 2 lần gọi, 2.500 / 400 token, gọi lại 8%, 20% hoá đơn cần kế toán viên kiểm tra 1,5 phút |
| `2_Định giá` | Gói kết hợp 1.990.000 đ/tháng gồm 1.000 hoá đơn, vượt 2.200 đ/hoá đơn; 70% văn phòng nhỏ (800 hoá đơn), 30% văn phòng lớn (4.000 hoá đơn); lương người được thay 8 triệu; không chia đối tác |
| `3_Giả định` | Cơ sở theo đề: 12 khách mới, tăng 5%/tháng, rời bỏ 3%, CAC 9 triệu, cố định 200 triệu, xây dựng 900 triệu, tiền mặt 2,5 tỷ |
| `4`, `5` | Chỉ số mỗi khách, dòng tiền 24 tháng, độ nhạy (giảm 20%), mức cảnh báo |
| `6_Hiệu quả nội bộ` | Không áp dụng (sản phẩm bán ra ngoài) |
| `7_Quyết định` | 5 câu quyết định và trả lời 3 câu hỏi riêng của đề |

## Kết quả chính

| Chỉ số | Cơ sở | Xấu |
|---|---|---|
| Chi phí mỗi hoá đơn | 704 đ (gọi AI 254 · người kiểm tra 250 · khác 200) | |
| Biên lợi nhuận gộp | 68,8% | 53,2% |
| LTV ÷ CAC | 10,1 | 2,6 |
| Hoàn vốn chi phí có khách | 3,3 tháng | 8,0 tháng |
| NPV 24 tháng | +935 triệu (IRR 47%/năm) | −5,0 tỷ |
| Tiền mặt thấp nhất | 173 triệu | −3,09 tỷ |
| Hoàn vốn dự án / hết tiền | hoàn vốn tháng 21 | **hết tiền tháng 7** |

- **Biến nguy hiểm nhất:** doanh thu bình quân / khách. Giảm 20% thì NPV còn −1.965 triệu; chỉ cần giảm 6,5% (dưới 3,71 triệu) là về hoà vốn.
- **Phụ thuộc văn phòng lớn:** nhóm này mang về 65% doanh thu và trả 8,59 triệu/tháng, bằng 107% lương một nhân viên nhập liệu (vượt mốc 70%). Nếu họ bỏ đi và được thay bằng văn phòng nhỏ, NPV còn −3,83 tỷ.
- **Gói không giới hạn** đẩy tiền AI ÷ doanh thu của văn phòng lớn lên 1,42 (nguy), nên không dùng.

## Quyết định: THỬ NGHIỆM NHỎ

Kịch bản cơ sở có lãi nhưng kịch bản xấu hết tiền ở tháng 7, nên không chọn "Làm". Từng khách vẫn có lãi (LTV ÷ CAC 10,1), nên cũng không chọn "Dừng".

- Thử 3 tháng với 12 văn phòng (giữ tỷ lệ 70% nhỏ / 30% lớn).
- Mở rộng khi doanh thu bình quân ≥ 3,71 triệu và rời bỏ ≤ 3%/tháng.
- **Luật xử lý:** NẾU doanh thu bình quân < 3.714.000 đ hoặc rời bỏ > 4,8%/tháng TRONG 2 tháng liên tiếp trên ít nhất 12 văn phòng THÌ dừng ký văn phòng mới, cắt đội 6 → 4 người, phỏng vấn lại các văn phòng lớn trong 2 tuần. KHÔNG THÌ: cấm hạ phí vượt dưới giá sàn 2.113 đ/hoá đơn và cấm bán gói không giới hạn.
- Chỉ cắt đội còn 4 người (chi phí cố định 140 triệu) thì kịch bản xấu vẫn hết tiền, chỉ lùi sang tháng 9 — vì vậy phải dừng cả chi phí bán hàng cho khách mới (~81 triệu/tháng ở kịch bản xấu).

### Trả lời 3 câu hỏi riêng của đề

1. Chi phí gọi AI (254 đ) và người kiểm tra (250 đ) gần bằng nhau; AI lớn hơn một chút, chiếm khoảng 36% chi phí mỗi hoá đơn.
2. Văn phòng lớn trả 107% lương một nhân viên nhập liệu nên có lý do bỏ đi hoặc ép giá. Cần phỏng vấn xem 4.000 hoá đơn/tháng đang tốn mấy nhân viên.
3. Kịch bản xấu hết tiền ở tháng 7, nên nhóm chọn Thử nghiệm nhỏ kèm kế hoạch cắt giảm ở trên.
