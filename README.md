# ChromaPDF
A PDF semantic search engine built with FastAPI, Ollama, ChromaDB, and Next.js. Using local AI embeddings, intelligent chunking, and vector similarity search, users can ask natural language questions and instantly discover the most relevant passages with contextual highlighting and page references

## Features
* Drag-and-drop PDF upload
* Semantic search using vector embeddings
* Local inference with Ollama
* Fast similarity search with ChromaDB
* Context-aware PDF chunking
* Highlighted search results
* Page number references
* Persistent vector storage
---

## Architecture
<img width="6008" height="3269" alt="image" src="https://github.com/user-attachments/assets/855976b2-0e29-4833-9df2-a291c2138978" />


## Tech Stack
### Frontend
* Next.js
* React
* TypeScript
* Tailwind CSS

### Backend
* FastAPI
* PyMuPDF
* LangChain Text Splitters
* Ollama
* ChromaDB

## Project Structure

```text
project/
├── backend/
│   ├── main.py
│   ├── chunker.py
│   ├── embedder.py
│   └── vector_store.py
│
├── frontend/
│   ├── app/
│   │   ├── page.tsx
│   │   └── results/
│   │
│   └── components/
│       └── ChunkCard.tsx
│
├── uploads/
├── chroma_db/
├── docker-compose.yml
└── README.md
```

---



## Running Locally

### 1. Clone Repository

```bash
git clone <repo-url>
cd project
```

### 2. Start Ollama

```bash
ollama serve
```

Pull embeddings model:

```bash
ollama pull nomic-embed-text
```

### 3. Backend Setup

```bash
cd backend

python -m venv venv
source venv/bin/activate

pip install -r requirements.txt
```

Run FastAPI:

```bash
uvicorn main:app --reload
```

Backend runs on:

```text
http://localhost:8000
```
---

### 4. Frontend Setup

```bash
cd frontend

npm install
npm run dev
```

Frontend runs on:

```text
http://localhost:3000
```

---

## Docker Deployment

Start the entire stack:

```bash
docker-compose up --build
```
Services:

| Service  | Port              |
| -------- | ----------------- |
| Next.js  | 3000              |
| FastAPI  | 8000              |
| Ollama   | 11434             |
| ChromaDB | Persistent Volume |

