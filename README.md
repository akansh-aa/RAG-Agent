# Excel RAG Agent using LangGraph

An AI-powered Excel RAG (Retrieval-Augmented Generation) agent built using LangGraph, Hugging Face embeddings, FAISS, and Pandas.

The system can:
- Read Excel files
- Convert rows into embeddings
- Perform semantic search
- Execute dataframe operations
- Answer natural language questions on Excel data

---

# Features

- Excel file ingestion
- Multi-sheet support
- Row-wise chunking
- Hugging Face embeddings
- FAISS vector database
- Semantic retrieval
- Pandas-based calculations
- LangGraph agent workflow
- Tool-based routing

---

# Architecture

```text
User Query
    ↓
LangGraph Agent
    ↓
Query Router
 ┌───────────────┬────────────────┐
 ↓               ↓                ↓
Retriever     Pandas Tool     Calculator
 ↓               ↓                ↓
Context + Computation Results
                ↓
               LLM
                ↓
            Final Answer
```

---

# Tech Stack

| Component | Technology |
|---|---|
| Agent Framework | LangGraph |
| Embeddings | Hugging Face BGE |
| Vector DB | FAISS |
| Data Processing | Pandas |
| LLM Framework | LangChain |
| Excel Parsing | openpyxl |
| Language | Python |

---

# Installation

## Create Environment

```bash
conda create -n excel_rag python=3.10 -y
conda activate excel_rag
```

## Install Dependencies

```bash
pip install numpy==1.26.4
pip install pandas
pip install torch
pip install transformers
pip install sentence-transformers
pip install faiss-cpu
pip install langgraph
pip install langchain
pip install langchain-community
pip install langchain-text-splitters
pip install openpyxl
```

---

# Project Structure

```text
excel-rag-agent/
│
├── app.py
├── requirements.txt
├── README.md
├── data/
│   └── sales.xlsx
├── vectorstore/
├── notebooks/
└── utils/
```

---

# Workflow

## 1. Load Excel File

The system reads all sheets using Pandas.

## 2. Convert Rows to Text

Each row is converted into semantic text chunks.

Example:

```text
Region: Delhi
Revenue: 50000
Year: 2024
```

## 3. Generate Embeddings

Embeddings are generated using Hugging Face BGE models.

## 4. Store in FAISS

Vectors are stored for semantic retrieval.

## 5. LangGraph Agent Routing

The agent decides whether to:
- retrieve semantic context
- execute dataframe operations
- perform calculations

---

# Example Queries

```text
What was total revenue in 2024?

Show sales from Delhi.

Which region had highest profit?

Summarize employee attendance trends.
```

---

# Embedding Model

Model used:

```text
BAAI/bge-small-en
```

Hugging Face:
https://huggingface.co/BAAI/bge-small-en

---

# Future Improvements

- Hybrid Retrieval (BM25 + Vector)
- Re-ranking
- Multi-agent workflows
- SQL generation
- Chart understanding
- OCR support for scanned tables
- Streaming responses
- FastAPI deployment

---

# Challenges Faced

- NumPy ABI compatibility
- Handling structured Excel data
- Semantic retrieval for tabular information
- Tool routing for calculations

---

# Author

Akansha Pal

---
