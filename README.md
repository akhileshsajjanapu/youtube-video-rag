# YouTube Video RAG 🎥🤖

Ask questions about YouTube videos and get answers grounded in their transcripts using **Retrieval-Augmented Generation (RAG)**.

This project demonstrates an AI-powered question-answering system that extracts YouTube transcripts, processes the content into semantic chunks, stores them in ChromaDB, retrieves relevant information, and generates context-based answers using Google Gemini.

## 🚀 Features

- **YouTube Transcript Extraction:** Retrieves transcript text from YouTube videos using the YouTube Transcript API.
- **Intelligent Text Chunking:** Splits transcript content into manageable chunks using LangChain's RecursiveCharacterTextSplitter.
- **Vector Database:** Stores transcript chunks in ChromaDB for efficient retrieval.
- **Semantic Search:** Retrieves relevant transcript sections based on user questions.
- **LLM-Powered Answers:** Uses Google Gemini to generate natural-language responses from retrieved context.
- **Context-Aware Generation:** Instructs the LLM to answer using the retrieved transcript information.
- **Interactive Notebook:** Explore and execute the complete RAG workflow using Google Colab or Jupyter Notebook.

## 🧠 Project Architecture

The system follows a Retrieval-Augmented Generation architecture.

```text
        YouTube Video
              |
              v
    Transcript Extraction
              |
              v
       Text Processing
              |
              v
      Semantic Chunking
              |
              v
       ChromaDB Storage
              |
              v
       User Question
              |
              v
      Semantic Retrieval
              |
              v
     Relevant Transcript
              |
              v
      Context Construction
              |
              v
       Google Gemini LLM
              |
              v
      Generated Answer
```

### Workflow

1. Extract the transcript from a YouTube video.
2. Process and clean the transcript text.
3. Split the transcript into overlapping chunks.
4. Store the chunks in ChromaDB.
5. Accept a question from the user.
6. Retrieve relevant transcript chunks.
7. Construct a context-based prompt.
8. Generate an answer using Google Gemini.

## 🛠️ Tech Stack

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Generative AI | Google Gemini API |
| Framework | LangChain |
| Vector Database | ChromaDB |
| Embeddings | Sentence Transformers |
| Embedding Model | all-MiniLM-L6-v2 |
| Transcript Extraction | YouTube Transcript API |
| Text Processing | LangChain Text Splitters |
| Development Environment | Google Colab, Jupyter Notebook |

## 📂 Project Structure

```text
youtube-video-rag/
│
├── README.md
│
├── requirements.txt
│
├── youtube_rag.ipynb
│
└── youtube_rag.py
```

### Files

- `youtube_rag.ipynb` — Main notebook containing the RAG workflow.
- `youtube_rag.py` — Python implementation and experimental workflow.
- `requirements.txt` — Project dependencies.
- `README.md` — Project documentation.

**Note:** The current Python file contains notebook-style commands. The notebook is the recommended starting point for executing the project.

## ⚙️ Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/akhileshsajjanapu/youtube-video-rag.git
```

Navigate to the project directory:

```bash
cd youtube-video-rag
```

### 2. Install Dependencies

Install the required Python packages:

```bash
pip install -r requirements.txt
```

For the Sentence Transformers embedding experiment:

```bash
pip install sentence-transformers
```

### 3. Configure Google Gemini API

Create an API key through [Google AI Studio](https://aistudio.google.com/).

For Google Colab:

1. Open the notebook.
2. Navigate to Secrets.
3. Create a secret named `api_key`.
4. Add your Gemini API key.
5. Allow the notebook to access the secret.

**Security:** Never upload API keys or credentials to GitHub.

### 4. Run the Project

Open the notebook:

```text
youtube_rag.ipynb
```

Run the notebook cells sequentially.

The current implementation uses a predefined YouTube video ID. Replace it with the ID of your target video.

Example:

```python
video_id = "YOUR_YOUTUBE_VIDEO_ID"
```

## 💡 Example

### User Question

```text
What does the speaker say about gratitude?
```

### Processing

The system:

1. Retrieves the transcript.
2. Splits it into chunks.
3. Searches for relevant transcript content.
4. Constructs a prompt using the retrieved context.
5. Sends the prompt to Google Gemini.

### Expected Output

A natural-language answer based on the retrieved transcript.

The generated answer depends on the selected video and the available transcript.

## 🔍 Retrieval-Augmented Generation

This project demonstrates the fundamental components of a RAG pipeline.

### 1. Data Ingestion

The YouTube Transcript API retrieves transcript text from the selected video.

### 2. Text Chunking

LangChain's RecursiveCharacterTextSplitter divides the transcript into smaller chunks.

Current configuration:

```python
chunk_size = 500
chunk_overlap = 100
```

### 3. Vector Storage

ChromaDB stores transcript chunks and supports similarity-based retrieval.

### 4. Retrieval

The system retrieves relevant chunks based on the user's question.

### 5. Generation

Google Gemini receives the retrieved context and generates an answer.

## 📦 Requirements

The main dependencies are:

```text
google-generativeai
chromadb
youtube-transcript-api
langchain-text-splitters
```

Additional package:

```bash
pip install sentence-transformers
```

## 🔐 Security and Limitations

- Gemini API access requires a valid API key.
- YouTube transcript availability depends on the video and its captions.
- API usage may be subject to quotas, rate limits, and billing.
- The current implementation does not provide verified timestamp citations in generated answers.
- Sentence Transformer embeddings are computed in the notebook, but the current ChromaDB collection does not explicitly use those embeddings for retrieval.
- The current implementation uses a predefined video ID rather than accepting arbitrary YouTube URLs through a complete user interface.

## 🚧 Future Enhancements

- [ ] Support direct YouTube URL input.
- [ ] Implement timestamp-aware transcript extraction.
- [ ] Add timestamp citations to generated answers.
- [ ] Integrate Sentence Transformer embeddings consistently with ChromaDB.
- [ ] Improve chunk metadata and document filtering.
- [ ] Build an interactive Streamlit interface.
- [ ] Add conversation history and follow-up questions.
- [ ] Implement retrieval evaluation and answer-quality assessment.
- [ ] Add error handling for unavailable transcripts and API failures.
- [ ] Improve modularity and production deployment readiness.

## 🎯 Learning Outcomes

Through this project, I explored:

- Retrieval-Augmented Generation architecture.
- LLM-based question answering.
- Semantic text chunking.
- Vector database integration.
- Embedding-based retrieval concepts.
- Prompt engineering.
- Google Gemini API integration.
- End-to-end AI application development.

## 🤝 Contributions

Suggestions, improvements, and contributions are welcome.

Feel free to open an issue or submit a pull request.

## 📄 License

No license is currently specified for this repository.

Please contact the repository owner before reusing or distributing the project.

---

**Developed by Akhilesh Sajjanapu**

AI/ML Engineer | Generative AI | Retrieval-Augmented Generation

[GitHub](https://github.com/akhileshsajjanapu)

[LinkedIn](https://www.linkedin.com/in/akhilesh-sajjanapu/)
