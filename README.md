# LangChain Learning: Build a Simple RAG Chatbot

Repo này dùng để học **framework LangChain** từ cơ bản đến cách xây dựng một **RAG chatbot đơn giản** bằng Python, OpenAI Embeddings và FAISS.

## Mục tiêu

Sau khi hoàn thành notebook, người học có thể:

- Gọi mô hình bằng `ChatOpenAI`
- Làm việc với `SystemMessage`, `HumanMessage`, `AIMessage`
- Tạo prompt bằng `PromptTemplate` và `ChatPromptTemplate`
- Kết nối các bước bằng LCEL
- Đọc dữ liệu từ TXT, PDF và DOCX
- Chia tài liệu thành các chunk
- Tạo embedding
- Lưu vector bằng FAISS
- Truy xuất tài liệu liên quan bằng Retriever
- Tạo một RAG chatbot hỏi đáp theo tài liệu

## Pipeline RAG

```text
Tài liệu
   ↓
Document Loader
   ↓
Text Splitter
   ↓
Embedding
   ↓
FAISS Vector Store
   ↓
Retriever
   ↓
Prompt + Context
   ↓
LLM
   ↓
Câu trả lời
```

## Cấu trúc repo

```text
langchain-learning/
├── .env
├── .gitignore
├── lang_chain(8).ipynb
└── README.md
```

## Nội dung notebook

Notebook `lang_chain(8).ipynb` gồm:

1. Khởi tạo `ChatOpenAI`
2. Sử dụng `invoke()`, `batch()`, `stream()`
3. Message và lịch sử hội thoại
4. Prompt Template
5. Output Parser
6. LCEL và Runnable
7. Document Loader
8. Chunking
9. Embedding
10. FAISS
11. Retriever
12. RAG chatbot cơ bản
13. Prompt Engineering và Prompt Safety

## Cài đặt

Tạo môi trường ảo:

```bash
python -m venv .venv
```

Kích hoạt trên Windows:

```powershell
.venv\Scripts\activate
```

Cài thư viện:

```bash
pip install python-dotenv jupyter \
    langchain-core langchain-community langchain-openai \
    langchain-text-splitters langchain-experimental \
    faiss-cpu pypdf docx2txt marker-pdf
```

## Cấu hình API key

Tạo file `.env`:

```env
OPENAI_API_KEY=your_openai_api_key
```

Không commit file `.env` lên GitHub.

## Chuẩn bị dữ liệu

Tạo thư mục:

```text
data/
├── sample.txt
├── sample.pdf
└── sample.docx
```

Sau đó sửa đường dẫn trong notebook cho phù hợp với dữ liệu của bạn.

## Chạy project

```bash
jupyter notebook
```

Mở file:

```text
lang_chain(8).ipynb
```

Nên chạy các cell từ trên xuống dưới.

## Ví dụ câu hỏi

```text
Nginx dùng để làm gì?

Nginx có thể làm reverse proxy không?

FastAPI có ưu điểm gì?

MySQL lưu trữ dữ liệu như thế nào?
```

## Công nghệ sử dụng

- Python
- LangChain
- OpenAI API
- FAISS
- Jupyter Notebook
- PyPDF
- Docx2txt
- Marker

## Hướng phát triển

- Thêm giao diện Streamlit
- Xây dựng backend bằng FastAPI
- Thêm trích dẫn nguồn
- Thêm lịch sử hội thoại
- Thêm reranking
- Đóng gói bằng Docker

## Lưu ý

Repo này phục vụ mục đích học tập và thử nghiệm. Không đưa API key hoặc dữ liệu nhạy cảm lên GitHub.
