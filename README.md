# semantic-search-engine1

An AI-powered document search engine allowing semantic search over PDF, Word, and text files. Built using FastAPI, FAISS, and Sentence Transformers with a React frontend.

---

## Semantic Search Engine

This project implements a semantic document search engine that extracts meaningful embeddings from uploaded documents and enables context-aware search queries beyond keyword matching.

---

## Features

- Semantic search based on Sentence Transformers embeddings  
- Multi-format upload: PDF, DOCX, TXT  
- Efficient similarity search using FAISS  
- Interactive React-based UI for uploading and searching documents

---

## Project Structure

### 1. `backend/app.py`  
FastAPI app handling document upload, indexing, and search.

### 2. `backend/build_index.py`  
Script to parse documents, generate embeddings, and build the FAISS index.

### 3. `frontend/src/App.js`  
React frontend for uploading documents and querying the semantic search.

### 4. `test/test_backend.py`  
Unit tests for backend API endpoints.

### 5. `requirements.txt`  
Backend dependencies including FastAPI, FAISS, Sentence Transformers.

### 6. `package.json`  
Frontend React dependencies.

---

## How to Run

- Install backend dependencies:  
  `pip install -r backend/requirements.txt`

- Start backend server:  
  `uvicorn backend.app:app --reload`

- Navigate to frontend and install dependencies:  
  `cd frontend && npm install`

- Start frontend app:  
  `npm start`

- Open browser at `http://localhost:3000`

---

## Usage

- Upload PDF, Word, or text files.  
- Enter natural language queries to perform semantic search.  
- View ranked relevant document snippets.

---

