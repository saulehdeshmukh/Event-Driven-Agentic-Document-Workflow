# 🧠 Event-Driven Agentic Document Intelligence System

This project implements an advanced, modular, **agentic RAG workflow** using **LlamaIndex**, **LlamaParse**, and **OpenAI GPT-3.5**. It intelligently processes resumes and application forms by parsing, indexing, querying, and feeding back information using a fully event-driven architecture.

---

## 🚀 Key Features

- 🧾 Upload and parse **resume + application form** (PDFs)
- 🧠 Semantic indexing using **VectorStoreIndex** from LlamaIndex
- 🔍 Contextual Q&A using **OpenAI GPT-3.5-turbo**
- 🧩 Event-driven agent design using `llama-index.utils.workflow`
- 💬 Collects structured feedback for downstream automation
- 🎯 Clean modular design for easy adaptation to other document types (invoices, legal docs, etc.)

---

## 🧱 Architecture Overview

- **Agents**: Structured around `Event` subclasses like `ParseFormEvent`, `QueryEvent`, `ResponseEvent`, and `FeedbackEvent`
- **Workflow**: Built with `@step` decorators and managed by `RAGWorkflow` class
- **Indexing**: Documents are parsed by `LlamaParse` and stored using `VectorStoreIndex`
- **Querying**: Uses `.as_query_engine()` with top-`k` similarity search for high relevance 🔧 Tech Stack

| Component         | Tool                                      |
|------------------|-------------------------------------------|
 LLM              | OpenAI GPT-3.5 (`llama-index-llms-openai`)|
| Document Parsing | `llama-parse`                             |
| Indexing         | `llama-index` VectorStore                 |
| Workflow Engine  | `llama-index.utils.workflow`              |
| Notebook Runtime | Jupyter + `nest_asyncio`                  |
| Visualization    | `Gradio` (optional frontend)              |

---

## 📁 Folder Structure

```bash
.
├── Event-Driven Agentic Document Workflow.ipynb   # Main notebook
├── helper.py                                      # API key loader + HTML content renderer
├── fake_resume.pdf                                # Sample test document
├── fake_application_form.pdf                      # Sample test document
├── storage/                                       # Persistent vector index store
├── lib/                                           # Any additional utility files
