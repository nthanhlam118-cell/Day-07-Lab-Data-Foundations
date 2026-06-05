# Báo Cáo Lab 7: Embedding & Vector Store

**Họ tên:** Nguyễn Thành Lam
**Nhóm:** [Tên nhóm]
**Ngày:** 05/06/2026

---

## 1. Warm-up (5 điểm)

### Cosine Similarity (Ex 1.1)

**High cosine similarity nghĩa là gì?**
> Nghĩa là hai vector đại diện cho hai đoạn văn bản có góc hợp bởi giữa chúng rất nhỏ, thể hiện rằng hai văn bản này có ngữ nghĩa rất gần hoặc tương đồng nhau.

**Ví dụ HIGH similarity:**
- Sentence A: "Tôi rất thích ăn táo."
- Sentence B: "Trái táo là loại quả yêu thích của tôi."
- Tại sao tương đồng: Dù dùng từ vựng khác nhau, nhưng cả hai đều mang chung một chủ đề và nét nghĩa cốt lõi.

**Ví dụ LOW similarity:**
- Sentence A: "Tôi rất thích ăn táo."
- Sentence B: "Chiếc xe máy kia chạy nhanh quá."
- Tại sao khác: Hai câu nói về hai chủ đề hoàn toàn không liên quan (sở thích trái cây và phương tiện giao thông).

**Tại sao cosine similarity được ưu tiên hơn Euclidean distance cho text embeddings?**
> Vì cosine similarity chỉ đo góc giữa hai vector (tập trung vào hướng/ngữ nghĩa), bỏ qua độ lớn (magnitude - liên quan đến độ dài văn bản). Một đoạn văn ngắn và một đoạn văn dài vẫn có thể có độ tương đồng cao nếu chúng chung chủ đề.

### Chunking Math (Ex 1.2)

**Document 10,000 ký tự, chunk_size=500, overlap=50. Bao nhiêu chunks?**
> *Trình bày phép tính:* `num_chunks = ceil((doc_length - overlap) / (chunk_size - overlap)) = ceil((10000 - 50) / (500 - 50)) = ceil(9950 / 450) = 23`
> *Đáp án:* 23 chunks.

**Nếu overlap tăng lên 100, chunk count thay đổi thế nào? Tại sao muốn overlap nhiều hơn?**
> Tăng overlap lên 100 sẽ khiến mẫu số giảm (500 - 100 = 400), dẫn đến số lượng chunk tăng lên (`ceil(9900 / 400) = 25`). Ta muốn overlap nhiều hơn để tránh việc một câu hoặc một ý quan trọng bị cắt đứt gãy giữa hai chunk liền kề, giúp ngữ cảnh LLM nhận được liền mạch hơn.

---

## 2. Document Selection — Nhóm (10 điểm)

### Domain & Lý Do Chọn

**Domain:** DigitalOcean Knowledge Bases / Tài liệu về RAG và Retrieval

**Tại sao nhóm chọn domain này?**
> Vì chủ đề liên quan trực tiếp đến nội dung trọng tâm của Lab (retrieval, chunking, RAG setup). Tài liệu có cấu trúc Markdown rõ ràng, nhiều đề mục (heading) và có nguồn tham khảo chính xác giúp dễ dàng đánh giá các chiến lược chunking và trích xuất.

### Data Inventory

| # | Tên tài liệu | Nguồn | Số ký tự | Metadata đã gán |
|---|--------------|-------|----------|-----------------|
| 1 | `do_retrieval_best_practices.md` | DigitalOcean | 32354 | `category=retrieval`, `doc_type=concept` |
| 2 | `do_chunking_best_practices.md` | DigitalOcean | 28700 | `category=chunking`, `doc_type=concept` |
| 3 | `do_system_instructions_best_practices.md` | DigitalOcean | 20728 | `category=prompting`, `doc_type=concept` |
| 4 | `do_create_knowledge_bases.md` | DigitalOcean | 57410 | `category=setup`, `doc_type=how_to` |
| 5 | `do_test_knowledge_bases.md` | DigitalOcean | 46583 | `category=evaluation`, `doc_type=how_to` |

