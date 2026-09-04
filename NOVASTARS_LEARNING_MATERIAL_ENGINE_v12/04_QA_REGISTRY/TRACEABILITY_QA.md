# DEEP TRACEABILITY & SKILL NECESSITY QA SUITE — C7 MATRIX & C8 TESTS

> **Module Identifier**: `04_QA_REGISTRY/TRACEABILITY_QA.md`  
> **Role**: Bộ Thẩm định Ma trận Truy xuất Sâu & Tính Cần thiết của Canonical Skill  
> **Precedence Level**: Level 2 Quality Control Suite  

---

## 1. PHƯƠNG PHÁP AUDIT MA TRẬN TRUY XUẤT SÂU (C7 DEEP TRACEABILITY MATRIX)

Mọi bài học generated phải xuất được bảng ma trận truy xuất Markdown trong phần `INTERNAL QA & METADATA (C7)` theo mẫu:

| Data Element in Story | Cognitive Operation ($C_1 \dots C_n$) | Question/Task in Mission | Required Evidence in Answer |
|---|---|---|---|
| Dữ kiện Story 1 | $C_1$: Nhận diện dữ kiện | Câu hỏi 1 | Bằng chứng thô E1 |
| Dữ kiện Story 2 | $C_2$: Phân tích mâu thuẫn | Câu hỏi 2 | Bằng chứng phân tích E2 |
| Dữ kiện Story 3 | $C_3$: Đánh giá nguyên nhân | Câu hỏi 3 | Bằng chứng nguyên nhân E3 |
| Dữ kiện Story 4 | $C_4$: Đề xuất giải pháp | Câu hỏi 4 | Giải pháp đề xuất E4 |

---

## 2. CANONICAL SKILL NECESSITY TESTS (C8.1 — C8.5)

5 bài kiểm tra tính cần thiết của từng thao tác nhận thức $C_1 \dots C_n$:

1. **TEST C8.1 — OPERATION C1 NECESSITY**: Thao tác $C_1$ có thực sự cần thiết để nhận diện dữ kiện Story hay không? (PASS/FAIL)
2. **TEST C8.2 — OPERATION C2 NECESSITY**: Thao tác $C_2$ có thực sự cần thiết để bóc tách mâu thuẫn Story hay không? (PASS/FAIL)
3. **TEST C8.3 — OPERATION C3 NECESSITY**: Thao tác $C_3$ có thực sự cần thiết để tìm nguyên nhân gốc rễ hay không? (PASS/FAIL)
4. **TEST C8.4 — OPERATION C4 NECESSITY**: Thao tác $C_4$ có thực sự mở rộng thành đề xuất giải pháp của học sinh hay không? (PASS/FAIL)
5. **TEST C8.5 — COGNITIVE CONTINUITY**: Chuỗi $C_1 \rightarrow C_2 \rightarrow C_3 \rightarrow C_4$ có liên tục và không bị đứt gãy hay nhảy vọt logic hay không? (PASS/FAIL)
