# IITB Basic Guide: PDF Q&A Chatbot[cite: 1]

This repository contains a Jupyter Notebook implementation of a Retrieval-Augmented Generation (RAG) chatbot[cite: 1]. The application allows users to upload PDF documents and ask questions based on their contents[cite: 1]. It utilizes FAISS for vector retrieval, Hugging Face models for text embeddings, and the Google Gemini API to generate accurate, context-aware answers[cite: 1]. 

---

## Features

* **PDF Document Ingestion:** Upload one or multiple PDF files directly into the environment and extract text automatically using `PyPDF2`[cite: 1].
* **Intelligent Text Chunking:** Splits long documents into manageable chunks (default size of 200 characters with an overlap of 40 characters) to preserve context during retrieval[cite: 1].
* **Vector Search Engine:** Generates embeddings using the `all-MiniLM-L6-v2` model and stores them in a FAISS vector database (`IndexFlatIP` with L2 normalization) for fast, semantic similarity searches[cite: 1].
* **AI-Powered Responses:** Integrates with the Google Gemini API (`gemini-3.5-flash` model) to answer user queries strictly based on the provided document context[cite: 1].
* **Built-in Hallucination Prevention:** Refuses to answer queries if the retrieval confidence score falls below a set threshold (0.20) or if the information is not present in the text[cite: 1].
* **Interactive Web UI:** Uses Gradio to launch a user-friendly chat interface ("IITB Basic Guide") directly from the notebook, displaying both the AI's answer and the cited source documents[cite: 1].

---

## Prerequisites

To run this notebook, you will need the following dependencies installed in your Python environment[cite: 1]:

* `PyPDF2`
* `torch`
* `faiss-cpu`
* `transformers`
* `sentence-transformers`
* `huggingface-hub`
* `tokenizers`
* `google-genai`
* `gradio`

**Required API Keys:**
* **Google Gemini API Key:** Required for the text generation model[cite: 1].
* **Hugging Face Access Token:** Required to download the embedding model weights[cite: 1].

---

## Setup and Usage Instructions

1. **Configure API Keys:** Open `FinalProject.ipynb` and replace the placeholder strings in the first cell with your actual API keys[cite: 1]:
    * Replace `gemini_key` with your Google Gemini API key[cite: 1].
    * Replace `hf_token` with your Hugging Face access token[cite: 1].
2. **Run the Initialization Cells:** Execute the first cell to install all required dependencies[cite: 1].
3. **Upload Documents:** When prompted by the `files.upload()` widget, select and upload the PDF documents you wish to query[cite: 1].
4. **Process Documents:** Run the subsequent cells sequentially. The script will:
    * Extract the text from your uploaded PDFs[cite: 1].
    * Chunk the text and generate embeddings[cite: 1].
    * Build the FAISS vector database[cite: 1].
5. **Launch the Chatbot:** Run the final cell to start the Gradio web application[cite: 1]. A public URL will be generated, allowing you to access the chat interface and start asking questions about your documents[cite: 1].