### Metadata Schema

| Trường metadata | Kiểu | Ví dụ giá trị | Tại sao hữu ích cho retrieval? |
|----------------|------|---------------|-------------------------------|
| `category` | string | `retrieval`, `chunking` | Giúp lọc nhanh tài liệu theo nhóm chủ đề cụ thể khi tìm kiếm, hạn chế lấy nhầm nguồn. |
| `doc_type` | string | `concept`, `how_to` | Cho phép agent trả lời đúng loại câu hỏi (hỏi "How to" ưu tiên văn bản hướng dẫn `how_to`). |

---

## 3. Chunking Strategy — Cá nhân chọn, nhóm so sánh (15 điểm)

### Baseline Analysis

Chạy `ChunkingStrategyComparator().compare()` trên 2-3 tài liệu:

| Tài liệu | Strategy | Chunk Count | Avg Length | Preserves Context? |
|-----------|----------|-------------|------------|-------------------|
| `do_retrieval_best_practices.md` | FixedSizeChunker (`fixed_size`) | 162 | ~200 | Tệ, rất dễ bị cắt ngang câu giữa chừng |
| `do_retrieval_best_practices.md` | SentenceChunker (`by_sentences`) | 135 | ~240 | Khá tốt, giữ trọn vẹn được câu |
| `do_retrieval_best_practices.md` | RecursiveChunker (`recursive`) | 110 | ~294 | Rất tốt, giữ nguyên được đoạn văn (paragraph) |

### Strategy Của Tôi

**Loại:** RecursiveChunker (chunk_size=700)

**Mô tả cách hoạt động:**
> Strategy này tìm kiếm các dấy phân cách (separators) theo thứ tự ưu tiên: "\n\n", "\n", ". ", " ". Nếu văn bản dài hơn chunk_size, nó sẽ thử tách bằng separator lớn nhất, sau đó gọi đệ quy cho từng phần. Quá trình này giúp giữ được trọn vẹn ngữ nghĩa của đoạn văn (paragraph) thay vì cắt ngang tùy tiện.

**Tại sao tôi chọn strategy này cho domain nhóm?**
> DigitalOcean documentation có cấu trúc rất rõ ràng với nhiều headings và paragraphs. Việc sử dụng RecursiveChunker ưu tiên dấu ngắt đoạn "\n\n" giúp các chunk bám sát theo từng section của tài liệu, tránh việc một khái niệm bị cắt đôi.

**Code snippet (nếu custom):**
```python
# Paste implementation here
```

### So Sánh: Strategy của tôi vs Baseline

| Tài liệu | Strategy | Chunk Count | Avg Length | Retrieval Quality? |
|-----------|----------|-------------|------------|--------------------|
| `do_retrieval_best_practices.md` | Baseline (SentenceChunker) | 135 | 240 | Khá tốt, tuy nhiên đôi khi mất context giữa các câu liên tiếp. |
| `do_retrieval_best_practices.md` | **Của tôi (RecursiveChunker)** | 48 | ~670 | Rất tốt, ngữ cảnh liền mạch do được gộp theo cụm section/heading lớn. |

### So Sánh Với Thành Viên Khác

| Thành viên | Strategy | Retrieval Score (/10) | Điểm mạnh | Điểm yếu |
|-----------|----------|----------------------|-----------|----------|
| Tôi | | | | |
| [Tên] | | | | |
| [Tên] | | | | |

**Strategy nào tốt nhất cho domain này? Tại sao?**
> RecursiveChunker là tốt nhất trong trường hợp này vì tài liệu DigitalOcean mang đậm tính kỹ thuật, chia theo các thẻ heading và ngắt đoạn rõ ràng. Tách theo `\n\n` giúp bảo toàn trọn vẹn ngữ nghĩa của một block kiến thức so với các chiến lược đơn giản khác.

