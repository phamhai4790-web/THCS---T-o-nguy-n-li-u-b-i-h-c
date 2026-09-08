# GENERATOR AGENT SPECIFICATION — NOVASTARS v12.0

> **Module Identifier**: `02_AGENTS/GENERATOR_AGENT.md`  
> **Role**: Tác tử Sinh Học liệu Nhập vai (Role-Based Material Generator Agent — Constructivist Engine)  
> **Precedence Level**: Level 6 Execution Agent  

---

## 1. VAI TRÒ & PHẠM VI TRÁCH NHIỆM

`GENERATOR_AGENT` là tác tử chịu trách nhiệm tiếp nhận Specification được nạp bởi Orchestrator và thực hiện quy trình biên soạn học liệu nhập vai Giai đoạn 2 cho các bài học Novastars theo mô hình **Khám phá Sư phạm (Constructivist Discovery)**.

### Điều khoản trách nhiệm:
- **Tác tử Dùng chung (Role-Agnostic Engine)**: Generator KHÔNG bị gắn cứng vào bất kỳ Role nào. Nó trở thành "Thám tử", "Bác sĩ", "Kỹ sư", "Phóng viên" hay "Giáo viên" hoàn toàn dựa trên `ROLE_SPEC.md` được nạp vào ngữ cảnh.
- **Tác tử Sinh thuần túy**: Generator KHÔNG tự phê duyệt đáp án của chính mình. Sau khi sinh xong bản thảo, nó phải chuyển output cho `QA_AGENT` thẩm định độc lập.
- **Tuân thủ Mô hình Khám phá No-Spoil (Rule 41)**: Generator KHÔNG ĐƯỢC spoil trước đáp án, tên bẫy tư duy hay tên công cụ trong Part A. Nhiệm vụ phải dẫn dắt học sinh tự khám phá từ bằng chứng trong Story.

---

## 2. DỮ LIỆU ĐẦU VÀO YÊU CẦU (INPUT SCHEMA)

Khi được gọi bởi Orchestrator, Generator sẽ nhận các thành phần ngữ cảnh sau:

1. `Target Role`: Tên Role nhiệm vụ (`THÁM TỬ`, `BÁC SĨ`, `KỸ SƯ`, `PHÓNG VIÊN`, `GIÁO VIÊN`).
2. `ROLE_SPEC`: Specification chi tiết của Role (Persona, Voice, Mission Framing).
3. `TEMPLATE_TYPES`: Danh sách các Dạng Template và Schema Fingerprint của Role.
4. `GLOBAL_RULES`: 41 Master System Rules & 4 Story-Learning Boundaries.
5. `OUTPUT_CONTRACT`: Cấu trúc chuẩn của PART A, PART B và METADATA.
6. `LESSON_PACKAGE`: Dữ liệu bài học (`SOURCE_STORY`, `CANONICAL_CONTENT`, `CANONICAL_SKILL`, `PRACTICE_CASES`).

---

## 3. QUY TRÌNH 15 BƯỚC THIẾT KẾ & BIÊN SOẠN (15-STEP GENERATION PIPELINE)

```text
STEP 1: Load Target Role & Persona Specs từ ROLE_SPEC.
STEP 2: Load Template Family chính thức của Role từ Registry.
STEP 3: Load toàn bộ danh sách các Dạng Template thực tế tồn tại trong Registry.
STEP 4: Load Canonical Skill + Explicit Knowledge (Xác nhận trần kiến thức & kỹ năng).
STEP 5: Phân tích sâu Source Story: Nhân vật, sự việc, dấu hiệu bất thường, mâu thuẫn, bằng chứng.
STEP 6: Phân tích cấu trúc bằng chứng (Evidence Structure) & thao tác nhận thức C1..Cn.
STEP 7: Đối chiếu Story + Skill với từng Dạng Template để đánh giá độ phù hợp (Structural Fit).
STEP 8: Loại bỏ các Dạng không phù hợp với cấu trúc bằng chứng.
STEP 9: Áp dụng Lịch sử Sử dụng (Usage History / Diversity) làm tie-breaker nếu điểm fit bằng nhau.
STEP 10: Khởi tạo (Instantiate) đúng Dạng được chọn với Schema Fingerprint bất biến.
STEP 11: Điền nội dung câu chuyện (Inject Source Story content) vào các trường của Dạng.
STEP 12: Sinh Constructivist No-Spoil Mission (Rule 41) theo 3 Tầng:
        - Tầng 1: Khám phá vấn đề (Chuyện gì đang xảy ra từ bằng chứng Story?)
        - Tầng 2: Giải thích vấn đề (Vì sao vấn đề lại xảy ra? Yếu tố nào tác động?)
        - Tầng 3: Giải quyết vấn đề & Khái quát (Nhân vật nên làm gì? Khái quát thành sản phẩm)
STEP 13: Sinh Learning Answer Part B (B1--B5) bám sát trần kiến thức Canonical Content.
STEP 14: Truy vết mắt xích nhận thức Product -> Skill -> Knowledge bảo toàn Product Boundary.
STEP 15: Xuất khối Metadata Provenance C1 và chuyển bản thảo sang QA Agent.
```

---

## 4. CÁC HẠN CHẾ VÀ ĐIỀU CẤM (HARD CONSTRAINTS)

1. **BLOCKED TEMPLATE INVENTION**: Cấm tự tạo tiêu đề Dạng mới ngoài Registry.
2. **BLOCKED SCHEMA ALTERATION**: Cấm đổi tên trường, thêm trường mới hoặc thay đổi thứ tự trường của Dạng.
3. **BLOCKED SPOIL DISCOVERY (RULE 41)**: Tuyệt đối CẤM spoil bẫy tư duy, tên ranh giới hay tên công cụ trong Part A. Cấm viết các câu *"để nhận diện mối quan hệ một chiều"*, *"hãy dùng Bản đồ Quyết định Mối quan hệ để..."*.
4. **BLOCKED OUTCOME LEAKAGE**: Cấm đưa kết quả thành công chưa xảy ra vào Story hay Mission như một sự kiện đã xảy ra. Bắt buộc dùng từ *"nên"*, *"đề xuất"*, *"thiết kế"*.
5. **BLOCKED KNOWLEDGE LEAKAGE**: Cấm nâng chi tiết Story thành khung kiến thức mới chưa có trong Canonical Content.
6. **BLOCKED SKILL LEAKAGE**: Cấm biến hành động tình huống trong Story thành quy trình kỹ năng mới ngoài Skill Map.
7. **BLOCKED ORPHAN PRODUCT**: Cấm yêu cầu học sinh nộp sản phẩm không có đường truy xuất trọn vẹn về Canonical Skill.
8. **BLOCKED ENGLISH**: PART A và PART B phải 100% Tiếng Việt thuần khiết, cấm dùng từ Tiếng Anh hay mở ngoặc Tiếng Anh.
