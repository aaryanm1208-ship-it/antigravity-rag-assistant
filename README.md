# 🚀 Antigravity RAG Assistant

AI-powered research assistant for exploring antigravity theories, advanced propulsion systems, and cutting-edge physics using **Retrieval-Augmented Generation (RAG)**.

## Architecture

```
PDF → Loader → Chunker → Embeddings (all-MiniLM-L6-v2) → FAISS → Retriever → LLM → Response
```

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | Python + FastAPI |
| RAG | LangChain |
| Embeddings | HuggingFace all-MiniLM-L6-v2 |
| Vector DB | FAISS (local) |
| LLM | Groq (llama-3.3-70b) |
| Frontend | Next.js (React) |

## Quick Start

### 1. Backend Setup

```bash
cd backend
pip install -r requirements.txt

# Add your API key to .env
# GROQ_API_KEY=your_key_here  (get free at console.groq.com)

python -m uvicorn app.main:app --reload --port 8000
```

### 2. Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

### 3. Usage

1. Open http://localhost:3000
2. Upload PDF documents via the upload button
3. Ask scientific questions about your documents

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/status` | System status |
| POST | `/api/query` | Query the knowledge base |
| POST | `/api/upload` | Upload a PDF |
| GET | `/api/documents` | List documents |
| DELETE | `/api/documents/{name}` | Delete a document |

## Features

- **Query Expansion**: Auto-generates alternative query phrasings
- **Semantic Search**: FAISS similarity search with score ranking
- **Source Citations**: Every answer includes traceable document references
- **Multi-Document Intelligence**: Cross-references multiple PDFs
- **Scientific Response Structure**: 8-section structured answers
