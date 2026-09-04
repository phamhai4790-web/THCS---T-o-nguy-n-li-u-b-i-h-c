# SYSTEM ARCHITECTURE — NOVASTARS v12.0

> **Module Identifier**: `01_CORE/SYSTEM_ARCHITECTURE.md`  
> **Role**: Kiến trúc Tổng thể Hệ thống & Quy tắc Tầng Sự thật (Source-of-Truth Precedence)  
> **Precedence Level**: Level 1 & Level 2 Master Specification  

---

## 1. TỔNG QUAN KIẾN TRÚC MỤC TIÊU

Hệ thống **Novastars Learning Material Engine v12.0** được thiết kế theo kiến trúc **Decoupled Modular Architecture** (Kiến trúc Mô-đun Tách biệt).

Mục tiêu cốt lõi của v12.0:
1. **Decoupling (Tách biệt hoàn toàn)**: Tách Master Prompt v11 monolith thành các specification độc lập.
2. **Selective Context Loading (Nạp context theo nhu cầu)**: Giảm từ ~15,200 tokens (v11) xuống ~3,800 tokens (v12) cho mỗi lần sinh bài bằng cách chỉ nạp đúng các module `REQUIRED`.
3. **One Generator + Many Role Specifications**: Chỉ giữ 1 Generator duy nhất có khả năng sinh cho mọi Role khi được nạp `ROLE_SPEC` tương ứng.
4. **Independent QA Agent**: QA là Agent độc lập có quyền `PASS/FAIL` và trả về `Repair Directive` bắt buộc.
5. **Zero Rule/Specification Duplication**: Loại bỏ 100% quy tắc trùng lặp. Mỗi quy tắc chỉ có DUY NHẤT một Nguồn Sự thật (Source of Truth).

---

## 2. THỨ BẬC NGUỒN SỰ THẬT (SOURCE-OF-TRUTH PRECEDENCE HIERARCHY)

Khi có bất kỳ mâu thuẫn hay nghi ngờ nào giữa các file/module trong quá trình thực thi, hệ thống tuân thủ tuyệt đối **Thứ bậc Ưu tiên 6 Tầng (Level 1..6)**:

```text
Level 1 — CANONICAL SPECIFICATION (Canonical Knowledge & Canonical Skill Ceiling)
   │
   ▼
Level 2 — GLOBAL RULES (40 Master System Rules + 4 Ranh giới SB, KC, SK, PD + Output Contract)
   │
   ▼
Level 3 — ROLE SPECIFICATION (Role Purpose, Persona, Voice & Cognitive Mission Framing)
   │
   ▼
Level 4 — TEMPLATE REGISTRY (Immutable Schema Fingerprints & Registered Template Families)
   │
   ▼
Level 5 — LESSON SPECIFICATION (Source Story & Situational Practice Data)
   │
   ▼
Level 6 — GENERATOR INTERPRETATION (Transient Draft Output Generation)
```

### Nguyên tắc Thực thi Thứ bậc:
- **Cấm Override cấp cao**: Module cấp thấp KHÔNG ĐƯỢC OVERRIDE specification cấp cao hơn.
- **Ranh giới Story (Level 5 vs Level 1 & 2)**: Source Story KHÔNG ĐƯỢC tự tạo thêm Kiến thức (Level 1), Kỹ năng (Level 1) hay Kết quả chưa xảy ra (Level 2).
- **Ranh giới Generator (Level 6 vs Level 4)**: Generator KHÔNG ĐƯỢC tự ý sửa Schema hay sáng tạo Dạng Template mới (Level 4).
- **Ranh giới QA**: QA Agent KHÔNG ĐƯỢC tự ý sửa Specification cấp cao để cho bài học `PASS`.
- **Giao thức Flag Conflict**: Nếu phát hiện xung đột giữa hai tầng, hệ thống dừng lại và phát tín hiệu `[FLAG CONFLICT]`, tuyệt đối cấm tự suy diễn.

---

## 3. CẤU TRÚC MÔ-ĐUN HỆ THỐNG

```text
NOVASTARS_LEARNING_MATERIAL_ENGINE_v12/
├── 00_ORCHESTRATOR/         # Điều phối luồng làm việc & nạp ngữ cảnh
│   └── ORCHESTRATOR.md
├── 01_CORE/                # Quy tắc cốt lõi & Hợp đồng đầu ra dùng chung
│   ├── SYSTEM_ARCHITECTURE.md
│   ├── GLOBAL_RULES.md
│   └── OUTPUT_CONTRACT.md
├── 02_AGENTS/              # Các tác tử thực thi chính
│   ├── GENERATOR_AGENT.md
│   └── QA_AGENT.md
├── 03_ROLE_REGISTRY/        # Định nghĩa các Role & Template Schemas
│   ├── ROLE_REGISTRY.md
│   ├── THAM_TU/
│   ├── KY_SU/
│   ├── BAC_SI/
│   ├── PHONG_VIEN/
│   └── GIAO_VIEN/
├── 04_QA_REGISTRY/          # Bộ tiêu chuẩn & Test suite kiểm định
│   ├── QA_MASTER.md
│   ├── TEMPLATE_QA.md
│   ├── STORY_BOUNDARY_QA.md
│   ├── KNOWLEDGE_SKILL_PRODUCT_QA.md
│   └── TRACEABILITY_QA.md
└── 05_LESSONS/             # Gói dữ liệu đầu vào của từng bài học
    ├── LESSON_9_11/
    └── LESSON_9_13/
```

---

## 4. QUY TẮC CHỐNG "MODULAR MONOLITH" (ANTI-DUPLICATION)

1. **Một Nguồn Sự Thật Duy Nhất**: Một quy tắc chỉ được định nghĩa tại file Canonical của nó. Các file khác chỉ được dẫn chiếu (`reference`), thừa kế (`inherit`), hoặc gọi (`invoke`).
2. **Không copy Global Rules vào Role Spec**: `ROLE_SPEC.md` của từng Role chỉ chứa điểm riêng của Role đó (Voice, Persona, Mission Framing). Cấm chép lại 40 Master Rules hay 4 Ranh giới.
3. **Không copy Template Schema vào Generator**: Schemas nằm 100% trong `TEMPLATE_TYPES.md` của từng Role. Generator chỉ nạp và Instantiate đúng Schema ID được chỉ định.
4. **Không copy QA Test vào Lesson Package**: `05_LESSONS` chỉ chứa dữ liệu bài học, 0% QA Test hay Rule.
