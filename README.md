# 🗝️ InsightVault: Unlock Answers from Articles

## Overview
InsightVault is a Retrieval-Augmented Generation (RAG) based research assistant for news articles. It helps users query multiple long-form articles and get meaningful, source-attributed answers. Unlike simply pasting text into a language model, InsightVault indexes your articles efficiently and retrieves only the most relevant information, ensuring scalability, accuracy, and explainability.

This project demonstrates the use of modern RAG techniques combining vector search, OpenAI embeddings, and large language models, wrapped in an easy-to-use Streamlit web application.

## Features
- Input up to three news article URLs and process them into a semantic vector store
- Semantic search over large or multiple documents
- Answer questions about the articles with citations to the source text
- Reusable vector index for repeated queries without reprocessing
- Web-based interface for ease of use

## Technologies Used
- Python
- Streamlit (web application framework)
- LangChain (orchestration of RAG pipeline)
- OpenAI GPT models (LLM and embeddings)
- FAISS (vector database)
- dotenv (environment variable management)

## How It Works
1. **Article Loading and Preprocessing**
   - Users enter up to three URLs to news articles.
   - Articles are fetched and loaded using `UnstructuredURLLoader`.
   - Text is split into manageable chunks.

2. **Embedding and Indexing**
   - Each chunk is embedded into a dense vector using OpenAI’s embedding model.
   - Vectors are stored in a FAISS index, serialized for reuse.

3. **Querying**
   - Users type a natural language question.
   - Relevant chunks are retrieved from FAISS via semantic similarity.
   - Retrieved context is passed to an OpenAI language model to generate an answer, with source references.

## Why Use InsightVault?
- Handles longer or multiple documents better than plain LLM input by indexing and retrieving only relevant parts.
- Reusable index saves time and cost for repeated queries.
- Provides transparency with source citations.
- Demonstrates practical application of RAG — a technique widely used in enterprise QA systems.