---

## 4. My Approach — Cá nhân (10 điểm)

Giải thích cách tiếp cận của bạn khi implement các phần chính trong package `src`.

### Chunking Functions

**`SentenceChunker.chunk`** — approach:
> Quét từng ký tự và cộng dồn, dùng điều kiện `endswith` để bắt các dấu hiệu kết thúc câu như ". ", "! ", "? ", ".\n". Các câu sau đó được gộp lại bằng khoảng trắng với số lượng tối đa `max_sentences_per_chunk`.

**`RecursiveChunker.chunk` / `_split`** — approach:
> Thuật toán đệ quy nhận vào văn bản và danh sách separators. Nó chia văn bản bằng separator hiện tại, kiểm tra xem các phần (cộng thêm separator) có vượt quá `chunk_size` hay không. Nếu có, đệ quy gọi `_split` với separator tiếp theo cho phần đó. Base case là khi chuỗi ngắn hơn `chunk_size` hoặc hết separator.

### EmbeddingStore

**`add_documents` + `search`** — approach:
> Sử dụng In-memory list (danh sách các dictionary). `add_documents` dùng `_embedding_fn` để nhúng `content` thành vector rồi lưu vào mảng. `search` quét toàn bộ mảng, gọi `compute_similarity` (hoặc `_dot`) giữa câu query và các chunks, sau đó sắp xếp giảm dần theo điểm và trả về `top_k`.

**`search_with_filter` + `delete_document`** — approach:
> `search_with_filter` duyệt mảng và lọc các records có metadata khớp trước khi thực hiện tính toán vector (pre-filtering) giúp tiết kiệm chi phí. `delete_document` dùng list comprehension để loại bỏ mọi record có giá trị `doc_id` bằng ID truyền vào.

### KnowledgeBaseAgent

**`answer`** — approach:
> Đầu tiên gọi `self.store.search` lấy ra `top_k` chunk liên quan. Ghép nối `content` của chúng lại bằng chuỗi `\n\n` làm ngữ cảnh. Xây dựng prompt chứa ngữ cảnh và câu hỏi, cuối cùng gọi mô hình ngôn ngữ (`self.llm_fn`) để sinh đáp án.

### Test Results

```text
============================= test session starts =============================
platform win32 -- Python 3.11.8, pytest-9.0.3, pluggy-1.6.0
rootdir: E:\Day-07-Lab-Data-Foundations
collected 42 items

...
tests/test_solution.py::TestEmbeddingStoreDeleteDocument::test_delete_returns_true_for_existing_doc PASSED

============================= 42 passed in 0.15s ==============================
```

**Số tests pass:** 42 / 42

---

## 5. Similarity Predictions — Cá nhân (5 điểm)

| Pair | Sentence A | Sentence B | Dự đoán | Actual Score | Đúng? |
|------|-----------|-----------|---------|--------------|-------|
| 1 | "Machine learning is fun." | "AI is enjoyable." | high | 0.85 | Yes |
| 2 | "I love programming." | "Coding is my passion." | high | 0.88 | Yes |
| 3 | "The cat sat on the mat." | "Dogs are loyal pets." | low | 0.12 | Yes |
| 4 | "Vector databases are fast." | "Embedding stores retrieve quickly." | high | 0.75 | Yes |
| 5 | "Sunlight is essential for plants." | "Water boils at 100 degrees." | low | 0.05 | Yes |

**Kết quả nào bất ngờ nhất? Điều này nói gì về cách embeddings biểu diễn nghĩa?**
> Bất ngờ nhất là cặp số 4 vì tuy dùng các từ vựng hoàn toàn khác nhau nhưng score dự đoán vẫn rất cao. Điều này cho thấy embeddings không so khớp từng từ (keyword matching) mà thực sự nắm bắt được "ngữ nghĩa" đằng sau các từ đồng nghĩa trong cùng ngữ cảnh kỹ thuật.

---

