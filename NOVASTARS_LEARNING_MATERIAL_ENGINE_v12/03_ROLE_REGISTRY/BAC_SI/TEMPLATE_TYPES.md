# TEMPLATE REGISTRY SCHEMAS — THEME BÁC SĨ

> **Module Identifier**: `03_ROLE_REGISTRY/BAC_SI/TEMPLATE_TYPES.md`  
> **Family Code**: `#TEMPLATE-CB-NOVA`  
> **Schema Fingerprint**: BẤT BIẾN 100%  

---

### DẠNG 1: HỒ SƠ BỆNH ÁN TÂM LÝ & HÀNH VI KNS
- **ID Registry**: `REG-CB-01`
- **Schema Fingerprint**:
```markdown
* **Mã bệnh án:** [Mã bệnh án]
* **Họ và tên Bệnh nhân:** [Tên nhân vật]
* **Lớp / Khối:** [Lớp / Khối tuổi] | **Bác sĩ tiếp nhận:** Nhóm Bác sĩ KNS Nova
* **Thời gian tiếp nhận:** Tiết 1 — Chuyên án: [Tên Bài học]

#### I. THÔNG TIN HÀNH CHÍNH & TIẾP NHẬN BỆNH NHÂN
* **Tình trạng khẩn cấp:** [Tóm tắt biểu hiện mâu thuẫn, hoảng loạn hoặc bế tắc của bệnh nhân]

#### II. DIỄN BIẾN LÂM SÀNG & TRIỆU CHỨNG BẮT GẶP
* **Dấu hiệu tâm lý:** [Cảm xúc tiêu cực, sợ hãi, bối rối...]
* **Dấu hiệu hành vi:** [Phản ứng sai lầm, im lặng, đổ lỗi...]
* **Môi trường tác động:** [Tác động từ bạn bè, mạng xã hội, gia đình...]

#### III. CHẨN ĐOÁN SƠ BỘ & CÂU HỎI HỘI CHẨN
* **Yêu cầu dành cho Bác sĩ:**
  1. Xác định "Bệnh lý / Bẫy tư duy" bệnh nhân đang gặp phải.
  2. Truy tìm nguyên nhân gốc rễ và đề xuất Phác đồ ứng phó KNS chuẩn.
```

---

### DẠNG 2: THƯ TƯ VẤN SỨC KHỎE HỌC ĐƯỜNG
- **ID Registry**: `REG-CB-02`
- **Schema Fingerprint**:
```markdown
* **Người gửi:** [Tên nhân vật / Bệnh nhân hidden]
* **Kính gửi:** Phòng Tư vấn Dinh dưỡng & Tâm lý Học đường Nova

> "Kính gửi các Bác sĩ Nova,
> Dạo gần đây em đang gặp một vấn đề nghiêm trọng về [Mô tả vấn đề sức khỏe / tâm lý / thói quen tiêu cực].
> [Mô tả chi tiết hoàn cảnh và diễn biến sự việc].
> Em đã thử [Phản ứng sai lầm] nhưng mọi chuyện càng tồi tệ hơn...
> Mong Bác sĩ cho em lời khuyên và phác đồ khắc phục!"
```

---

### DẠNG 3: NHẬT KÝ THEO DÕI TRIỆU CHỨNG / SINH HIỆU
- **ID Registry**: `REG-CB-03`
- **Schema Fingerprint**:
```markdown
* **Bệnh nhân:** [Tên nhân vật] | **Mã theo dõi:** SH-[MÃ_BÀI]
* **Mốc 1 (Trước sự cố):** [Trạng thái bình thường / Kỳ vọng]
* **Mốc 2 (Sự cố bùng nổ):** [Triệu chứng cấp tính / Sự cố xảy ra]
* **Mốc 3 (Hậu quả / Bế tắc):** [Diễn biến xấu đi do chọn sai cách ứng phó]
```
