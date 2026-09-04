# SYSTEM ORCHESTRATOR — NOVASTARS v12.0

> **Module Identifier**: `00_ORCHESTRATOR/ORCHESTRATOR.md`  
> **Role**: Bộ Điều phối Trung tâm Hệ thống (Master System Orchestrator)  
> **Precedence Level**: System Execution Control  

---

## 1. VAI TRÒ & NGUYÊN TẮC ĐIỀU PHỐI

Orchestrator là bộ điều hành duy nhất quản lý vòng đời sinh học liệu và kiểm định chất lượng của Novastars.

### Nguyên tắc bất biến:
1. **Không chứa quy tắc nghiệp vụ**: Orchestrator KHÔNG tự phát minh Rule, Template hay QA Test. Nó chỉ điều phối dữ liệu từ `01_CORE`, `03_ROLE_REGISTRY`, `04_QA_REGISTRY` và `05_LESSONS`.
2. **Selective Context Loading**: Orchestrator chỉ nạp đúng các module `REQUIRED` cho nhiệm vụ hiện tại (phụ thuộc vào Role, Template và Lesson), tuyệt đối KHÔNG nạp toàn bộ hệ thống.
3. **Phân tách tạo - kiểm**: Orchestrator gọi `GENERATOR_AGENT` để sinh bản thảo, sau đó bắt buộc gọi `QA_AGENT` để kiểm định độc lập. Generator KHÔNG được tự phê duyệt output.
4. **Bắt buộc vòng lặp sửa lỗi (Repair Loop)**: Nếu `QA_AGENT` trả về `FAIL`, Orchestrator truyền phản hồi sửa lỗi chi tiết cho Generator sửa lại cho đến khi đạt `PASS`.

---

## 2. QUY TRÌNH ĐIỀU PHỐI 12 BƯỚC (12-STEP EXECUTION WORKFLOW)

```text
[BƯỚC 1: Tiếp nhận Lesson ID] ──> [BƯỚC 2: Xác định Role & Lesson Spec]
                                          │
                                          ▼
                               [BƯỚC 3: Tra cứu Dynamic Manifest]
                                          │
                                          ▼
                               [BƯỚC 4: Selective Context Load]
                                          │
                                          ▼
                               [BƯỚC 5: Gọi Generator Agent]
                                          │
                                          ▼
                               [BƯỚC 6: Tạo Draft Output (Part A, B, Metadata)]
                                          │
                                          ▼
                               [BƯỚC 7: Nạp QA Registry Suite phù hợp]
                                          │
                                          ▼
                               [BƯỚC 8: Gọi QA Agent Kiểm định Độc lập]
                                          │
                                ┌─────────┴─────────┐
                                ▼                   ▼
                             [PASS]              [FAIL]
                                │                   │
                                │         [BƯỚC 9: Tạo Repair Directive]
                                │                   │
                                │         [BƯỚC 10: Generator Sửa lại]
                                │                   │
                                │         [BƯỚC 11: QA Re-Audit Loop]
                                │                   │
                                └─────────┬─────────┘
                                          │
                                          ▼
                               [BƯỚC 12: Xuất bản Final Output]
```

### Chi tiết các bước:

- **BƯỚC 1 — Tiếp nhận Yêu cầu Bài học**: Tiếp nhận `LESSON_ID` (Ví dụ: `LESSON_9_11` hoặc `LESSON_9_13`).
- **BƯỚC 2 — Xác định Role & File Bài học**: Xác định Role của bài học (`THÁM TỬ`, `BÁC SĨ`, `KỸ SƯ`, `PHÓNG VIÊN`, `GIÁO VIÊN`) từ `05_LESSONS/<LESSON_ID>/INPUT_SPEC.md`.
- **BƯỚC 3 — Tra cứu Dynamic Module Manifest**: Tra cứu bảng Module Manifest để xác định các file `REQUIRED`.
- **BƯỚC 4 — Selective Context Loading**: Nạp vào Context chỉ bao gồm các file:
  - `01_CORE/GLOBAL_RULES.md`
  - `01_CORE/OUTPUT_CONTRACT.md`
  - `03_ROLE_REGISTRY/<ROLE>/ROLE_SPEC.md`
  - `03_ROLE_REGISTRY/<ROLE>/TEMPLATE_TYPES.md`
  - `05_LESSONS/<LESSON_ID>/` (`SOURCE_STORY.md`, `CANONICAL_CONTENT.md`, `CANONICAL_SKILL.md`, `PRACTICE_CASES.md`)
