# 🤖 Intelligent HR Assistant Bot

An AI-powered HR assistant that intelligently matches candidate resumes to recruiter queries using embeddings, vector similarity search, and conversational AI. The system automates resume parsing, semantic search, and contextual responses with memory.

---

## 🚀 Project Overview

The **Intelligent HR Assistant Bot** allows recruiters and HR teams to:

* Upload and process resumes automatically (via Gmail)
* Generate semantic embeddings of resume content
* Store and search resumes using vector similarity (cosine similarity)
* Ask natural language questions like:

  > "Find me a data analyst with Python and SQL experience"
* Receive AI-generated, context-aware responses

The chatbot interface mimics a **ChatGPT-style UI**, while the backend is orchestrated using **n8n**, **Supabase Vector Store**, and **LLMs**.

---

## 🧠 Key Features

* 📄 **Automated Resume Ingestion** (Gmail → Text → Cleaned Content)
* 🧩 **AI-based Resume Parsing** (skills, education, experience, metadata)
* 🔢 **Embeddings Generation** (OpenAI embeddings)
* 📦 **Vector Database Storage** (Supabase + pgvector)
* 🔍 **Semantic Resume Search** using cosine similarity
* 💬 **ChatGPT-like Chatbot Interface** (Next.js)
* 🧠 **Conversation Memory** stored in database
* ⚡ **Real-time Query Embeddings** (no query storage required)

---

## 🏗️ Architecture

```
Frontend (Next.js Chat UI)
        ↓ HTTPS
n8n Webhook (Production URL)
        ↓
AI Agent (Prompt + Memory)
        ↓
Supabase Vector Store (Resume Embeddings)
        ↓
Cosine Similarity Search
        ↓
Respond to Webhook → UI
```

---

## 🛠️ Tech Stack

### Frontend

* **Next.js (App Router)**
* **React**
* **Tailwind CSS**
* **Framer Motion**

### Backend / Orchestration

* **n8n (Cloud)**
* **OpenAI Embeddings**
* **AI Agent Node (LLM)**

### Database

* **Supabase**
* **pgvector** for vector similarity search

---

## 📂 Workflow Highlights (n8n)

* Gmail Trigger → Fetch Attachments
* Binary → Text Conversion
* Text Cleaning & Parsing
* Metadata + Content Alignment
* Resume Embeddings Creation
* Store in Supabase Vector Store
* Query Embeddings (Real-time)
* Cosine Similarity Search
* AI Agent Response
* Respond to Webhook (with CORS support)

---

## 💬 Chatbot UI

* ChatGPT-style chat interface
* Sidebar showing last 2–3 conversations
* Real-time responses from AI agent
* Error handling & loading states
* Connects to n8n via HTTPS webhook

---

## 🔐 Security & Best Practices

* HTTPS-only webhook communication
* No client-side API keys
* Vector search handled server-side
* CORS-safe webhook responses

---

## ⚙️ Setup Instructions (High Level)

1. Deploy **n8n** (Cloud)
2. Configure Supabase with `pgvector`
3. Create resume ingestion & query workflows
4. Activate production webhook
5. Run frontend locally using:

   ```bash
   npm install
   npm run dev
   ```
6. Connect UI to n8n production webhook

---

## 📈 Optimization Considerations

* Chunk resumes before embedding
* Limit chat memory window
* Cache frequent queries
* Reduce token usage in AI agent

---

## 🧪 Example Query

> "Find resumes for a data analyst with Python, SQL, and cloud experience"

**AI Response:**

> Returns best-matching candidates ranked by similarity score with summarized strengths.

---

## 🌟 Future Enhancements

* Resume ranking UI cards
* Candidate confidence score display
* Authentication & user sessions
* Multi-role HR support
* Streaming AI responses

---

## 👩‍💻 Author

**Zainab Waseem**
AI / Data Enthusiast | HR Tech Automation

---

## 📄 License

This project is for educational and portfolio purposes.
