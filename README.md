# 🎥 Multimodal AI ChatBot for YouTube Video QA

This is the final Ironhack NLP project by **shatha Kamal**, designed to build a production-ready, multimodal AI chatbot. The system accepts YouTube audio/video, transcribes it using Whisper, and enables multilingual natural language queries using LangChain agents and LangSmith traceability.

---

## 🎯 Project Goal

To create a multimodal, multilingual, AI-powered chatbot that allows users to ask questions about YouTube video content — combining audio processing, text analysis, and vector-based retrieval.

Use cases include:
- Improving accessibility for hearing-impaired users.
- Enabling efficient navigation and search within long videos.
- Supporting educational content summarization and QA.

---

## 🧠 System Architecture

1. **YouTube Video Input** or MP3 audio file.
2. **Transcription** using Whisper (chunked if needed).
3. **Text Chunking** with LangChain's RecursiveCharacterTextSplitter.
4. **Vector Storage** with ChromaDB.
5. **Retrieval + LLM Agent** via LangChain Tools + `initialize_agent`.
6. **Tracing** and interaction logging via LangSmith.

```
[Video/Audio] → Whisper → Text → Chunks → Chroma → LangChain Agent → Answer
```

---

## 🔬 Methodology

- Built with modular functions for whisper loading, transcription, chunking, embedding, and QA.
- Integrated LangSmith’s `@traceable` for full run tracking and debugging.
- Chroma vector store was selected for persistent local indexing.
- Testing was performed on multilingual transcripts (English, Arabic, Chinese).
- Agent actions and final answers are validated through trace visualization.

---

## 🛠️ Setup Instructions

### 1. Clone the Repo

```bash
git clone https://github.com/yourname/yt-qa-bot.git
cd yt-qa-bot
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

Make sure you have `ffmpeg` installed and added to PATH.

### 3. Create `.env` File or Set Keys

```
OPENAI_API_KEY=your_openai_key
LANGCHAIN_API_KEY=your_langsmith_key
LANGCHAIN_TRACING_V2=true
LANGSMITH_PROJECT=Doha_Final_Project
```

### 4. Run the Notebook

```
AI ChatBot for YouTube Video QA.ipynb
```

---

## 📁 Repository Structure

```
├── ChatBot_Chunked_Clean.ipynb     # Main notebook
├── README.md                       # Project documentation
├── requirements.txt                # Required Python packages
├── /downloads                      # Audio files
├── /db                             # Chroma vector store
```

---

## 🌐 Live Demo

👉 [Click here to try the app live](https://drive.google.com/drive/folders/1TFWhXsA0E16b5_2BF_rM3gRJm7GzReHl?usp=drive_link)  


---

## ❓ Sample Questions

- "What is the video about?"
- "Summarize the key message in Arabic."
- "Who is the speaker talking about?"
- "ما الفكرة الرئيسية في هذا الفيديو؟"

---

## 🖼️ Presentation Slides

A detailed presentation is included separately. It covers:
- Project motivation and use case
- Pipeline architecture and tools
- Evaluation results and limitations
- Future improvements

> 📍 File: `Smart Video QA Bot.pptx`

---

## 📌 Notes

- Whisper uses chunking for large files (>25MB).
- LangSmith `@traceable` is used for complete observability.
- Agent is built using `initialize_agent()` with tool descriptions.
- Works offline (Chroma persistence) and can be deployed as a web app.

---

## 👩‍💻 Author

Prepared with  by **shatha kamal;**  
Ironhack 2025 – Final Project (NLP Track)
