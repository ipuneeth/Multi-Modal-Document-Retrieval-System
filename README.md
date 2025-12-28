<h1 align="center">
  📄🔍 Multi-Modal Document Retrieval System
</h1>

<p align="center">
  <strong>Semantic Search for Scanned Documents using OCR & Vector Embeddings</strong>
</p>

<p align="center">
  <a href="https://www.python.org/">
    <img src="https://img.shields.io/badge/Python-3.x-blue?style=flat-square&logo=python" alt="Python">
  </a>
  <a href="https://github.com/tesseract-ocr/tesseract">
    <img src="https://img.shields.io/badge/OCR-Tesseract-green?style=flat-square&logo=google" alt="Tesseract">
  </a>
  <a href="https://github.com/facebookresearch/faiss">
    <img src="https://img.shields.io/badge/Vector_DB-FAISS-yellow?style=flat-square" alt="FAISS">
  </a>
  <a href="https://huggingface.co/sentence-transformers">
    <img src="https://img.shields.io/badge/AI-Sentence--Transformers-orange?style=flat-square&logo=huggingface" alt="HuggingFace">
  </a>
  <a href="https://colab.research.google.com/">
    <img src="https://img.shields.io/badge/Platform-Google_Colab-orange?style=flat-square&logo=googlecolab" alt="Colab">
  </a>
</p>

<hr>

## 📌 Project Overview

This project is a **Multi-Modal Document Retrieval System** designed to solve the challenge of searching through scanned image documents. Unlike traditional `Ctrl+F` which requires exact text matching, this system uses **Deep Learning** to understand the *meaning* (semantics) of a user's query.

It seamlessly combines **Computer Vision (OCR)** to read images and **NLP (Embeddings)** to understand context. For example, a search for *"financials"* will instantly retrieve an *"Invoice"* document, even if the word "financials" never appears in the text.

### ✨ Key Features
* **📷 OCR Extraction:** Automatically extracts text from scanned images (`.png`, `.jpg`) using **Tesseract**.
* **🧠 Semantic Search:** Uses **Sentence-Transformers** (`all-MiniLM-L6-v2`) to convert text into high-dimensional vectors.
* **⚡ Fast Indexing:** Implements **FAISS** (Facebook AI Similarity Search) for millisecond-level retrieval speeds.
* **🤖 Smart Matching:** Finds documents based on context, not just keywords.
* **💻 Interactive CLI:** Includes a user-friendly Command Line Interface for real-time querying.

---

## 🛠️ Tech Stack

| Component | Technology Used | Purpose |
| :--- | :--- | :--- |
| **Language** | Python 3.10+ | Core logic and pipeline integration |
| **OCR Engine** | Tesseract (pytesseract) | Extracting raw text from pixels |
| **Embeddings** | Sentence-Transformers | Converting text to 384-dim vectors |
| **Vector DB** | FAISS (CPU) | Efficient similarity search & indexing |
| **Interface** | CLI (Python Input) | User interaction loop |

---

## ⚙️ The Pipeline

The system follows a strict 4-stage pipeline to process data:

```mermaid
graph LR
A[Scanned Image] -->|Step 1: OCR| B(Raw Text)
B -->|Step 2: Encoding| C(Vector Embeddings)
C -->|Step 3: Indexing| D[FAISS Database]
E[User Query] -->|Step 4: Search| D
