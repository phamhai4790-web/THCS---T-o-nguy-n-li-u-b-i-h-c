# OUTPUT CONTRACT SPECIFICATION — NOVASTARS v12.0

> **Module Identifier**: `01_CORE/OUTPUT_CONTRACT.md`  
> **Role**: Hợp đồng Cấu trúc Đầu ra Chuẩn (Output Structure Contract)  
> **Precedence Level**: Level 2 Master Specification  

---

## 1. TỔNG QUAN OUTPUT CONTRACT v12.0

Mọi bài học được tạo ra bởi `GENERATOR_AGENT` và phê duyệt bởi `QA_AGENT` bắt buộc phải tuân thủ 100% cấu trúc đầu ra gồm 3 phần độc lập:

1. **PART A — ĐỀ BÀI / NHIỆM VỤ HỌC SINH**: 100% Student-Facing, thuần Việt hoàn toàn, 0% metadata, 0% đáp án trước.
2. **PART B — MÔ HÌNH LỜI GIẢI SƯ PHẠM**: Dành cho Giáo viên, chứa chuỗi suy luận logic $C_1 \dots C_n$, khung đánh giá E1--E5 và bảng chẩn đoán lỗi.
3. **INTERNAL QA & METADATA**: Dành cho Hệ thống & Kiểm định, chứa Metadata Provenance C1, Rationale C2, Traceability Matrix C7 và Kết quả Thẩm định C9.

---

## 2. CHUẨN CẤU TRÚC KÊU GỌI (OUTPUT SCHEMA TEMPLATE)

```markdown
# PART A — ĐỀ BÀI / NHIỆM VỤ HỌC SINH

## 1. Vai trò
[Định vị vai trò nhập vai tự nhiên theo Role Specification]

## 2. Nhiệm vụ
[Tóm tắt nhiệm vụ học sinh cần giải quyết trong Tiết 1]

## 3. Nguyên liệu
[Instantiate đúng 100% Schema Fingerprint của Dạng Template được chọn từ Registry. Ngôn ngữ 100% Tiếng Việt Thuần Khiết]

## 4. Nhiệm vụ [Hội chẩn / Điều tra / Chẩn đoán / Biên tập / Kỹ thuật]
[Question-Driven Mission với văn phong nhập vai tự nhiên, định hình thao tác C4 dưới dạng PROPOSED ACTION của Học sinh]

## 5. Sản phẩm cần nộp
[Danh sách sản phẩm học sinh nộp có đường truy xuất 100% về Canonical Skill. CẤM sản phẩm mồ côi]

## 6. Lưu ý
[Các lưu ý thực thi quan trọng dành cho học sinh]

---

# PART B — LEARNING ANSWER

## B1. Expected Discovery
[Phát hiện bắt buộc học sinh cần rút ra, bám sát C1 -> C4, coi C4 là giải pháp đề xuất]

## B2. Expected Reasoning
[Chuỗi suy luận logic chi tiết từng bước: C1 -> C2 -> C3 -> C4]

## B3. Acceptable Solution Range
[Khoảng đáp án mở có kiểm soát, chấp nhận sự đa dạng thể hiện của học sinh nhưng nằm trong ranh giới sư phạm]

## B4. Required Evidence Framework
[Khung 5 tiêu chí đánh giá năng lực E1 -- E5 truy xuất trực tiếp từ C1 -- C4]

## B5. Diagnostic Error Matrix
[Bảng chẩn đoán 4 lỗi thường gặp của học sinh, biểu hiện và nguyên nhân gốc rễ]

---

# INTERNAL QA & METADATA

## C1. Template Provenance Metadata
- **Template Family:** [Tên Family, ví dụ: #TEMPLATE-TT-NOVA]
- **Template Type:** [Tên Dạng chính thức từ Registry]
- **Template Registry ID:** [Mã ID, ví dụ: REG-TT-01]
- **Template Version:** 12.0
- **Schema Version:** 12.0
- **Selection Reason:** [Giải trình căn cứ cấu trúc bằng chứng]
- **Canonical Skill:** [Tên Tiếng Việt của Canonical Skill]
- **Source Story ID:** [Mã bài học / Story ID]

## C2. Template Type Selection Rationale
[Phân tích chi tiết Evidence Structure Fit giữa Story, Skill và Dạng Template]

## C3. Canonical Skill Execution Mapping
[Ma trận ánh xạ từ Explicit Knowledge Layer 1 & Skill Specs Layer 2 sang C1..C4]

## C4. Structural Template Fidelity & Schema Fingerprint Audit
[Kết quả kiểm thử 16 Tests TF1 -- TF16]

## C5. Story-Learning Boundary Audit
[Kết quả kiểm thử các ranh giới: SB1--SB5, KC1--KC3, SK1--SK2, PD1--PD2]

## C6. Mission Naturalness & Role Voice Audit
[Kết quả kiểm thử 8 Tests M1 -- M8 về văn phong nhập vai và tính tự nhiên]

## C7. Deep Traceability Matrix
[Bảng Markdown truy xuất sâu từ Source Story Data -> C1..C4 -> Student Mission -> Required Evidence]

## C8. Canonical Skill Necessity Test
[Kết quả 5/5 bài kiểm tra tính cần thiết của Canonical Skill]

## C9. Lesson-Level QA Verdict
[Kết luận phê duyệt: PASS / CONDITIONAL PASS — GOLDEN SAMPLE CANDIDATE v12.0]
```