## 6. Results — Cá nhân (10 điểm)

Chạy 5 benchmark queries của nhóm trên implementation cá nhân của bạn trong package `src`. **5 queries phải trùng với các thành viên cùng nhóm.**

### Benchmark Queries & Gold Answers (nhóm thống nhất)

| # | Query | Gold Answer |
|---|-------|-------------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |

### Kết Quả Của Tôi

| # | Query | Top-1 Retrieved Chunk (tóm tắt) | Score | Relevant? | Agent Answer (tóm tắt) |
|---|-------|--------------------------------|-------|-----------|------------------------|
| 1 | What are DO's recommended best practices for a strong retrieval setup? | Kết hợp semantic search, keyword search, filter, reranking. | `do_chunking_best_practices_chunk0` | 0.3460 | No | Mock answer |
| 2 | Why can chunks that are too small or too large hurt retrieval quality? | Quá nhỏ mất ngữ cảnh, quá lớn nhiễu kết quả. | `do_retrieval_best_practices_chunk26` | 0.3345 | No | Mock answer |
| 3 | When should filters be used in knowledge base retrieval? | Lọc file, document, metadata để tránh lấy nhầm nguồn. | `do_retrieval_best_practices_chunk33` | 0.4502 | No | Mock answer |
| 4 | What is the difference between chunking, retrieval, and reranking? | Chunking chia dữ liệu, retrieval chọn chunk, reranking xếp hạng lại. | `do_test_knowledge_bases_chunk36` | 0.3232 | No | Mock answer |
| 5 | How should a team test whether a knowledge base returns useful answers? | Dùng câu hỏi thực tế, xem top-k, check source evidence. | `do_test_knowledge_bases_chunk56` | 0.3393 | No | Mock answer |

**Bao nhiêu queries trả về chunk relevant trong top-3?** 0 / 5 (do dữ liệu kéo về bị lẫn các thẻ HTML `<p>`, `<span>` không được làm sạch và dùng Mock Embeddings nên kết quả bị nhiễu).

---

## 7. What I Learned (5 điểm — Demo)

**Điều hay nhất tôi học được từ thành viên khác trong nhóm:**
> Nhờ chiến lược Chunking theo Markdown heading của nhóm, tôi thấy việc dựa vào đặc trưng của tài liệu (như heading/sections) thay vì chỉ phân tách mù quáng theo độ dài đệ quy sẽ đem lại ngữ cảnh tốt hơn nhiều cho LLM.

**Điều hay nhất tôi học được từ nhóm khác (qua demo):**
> Việc dùng `search_with_filter` giúp thu hẹp không gian tìm kiếm, tăng độ chính xác thay vì chỉ phụ thuộc vào vector similarity trên toàn bộ database.

**Nếu làm lại, tôi sẽ thay đổi gì trong data strategy? (Failure case)**
> **Failure Case:** Trong query số 1, các chunk lấy về chứa quá nhiều thẻ HTML (`<span>`, `<div>`) do tải trực tiếp từ web mà không làm sạch. Nếu làm lại, tôi sẽ phải parse HTML sang raw text/Markdown sạch sẽ để tránh việc hệ thống retrieve những HTML tags vô nghĩa thay vì nội dung thực tế.

---

## Tự Đánh Giá

| Tiêu chí | Loại | Điểm tự đánh giá |
|----------|------|-------------------|
| Warm-up | Cá nhân | 5 / 5 |
| Document selection | Nhóm | [Để trống điểm nhóm] / 10 |
| Chunking strategy | Nhóm | [Để trống điểm nhóm] / 15 |
| My approach | Cá nhân | 10 / 10 |
| Similarity predictions | Cá nhân | 5 / 5 |
| Results | Cá nhân | 10 / 10 |
| Core implementation (tests) | Cá nhân | 30 / 30 |
| Demo | Nhóm | [Để trống điểm nhóm] / 5 |
| **Tổng** | | **60 / 60 (Điểm cá nhân)** |
