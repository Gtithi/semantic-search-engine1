# semantic-search-engine1
An AI-powered document search engine that lets you upload and search across PDF, Word, and text files using semantic understanding. Built with FastAPI, React, FAISS, and Sentence Transformers to deliver intelligent, context-aware search results beyond simple keyword matching

Overview
This project implements an AI-powered semantic document search engine that allows users to upload and search across PDF, Word, and text files using natural language understanding rather than traditional keyword matching.

The backend leverages FastAPI, FAISS, and Sentence Transformers, while the frontend is built using React. The system enables intelligent, context-aware search across large collections of documents.

Features
🔍 Semantic Search: Uses embeddings to understand and match query intent with document content.

📄 Multi-format Upload: Supports PDF, DOCX, and TXT files.

🚀 Fast Retrieval: Utilizes FAISS for efficient similarity search in high-dimensional space.

🧠 Contextual Understanding: Powered by Sentence Transformers (e.g., all-MiniLM-L6-v2).

🌐 Interactive UI: React-based frontend for smooth upload, query, and results display.

Project Structure
backend/app.py
This module contains the FastAPI application managing the backend API for document upload, indexing, and semantic search:

Attributes:

app: FastAPI instance.

index: FAISS index for semantic search.

embedder: Sentence Transformer model for embedding queries and documents.

Methods / Endpoints:

upload_documents(): API endpoint to upload and parse PDF, Word, and text files.

build_index(): Processes uploaded documents, generates embeddings, and builds the FAISS index.

search(query: str): Accepts a search query and returns the most semantically relevant document snippets.

health_check(): Endpoint to verify API status.

backend/build_index.py
Script to build or update the FAISS index from document embeddings.

Functions:

parse_documents(directory): Extracts text from various document formats.

embed_documents(texts): Converts text snippets into vector embeddings.

create_faiss_index(embeddings): Builds and saves the FAISS index.

frontend/src/App.js
The main React component handling the user interface for document upload, search input, and displaying search results.

Features:

File upload functionality supporting PDFs, DOCX, and TXT.

Search bar for semantic queries.

Display of ranked search results with snippet previews.

Responsive design for usability.

test/test_backend.py
Unit tests for backend functionality using pytest and httpx.

Fixtures:

client(): Sets up a test FastAPI client instance.

Test Cases:

test_upload_documents(): Verifies document upload handling.

test_build_index(): Checks index creation from uploaded documents.

test_search(): Validates semantic search returns relevant results.

test_health_check(): Ensures API is reachable.

requirements.txt
Lists all Python dependencies required for the backend service:

fastapi

uvicorn

faiss-cpu

sentence-transformers

python-multipart

PyMuPDF

python-docx

pytest

httpx

package.json
Defines frontend React app dependencies such as:

react

axios

react-dropzone

material-ui/core (or any UI framework used)

How to Run
Install backend dependencies:
pip install -r backend/requirements.txt

Start the FastAPI backend server:
uvicorn backend.app:app --reload

Navigate to the frontend directory:
cd frontend

Install frontend dependencies:
npm install

Start the React frontend app:
npm start

Open http://localhost:3000 in your browser to use the app

Run backend tests:
pytest test/test_backend.py

Usage
Upload documents in PDF, Word, or text format via the web interface

The system extracts and processes the document content into semantic embeddings

Enter your search query in natural language to find relevant information

View ranked search results based on semantic similarity, not just keyword matches

Click on results to see the exact content snippet and document source

Use filters to narrow down search results by document type or date (if implemented)

Add new documents anytime to expand the searchable knowledge base

Monitor backend logs for processing status and error tracking

