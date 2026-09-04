# TEMPLATE REGISTRY SCHEMAS — THEME PHÓNG VIÊN

> **Module Identifier**: `03_ROLE_REGISTRY/PHONG_VIEN/TEMPLATE_TYPES.md`  
> **Family Code**: `#TEMPLATE-PV-NOVA`  
> **Schema Fingerprint**: BẤT BIẾN 100%  

---

### DẠNG 1: HỒ SƠ HIỆN TRƯỜNG (FIELD REPORT)
- **ID Registry**: `REG-PV-01`
- **Schema Fingerprint**:
```markdown
* **Mã bản tin:** [Mã bản tin]
* **Phóng viên tiếp cận:** [Tên phóng viên / Nhóm]
* **Thời gian:** [Thời điểm xảy ra sự việc] | **Địa điểm:** [Vị trí hiện trường]

#### I. GHI NHẬN HIỆN TRƯỜNG
* **Nhân vật liên quan:** [Tên nhân vật / Đối tượng]
* **Sự việc vừa xảy ra:** [Mô tả ngắn gọn diễn biến chính]
* **Những gì quan sát được:** [Chi tiết dấu hiệu, cảm xúc, biểu hiện...]
* **Phản ứng của các nhân vật:** [Phản ứng ban đầu, mâu thuẫn...]
* **Dữ kiện đáng chú ý:** [Chi tiết quan trọng phục vụ bóc tách]
```

---

### DẠNG 2: ĐOẠN CHAT / LỊCH SỬ TRÒ CHUYỆN (CHAT LOG)
- **ID Registry**: `REG-PV-02`
- **Schema Fingerprint**:
```markdown
* **Nguồn trích xuất:** [Nhóm Chat Lớp / Tin nhắn riêng]
* **Thời gian ghi nhận:** [Mốc thời gian]
```text
[HH:MM] Nhân vật A: "..."
[HH:MM] Nhân vật B: "..."
[HH:MM] Nhân vật C: "..."
```
```

---

### DẠNG 3: TRANG NHẬT KÝ (DIARY ENTRY)
- **ID Registry**: `REG-PV-03`
- **Schema Fingerprint**:
```markdown
* **Ngày:** [Thời gian] | **Chủ nhân nhật ký:** [Tên nhân vật]
> "Hôm nay mọi thứ... [Nội dung nhật ký thể hiện diễn biến tâm lý và bế tắc của nhân vật]."
```

---

### DẠNG 4: BÀI ĐĂNG MẠNG XÃ HỘI (SOCIAL POST)
- **ID Registry**: `REG-PV-04`
- **Schema Fingerprint**:
```markdown
* **Tài khoản đăng bài:** [Tên tài khoản] | **Thời gian:** [Thời điểm đăng]
> "Nội dung bài đăng..."
> ❤️ [Số lượt thích]    💬 [Số bình luận]    ↪ [Số chia sẻ]
> **Bình luận:**
> - User 1: "..."
> - User 2: "..."
```

---

### DẠNG 5: LỜI KỂ NHÂN CHỨNG (WITNESS STATEMENT)
- **ID Registry**: `REG-PV-05`
- **Schema Fingerprint**:
```markdown
* **Nhân chứng:** [Tên / Chức danh] | **Địa điểm:** [Nơi phỏng vấn]
> "Tôi nhìn thấy... Tôi nghe thấy... Theo tôi..."
```
