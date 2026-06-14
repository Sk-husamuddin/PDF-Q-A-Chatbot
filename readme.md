## Updated `README.md` — Project 3 Complete (CLI + Web) 📝

```markdown
# 📄 PDF Q&A RAG Chatbot

A retrieval-augmented generation (RAG) chatbot that answers questions from your PDF documents — with accurate source citations (filename + page number).

Built from scratch — no LangChain, no black boxes. Every embedding, chunk, and retrieval step is hand-coded to understand exactly how RAG works under the hood.

## 🚀 Live Demo

- **Web App:** _coming soon_
- **Backend API:** _coming soon_

## 🧠 How It Works

```
PDF Upload (multiple PDFs supported)
    ↓
PyMuPDF extracts text page by page
    ↓
Text split into chunks (500 chars, 50 overlap)
    ↓
Sentence Transformers embed chunks (all-MiniLM-L6-v2)
    ↓
ChromaDB stores vectors + metadata (filename, page)
    ↓
User asks a question
    ↓
Question embedded → ChromaDB semantic search
    ↓
Top 3 relevant chunks retrieved
    ↓
Chunks + Question → Groq (llama-3.3-70b-versatile)
    ↓
Answer + Source citations ✅
```

## ✨ Features

- Multiple PDF upload with source tracking (filename + page)
- Semantic search — finds meaning, not just keywords
- Overlap chunking — no information lost at chunk boundaries
- Faithful answers — says "I don't know" if not in the documents
- Two interfaces: CLI (terminal) and Web (browser)

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| PDF Loading | PyMuPDF |
| Chunking | Custom overlap strategy |
| Embeddings | Sentence Transformers (all-MiniLM-L6-v2) |
| Vector DB | ChromaDB (persistent) |
| LLM | Groq (llama-3.3-70b-versatile) |
| Backend | FastAPI |
| Frontend | HTML / CSS / JavaScript |
| Deployment | Railway (backend) + Vercel (frontend) |

## 📁 Project Structure

```
PDF-Q-A-Chatbot/
│
├── frontend/
│   ├── index.html      # Web UI
│   ├── style.css        # Styling
│   └── script.js         # Upload + chat logic
│
├── pdf_loader.py        # PDF loading + chunking
├── vector_store.py       # ChromaDB operations
├── rag_engine.py          # Retrieval + LLM
├── main.py                 # CLI interface
├── backend.py              # FastAPI server (web interface)
│
├── requirements.txt
├── Procfile
├── .gitignore
└── README.md
```

## ⚙️ Setup

### 1. Clone the repo
```bash
git clone https://github.com/Sk-husamuddin/PDF-Q-A-Chatbot
cd PDF-Q-A-Chatbot
```

### 2. Create virtual environment
```bash
python -m venv venv
venv\Scripts\activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Create `.env` file
```
GROQ_API_KEY=your_groq_api_key_here
```

## 💬 Usage

### Option A — CLI version
```bash
python main.py
```
```
Enter PDF path or 'done' to start chatting: document.pdf
✅ Extracted 12 chunks from document.pdf
✅ Added 12 chunks from document.pdf

Enter PDF path or 'done' to start chatting: done

Chatbot Ready!!
========================================
You: What is machine learning?

Answer: Machine Learning is a subset of AI that
enables computers to learn from data...

Sources:
 📄 document.pdf (page 2)
```

### Option B — Web version
```bash
uvicorn backend:app --reload
```
Then open `frontend/index.html` in your browser.

## 🌐 Deployment

```
Backend  → Railway
           (set GROQ_API_KEY as environment variable)

Frontend → Vercel
           (update BACKEND_URL in script.js to Railway URL)
```

## 📍 Part of GenAI Learning Journey

This is **Project 3** of a structured 3-month GenAI learning roadmap.

| Project | Description | Status |
|---------|-------------|--------|
| Project 1 | Prompt System Designer | ✅ |
| Project 2 | Terminal Chatbot | ✅ |
| Project 2.5 | Live Web Chatbot | ✅ |
| **Project 3** | **PDF Q&A RAG Chatbot** | ✅ |
| Project 4 | Research Agent | 🔄 Coming Soon |
| Project 5 | Capstone App | 🔄 Coming Soon |

## 👨‍💻 Author

**Shaik Husamuddin**
B.Tech CSE/AI-ML — Vijayawada, Andhra Pradesh

- GitHub: [Sk-husamuddin](https://github.com/Sk-husamuddin)
- Learning Journey: [genai-learning-journey](https://github.com/Sk-husamuddin/genai-learning-journey)
```

---
