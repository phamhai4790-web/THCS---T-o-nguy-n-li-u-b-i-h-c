# KNOWLEDGE, SKILL & PRODUCT BOUNDARY QA SUITE — KC, SK, PD

> **Module Identifier**: `04_QA_REGISTRY/KNOWLEDGE_SKILL_PRODUCT_QA.md`  
> **Role**: Bộ Thẩm định Trần Kiến thức, Trần Kỹ năng & Đường truy xuất Sản phẩm (KC1..KC3, SK1..SK2, PD1..PD2)  
> **Precedence Level**: Level 2 Quality Control Suite  

---

## 1. KNOWLEDGE-CONTENT BOUNDARY TESTS (KC1 — KC3)

1. **TEST KC1 — KNOWLEDGE-CONTENT BOUNDARY**: Mọi khái niệm/tiêu chí xuất hiện trong bài học đều truy xuất trực tiếp về Canonical Content. (PASS/FAIL)
2. **TEST KC2 — NO IMPLICIT KNOWLEDGE INJECTION**: Tuyệt đối CẤM nâng dữ kiện chi tiết trong Story thành khung kiến thức/cẩm nang học thuật mới chưa được dạy trong Specification. (PASS/FAIL)
3. **TEST KC3 — CANONICAL SOURCE TRACEABILITY**: Truy xuất trọn vẹn theo chuỗi Canonical Knowledge. (PASS/FAIL)

---

## 2. SKILL BOUNDARY TESTS (SK1 — SK2)

1. **TEST SK1 — NO INVENTED SKILL OPERATIONS**: Tuyệt đối CẤM biến tình huống/hành động cụ thể trong Story thành quy trình kỹ năng mới ngoài Skill Map $C_1 \dots C_n$. (PASS/FAIL)
2. **TEST SK2 — CANONICAL SKILL COMPLIANCE**: Mọi thao tác nhận thức $C_1 \dots C_n$ phải tuân thủ 100% cấu trúc của Canonical Skill. (PASS/FAIL)

---

## 3. PRODUCT BOUNDARY TESTS (PD1 — PD2)

1. **TEST PD1 — PRODUCT TRACEABILITY CHAIN**: Mọi sản phẩm yêu cầu học sinh nộp bắt buộc phải có đường truy xuất trọn vẹn: `STUDENT PRODUCT -> CANONICAL SKILL -> EXPLICIT KNOWLEDGE`. (PASS/FAIL)
2. **TEST PD2 — ORPHAN PRODUCT ELIMINATION**: Loại bỏ 100% các sản phẩm mồ côi không có cơ sở trong Canonical Specification. (PASS/FAIL)
