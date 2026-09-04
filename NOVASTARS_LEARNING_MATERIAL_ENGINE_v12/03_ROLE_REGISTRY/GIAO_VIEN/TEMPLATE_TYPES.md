# TEMPLATE REGISTRY SCHEMAS — THEME GIÁO VIÊN

> **Module Identifier**: `03_ROLE_REGISTRY/GIAO_VIEN/TEMPLATE_TYPES.md`  
> **Family Code**: `#TEMPLATE-GV-NOVA`  
> **Schema Fingerprint**: BẤT BIẾN 100%  

---

### DẠNG 1: HỒ SƠ HỌC SINH
- **ID Registry**: `REG-GV-01`
- **Schema Fingerprint**:
```markdown
- **Mã hồ sơ:** [Mã HS]
- **Họ và tên:** [Tên học sinh] | **Lớp:** [Tên lớp]
- **Đặc điểm nổi bật:** [Tiền sử / Học lực / Tình cảnh gia đình]
- **Biểu hiện gần đây:** [Thay đổi điểm số / Nghỉ học / Thái độ...]
- **Sự cố kích hoạt:** [Mô tả ngắn 2-3 câu về sự việc bất thường mới xảy ra]
```

---

### DẠNG 2: TRÍCH XUẤT CAMERA LỚP HỌC
- **ID Registry**: `REG-GV-02`
- **Schema Fingerprint**:
```markdown
- **Thiết bị:** Camera phòng [Số phòng] | **Mã trích xuất:** CAM-[Ngày/Tháng]
- **Thời gian:** [HH:MM - HH:MM] | **Đối tượng:** [Học sinh A, Học sinh B...]
- **Diễn biến:** [Mô tả ngắn hành vi va chạm / mâu thuẫn trên lớp]
- **Lời thoại mâu thuẫn (nếu có):**
> **[Học sinh A]:** "[Lời thoại ngắn 1]"  
> **[Học sinh B]:** "[Lời thoại ngắn 2]"
- **Hậu quả tại hiện trường:** [Lớp học hỗn loạn / Học sinh bỏ chạy...]
```

---

### DẠNG 3: THƯ ẨN DANH
- **ID Registry**: `REG-GV-03`
- **Schema Fingerprint**:
```markdown
- **Nơi nhận:** Hòm thư góp ý lớp [Tên lớp]
- **Người gửi:** Ẩn danh (Một học sinh trong lớp)
> Gửi thầy/cô,  
> Em muốn báo với thầy/cô về việc [Mô tả ngắn gọn sự việc].  
> Mong thầy/cô giúp đỡ em/bạn [tên nhân vật].
```

---

### DẠNG 4: EMAIL CỦA PHỤ HUYNH
- **ID Registry**: `REG-GV-04`
- **Schema Fingerprint**:
```markdown
- **Từ:** Phụ huynh em [Tên học sinh]
- **Tiêu đề:** [Phản ánh khẩn]
> Kính gửi thầy/cô [Tên GV],  
> Tôi muốn trao đổi về cháu [Tên HS]. Gần đây cháu [tên học sinh][mô tả ngắn gọn về sự việc].  
> Gia đình rất mong thầy/cô [Mong muốn từ phụ huynh].
```

---

### DẠNG 5: THÔNG BÁO KHẨN
- **ID Registry**: `REG-GV-05`
- **Schema Fingerprint**:
```markdown
- **Đơn vị phát hành:** Ban BGH / Phòng Tư vấn / Đoàn Đội
- **Mã thông báo:** TBK-[Mã bài học]
- **Sự cố ghi nhận:** [Mô tả sự cố bất ngờ]
- **Địa điểm & Thời gian:** [Thời gian, địa điểm, các bên liên quan]
- **Yêu cầu xử lý:** [GVCN cần rà soát và nắm tình hình trước HH:MM]
```

---

### DẠNG 6: ĐOẠN CHAT NHÓM LỚP
- **ID Registry**: `REG-GV-06`
- **Schema Fingerprint**:
```markdown
- **Nguồn trích xuất:** Nhóm Zalo / Messenger lớp [Tên lớp]
```text
[HH:MM] Học sinh A: [Tin nhắn]
[HH:MM] Học sinh B: [Tin nhắn]
[HH:MM] Học sinh C: [Tin nhắn]
```
```
