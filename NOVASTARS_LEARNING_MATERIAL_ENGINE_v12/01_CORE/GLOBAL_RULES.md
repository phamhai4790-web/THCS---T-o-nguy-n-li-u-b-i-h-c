# GLOBAL RULES — MASTER SYSTEM RULES v12.0

> **Module Identifier**: `01_CORE/GLOBAL_RULES.md`  
> **Role**: Tập hợp Quy tắc Hệ thống Cốt lõi (Master System Rules & Story-Learning Boundaries)  
> **Precedence Level**: Level 2 Master Specification  

---

## 1. BỐN RANH GIỚI BẤT BIẾN HỆ THỐNG (STORY-LEARNING BOUNDARIES)

```text
SOURCE STORY ≠ SOLUTION STORY.
STORY = OBSERVED / PROBLEM STATE & PRACTICE DATA.
CANONICAL CONTENT = KNOWLEDGE CEILING.
CANONICAL SKILL = COGNITIVE OPERATION CEILING.
MISSION = INVESTIGATION & PROPOSAL.
STUDENT = SOLVER / DESIGNER.
OUTPUT = PROPOSED / AFTER STATE.
```

### 1.1 SB — STORY STATE BOUNDARY (Observed Fact ≠ Proposed Action ≠ Outcome)
- **Mô tả**: Phân biệt rành mạch 3 trạng thái của câu chuyện:
  1. `OBSERVED STATE`: Những sự kiện đã xảy ra và có bằng chứng rõ ràng trong Story.
  2. `PROPOSED ACTION STATE`: Những hành động hoặc giải pháp mà học sinh được yêu cầu thiết kế ($C_4$).
  3. `OUTCOME STATE`: Kết quả sau khi áp dụng giải pháp.
- **Quy tắc bắt buộc**: Nếu Source Story chỉ mô tả vấn đề/bế tắc, Mission và Learning Answer **TUYỆT ĐỐI CẤM** viết Outcome chưa xảy ra như một sự kiện đã thành công.
- **Ví dụ vi phạm (FAIL)**: "Tuấn đã nhận lỗi với Nam và nhóm đã cùng nhau thống nhất..." (Outcome leakage).
- **Ví dụ chuẩn (PASS)**: "Tuấn nên trao đổi với Nam như thế nào để cùng hoàn thiện lập luận?" (Proposed Action).

### 1.2 KC — KNOWLEDGE-CONTENT BOUNDARY (Canonical Knowledge ≠ Story Data)
- **Mô tả**: Canonical Content (Explicit Knowledge Layer 1 & Canonical Skill Layer 2) là **trần kiến thức tối đa của bài học**.
- **Quy tắc bắt buộc**: Generator **TUYỆT ĐỐI CẤM** lấy các dữ kiện xuất hiện trong Story rồi tự suy diễn, nâng cấp thành một bộ tiêu chí, cẩm nang hay khung kiến thức học thuật mới chưa được dạy trong Canonical Content.
- **Ví dụ vi phạm (FAIL)**: Story có nhiều nguồn tin $\rightarrow$ Tự sinh thêm "3 tiêu chí đánh giá độ tin cậy nguồn tin" (khi Canonical Content không có bộ 3 tiêu chí này).

### 1.3 SK — SKILL BOUNDARY (Canonical Skill ≠ Story-specific Action)
- **Mô tả**: Story tạo Context cho tình huống, nhưng **KHÔNG tạo ra Skill mới**.
- **Quy tắc bắt buộc**: Generator **TUYỆT ĐỐI CẤM** biến một hành động tình huống cụ thể trong Story thành một kỹ năng/quy trình chuẩn mực mới nằm ngoài Skill Map $C_1 \dots C_n$.
- **Ví dụ vi phạm (FAIL)**: Story 9.13 mô tả "chụp thử tại công viên" $\rightarrow$ Tự sinh thêm "Quy trình khảo sát địa điểm 5 bước".

### 1.4 PD — PRODUCT BOUNDARY (Student Product → Canonical Skill → Explicit Knowledge)
- **Mô tả**: Chuỗi truy xuất sản phẩm học sinh.
- **Quy tắc bắt buộc**: Mọi sản phẩm yêu cầu học sinh nộp bắt buộc phải có đường truy xuất trọn vẹn: `STUDENT PRODUCT -> CANONICAL SKILL -> EXPLICIT KNOWLEDGE`.
- **Loại bỏ 100% Sản phẩm Mồ côi (Orphan Product)**: Cấm yêu cầu nộp sản phẩm không có cơ sở trong Canonical Specification.

