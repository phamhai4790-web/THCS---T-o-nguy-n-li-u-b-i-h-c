# TEMPLATE SELECTION & SCHEMA FIDELITY QA SUITE — TF1 TO TF16

> **Module Identifier**: `04_QA_REGISTRY/TEMPLATE_QA.md`  
> **Role**: Bộ Thẩm định Chọn Dạng & Bảo toàn Schema Fingerprint (TF1 -- TF16)  
> **Precedence Level**: Level 2 Quality Control Suite  

---

## 1. DANH SÁCH 16 TEMPLATE QA TESTS (TF1 — TF16)

1. **TEST TF1 — TEMPLATE FAMILY FIDELITY**: Sử dụng đúng Template Family chính thức của Role. (PASS/FAIL)
2. **TEST TF2 — TEMPLATE TYPE DISCOVERY**: Nhận diện và đọc đầy đủ danh sách các Dạng có sẵn trong Registry trước khi chọn. (PASS/FAIL)
3. **TEST TF3 — TEMPLATE TYPE FIT**: Dạng được chọn được giải trình căn cứ từ Evidence Structure + Story + Skill. (PASS/FAIL)
4. **TEST TF4 — TEMPLATE SCHEMA PRESERVATION**: Giữ nguyên 100% tiêu đề, tên trường và cấu trúc của Dạng đã chọn. (PASS/FAIL)
5. **TEST TF5 — NO DEFAULT DẠNG 1**: Không có luật ngầm mặc định chọn Dạng 1 khi chưa phân tích cấu trúc bằng chứng. (PASS/FAIL)
6. **TEST TF6 — TEMPLATE USAGE DIVERSITY**: Ưu tiên Dạng ít dùng gần đây khi điểm phù hợp tương đương. (PASS/FAIL)
7. **TEST TF7 — NO FORCED DIVERSITY**: Độ phù hợp Cấu trúc Bằng chứng luôn được ưu tiên hơn tính đa dạng. (PASS/FAIL)
8. **TEST TF8 — ROLE TEMPLATE LOCK**: Không tạo Template Family tùy tiện ngoài Registry. (PASS/FAIL)
9. **TEST TF9 — SOURCE STORY NATURALNESS**: Dạng được chọn thể hiện câu chuyện nguồn một cách tự nhiên, không gượng ép. (PASS/FAIL)
10. **TEST TF10 — MULTI-TYPE GENERALIZATION**: Thể hiện khả năng sử dụng linh hoạt các Dạng khác nhau cho cùng một Role qua nhiều bài. (PASS/FAIL)
11. **TEST TF11 — TEMPLATE SOURCE TRACEABILITY**: Truy ngược được 100% từ Generated Material $\rightarrow$ Template Type $\rightarrow$ Registry $\rightarrow$ Template Source. (PASS/FAIL)
12. **TEST TF12 — SCHEMA FINGERPRINT**: Cấu trúc tiêu đề, trường thông tin và thứ tự trường khớp 100% với mẫu trong Registry. (PASS/FAIL)
13. **TEST TF13 — METADATA FIDELITY**: Tên Family, Tên Dạng, Version, Schema ID đúng 100% với Nguồn Registry. (PASS/FAIL)
14. **TEST TF14 — TEMPLATE INVENTION BLOCK**: Không tự phát minh Dạng mới ngoài Registry. (PASS/FAIL)
15. **TEST TF15 — TYPE BIAS AUDIT**: Kiểm tra tỷ lệ sử dụng từng Dạng trong Family, cảnh báo nếu có hiện tượng neo lệch vào Dạng 1 (>70%). (PASS/FAIL)
16. **TEST TF16 — SOURCE STORY / TEMPLATE FIT**: Đánh giá độ khớp giữa loại bằng chứng trong Story và khả năng biểu đạt của Dạng. (PASS/FAIL)
