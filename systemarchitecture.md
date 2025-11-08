

##  **systemArchitecture.md**

```markdown
# System Architecture – The life Line

## 📘 Overview
The life Line is built as a **modular web application** that connects users to a unified communication hub — integrating **voice**, **text**, and **AI-driven summaries**.  

The system is composed of three primary layers:
1. **Frontend (User Interface)**
2. **Backend (API & Business Logic)**
3. **Database & AI Integration**

-----------------------------

## Architecture Summary

### **1. Frontend Layer**
- **Technology:** React (Next.js) + TailwindCSS  
- **Purpose:** Provides a fast, responsive UI for users to manage calls, messages, and view insights.  
- **Communication:** Uses RESTful API requests to interact with the backend.  
- **Key Components:**
  - Login/Signup (Firebase Authentication)
  - Unified Inbox (calls + texts)
  - Call Summary Dashboard
  - Settings & Profile Management

-----------------------------

### **2. Backend Layer**
- **Technology:** Node.js (Express Framework)  
- **Purpose:** Handles user requests, processes communication data, and connects to external APIs (AI, voice, messaging).  
- **Endpoints:**  
  - `/api/auth` – handles user login, signup, and token validation  
  - `/api/calls` – logs and fetches call records  
  - `/api/texts` – manages messages  
  - `/api/ai` – routes transcription and summarization requests to the OpenAI API  

**Security:**  
- JWT-based authentication (managed via Firebase tokens)  
- HTTPS enforcement for all endpoints  
- Input validation and rate limiting

-----------------------------

### **3. Database Layer**
- **Technology:** MongoDB Atlas (Cloud NoSQL)  
- **Collections:**
  - `users` – user profiles and linked phone numbers  
  - `calls` – call metadata, transcripts, and summaries  
  - `messages` – incoming/outgoing text messages  
  - `devices` – registered user devices for synchronization  

**Why MongoDB:**  
- Flexible schema for handling diverse communication records  
- Scalable for high read/write workloads

-----------------------------

### **4. AI & Integration Layer**
- **Technology:** Claude  
- **Functions:**  
  - Converts speech-to-text (transcription)  
  - Summarizes call conversations  
  - Provides smart response suggestions  

**Workflow:**  
Frontend → Backend → OpenAI API → Backend stores results → Frontend displays summaries  

-----------------------------

### **5. Hosting & Deployment**
- **Frontend:** Hosted on **Vercel** (for optimized React builds)  
- **Backend:** Hosted on **Render** (Node.js server environment)  
- **Database:** Hosted on **MongoDB Atlas **  
- **CI/CD:** GitHub Actions for automated testing and deployment

-----------------------------

##  Data Flow Diagram (Textual Overview)

