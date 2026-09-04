# ROLE REGISTRY MASTER CATALOG — NOVASTARS v12.0

> **Module Identifier**: `03_ROLE_REGISTRY/ROLE_REGISTRY.md`  
> **Role**: Danh mục Đăng ký Master các Role & Template Families  
> **Precedence Level**: Level 4 Master Specification  

---

## 1. DÂN THUẬT DANH MỤC ROLE CHÍNH THỨC

Hệ thống Novastars v12.0 hỗ trợ 5 Role nhập vai chuẩn, mỗi Role được khóa cố định vào một **Template Family** chính thức trong Registry.

```text
ROLE REGISTRY MAP:
├── THÁM TỬ ──────> Family Code: #TEMPLATE-TT-NOVA (4 Registered Types)
├── BÁC SĨ ───────> Family Code: #TEMPLATE-CB-NOVA (3 Registered Types)
├── KỸ SƯ ────────> Family Code: #TEMPLATE-KS-NOVA (3 Registered Types)
├── PHÓNG VIÊN ───> Family Code: #TEMPLATE-PV-NOVA (5 Registered Types)
└── GIÁO VIÊN ────> Family Code: #TEMPLATE-GV-NOVA (6 Registered Types)
```

---

## 2. BẢNG MÃ MẸO & DANH SÁCH DẠNG TRONG REGISTRY

| Role / Theme | Code Family | File Directory Path | Registered Template Types (DẠNG) |
|---|---|---|---|
| **THÁM TỬ** | `#TEMPLATE-TT-NOVA` | `03_ROLE_REGISTRY/THAM_TU/` | Dạng 1: Hồ sơ chuyên án khẩn cấp<br>Dạng 2: Báo cáo sự cố / Thư SOS<br>Dạng 3: Trích xuất nhật ký cá nhân<br>Dạng 4: Lịch sử trò chuyện / Chat Log |
| **BÁC SĨ** | `#TEMPLATE-CB-NOVA` | `03_ROLE_REGISTRY/BAC_SI/` | Dạng 1: Hồ sơ bệnh án tâm lý & hành vi<br>Dạng 2: Thư tư vấn sức khỏe học đường<br>Dạng 3: Nhật ký theo dõi triệu chứng |
| **KỸ SƯ** | `#TEMPLATE-KS-NOVA` | `03_ROLE_REGISTRY/KY_SU/` | Dạng 1: Phản hồi từ khách hàng / Người dùng<br>Dạng 2: Báo cáo sự cố kỹ thuật<br>Dạng 3: Bản vẽ / Sơ đồ thông số vận hành |
| **PHÓNG VIÊN** | `#TEMPLATE-PV-NOVA` | `03_ROLE_REGISTRY/PHONG_VIEN/` | Dạng 1: Hồ sơ hiện trường (Field Report)<br>Dạng 2: Đoạn chat / Lịch sử trò chuyện<br>Dạng 3: Trang nhật ký cá nhân<br>Dạng 4: Bài đăng mạng xã hội<br>Dạng 5: Lời kể nhân chứng |
| **GIÁO VIÊN** | `#TEMPLATE-GV-NOVA` | `03_ROLE_REGISTRY/GIAO_VIEN/` | Dạng 1: Hồ sơ học sinh<br>Dạng 2: Trích xuất camera lớp học<br>Dạng 3: Thư ẩn danh<br>Dạng 4: Email của phụ huynh<br>Dạng 5: Thông báo khẩn<br>Dạng 6: Đoạn chat nhóm lớp |

---

## 3. QUY TẮC KHÓA DẠNG TEMPLATE (FAMILY LOCK RULE)

- **Rule 29 Enforcement**: Generator tuyệt đối CẤM lấy Template Family của Role này sử dụng cho Role khác (Ví dụ: Cấm lấy `#TEMPLATE-KS-NOVA` cho Thám tử).
- **Schema Fingerprint Invariance**: Mỗi Dạng trong Registry sở hữu một Schema Fingerprint bất biến. Generator tuyệt đối KHÔNG được tự ý sửa đổi tên trường hay thứ tự trường của Dạng.
