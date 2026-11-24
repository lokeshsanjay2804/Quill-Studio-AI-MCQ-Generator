# Quill Studio – AI-Based MCQ & Quiz Generator

**Quill Studio** is an AI-assisted educational application that automatically generates Multiple Choice Questions (MCQs) from uploaded study materials. It helps students and educators convert lengthy PDF documents into interactive quizzes, making learning, revision, and assessment more efficient.

## Overview

Preparing questions manually from lengthy study materials can be time-consuming. Quill Studio simplifies this process by extracting text from documents, identifying relevant content, and generating MCQs that users can review and attempt.

The application combines document processing, Retrieval-Augmented Generation (RAG), semantic search, and question-generation techniques.

## Key Features

- **PDF Upload:** Upload study materials in PDF format.
- **Text Extraction:** Extract text from uploaded documents.
- **Document Chunking:** Divide lengthy documents into smaller sections for processing.
- **Semantic Search:** Retrieve relevant document content using text embeddings and FAISS.
- **MCQ Generation:** Generate multiple-choice questions using the available rule-based generation system.
- **Optional AI Generation:** Supports a Hugging Face Transformers-based generation pipeline when configured.
- **Interactive Quiz:** Attempt generated questions and evaluate your answers.
- **Results:** View quiz performance and results.
- **Fallback Retrieval:** Supports keyword-based retrieval when FAISS is unavailable.

## Technology Stack

| Component | Technology |
|---|---|
| Programming Language | Python |
| Frontend | Streamlit |
| Backend | Python |
| Document Processing | PDF text extraction |
| Embedding Model | sentence-transformers/all-MiniLM-L6-v2 |
| Vector Search | FAISS |
| AI Model Support | Hugging Face Transformers |
| Example Generation Model | google/flan-t5-small |
| Data Storage | SQLite |

## System Workflow

1. User uploads a PDF document.
2. The application extracts text from the document.
3. Extracted text is divided into smaller chunks.
4. The embedding model converts text chunks into numerical vectors.
5. FAISS performs similarity search to retrieve relevant chunks.
6. The question-generation component creates MCQs using the retrieved content.
7. Users review the generated questions and attempt the quiz.
8. The application displays the quiz results.

## Architecture

```text
             User
               |
               v
        Streamlit Interface
               |
               v
        Python Backend
               |
               v
         PDF Processing
               |
               v
        Text Extraction
               |
               v
         Text Chunking
               |
               v
       Embedding Generation
               |
               v
        FAISS Retrieval
               |
               v
       MCQ Generation
               |
               v
       Interactive Quiz
               |
               v
         Results Display
```

## Models and Retrieval

### Embedding Model
The project uses `sentence-transformers/all-MiniLM-L6-v2` to convert document chunks into numerical embeddings for semantic similarity search.

### FAISS
FAISS is used to efficiently search for similar vectors and retrieve relevant document chunks. It is a retrieval component, not a question-generation model.

### Question Generation
The default generation configuration uses a rule-based approach. An optional Hugging Face Transformers pipeline supports model-based generation, with `google/flan-t5-small` as an example configuration.

**Note:** Model-based generation is optional and depends on the project configuration and model availability.

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/Quill-Studio-AI-MCQ-Generator.git
```

### 2. Navigate to the project folder

```bash
cd Quill-Studio-AI-MCQ-Generator
```

### 3. Create a virtual environment

```bash
python -m venv .venv
```

### 4. Activate the environment

**Windows PowerShell:**

```powershell
.\.venv\Scripts\Activate.ps1
```

### 5. Install dependencies

```bash
pip install -r requirements.txt
```

### 6. Run the application

```bash
python -m streamlit run app.py
```

The application should open in your browser at:

```text
http://localhost:8501
```

## Project Structure

```text
Quill-Studio/
│
├── app.py
├── backend/
│   └── app.py
├── src/
│   └── streamlit_ui.py
├── requirements.txt
├── README.md
└── .gitignore
```

*The structure above is representative. Additional modules and folders may be present in the repository.*

## Future Improvements

- Improve MCQ quality and difficulty-level control.
- Add support for more document formats.
- Improve multilingual question generation.
- Add more AI-based question-generation models.
- Introduce user authentication and personalized learning history.
- Deploy the application for public access.

## Learning Outcomes

This project provided practical experience in:

- Python application development.
- Streamlit-based interface development.
- Natural Language Processing concepts.
- Text embeddings and semantic search.
- Retrieval-Augmented Generation.
- Integrating machine-learning models into applications.
- Testing and debugging a full-stack Python project.

## Contributors

Developed as an academic team project.

- Contributor 1 – [Name]
- Contributor 2 – [Name]
- Contributor 3 – [Name]

## License

This project is intended for educational and academic purposes.