# 📄 AI-Powered Document Q&A

This project is a minimal prototype that allows users to **upload a document (PDF/TXT ≤ 2 MB)** and then ask natural language questions about its contents. The answers are generated **strictly from the uploaded document**, with a safe fallback when the answer is not found.

---

## 🚀 Setup Instructions

### Prerequisites
- Python 3.9+
- Jupyter Notebook or Google Colab
- Basic knowledge of running notebooks

### Steps

1. **Clone or download this repository** and place both notebooks in the same directory:
   - `front-end.ipynb` — user interface (Gradio web app)
   - `model.ipynb` — document processing and question-answering logic

2. **Install dependencies** inside each notebook by running the provided setup cells. They install:
   - `gradio`
   - `pdfplumber`
   - `scikit-learn`
   - `transformers`
   - `accelerate`

3. **Run `model.ipynb`** first:
   - This notebook handles document parsing, chunking, retrieval, and LLM question answering.

4. **Run `front-end.ipynb`** next:
   - Launches a Gradio-based web interface (dark-themed, centered, smoother buttons).
   - Upload your PDF/TXT file (≤ 2 MB).
   - Ask questions via the chat UI.

5. **Test with the included sample document**  
   Try uploading `sample_test_doc.pdf` and asking:
   - *What is Flutter?*
   - *What is the capital of France?*
   - *How many days does Earth take to revolve around the Sun?*

---

## 📌 Assumptions Made
- Users will run notebooks either in **Google Colab** (recommended for simplicity) or **locally** with Jupyter.
- Only **PDF** and **TXT** files are supported.
- Maximum file size is **2 MB**, to keep runtime fast and memory-friendly.
- Answers must come strictly from the uploaded document; if not found, the model must say:
  > *I couldn’t find that in the provided document.*
- No persistent storage — documents and chunks exist only for the notebook session.
- Small open-source models (e.g., Flan-T5) are used to avoid API costs.

---

## 💡 Potential Improvements
- **Support larger documents** with vector DBs (FAISS, Chroma) instead of TF-IDF.
- **OCR integration** for scanned PDFs.
- **Citation highlighting** in answers (pointing to exact document snippet).
- **Multi-document Q&A** (upload several docs at once).
- **Authentication & persistence** if deployed for multiple users.
- **Flutter frontend** (planned) to integrate with this backend, for mobile/web deployment.
- **Docker containerization** for easier setup.
- **Streaming answers** in the UI for a more conversational feel.
