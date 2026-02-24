
# NVIDIA NIM RAG Application

This project demonstrates how to build a Retrieval-Augmented Generation (RAG) system using NVIDIA NIM (NVIDIA Inference Microservices). It integrates NVIDIA-hosted large language models and embedding APIs with LangChain, FAISS, and Streamlit to create a document-aware AI assistant.

The project explores high-performance inference, vector search, and real-time streaming responses powered by GPU-optimized NVIDIA endpoints.

---

## Features

### NVIDIA LLM Integration:

Integrated NVIDIA-hosted LLaMA 3 70B model using the ChatNVIDIA interface.
Enabled streaming responses for fast token-by-token output.
Used secure API-based authentication for model access.

### NVIDIA Embeddings:

Generated vector embeddings using NVIDIA Embedding API.
Converted document chunks into semantic vectors for similarity search.
Optimized chunk size and overlap for better retrieval performance.

### Retrieval-Augmented Generation (RAG):

Loaded multiple PDF documents from a directory.
Split documents into manageable chunks using recursive text splitting.
Stored embeddings in FAISS vector database.
Retrieved relevant document context before generating answers.

### Streamlit Application:

Built a clean interactive UI.
Added document embedding button for vector DB initialization.
Displayed model responses along with source context for transparency.

---

## Getting Started

### Prerequisites

Python 3.10 or higher
Conda (recommended)
Essential Python libraries: LangChain, FAISS, Streamlit, python-dotenv, OpenAI client

Install the required packages using:

```
pip install -r requirements.txt
```

---

## Dataset

The project uses custom PDF documents stored locally in a data directory.

Documents are:

* Automatically loaded from a folder
* Split into chunks
* Converted into vector embeddings
* Stored in FAISS for semantic retrieval

You can replace the PDFs with your own domain-specific documents.

---

## How to Run

Clone this repository:

```
git clone https://github.com/your-username/nvidia-nim-rag.git
```

Navigate to the project directory:

```
cd nvidia-nim-rag
```

Create and activate environment:

```
conda create -p venv python=3.10
conda activate venv
```

Install dependencies:

```
pip install -r requirements.txt
```

Create a `.env` file and add your NVIDIA API key:

```
NVIDIA_API_KEY=your_api_key_here
```

Run the application:

```
streamlit run final_app.py
```

Steps inside app:

* Click "Document Embedding"
* Wait for vector store initialization
* Ask questions related to your documents
* View answer + similarity context

---

## Results

### LLM Performance:

Fast streaming inference using NVIDIA NIM.
Low latency response generation powered by GPU infrastructure.

### Retrieval Accuracy:

Accurate responses grounded in document context.
Similarity search returns relevant document chunks.

### Observability:

Displays source context used for answering.
Ensures transparency in RAG workflow.

---

## Analysis

Inference Speed:
NVIDIA NIM delivers optimized GPU-backed inference, resulting in fast streaming responses compared to traditional CPU-based deployments.

Retrieval Quality:
Using FAISS with NVIDIA embeddings improves semantic search accuracy and context relevance.

Scalability:
API-based microservices architecture allows deployment across environments without hosting models locally.

Security:
API keys are stored securely using environment variables, preventing credential exposure.

---

## Key Learnings

* NVIDIA NIM simplifies enterprise-grade LLM deployment.
* Embeddings play a crucial role in retrieval quality.
* Chunk size and overlap significantly affect RAG performance.
* GPU-optimized inference improves real-time AI responsiveness.
* OpenAI-compatible clients make integration seamless.

---

## Future Work

* Add multi-modal model integration.
* Benchmark latency against OpenAI / Bedrock.
* Deploy via Docker and Kubernetes.
* Add authentication and access control.
* Implement caching for faster repeated queries.
* Add evaluation metrics for retrieval precision.

