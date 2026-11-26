# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 08
- **Họ tên:Lê Ngô Hoàng Mạnh 
- **Lớp:CNTT 2
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):**

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt lịch khám ra JSON

**KET QUA AI**

```text
[
  {
    "ma_dich_vu": "TRAMRANG",
    "ngay_hen": "2026-12-17",
    "nguoi_lon": 2,
    "tre_em": 1,
    "khung_gio": "chieu",
    "ghi_chu": null
  },
  {
    "ma_dich_vu": "CAOVOI",
    "ngay_hen": "2027-01-06",
    "nguoi_lon": 3,
    "tre_em": 0,
    "khung_gio": null,
    "ghi_chu": "1 người bị tiểu đường"
  },
  {
    "ma_dich_vu": "TAYTRANG",
    "ngay_hen": null,
    "nguoi_lon": 4,
    "tre_em": 0,
    "khung_gio": "sang",
    "ghi_chu": "1 người dị ứng thuốc tê"
  }
]
```

**Link trò chuyện: https://share.gemini.google/yynBdquY2uda

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
TÍNH TỔNG TIỀN YÊU CẦU BÁO GIÁ

1. Tiền người lớn:
Nhóm có 6 người lớn làm dịch vụ CAOVOI (350.000 đồng/người):
6 x 350.000 = 2.100.000 đồng

2. Tiền trẻ em:
Có 2 trẻ trong độ tuổi 6-12 (7 tuổi và 11 tuổi) tính 80% giá người lớn, và 1 bé 4 tuổi (dưới 6 tuổi) được miễn phí (0 đồng):
2 x (350.000 x 80%) + 1 x 0 = 2 x 280.000 + 0 = 560.000 đồng

3. Tiền dịch vụ:
Tổng tiền người lớn và tiền trẻ em:
2.100.000 + 560.000 = 2.660.000 đồng

4. Giảm giá nhóm:
Nhóm có 6 người lớn (>= 5 người lớn) nên được giảm 10% trên tiền dịch vụ:
2.660.000 x 10% = 266.000 đồng
(Tiền dịch vụ sau giảm: 2.660.000 - 266.000 = 2.394.000 đồng)

5. Phí X-quang:
3 người chụp X-quang, mỗi người 1 phim (150.000 đồng/phim, không giảm giá):
3 x 150.000 = 450.000 đồng

6. Tổng tiền:
Tiền dịch vụ sau giảm cộng phí X-quang:
2.394.000 + 450.000 = 2.844.000 đồng

[RESULT: 2.844.000 đồng]```

**Link trò chuyện: https://share.gemini.google/Byyr7ZGqfj0n

### b) Kiểm tra kết quả AI

(Ghi kết luận AI đúng hay sai; nếu sai, ghi bước sai đầu tiên và kết quả đúng của bước đó – xoá dòng này)

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_su_co": "tre_hen",
  "so_khach": 3,
  "so_lan_hen_bi_tre": 2,
  "tom_tat": "Khách hàng 3 người phải chờ hơn 1 tiếng trong 2 lần hẹn cạo vôi răng vào ngày 05/11 và 12/11."
}```

**Link trò chuyện:https://share.gemini.google/opf4WPKnd6sG

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| :--- | :--- | :--- | :--- |
| Đúng thông tin (50%) | 0/5 | 1. Sai giá dịch vụ:<br>- Câu bị lỗi: "Trám răng bên em 450k/răng thôi, đẹp như răng thật luôn."<br>- Lý do sai: Giá chuẩn của công ty là 500.000 đồng/răng, tư vấn 450k/răng là sai lệch thông tin.<br>- Câu sửa đề xuất: "Dịch vụ trám răng tại nha khoa có chi phí là 500.000 đồng/răng."<br><br>2. Sai chính sách bảo hành:<br>- Câu bị lỗi: "Bong sau 8 tháng thì em làm lại free cho anh nha."<br>- Lý do sai: Bong sau 8 tháng (thuộc khoảng từ tháng 7 đến tháng 12) chỉ được giảm 50%, không được làm lại miễn phí (chỉ miễn phí trong 6 tháng đầu).<br>- Câu sửa đề xuất: "Về chính sách bảo hành, nếu miếng trám bong trong 6 tháng đầu sẽ được làm lại miễn phí; từ tháng 7 đến tháng 12 được giảm 50%; sau 12 tháng nha khoa không áp dụng bảo hành ạ." | Nêu đúng giá 500.000 đồng/răng và đầy đủ 3 mốc thời gian của chính sách bảo hành. |
| Đầy đủ (30%) | 0.5/3 | Thiếu lời mời cung cấp ngày hẹn, khung giờ để đặt lịch:<br>- Câu bị lỗi: "Cần gì cứ inbox em ạ!"<br>- Lý do sai: Câu kết chưa chủ động mời khách cung cấp ngày hẹn và khung giờ để đặt lịch hẹn khám/trám răng.<br>- Câu sửa đề xuất: "Anh vui lòng cho em xin ngày hẹn và khung giờ mong muốn để nha khoa hỗ trợ đặt lịch tư vấn và điều trị cho mình ạ." | Bổ sung lời mời khách cung cấp ngày hẹn và khung giờ cụ thể để đặt lịch. |
| Giọng điệu (20%) | 0.5/2 | Dùng từ ngữ suồng sã, thiếu tính chuyên nghiệp:<br>- Câu bị lỗi: "Trám răng bên em 450k/răng thôi, đẹp như răng thật luôn." và "Bong sau 8 tháng thì em làm lại free cho anh nha. Cần gì cứ inbox em ạ!"<br>- Lý do sai: Các từ như "bên em", "450k", "free", "nha", "inbox" mang sắc thái thân mật quá mức/suồng sã, chưa chuẩn mực trong giao tiếp tư vấn dịch vụ y tế/nha khoa.<br>- Câu sửa đề xuất: "Dạ chào anh! Dịch vụ trám răng tại nha khoa có chi phí 500.000 đồng/răng ạ. Nếu miếng trám bong trong 6 tháng đầu sẽ được làm lại miễn phí, từ tháng 7 đến tháng 12 giảm 50%, và sau 12 tháng không bảo hành. Anh cho em xin ngày hẹn và khung giờ để bên em đặt lịch cho anh nhé." | Sử dụng xưng hô chuẩn mực, ngôn ngữ tiếng Việt rõ ràng, lịch sự và chuyên nghiệp hơn. |

Tổng điểm: 1/10```

**Link trò chuyện:https://share.gemini.google/NotRADoXa44I
