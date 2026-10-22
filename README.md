# QA Chatbot using Retrieval-Augmented Generation (RAG)

This project implements a **Question Answering (QA) chatbot using Retrieval-Augmented Generation (RAG)**.  
It explores the **end-to-end RAG pipeline**, along with a **systematic evaluation of embedding models and retrievers**, focusing on **retrieval quality, semantic similarity, and grounding**.

The repository is structured as a **research + engineering prototype**, emphasizing **experimentation, evaluation, and reproducibility**.

<!-- --- -->

## Repository Structure

QA-Chatbot-using-RAG/  
├── Basic RAG pipeline.ipynb  
├── Embedding models and evaluation.ipynb  
├── Retriever_Pipeline_Evaluations.ipynb  
├── Embedding models evaluations/  
│   ├── embedding_models_evaluation.csv  
│   └── embedding_models_scores.csv  
├── Retriever Ragas result/  
│   ├── chroma_retriever.csv  
│   ├── ensemble_bm25_retriever.csv  
│   ├── multi_query_retriever.csv  
│   ├── compression_retriever.csv  
│   ├── cross_encoder_compression.csv  
│   └── parent_document_retriever.csv  
├── sample_doc_1.pdf  
├── qa chatbot rag.pdf  
├── Comparision Analysis.csv  
├── requirements.txt  
├── .gitignore  
└── README.md  

<!-- --- -->

## Project Overview

The project is divided into **three main components**:

### 1. Basic RAG Pipeline
Implemented in `Basic RAG pipeline.ipynb`
- PDF ingestion using PyPDF2
- Text chunking with RecursiveCharacterTextSplitter
- Embedding generation using:
  - Sentence Transformers (MiniLM)
  - OpenAI embeddings (optional)
- Vector storage and similarity search using FAISS
- Answer generation using GPT-3.5 via LangChain
- Prompt-driven QA with retrieved context

This notebook demonstrates a **minimal, end-to-end RAG workflow**.

### 2. Embedding Models Evaluation
Implemented in `Embedding models and evaluation.ipynb`
Embedding models evaluated:
- Sentence Transformers:
  - all-MiniLM-L6-v2
  - Matryoshka embeddings (mpnet-based)
- HuggingFace:
  - BAAI/bge-base-en-v1.5
- Cohere embeddings
- OpenAI embeddings

Evaluation methodology:
- Cosine similarity on sentence pairs
- Comparison against human-annotated STS-style scores
- Metrics used:
  - Pearson correlation
  - Spearman correlation
  - Mean Squared Error (MSE)

Results are saved as CSV files under: `Embedding models evaluations/`

### 3. Retriever Evaluation with RAGAS
Implemented in `Retriever_Pipeline_Evaluations.ipynb`
Retrievers evaluated include:
- Chroma-based retriever
- BM25 ensemble retriever
- Multi-query retriever
- Contextual compression retriever
- Cross-encoder compression retriever
- Parent document retriever

Evaluation framework:
- RAGAS metrics for retrieval quality
- Comparison across multiple retriever strategies
- Results stored as CSV files under: `Retriever Ragas result/`

<!-- --- -->

## Key Learnings & Observations

- Embedding choice significantly impacts retrieval quality, even before LLM generation.
- Lightweight models like MiniLM perform competitively on semantic similarity benchmarks.
- Advanced retrievers (multi-query, compression-based) improve grounding at the cost of complexity.
- Retrieval evaluation is as important as answer generation in RAG systems.

<!-- --- -->

## Installation & Setup
1. **Clone the Repository**
  ```bash
  git clone https://github.com/Dhruv-Kapri/QA-Chatbot-using-RAG.git
  cd QA-Chatbot-using-RAG
  ```

2. **Create a Virtual Environment**
  ```bash
  python3 -m venv .venv
  source .venv/bin/activate    # For Linux/Mac
  # .venv\Scripts\activate       # For Windows
  ```

3. **Install Dependencies**
  ```bash
  pip install -r requirements.txt
  ```

4. **Set Up Environment Variables**  
Create a `.env` file in the root directory, with content:
  ```
  OPENAI_API_KEY=your_openai_key
  COHERE_API_KEY=your_cohere_key
  HUGGINGFACE_API_KEY=your_hf_key
  ```

<!-- --- -->

## License  
MIT License - feel free to use this code for your own projects!
---

<sub>Part of [Dhruv Kapri's portfolio](https://dhruv-kapri.github.io/) · [all projects](https://github.com/Dhruv-Kapri)</sub>