- **BƯỚC 5 — Gọi Generator Agent**: Chuyển context đã nạp sang `GENERATOR_AGENT.md` thực thi quy trình 15 bước thiết kế.
- **BƯỚC 6 — Tiếp nhận Bản thảo (Draft Output)**: Thu nhận Part A, Part B và Metadata ban đầu từ Generator.
- **BƯỚC 7 — Nạp QA Suite Tương ứng**: Nạp `02_AGENTS/QA_AGENT.md` cùng các bộ QA test liên quan từ `04_QA_REGISTRY/`.
- **BƯỚC 8 — QA Agent Thẩm định Độc lập**: `QA_AGENT` chấm điểm độc lập dựa trên 41 QA Tests (TF, SB, KC, SK, PD, M, C8).
- **BƯỚC 9 — Phân nhánh Kết quả**:
  - Nếu **PASS**: Chuyển thẳng sang BƯỚC 12.
  - Nếu **FAIL**: Trích xuất `Repair Directive` (Mã QA Test thất bại, bằng chứng vi phạm, Rule vi phạm, chỉ thị sửa đổi).
- **BƯỚC 10 — Vòng lặp Sửa lỗi (Repair Loop)**: Yêu cầu Generator sửa lại đúng các phần bị vi phạm theo `Repair Directive`.
- **BƯỚC 11 — Tái Kiểm định (Re-Audit)**: Gửi lại bản thảo đã sửa cho `QA_AGENT` kiểm tra lại. Vòng lặp tối đa 3 lần.
- **BƯỚC 12 — Phê duyệt & Xuất bản (Publish)**: Ghi nhận trạng thái `GOLDEN SAMPLE v12.0` và xuất bản học liệu hoàn chỉnh.

---

## 3. DYNAMIC CONTEXT LOAD MANIFEST TABLE

Khi thực thi một nhiệm vụ cụ thể, Orchestrator áp dụng quy tắc nạp ngữ cảnh tối ưu sau:

| Task Target Role | Module Required (Load 100%) | Module Excluded (0% Load) |
|---|---|---|
| **THÁM TỬ** | `GLOBAL_RULES`, `OUTPUT_CONTRACT`, `THAM_TU/*`, Target Lesson Package | `KY_SU/*`, `BAC_SI/*`, `PHONG_VIEN/*`, `GIAO_VIEN/*` |
| **BÁC SĨ** | `GLOBAL_RULES`, `OUTPUT_CONTRACT`, `BAC_SI/*`, Target Lesson Package | `THAM_TU/*`, `KY_SU/*`, `PHONG_VIEN/*`, `GIAO_VIEN/*` |
| **KỸ SƯ** | `GLOBAL_RULES`, `OUTPUT_CONTRACT`, `KY_SU/*`, Target Lesson Package | `THAM_TU/*`, `BAC_SI/*`, `PHONG_VIEN/*`, `GIAO_VIEN/*` |
| **PHÓNG VIÊN** | `GLOBAL_RULES`, `OUTPUT_CONTRACT`, `PHONG_VIEN/*`, Target Lesson Package | `THAM_TU/*`, `BAC_SI/*`, `KY_SU/*`, `GIAO_VIEN/*` |
| **GIÁO VIÊN** | `GLOBAL_RULES`, `OUTPUT_CONTRACT`, `GIAO_VIEN/*`, Target Lesson Package | `THAM_TU/*`, `BAC_SI/*`, `KY_SU/*`, `PHONG_VIEN/*` |

---

## 4. QUY TRÌNH XỬ LÝ XUNG ĐỘT (CONFLICT PROTOCOL)

Nếu trong quá trình nạp context hoặc thực thi phát hiện bất kỳ mâu thuẫn nào giữa các tầng (Ví dụ: Source Story yêu cầu một hành động trái với Canonical Skill Ceiling Level 1):

1. **Dừng quy trình sinh tức thì**.
2. **Xuất báo cáo xung đột**:
   ```markdown
   [FLAG CONFLICT DETECTED]
   - Level Higher: [Tên File & Level, ví dụ Level 1 Canonical Skill]
   - Level Lower: [Tên File & Level, ví dụ Level 5 Source Story]
   - Detail: [Mô tả chi tiết điểm mâu thuẫn]
   - Action: Cấm tự suy diễn để giải quyết. Yêu cầu sửa dữ liệu đầu vào.
   ```
3. **Đánh nhãn bài học**: `STATUS: CONFLICT_BLOCKED`.
