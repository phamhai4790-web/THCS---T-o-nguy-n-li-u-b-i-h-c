# STORY STATE BOUNDARY QA SUITE — SB1 TO SB5

> **Module Identifier**: `04_QA_REGISTRY/STORY_BOUNDARY_QA.md`  
> **Role**: Bộ Thẩm định Ranh giới Trạng thái Câu chuyện & Chống Outcome Leakage (SB1 -- SB5)  
> **Precedence Level**: Level 2 Quality Control Suite  

---

## 1. DANH SÁCH 5 STORY STATE BOUNDARY TESTS (SB1 — SB5)

1. **TEST SB1 — STORY STATE BOUNDARY**: Phân biệt rõ `OBSERVED STATE` và `PROPOSED STATE`. Dùng từ định hình: *"nên"*, *"đề xuất"*, *"thiết kế"*. (PASS/FAIL)
2. **TEST SB2 — EVIDENCE AVAILABILITY**: Mọi câu hỏi đều truy xuất 100% từ dữ kiện Story. Cấm hỏi kết quả chưa xảy ra. (PASS/FAIL)
3. **TEST SB3 — ACTION OWNERSHIP**: Phân biệt `STORY ACTION` (hành động đã có) và `STUDENT ACTION` (hành động đề xuất của học sinh $C_4$). (PASS/FAIL)
4. **TEST SB4 — OUTCOME LEAK**: Part A, Part B không rò rỉ kết quả tương lai thành công chưa xảy ra trong Story thành sự kiện hiện tại. (PASS/FAIL)
5. **TEST SB5 — C4 ACTION GENERATION**: Thao tác $C_4$ là sản phẩm đề xuất tư duy do học sinh tạo ra. (PASS/FAIL)

---

## 2. QUY TRÌNH KIỂM NGHỆM SB4 (OUTCOME LEAK DETECTOR)

```text
Kiểm tra từng câu văn trong Part A (Mục 4 Mission) & Part B (B1 Expected Discovery):
├── NẾU phát hiện câu mô tả kết quả thành công chưa xuất hiện trong Story như một sự kiện đã xảy ra:
│   └── VERDICT: FAIL SB4 (Outcome Leakage Detected)
└── NẾU toàn bộ yêu cầu hành động C4 được diễn đạt dưới dạng ĐỀ XUẤT HÀNH ĐỘNG ("Tuấn nên...", "Học sinh thiết kế..."):
    └── VERDICT: PASS SB4
```
