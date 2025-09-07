# 🧠 QA Chatbot using RAG

An **abstractive Question Answering (QA) chatbot** built using **Retrieval-Augmented Generation (RAG)**.  
The system integrates **advanced retrievers, rerankers, embeddings, and LLMs** to deliver **highly relevant and context-aware answers**.

---

## 🚀 Features
- **RAG-based QA pipeline** using **LangChain** and **OpenAI GPT-3.5** for abstractive responses.
- **Multi-retriever integration**: Contextual Compression, Multi-query retriever, Ensemble BM25, Parent Document retriever.
- **Advanced reranking**: Cohere reranker and Cross Encoder reranker for top-N document relevancy.
- **Vector stores**: FAISS and ChromaDB for efficient indexing and retrieval.
- **Embedding models tested**: MiniLM, Cohere, OpenAI, HuggingFace BGE, and Matryoshka.
- **Evaluation** powered by **RAGAS** and **STS benchmark**, achieving:
  - **Answer relevancy:** 94.4%
  - **Context precision & recall:** **1.0 (perfect scores)**
  - **Faithfulness score:** 1.0 (completely factual retrievals)

---

## ⚙️ Installation & Setup
1. **Clone the Repository**
```bash
git clone https://github.com/Dhruv-Kapri/QA-Chatbot-using-RAG.git
cd QA-Chatbot-using-RAG
```

2. **Create a Virtual Environment**
```bash
python -m venv venv
source venv/bin/activate    # For Linux/Mac
venv\Scripts\activate       # For Windows
```

3. **Install Dependencies**
```bash
pip install -r requirements.txt
```

4. **Set Up Environment Variables**  
Create a .env file in the root directory:
```bash
OPENAI_API_KEY=your_openai_key
COHERE_API_KEY=your_cohere_key
HUGGINGFACE_API_KEY=your_hf_key
```

5. **Run the Application**
```bash
uvicorn src.app:app --reload
```

---

## License  
MIT License - feel free to use this code for your own projects!