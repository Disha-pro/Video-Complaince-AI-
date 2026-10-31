# Video-Complaince-AI-
AI-powered video compliance auditing system using Python, FastAPI, LangGraph, Azure Video Indexer and LLMs to analyze video content for brand safety, policy violations and compliance risks.

# 🎥 Video Compliance AI

### AI-Powered Video Compliance & Brand Safety Auditing

An AI-powered video analysis system designed to audit YouTube video content against brand compliance and safety guidelines.

The project combines video intelligence, workflow orchestration, and LLM-based reasoning to build a pipeline for extracting video information and identifying potential compliance risks.

> **Project status:** Active development. FastAPI server and API endpoints are operational. End-to-end video processing and transcript extraction are currently being debugged.

---

## 🎯 Project Objective

Build an automated system that can:

- Accept a YouTube video URL.
- Extract video content and metadata.
- Process video content using Azure Video Indexer.
- Extract transcripts and OCR information.
- Analyze content against compliance guidelines.
- Identify potential brand safety and policy risks.
- Return structured compliance results.

## 🏗️ Architecture

```text
                  YouTube Video URL
                         |
                         v
                   FastAPI Backend
                         |
                         v
                   LangGraph Workflow
                         |
              +----------+----------+
              |                     |
              v                     v
         Video Indexer          Audit Engine
         (Azure)                (LLM-based)
              |                     |
              v                     v
       Transcript & OCR       Compliance Analysis
              |                     |
              +----------+----------+
                         |
                         v
                 Structured JSON
                  Audit Report
```

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python 3.12 | Backend development |
| FastAPI | REST API |
| LangGraph | Workflow orchestration |
| Azure Video Indexer | Video intelligence and transcription |
| Azure OpenAI | LLM-based analysis |
| Azure AI Search | Compliance knowledge retrieval |
| yt-dlp | YouTube video downloading |
| Swagger UI | API testing |

## ⚙️ Current API Endpoints

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/health` | Health check |
| POST | `/audit` | Submit a video for auditing |
| GET | `/docs` | Interactive API documentation |

### Example Request

```json
{
  "video_url": "https://www.youtube.com/watch?v=YOUR_VIDEO_ID"
}
```

### Example Response Structure

```json
{
  "session_id": "unique-session-id",
  "video_id": "video-id",
  "status": "FAIL",
  "final_report": "Audit skipped because video processing failed (No Transcript).",
  "compliance_results": []
}
```

The response above represents the initial test result, not a successful audit.

## 🚀 Local Setup

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/video-compliance-ai.git
cd video-compliance-ai
```

### 2. Create the Python environment

```bash
uv venv --python 3.12
```

### 3. Install dependencies

```bash
uv sync --python 3.12
```

### 4. Configure environment variables

Create a `.env` file using `.env.example` as a template.

Configure the required Azure services and credentials locally. Never commit your actual `.env` file.

### 5. Start the API server

```powershell
$env:PYTHONPATH = "$PWD\backend"
uv run --python 3.12 uvicorn backend.src.api.server:app --reload --app-dir backend
```

### 6. Open API documentation

```text
http://127.0.0.1:8000/docs
```

## 📊 Development Progress

- [x] Python 3.12 environment configured
- [x] Dependencies installed
- [x] FastAPI backend started
- [x] Swagger API documentation available
- [x] Health and audit endpoints operational
- [x] Azure ARM authentication token acquired
- [x] Azure AI Search indexing and retrieval tested
- [ ] Complete Azure Video Indexer account-token integration
- [ ] Complete video upload and transcript extraction
- [ ] Verify end-to-end LangGraph execution
- [ ] Generate and validate final compliance reports

## 🔐 Security

- Keep API keys and connection strings in environment variables.
- Never commit `.env` files.
- Use appropriate Azure access permissions.
- Do not publish private credentials or customer video data.

## 🔮 Planned Enhancements

- Detailed compliance scoring.
- Risk categorization and severity assessment.
- Evidence-based violation reporting.
- Video processing status tracking.
- Production deployment and monitoring.
- Interactive compliance dashboard.

---

## 👩‍💻 Author

**Disha Sonkar**

AI Engineering | Generative AI | Agentic AI | Data Analytics

GitHub: https://github.com/Disha-pro

---

*Built as an applied AI engineering project exploring video intelligence, workflow orchestration, and automated compliance analysis.*
