# PDF-Based RAG Application

A Retrieval-Augmented Generation (RAG) application that allows users to retrieve relevant information from PDF documents and generate context-aware answers using a Large Language Model (LLM).

## Overview

This project implements a document-based RAG pipeline. It processes PDF documents, converts their content into text chunks, generates vector embeddings, and stores them in ChromaDB.

When a user asks a question, the application retrieves relevant document chunks and uses them as context to generate an answer.

## Tech Stack

- **Python** – Core programming language
- **LangChain** – Document loading and text splitting
- **PyPDF** – PDF document processing
- **Sentence Transformers** – Text embeddings
- **ChromaDB** – Vector database
- **Groq / LLM API** – Language model integration
- **Jupyter Notebook** – Development environment

## RAG Pipeline

1. **Document Loading:** Load PDF documents using PyPDFLoader.
2. **Text Extraction:** Extract text from the loaded documents.
3. **Text Chunking:** Split documents into smaller chunks using RecursiveCharacterTextSplitter.
4. **Embedding Generation:** Generate vector embeddings using `all-MiniLM-L6-v2`.
5. **Vector Storage:** Store document chunks and embeddings in ChromaDB.
6. **Retrieval:** Retrieve relevant chunks based on the user's query.
7. **Response Generation:** Pass retrieved context to an LLM to generate a context-aware response.

## Project Structure

```text
RAG_project/
│
├── data/
│   ├── pdfs/
│   └── vector_store/
│
├── RAG_pipeline.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

## Installation and Setup

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd RAG_project
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it:

**Mac/Linux**
```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure API Key

Create a `.env` file in the project directory:

```env
GROQ_API_KEY=your_api_key_here
```

Never upload your `.env` file or expose your API key publicly.

### 5. Run the project

Open `RAG_pipeline.ipynb` in Jupyter Notebook or JupyterLab and execute the cells.

## Current Features

- PDF document loading
- Text extraction and chunking
- Semantic embeddings
- Persistent vector storage using ChromaDB
- Similarity-based document retrieval
- LLM-based response generation

## Future Improvements

- Support for multiple document formats
- Improved retrieval and ranking
- Streamlit or web-based user interface
- Conversation history and multi-turn question answering
- Evaluation of retrieval and response quality