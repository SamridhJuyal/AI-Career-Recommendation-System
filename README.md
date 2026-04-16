# Ai-Powered-career-Recommendation


A full-stack AI-powered career assistant that helps users find relevant job roles, generate and improve resumes to pass applicant tracking systems (ATS), and learn the exact skills they need via curated research and learning roadmaps.

---

## Demo / Screenshots
*(Attach screenshots / GIFs here)*

- Job suggestion UI (natural language query)
- ATS score & resume rewrites
- Research Assistant (RAG-style) with papers, sources, and roadmap
- Resume preview & PDF export

---

## Features

- **Natural-language Job Search** — enter free-text queries (e.g., “Remote Python backend roles in Bengaluru with 8 LPA min”), results from Adzuna.
- **NLP extraction** — extract role, skills, location, salary intent from the query.
- **Resume Generator & Rewriter** — generative AI creates or rewrites resumes optimized for ATS.
- **ATS Scoring & Suggestions** — compares resume against a JD and returns a match score + prioritized suggestions to improve ATS fit.
- **Research Assistant (RAG)** — retrieve latest articles, papers, and curated resources for any topic and produce a learning roadmap.
- **User profile & save** — optional user profiles to store resumes, job searches and suggested learning paths (MongoDB support).
- **Modular LLM provider** — works with OpenRouter, OpenAI, or other providers via pluggable settings.

---

## Tech stack

- **Frontend:** React / Next.js, Tailwind CSS
- **Backend:** Python, FastAPI (REST)
- **NLP & ML:** Transformers / LLMs, sentence-transformers, spaCy (configurable)
- **Job API:** Adzuna
- **Vector DB (optional):** FAISS / Pinecone / Milvus (for retrieval)
- **Database (optional):** MongoDB
- **Deployment:** Docker / Vercel / Render / any cloud provider

---

## Architecture (high-level)

1. Frontend (Next.js) — UI for job search, resume editing, ATS feedback, research assistant.
2. API Server (FastAPI) — endpoints for job search, resume generation, scoring and retrieval.
3. External integrations:
   - Adzuna for job listings
   - LLM provider (OpenRouter/OpenAI) for generation & rewriting
   - Vector store for document retrieval
4. Optional persistence: MongoDB for user data, saved resumes, and feedback.

---

## Quick start (local)

> These commands assume the repo contains `frontend/` and `backend/` folders. Adjust paths if different.

### 1) Clone
```bash
git clone https://github.com/<your-username>/ai-ml-career-toolkit.git
cd ai-ml-career-toolkit

cd backend
python -m venv .venv
source .venv/bin/activate        # macOS / Linux
.venv\Scripts\activate           # Windows PowerShell

pip install -r requirements.txt
# Run FastAPI
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000

Frontend (Next.js)
cd ../frontend
npm install
npm run dev
# opens at http://localhost:3000


