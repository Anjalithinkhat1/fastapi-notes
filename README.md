# 🧠 FORMD AI Tutor

FORMD AI Tutor is a document-aware Q&A platform that uses a Retrieval-Augmented Generation (RAG) pipeline to allow students to interact with uploaded content. It converts unstructured documents into vector embeddings, performs semantic search, and uses Google Gemini to respond in a conversational manner.

---

## 📌 Overview

- Converts uploaded files into text
- Generates semantic embeddings
- Stores vectors in Pinecone
- Uses Gemini LLM for smart, context-based answers
- Tracks sessions using chat memory
- Built using Python, FastAPI, and React

---

## 🏗️ Architecture Summary

> **Architecture Flow:**

1. 📁 Upload Document
2. ✅ Validate + Store to GCS
3. ✂️ Extract Text & Chunk
4. 🔢 Embed via BAAI bge-large-en v1.5
5. 📦 Store vectors in Pinecone (via LlamaIndex)
6. 🗃️ Update metadata in Hasura
7. ❓ Accept user query via chat
8. 🔍 Retrieve relevant chunks from Pinecone
9. 🧠 Gemini processes context + memory
10. 💬 AI responds back to user

---

## 🔧 Technologies Used

| Component              | Tool/Technology         | Version            |
|------------------------|-------------------------|--------------------|
| Frontend               | React.js                | N/A                |
| Backend                | FastAPI (Python)        | N/A                |
| LLM                    | Google Gemini           | gemini-2.0-flash   |
| Embedding Model        | BAAI bge-large-en       | v1.5               |
| Vector Store           | Pinecone                | Cloud Hosted       |
| Orchestration Engine   | LlamaIndex              | v0.12.33           |
| Document Storage       | Google Cloud Storage    | N/A                |
| Metadata Database      | Hasura (PostgreSQL)     | N/A                |
| Chat Memory            | In-Memory Buffer        | Internal           |

---

## 🔌 API Endpoints (FastAPI)

| Method | Path         | Description                      |
|--------|--------------|----------------------------------|
| POST   | /upload      | Upload a new document            |
| GET    | /docs        | List uploaded documents          |
| POST   | /query       | Ask a question to the AI tutor   |

More endpoints documented in [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)

---

## 🧪 Run the Server (Local Development)

### Install requirements:

```bash
pip install fastapi uvicorn llama-index
