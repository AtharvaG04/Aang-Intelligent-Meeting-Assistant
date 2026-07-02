# 🎙️ Aang – AI Meeting Intelligence Assistant

> Transform recorded meetings into searchable knowledge using AI.

Aang is an AI-powered Meeting Intelligence Assistant that automatically converts meeting recordings into structured Minutes of Meeting (MoM), generates concise summaries, extracts action items and key decisions, and enables users to chat with meeting transcripts using Retrieval-Augmented Generation (RAG).

Designed for organizations to improve productivity, knowledge sharing, and meeting documentation, Aang supports both YouTube meeting recordings and uploaded audio files through an intuitive Streamlit interface.

---

## 🚀 Features

- 🎥 Process meeting recordings from **YouTube URLs**
- 📁 Upload local audio files (WAV, MP3, M4A, etc.)
- 🎤 Accurate speech-to-text transcription using **OpenAI Whisper**
- 🌍 Hindi/Hinglish to English transcription using **Sarvam AI**
- 📝 Automatic Minutes of Meeting (MoM) generation
- 📌 Extract Action Items
- ✅ Identify Key Decisions
- 📖 Generate concise meeting summaries
- 💬 Chat with meeting transcripts using **RAG**
- 🔍 Semantic search powered by **ChromaDB**
- 📄 Export meeting reports as PDF and TXT
- 🖥️ Interactive Streamlit dashboard

---

# 🏗️ System Architecture

```text
                    User
                      │
                      ▼
              Streamlit Interface
                      │
          ┌───────────┴───────────┐
          │                       │
     YouTube URL             Local Audio
          │                       │
          ▼                       ▼
      yt-dlp Download       Audio Conversion
                  │
                  ▼
          Audio Preprocessing
                  │
                  ▼
          Audio Chunking
                  │
                  ▼
         Speech Recognition
          │                 │
          │                 │
      English          Hindi/Hinglish
          │                 │
     Whisper         Sarvam AI
          │                 │
          └─────────Transcript────────┘
                        │
                        ▼
              LangChain Text Splitter
                        │
                        ▼
            HuggingFace Embeddings
                        │
                        ▼
                  ChromaDB
                        │
         ┌──────────────┴──────────────┐
         ▼                             ▼
  Meeting Summarization          RAG Chatbot
         │                             │
         ▼                             ▼
     Mistral LLM               Semantic Retrieval
         │
         ▼
Summary • Action Items • Key Decisions
```

---

# 💡 Enterprise Use Cases

This application is useful for:

- Daily Stand-up Meetings
- Sprint Planning
- Client Meetings
- Product Discussions
- HR Interviews
- Team Sync Meetings
- Sales Calls
- Training Sessions
- Technical Discussions

Instead of replaying long meeting recordings, employees can simply ask:

- "What was decided about the deployment?"
- "Who is responsible for the API integration?"
- "What are the pending action items?"
- "Summarize yesterday's client meeting."

---

# 🛠 Tech Stack

### Programming Language

- Python

### Speech Processing

- OpenAI Whisper
- Sarvam AI Speech-to-Text

### LLM

- Mistral AI

### GenAI Framework

- LangChain (LCEL)

### Retrieval-Augmented Generation

- ChromaDB
- HuggingFace Embeddings

### Audio Processing

- yt-dlp
- Pydub
- FFmpeg

### Frontend

- Streamlit

---

# 📂 Project Structure

```
Aang-AI-Meeting-Assistant
│
├── app.py
├── main.py
├── core/
│   ├── transcriber.py
│   ├── summarizer.py
│   ├── extractor.py
│   ├── vector_store.py
│   └── rag_engine.py
│
├── utils/
│   └── audio_processor.py
│
├── downloads/
├── vector_db/
├── requirements.txt
├── README.md
└── .env.example
```

---

# ⚙️ Installation

Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/Aang-AI-Meeting-Assistant.git

cd Aang-AI-Meeting-Assistant
```

Install dependencies

```bash
uv sync
```

or

```bash
pip install -r requirements.txt
```

Create a `.env` file

```env
SARVAM_API_KEY=YOUR_API_KEY
MISTRAL_API_KEY=YOUR_API_KEY

WHISPER_MODEL=base
```

Run the application

```bash
streamlit run app.py
```

---

# 📖 Workflow

1. Upload an audio file or provide a YouTube meeting URL.
2. Audio is downloaded and converted into WAV format.
3. Audio is divided into smaller chunks.
4. Whisper (or Sarvam AI) transcribes the meeting.
5. LangChain processes the transcript.
6. Mistral generates:
   - Meeting Summary
   - Action Items
   - Key Decisions
7. Transcript is embedded using HuggingFace Embeddings.
8. Embeddings are stored in ChromaDB.
9. Users can ask questions about the meeting using the RAG chatbot.
10. Reports can be exported as PDF or TXT.

---

# 🎯 Example Questions

- Summarize this meeting.
- What were the major decisions?
- List all action items.
- Who is assigned which task?
- What deadlines were discussed?
- What was decided regarding the deployment?
- Explain the discussion about database migration.

---

# 🔮 Future Enhancements

- Live meeting transcription
- Speaker diarization
- Microsoft Teams integration
- Google Meet integration
- Zoom integration
- Meeting calendar sync
- Email meeting summaries
- Slack & Microsoft Teams notifications
- Multi-language support
- Cloud deployment

---

# 📸 Screenshots

> Add screenshots of the application here.

- Home Page
- Meeting Summary
- RAG Chat Interface
- Action Items
- Exported PDF

---

# ⭐ Key Highlights

- End-to-End AI Meeting Intelligence Platform
- Speech-to-Text using Whisper
- Hindi/Hinglish Translation with Sarvam AI
- Retrieval-Augmented Generation (RAG)
- LangChain LCEL Pipeline
- ChromaDB Vector Database
- Semantic Search over Meeting Knowledge
- Interactive Streamlit Interface
- Enterprise Meeting Documentation Automation

---

# 👨‍💻 Author

**Atharva Gujarathi**

LinkedIn: https://www.linkedin.com/in/YOUR_LINKEDIN

GitHub: https://github.com/YOUR_GITHUB
