# TEMPLATE REGISTRY SCHEMAS — THEME KỸ SƯ

> **Module Identifier**: `03_ROLE_REGISTRY/KY_SU/TEMPLATE_TYPES.md`  
> **Family Code**: `#TEMPLATE-KS-NOVA`  
> **Schema Fingerprint**: BẤT BIẾN 100%  

---

### DẠNG 1: PHẢN HỒI TỪ KHÁCH HÀNG / NGƯỜI DÙNG
- **ID Registry**: `REG-KS-01`
- **Schema Fingerprint**:
```markdown
* **Mã phiếu:** [Mã phiếu]
* **Người phản ánh:** [Tên nhân vật]
* **Kênh tiếp nhận:** [Hòm thư góp ý / Trang hỗ trợ / Nhắn tin trực tiếp]

> "Gửi Bộ phận Kỹ thuật Nova,
> Tôi/Em muốn phản ánh về việc [Mô tả ngắn gọn sự cố / vấn đề bế tắc / mục tiêu bị chệch hướng].
> Rất mong Kỹ sư kiểm tra và tìm nguyên nhân khắc phục!"
```

---

### DẠNG 2: BÁO CÁO SỰ CỐ KỸ THUẬT (INCIDENT REPORT)
- **ID Registry**: `REG-KS-02`
- **Schema Fingerprint**:
```markdown
* **Mã sự cố:** [Mã sự cố]
* **Hệ thống xảy ra:** [Tên phần mềm / Thiết bị / Kế hoạch cá nhân]
* **Mức độ ảnh hưởng:** [Cao / Trung bình]

#### I. MÔ TẢ HIỆN TRẠNG & TÍNH NĂNG BỊ LỖI
* **Hiện tượng:** [Biểu hiện sai lệch, lãng phí thời gian, bế tắc mục tiêu...]
* **Hậu quả:** [Giảm hiệu suất, mệt mỏi, xảy ra rủi ro...]

#### II. THÔNG SỐ VẬN HÀNH THU THẬP ĐƯỢC
* **Thông số 1:** [Dữ kiện 1 từ nguồn]
* **Thông số 2:** [Dữ kiện 2 từ nguồn]

#### III. YÊU CẦU DÀNH CHO KỸ SƯ
1. Tìm điểm nghẽn / Nguyên nhân gốc rễ gây ra sự cố.
2. Thiết kế Quy trình / Sơ đồ giải pháp tối ưu hệ thống.
```

---

### DẠNG 3: BẢN VẼ / SƠ ĐỒ THÔNG SỐ VẬN HÀNH
- **ID Registry**: `REG-KS-03`
- **Schema Fingerprint**:
```markdown
* **Tên sơ đồ:** Sơ đồ luồng công việc / Ma trận thông số
* **Mô tả luồng hiện tại:** [Trình bày các bước vận hành hiện tại chứa lỗ hổng / sai sót]
* **Bối cảnh sai lệch:** [Lý do dẫn tới thất bại của hệ thống]
```
