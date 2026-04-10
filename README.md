## End-to-End RAG Pipeline (HuggingFace & ChromaDB)
A comprehensive Retrieval-Augmented Generation (RAG) pipeline for document-based question answering. This project uses HuggingFace embeddings for semantic representation and ChromaDB for efficient vector storage and retrieval. It integrates with state-of-the-art LLMs via the Groq and Google Gemini APIs to generate accurate, context-aware answers.

## Overview
This project implements a complete RAG pipeline that:

Document Ingestion: Loads PDF and text files from a local directory.
Text Splitting: Breaks documents into smaller chunks using LangChain’s RecursiveCharacterTextSplitter.
Embedding Generation: Converts text chunks into dense vectors using HuggingFace SentenceTransformer (all-MiniLM-L6-v2).
Vector Storage: Stores embeddings locally in ChromaDB for efficient semantic search.
Context Retrieval: Retrieves the most relevant chunks based on user queries using cosine similarity.
Answer Generation: Uses retrieved context to generate responses with LLMs such as Qwen (Groq API) and Gemini 2.5 Flash (Google GenAI API).
## What We Built (Core Implementation)
--**Built an End-to-End RAG System:** We successfully transitioned raw documents into actionable knowledge by implementing proper document loaders and recursive text chunking.
--**Integrated Multiple External LLMs:** To generate the final answers, we utilized both the Groq API and the Google Gemini API. By plugging directly into their powerful LLMs (specifically Qwen running on Groq, and Gemini 2.5 Flash), our pipeline synthesizes highly accurate answers natively based on the retrieved context!
--**Switched to ChromaDB:** We integrated ChromaDB to securely and persistently store our HuggingFace dense vector embeddings locally.
## Tech Stack
--**Language:** Python
--**Orchestration:** LangChain (langchain, langchain-core, langchain-community)
--**Embeddings:** HuggingFace Sentence Transformers (all-MiniLM-L6-v2)
--**Vector Store:** ChromaDB
--**LLMs:** Groq API (qwen/qwen3-32b) and Google Generative AI (gemini-2.5-flash)
--**Document Loaders:** PyPDFLoader, TextLoader
## Project Structure
RAG-Project/
```bash
│
├── RAG_pipeline.ipynb       # Main Jupyter Notebook containing the full pipeline code
├── README.md                # Project documentation
│
├── Data/                    # Input files (PDFs / text) and persistent vector store
│   ├── vector_store/        # Stored ChromaDB collections
│   ├── .pdf files           # Research papers and other PDF documents
│   └── .txt files           # Text documents
│
└── .env                     # Environment variables storing API keys (Groq, Gemini)
'''
