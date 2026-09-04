# QA MASTER FRAMEWORK — NOVASTARS v12.0

> **Module Identifier**: `04_QA_REGISTRY/QA_MASTER.md`  
> **Role**: Hệ thống Thẩm định Master & Bộ Kiểm định Kiến thức Architecture QA (AQ1 – AQ12)  
> **Precedence Level**: Level 2 Quality Control Framework  

---

## 1. PHÂN CẤP CÁC BỘ TEST TRONG QA REGISTRY

Hệ thống QA Registry quản lý toàn bộ **41 Lesson QA Tests** cùng **12 Architecture QA Tests** phân chia thành các sub-suite độc lập:

```text
04_QA_REGISTRY/
├── QA_MASTER.md                       <-- [File hiện tại: QA Workflow, AQ1..AQ12, M1..M8]
├── TEMPLATE_QA.md                     <-- [TF1 -- TF16: Template Selection & Schema Fidelity]
├── STORY_BOUNDARY_QA.md               <-- [SB1 -- SB5: Story State Boundary & Outcome Leakage]
├── KNOWLEDGE_SKILL_PRODUCT_QA.md      <-- [KC1..KC3, SK1..SK2, PD1..PD2: Knowledge, Skill, Product]
└── TRACEABILITY_QA.md                 <-- [C7 Matrix Audit & C8.1..C8.5 Skill Necessity Tests]
```

---

## 2. BỘ ARCHITECTURE QA TESTS (AQ1 — AQ12)

Đây là 12 bài kiểm tra kiến thức hệ thống v12.0, bắt buộc phải đạt `PASS 12/12` trước khi phát hành phiên bản:

| Test ID | Tên Architecture Test | Đối tượng Kiểm tra | Tiêu chuẩn PASS |
|---|---|---|---|
| **AQ1** | Source of Truth Integrity | Hệ thống Thứ bậc | Cấp thấp KHÔNG override cấp cao (Level 1..6 integrity). |
| **AQ2** | No Duplicated Global Rule | Core vs Roles | 40 Master Rules chỉ nằm ở `01_CORE/GLOBAL_RULES.md`. 0% trùng lặp. |
| **AQ3** | No Orphan Rule | Bảo toàn Quy tắc | Tất cả 40 Rules v11 trace 100% vào `GLOBAL_RULES.md`. |
| **AQ4** | No Orphan Template | Registry Schemas | Tất cả Dạng Template liên kết trực tiếp với Role Family. |
| **AQ5** | No Orphan QA Test | QA Registry | Tất cả 41 QA tests nằm ở `04_QA_REGISTRY/`. 0% thiếu hụt. |
| **AQ6** | No Cross-Role Context Leakage| Role Specs | Nạp Kỹ sư không nạp token của Thám tử, Bác sĩ hay Phóng viên. |
| **AQ7** | No Lesson Data in Global Spec | Global Specs | `01_CORE/` chứa 0% dữ kiện của bài học cụ thể. |
| **AQ8** | No Global Rule in Lesson Pkg | Lesson Package | `05_LESSONS/` chỉ chứa input dữ liệu, 0% hệ thống quy tắc. |
| **AQ9** | Load-on-Demand Compliance | Orchestrator | Orchestrator nạp đúng manifest `REQUIRED`, giảm >70% tokens. |
| **AQ10** | Generator / QA Separation | Agents | Generator 0% logic QA; QA Agent 0% logic sinh học liệu. |
| **AQ11** | Version Traceability | Manifest | `VERSION_MANIFEST.md` map 100% item v11 sang v12. |
| **AQ12** | Semantic Preservation | Ngôn ngữ Sư phạm | 0% thay đổi Canonical Knowledge, Skills, hay Boundaries. |

---

## 3. MISSION NATURALNESS & ROLE VOICE SUITE (M1 — M8)

8 bài kiểm tra văn phong nhập vai tự nhiên của Student Mission:

1. **TEST M1 — ROLE VOICE AUTHENTICITY**: Văn phong nhập vai tự nhiên theo đúng Role Spec. (PASS/FAIL)
2. **TEST M2 — QUESTION-DRIVEN MISSION**: Nhiệm vụ dẫn dắt bởi câu hỏi tự nhiên. (PASS/FAIL)
3. **TEST M3 — PROPOSED ACTION FRAMING**: Mission yêu cầu học sinh ĐỀ XUẤT giải pháp ($C_4$). (PASS/FAIL)
4. **TEST M4 — NO PRE-BAKED DISCOVERY**: Mission không tiết lộ đáp án/bẫy tư duy. (PASS/FAIL)
5. **TEST M5 — AGE APPROPRIATENESS**: Ngôn ngữ phù hợp khối học sinh Khối 8/9. (PASS/FAIL)
6. **TEST M6 — PURE VIETNAMESE**: 100% Tiếng Việt thuần khiết, 0% từ Tiếng Anh. (PASS/FAIL)
7. **TEST M7 — DELIVERABLE CLARITY**: Sản phẩm cần nộp rõ ràng, dễ hiểu. (PASS/FAIL)
8. **TEST M8 — NO TEACHER METADATA IN PART A**: Part A sạch 100% metadata sư phạm. (PASS/FAIL)
