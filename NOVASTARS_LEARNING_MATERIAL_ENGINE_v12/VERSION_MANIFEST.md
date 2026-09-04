# VERSION MANIFEST — MIGRATION FROM MASTER PROMPT v11.0 TO MODULAR ARCHITECTURE v12.0

> **System Name**: Novastars Learning Material Engine v12.0  
> **Source Document**: MASTER_PROMPT_ROLE_MATERIAL_GENERATOR_v11.0.md  
> **Architecture**: Decoupled Modular Specification Engine  
> **Migration Status**: 100% MIGRATED & VERIFIED  

---

## 1. MIGRATION SUMMARY & STATUS DEFINITIONS

- `[MIGRATED]`: Item relocated from v11.0 to its single canonical v12.0 Source of Truth file.
- `[VERIFIED]`: Item validated via Architecture QA (AQ1–AQ12) and Regression Tests (9.11 & 9.13).
- `[CONFLICT]`: Item had precedence or definition ambiguities (0 items).
- `[UNMAPPED]`: Item not assigned to a v12.0 module (0 items).
- `[DUPLICATED]`: Item copied redundantly across multiple files (0 items — reference only).
- `[INTENTIONALLY_DEPRECATED]`: Monolithic inline system prompt structure replaced by dynamic Orchestrator nạp context theo nhu cầu.

---

## 2. COMPONENT TRACEABILITY MATRIX

### 2.1 Core Architectural Principles & Boundaries

| v11.0 Component / Directive | v11.0 Source Section | v12.0 Canonical File | Status | Notes / Precedence Level |
|---|---|---|---|---|
| Master Architectural Principles | Sec 2 | `01_CORE/SYSTEM_ARCHITECTURE.md` | `[VERIFIED]` | Level 1 & Level 2 Precedence |
| Source-of-Truth Precedence Hierarchy | Feedback Mandate | `01_CORE/SYSTEM_ARCHITECTURE.md` | `[VERIFIED]` | Level 1..6 Hierarchy |
| Story State Boundary (SB) | Sec 3.1 & Rule 37 | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` | Level 2 Precedence |
| Knowledge-Content Boundary (KC) | Sec 3.2 & Rule 38 | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` | Level 2 Precedence |
| Skill Boundary (SK) | Sec 3.3 & Rule 39 | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` | Level 2 Precedence |
| Product Boundary (PD) | Sec 3.4 & Rule 40 | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` | Level 2 Precedence |
| Output Contract Schema | Sec 8 | `01_CORE/OUTPUT_CONTRACT.md` | `[VERIFIED]` | Level 2 Precedence |

---

### 2.2 40 Master System Rules Traceability

| Rule ID | v11.0 Rule Name | v11.0 Source Location | v12.0 Canonical File | Migration Status |
|---|---|---|---|---|
| Rule 01 | PIPELINE DIRECTION | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 02 | PART A / B BOUNDARY | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 03 | EVIDENCE PRECEDES INTERPRETATION | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 04 | CHARACTER BELIEF ≠ FACT | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 05 | LEARNING TOOL ≠ CANONICAL SKILL | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 06 | PROBLEM TO SOLVE | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 07 | TEMPLATE INVENTION BLOCK | Sec 2 Mandate | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 08 | SCHEMA MODIFICATION BLOCK | Sec 2 Mandate | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 09 | ANTI-DEFAULT TYPE 1 BIAS | Sec 2 Mandate | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 10 | OUTCOME LEAKAGE BLOCK | Sec 2 Mandate | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 11 | KNOWLEDGE LEAKAGE BLOCK | Sec 2 Mandate | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 12 | SKILL LEAKAGE BLOCK | Sec 2 Mandate | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 13 | PRODUCT LEAKAGE BLOCK | Sec 2 Mandate | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 14 | DIVERSITY AS TIE-BREAKER | Sec 2 Mandate | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 15 | KNOWLEDGE CEILING ENFORCEMENT | Sec 2 Mandate | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 16 | SKILL CEILING ENFORCEMENT | Sec 2 Mandate | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 17 | MISSION PROPOSED ACTION FRAMING | Sec 2 Mandate | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 18 | STUDENT AS SOLVER / DESIGNER | Sec 2 Mandate | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 19 | VIETNAMESE PURITY & AGE FIT | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 20 | SCHEMA FINGERPRINT INVARIANCE | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 21 | STRICT NO ENGLISH IN PART A/B | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 22 | RAW FACTS ONLY IN MATERIAL | Sec 1 Directive | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 23 | QUESTION-DRIVEN ROLE MISSION | Sec 5 Step 12 | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 24 | EXPECTED REASONING C1..C4 LOGIC | Sec 8 B2 | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 25 | CONTROLLED ACCEPTABLE RANGE | Sec 8 B3 | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 26 | EXPLICIT CONTENT IMMUTABILITY | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 27 | EVIDENCE FRAMEWORK E1..E5 TRACE | Sec 8 B4 | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 28 | DIAGNOSTIC ERROR MATRIX | Sec 8 B5 | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 29 | ROLE DETERMINES TEMPLATE FAMILY | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 30 | DYNAMIC TEMPLATE TYPE SELECTION | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 31 | DEEP TRACEABILITY MATRIX | Sec 8 C7 | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 32 | METADATA PROVENANCE REQUIREMENT | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 33 | CANONICAL TEMPLATE NAMING | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 34 | OBJECTIVE QA LANGUAGE | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 35 | SCHEMA FINGERPRINT CHECK | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 36 | DEFAULT TYPE BIAS AUDIT | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 37 | STORY STATE BOUNDARY (SB) | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 38 | KNOWLEDGE-CONTENT BOUNDARY (KC) | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 39 | SKILL BOUNDARY (SK) | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |
| Rule 40 | PRODUCT BOUNDARY (PD) | Sec 6 Table | `01_CORE/GLOBAL_RULES.md` | `[VERIFIED]` |