---

## 2. BẢNG 40 MASTER SYSTEM RULES v12.0

| Mã Rule | Tên Quy tắc | Nội dung Bắt buộc & Điều khoản Thi hành |
|:---|:---|:---|
| **Rule 01** | `PIPELINE DIRECTION` | Sinh 1 chiều duy nhất từ Source Story Reconstruction đến Student Mission. Cấm suy ngược từ đáp án về Material. |
| **Rule 02** | `PART A / B BOUNDARY` | PART A 100% Student-Facing (0% metadata, 0% kết luận trước). PART B là Mô hình lời giải sư phạm cho Giáo viên. |
| **Rule 03** | `EVIDENCE PRECEDES INTERPRETATION` | Material CHỈ CUNG CẤP Raw Facts, Observations, Logs, Quotes. Cấm đưa diễn giải/kết luận sư phạm vào Material. |
| **Rule 04** | `CHARACTER BELIEF ≠ FACT` | Phát ngôn của nhân vật là Ý kiến Chủ quan Nhân vật, không phải Factual Evidence chứng minh sự thật. |
| **Rule 05** | `LEARNING TOOL ≠ CANONICAL SKILL` | Được xuất hiện tên Tiếng Việt của Learning Tool trong Part A; Ẩn hoàn toàn tên Canonical Skill thiết kế khỏi Part A. |
| **Rule 06** | `PROBLEM TO SOLVE` | Student Mission đặt ra vấn đề thực tế cần giải quyết, cấm khoanh vùng/tiết lộ trước Expected Discovery. |
| **Rule 07** | `TEMPLATE INVENTION BLOCK` | Cấm tự phát minh Dạng Template mới nằm ngoài Registry chính thức. |
| **Rule 08** | `SCHEMA MODIFICATION BLOCK` | Cấm tự thay đổi, thêm bớt trường thông tin hoặc sửa tiêu đề của Dạng Template đã chọn. |
| **Rule 09** | `ANTI-DEFAULT TYPE 1 BIAS` | Cấm mặc định chọn Dạng 1 cho mọi bài học khi chưa phân tích cấu trúc bằng chứng. |
| **Rule 10** | `OUTCOME LEAKAGE BLOCK` | Cấm rò rỉ kết quả tương lai chưa xảy ra trong Story thành dữ kiện hiện tại. |
| **Rule 11** | `KNOWLEDGE LEAKAGE BLOCK` | Cấm nâng chi tiết Story thành khung kiến thức học thuật chưa có trong Canonical Content. |
| **Rule 12** | `SKILL LEAKAGE BLOCK` | Cấm biến hành động tình huống trong Story thành quy trình kỹ năng mới ngoài Skill Map. |
| **Rule 13** | `PRODUCT LEAKAGE BLOCK` | Cấm yêu cầu nộp sản phẩm không có đường truy xuất trọn vẹn về Canonical Skill. |
| **Rule 14** | `DIVERSITY AS TIE-BREAKER` | Tính đa dạng dạng bài chỉ đóng vai trò phân định khi độ phù hợp cấu trúc bằng chứng ngang nhau. |
| **Rule 15** | `KNOWLEDGE CEILING ENFORCEMENT` | Canonical Content là trần kiến thức tối đa. Không nạp kiến thức chưa dạy. |
| **Rule 16** | `SKILL CEILING ENFORCEMENT` | Canonical Skill $C_1 \dots C_n$ là trần thao tác nhận thức tối đa. |
| **Rule 17** | `MISSION PROPOSED ACTION FRAMING` | Nhiệm vụ học sinh bắt buộc phải yêu cầu học sinh ĐỀ XUẤT hành động/giải pháp cho $C_4$. |
| **Rule 18** | `STUDENT AS SOLVER / DESIGNER` | Học sinh được định vị là người giải quyết vấn đề / nhà thiết kế giải pháp. |
| **Rule 19** | `VIETNAMESE PURITY & AGE FIT` | PART A & B tuyệt đối KHÔNG dùng từ Tiếng Anh hay mở ngoặc Tiếng Anh. Ngôn ngữ 100% Tiếng Việt thuần khiết. |
| **Rule 20** | `SCHEMA FINGERPRINT INVARIANCE` | Cấu trúc tiêu đề, tên trường và thứ tự trường của Dạng là Hợp đồng Bất biến. |
| **Rule 21** | `STRICT NO ENGLISH IN PART A/B` | Cấm dùng các thuật ngữ như "Case File", "Field Report", "Chat log"... trong phần Part A & Part B. |
| **Rule 22** | `RAW FACTS ONLY IN MATERIAL` | Nguyên liệu chỉ chứa dữ kiện thô, bằng chứng thực tế, ghi nhận hiện trường hoặc thoại trực tiếp. |
| **Rule 23** | `QUESTION-DRIVEN ROLE MISSION` | Nhiệm vụ nhập vai được dẫn dắt bởi câu hỏi hỏi gợi mở tự nhiên theo văn phong của Role. |
| **Rule 24** | `EXPECTED REASONING C1..C4 LOGIC` | Chuỗi suy luận Part B phải thể hiện đúng tiến trình nhận thức $C_1 \rightarrow C_2 \rightarrow C_3 \rightarrow C_4$. |
| **Rule 25** | `CONTROLLED ACCEPTABLE RANGE` | Khoảng đáp án mở Part B phải có tiêu chuẩn kiểm soát, cấm đáp án mở tràn lan không định hướng. |
| **Rule 26** | `EXPLICIT CONTENT IMMUTABILITY` | Kiến thức hiển ngôn (Layer 1) & Skill Specs (Layer 2) là Nguồn Sự Thật Bất Biến. |
| **Rule 27** | `EVIDENCE FRAMEWORK E1..E5 TRACE` | Khung 5 tiêu chí năng lực E1--E5 trong Part B phải truy ngược được về $C_1 \dots C_n$. |
| **Rule 28** | `DIAGNOSTIC ERROR MATRIX` | Bảng chẩn đoán Part B phải liệt kê đúng 4 lỗi thường gặp của học sinh và nguyên nhân gốc rễ. |
| **Rule 29** | `ROLE DETERMINES TEMPLATE FAMILY` | Role khóa cố định vào Template Family chính thức. Cấm dùng nhầm Family giữa các Role. |
| **Rule 30** | `DYNAMIC TEMPLATE TYPE SELECTION` | Source Story + Canonical Skill quyết định Dạng Template thông qua Fit Audit. |
| **Rule 31** | `DEEP TRACEABILITY MATRIX` | Phải xuất ma trận truy xuất chi tiết từ Story Data $\rightarrow C_1..C_n \rightarrow$ Mission $\rightarrow$ Evidence. |
| **Rule 32** | `METADATA PROVENANCE REQUIREMENT` | Mỗi bài sinh ra phải có khối Metadata Template Provenance C1 đầy đủ nguồn gốc. |
| **Rule 33** | `CANONICAL TEMPLATE NAMING` | Phải dùng đúng tên Dạng chính thức trong Registry, cấm tự đổi tên. |
| **Rule 34** | `OBJECTIVE QA LANGUAGE` | Ngôn ngữ QA phải khách quan, dựa trên bằng chứng kiểm thử, cấm từ tự bốc phét. |
| **Rule 35** | `SCHEMA FINGERPRINT CHECK` | Kiểm tra Schema Fingerprint trước khi duyệt PASS. Mọi sai lệch tiêu đề sẽ nhận nhãn FAIL. |
| **Rule 36** | `DEFAULT TYPE BIAS AUDIT` | Cảnh báo Bias nếu 1 Dạng chiếm quá 70% tỷ lệ sử dụng trong cùng một Family. |
| **Rule 37** | `STORY STATE BOUNDARY (SB)` | Observed Fact $\ne$ Proposed Action $\ne$ Outcome. Cấm rò rỉ kết quả chưa xảy ra. |
| **Rule 38** | `KNOWLEDGE-CONTENT BOUNDARY (KC)` | Canonical Knowledge $\ne$ Story Data. Cấm nâng chi tiết Story thành kiến thức mới. |
| **Rule 39** | `SKILL BOUNDARY (SK)` | Canonical Skill $\ne$ Story Action. Story không tự tạo Skill mới ngoài Skill Map. |
| **Rule 40** | `PRODUCT BOUNDARY (PD)` | Student Product $\rightarrow$ Canonical Skill $\rightarrow$ Canonical Knowledge. Cấm sản phẩm mồ côi. |
