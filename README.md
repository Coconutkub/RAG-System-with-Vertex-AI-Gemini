# Building a Scalable RAG System with Vertex AI & Gemini

This repository contains an end-to-end implementation of a Retrieval-Augmented Generation (RAG) system using Google Cloud's Vertex AI. The project demonstrates how to enrich Large Language Models (LLMs) with private knowledge to reduce hallucinations and provide accurate, context-aware responses.

## 🚀 Project Overview

This Jupyter Notebook (`rag.ipynb`) walks through the complete RAG pipeline:
1.  **Data Ingestion & Chunking:** Importing documents from local files, Google Cloud Storage (public and private buckets), and Google Drive.
2.  **Corpus Creation:** Building and managing vector databases using Vertex AI RAG Engine.
3.  **Embedding Generation:** Utilizing Google's first-party embedding models (`text-embedding-005` and `text-multilingual-embedding-002`).
4.  **Retrieval & Generation:** Querying the RAG corpus using the Vertex AI SDK and passing the retrieved context to Gemini models (`gemini-2.5-flash`).
5.  **LangChain Integration:** Demonstrating how to use `VertexAIRagSearch` within a LangChain workflow.

## 📊 Lab Evaluation: Curriculum Document QA

A significant portion of this project focuses on empirically evaluating the RAG system's performance on a specialized dataset (Thai university curriculum documents). 

**Key Evaluation Highlights:**
* **System Prompting:** Implementing strict grounding rules to ensure the model only answers questions based on the provided documents and refuses out-of-bounds queries.
* **Fact-Checking & Ambiguity Testing:** Evaluating the model against explicit facts, intentionally out-of-bounds questions (e.g., general knowledge), and ambiguous queries requiring multi-document synthesis.
* **Multilingual Embeddings:** Testing the recall rate of chunks using `text-multilingual-embedding-002` versus standard embedding models for Thai language queries.
* **Metric Used:** Evaluated retrieval accuracy using the `Recall@10` metric against a manually curated Ground Truth dataset.

## 🛠️ Tech Stack
* **Cloud Platform:** Google Cloud (Vertex AI)
* **Generative AI:** Gemini 2.5 Flash
* **Frameworks/Libraries:** Google Gen AI SDK, Vertex AI SDK, LangChain (`langchain-google-vertexai`)
* **Environment:** Google Colab / Jupyter Notebook

## ⚙️ Setup & Usage
*Note: You must have a Google Cloud Project with the Vertex AI API enabled to run this notebook.*

1. Clone this repository.
2. Open `rag.ipynb` in Google Colab, Colab Enterprise, or Vertex AI Workbench.
3. Replace the placeholder `<YOUR_PROJECT_ID>` and `<YOUR_BUCKET_NAME>` with your actual Google Cloud credentials.
4. Run the cells sequentially to authenticate, build the corpus, and test the generative responses. 

## 👨‍💻 Author

**Nuttawut Simcharoen (Nut)**
*Computer Engineering Student at King Mongkut's University of Technology Thonburi (KMUTT)*

I am an aspiring AI Engineer passionate about building scalable AI solutions and currently actively seeking full-time opportunities.

