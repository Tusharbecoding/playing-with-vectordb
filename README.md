# Playing with Vector Database (Pinecone + LangChain)

A simple Jupyter notebook demonstrating a complete **RAG (Retrieval-Augmented Generation)** pipeline using Pinecone vector database for fast document search and question answering.

## What This Does

This project implements a document processing and search pipeline:

1. **📄 Document Loading** - Loads PDF documents from the `documents/` folder
2. **✂️ Text Chunking** - Breaks documents into smaller chunks (800 chars with 50 char overlap)
3. **🔢 Vectorization** - Converts text chunks into embeddings using OpenAI's embedding model
4. **☁️ Vector Database Upload** - Stores embeddings in Pinecone for fast similarity search
5. **🔍 Similarity Search** - Retrieves relevant document chunks based on user queries
6. **🤖 Question Answering** - Uses OpenAI's LLM to answer questions from retrieved context

## Quick Start

### 1. Install Dependencies

```bash
pip install -r requirements.txt
```

### 2. Set Environment Variables

Create a `.env` file with:

```
OPENAI_API_KEY=your_openai_api_key
PINECONE_API_KEY=your_pinecone_api_key
```

### 3. Add Documents

Place your PDF files in the `documents/` folder.

### 4. Run the Notebook

Open `main.ipynb` and run all cells to:

- Process your documents
- Upload to Pinecone
- Test queries like: _"How much will the agriculture target increase and in how many crores"_

## Key Features

- **Fast Vector Search**: Uses Pinecone's serverless infrastructure for quick similarity search
- **Chunked Processing**: Handles large documents by breaking them into manageable pieces
- **OpenAI Integration**: Leverages GPT for embeddings and question answering
- **Simple Pipeline**: Complete RAG implementation in a single notebook

## Tech Stack

- **LangChain** - Document processing and QA chains
- **Pinecone** - Vector database for similarity search
- **OpenAI** - Embeddings and language model
- **PyPDF** - PDF document loading

## Sample Query

```python
query = "How much will the agriculture target increase and in how many crores"
answer = retrieve_answers(query)
```

The system will find relevant document chunks and provide accurate answers based on your uploaded documents.