---

### 2.3 41 QA Tests Traceability

| QA Test Range | Description | v11.0 Source Section | v12.0 Canonical File | Status |
|---|---|---|---|---|
| TF1 – TF16 | Template Selection & Schema Tests (16 Tests) | Sec 7.A | `04_QA_REGISTRY/TEMPLATE_QA.md` | `[VERIFIED]` |
| SB1 – SB5 | Story State Boundary Tests (5 Tests) | Sec 7.B | `04_QA_REGISTRY/STORY_BOUNDARY_QA.md` | `[VERIFIED]` |
| KC1 – KC3 | Knowledge-Content Boundary Tests (3 Tests) | Sec 7.C | `04_QA_REGISTRY/KNOWLEDGE_SKILL_PRODUCT_QA.md` | `[VERIFIED]` |
| SK1 – SK2 | Skill Boundary Tests (2 Tests) | Sec 7.D | `04_QA_REGISTRY/KNOWLEDGE_SKILL_PRODUCT_QA.md` | `[VERIFIED]` |
| PD1 – PD2 | Product Boundary Tests (2 Tests) | Sec 7.E | `04_QA_REGISTRY/KNOWLEDGE_SKILL_PRODUCT_QA.md` | `[VERIFIED]` |
| M1 – M8 | Mission Naturalness & Role Voice Tests (8 Tests) | Sec 8 C6 | `04_QA_REGISTRY/QA_MASTER.md` | `[VERIFIED]` |
| C8.1 – C8.5 | Canonical Skill Necessity Tests (5 Tests) | Sec 8 C8 | `04_QA_REGISTRY/TRACEABILITY_QA.md` | `[VERIFIED]` |

---

### 2.4 Roles & Template Schemas Traceability

| Role Name | Family Code | Template Types Count | v12.0 Role File Path | Status |
|---|---|---|---|---|
| **THÁM TỬ** | `#TEMPLATE-TT-NOVA` | 4 Dạng (Case File, SOS Letter, Diary, Chat Log) | `03_ROLE_REGISTRY/THAM_TU/` | `[VERIFIED]` |
| **BÁC SĨ** | `#TEMPLATE-CB-NOVA` | 3 Dạng (Bệnh án, Thư tư vấn, Nhật ký sinh hiệu) | `03_ROLE_REGISTRY/BAC_SI/` | `[VERIFIED]` |
| **KỸ SƯ** | `#TEMPLATE-KS-NOVA` | 3 Dạng (Phản hồi KH, Incident Report, Bản vẽ sơ đồ) | `03_ROLE_REGISTRY/KY_SU/` | `[VERIFIED]` |
| **PHÓNG VIÊN** | `#TEMPLATE-PV-NOVA` | 5 Dạng (Field Report, Chat Log, Diary, Social Post, Witness) | `03_ROLE_REGISTRY/PHONG_VIEN/` | `[VERIFIED]` |
| **GIÁO VIÊN** | `#TEMPLATE-GV-NOVA` | 6 Dạng (Hồ sơ HS, Camera, Thư ẩn danh, Email PH, TB Khẩn, Chat Group) | `03_ROLE_REGISTRY/GIAO_VIEN/` | `[VERIFIED]` |

---

### 2.5 System Orchestration & Agents

| Component | Purpose | v12.0 Canonical File | Status |
|---|---|---|---|
| System Orchestrator | Workflow execution 1..12, dynamic context loader, repair loop | `00_ORCHESTRATOR/ORCHESTRATOR.md` | `[VERIFIED]` |
| Generator Agent | Role-agnostic material synthesis logic | `02_AGENTS/GENERATOR_AGENT.md` | `[VERIFIED]` |
| QA Agent | Independent validation agent with PASS/FAIL authority & repair feedback | `02_AGENTS/QA_AGENT.md` | `[VERIFIED]` |
| Master QA Suite | Execution framework, dynamic trigger matrix, aggregated verdict | `04_QA_REGISTRY/QA_MASTER.md` | `[VERIFIED]` |
| Architecture QA | AQ1–AQ12 System modularity & decoupling validation | `04_QA_REGISTRY/QA_MASTER.md` | `[VERIFIED]` |
