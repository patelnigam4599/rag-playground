# RAG Playground

A Python playground for learning and experimenting with Retrieval-Augmented Generation (RAG) pipelines using LangChain, document loaders, text splitters, embeddings, vector stores, and LLM providers.

The project is notebook-first. The notebooks show how to load local text/PDF files, split documents into chunks, preserve metadata, and prepare data for retrieval.

## What This Project Covers

- Loading plain text files with LangChain document loaders
- Loading PDFs with `PyPDFLoader` and `PyMuPDFLoader`
- Processing local documents from the `data/` directory
- Splitting documents with recursive text splitters
- Preparing metadata for retrieval workflows
- Experimenting with vector store tooling such as FAISS, ChromaDB, and Typesense
- Connecting RAG experiments to OpenAI or Groq models

## Project Structure

```text
rag-playground/
|-- data/
|   |-- pdf/
|   |   `-- Company_Handbook.pdf
|   `-- text_files/
|       |-- machine_learning.txt
|       `-- python_intro.txt
|-- notebook/
|   |-- document.ipynb
|   `-- pdf_loader.ipynb
|-- main.py
|-- pyproject.toml
|-- requirments.txt
|-- uv.lock
`-- README.md
```

## Requirements

- Python 3.12 or newer
- `uv` recommended for dependency management
- Jupyter or VS Code notebook support

Main dependencies include:

- `langchain`
- `langchain-core`
- `langchain-community`
- `langchain-openai`
- `langchain-groq`
- `langgraph`
- `openai`
- `pypdf`
- `pymupdf`
- `sentence-transformers`
- `faiss-cpu`
- `chromadb`
- `typesense`
- `python-dotenv`

## Setup

Clone the repository:

```powershell
git clone https://github.com/patelnigam4599/rag-playground.git
cd rag-playground
```

Install dependencies with `uv`:

```powershell
uv sync
```

Or install with `pip`:

```powershell
python -m venv .venv
.\.venv\Scripts\activate
pip install -r requirments.txt
```

## Environment Variables

Create a `.env` file in the project root if you use hosted model providers:

```env
OPENAI_API_KEY=your_openai_api_key
GROQ_API_KEY=your_groq_api_key
```

Only add the keys required for the notebook or experiment you are running.

## Data And Generated Files

The repository includes sample files under `data/`:

- `data/pdf/Company_Handbook.pdf`
- `data/text_files/python_intro.txt`
- `data/text_files/machine_learning.txt`

Generated vector indexes should be stored under:

```text
data/vector_store/
```

That folder is ignored by git, so local vector database files are not committed.

## Running The Project

Run the simple Python entry point:

```powershell
uv run python main.py
```

Open the notebooks:

```powershell
uv run jupyter notebook
```

Then run:

- `notebook/document.ipynb` for LangChain document loading examples
- `notebook/pdf_loader.ipynb` for PDF ingestion and chunking experiments

## Typical RAG Flow

1. Load documents from `data/`.
2. Split documents into smaller chunks.
3. Generate embeddings for each chunk.
4. Store embeddings in a vector store.
5. Retrieve relevant chunks for a user query.
6. Pass retrieved context to an LLM.
7. Generate an answer grounded in the source documents.

## Notes

- This repository is intended for learning and experimentation.
- Most of the current workflow lives in notebooks.
- `main.py` is a minimal entry point.
- The file name `requirments.txt` is kept as-is, although the conventional spelling is `requirements.txt`.
