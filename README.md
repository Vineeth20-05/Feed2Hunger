# 🚀 HireIQ

## AI-Powered Recruitment Intelligence Platform

HireIQ is a production-deployed AI recruitment platform that transforms traditional resume screening into an intelligent, semantic, and automated hiring workflow.

The platform combines **AI-powered candidate screening, semantic resume matching, ATS analysis, talent search, interview planning, and recruiter assistance** within a unified recruitment ecosystem.

Built using a **Django + FastAPI microservices architecture**, HireIQ integrates semantic embeddings, vector search, RAG, and LLM-powered analysis with a production-ready cloud and DevOps pipeline.

---

## 📌 Overview

Traditional recruitment systems often depend heavily on manual resume screening and exact keyword matching, making candidate evaluation slow and potentially overlooking relevant applicants.

HireIQ addresses this by analyzing the **semantic relationship between candidate profiles and job requirements**.

The platform provides dedicated workflows for both recruiters and candidates.

### 👨‍💼 Recruiters can

- Screen and rank multiple candidates
- Analyze candidate suitability for a job role
- Search talent using semantic search
- Identify matched and missing skills
- Generate structured interview questions
- Access AI-assisted recruitment insights

### 👨‍💻 Candidates can

- Analyze their resume against a job description
- View ATS compatibility scores
- Identify matched and missing skills
- Receive AI-generated resume feedback
- Understand strengths and potential risks
- Prepare with role-specific interview questions

---

# ✨ Key Features

## 🎯 AI Candidate Screening

Upload multiple resumes with a job description and automatically:

- Extract resume content
- Generate semantic embeddings
- Calculate job-resume similarity
- Rank candidates by relevance
- Shortlist suitable applicants
- Generate detailed candidate analysis

---

## 📊 ATS & Candidate Intelligence

HireIQ generates structured AI-powered evaluation reports containing:

- ATS Match Score
- Hiring Recommendation
- Matched Skills
- Missing Skills
- Experience Alignment
- Project Quality Analysis
- Candidate Strengths
- Hiring Risks
- Executive Summary

---

## 🔎 Semantic Talent Search

Recruiters can search for candidates based on skills, technologies, and experience.

Unlike traditional exact keyword search, HireIQ uses **embeddings and vector search** to retrieve contextually relevant candidate profiles.

---

## 🎤 AI Interview Planning

The platform generates role-specific interview questions based on job requirements.

Generated interview plans can contain:

- Technical questions
- Project-based questions
- Skill-specific questions
- Difficulty levels
- Expected answers
- Sample code
- Time and space complexity
- Interviewer evaluation notes

---

## 🤖 AI Recruiter Assistant

HireIQ includes an intelligent recruiter assistant powered by **Retrieval-Augmented Generation (RAG)**.

The assistant combines vector retrieval with LLM generation to provide context-aware responses for recruitment-related queries.

---

# 🛠️ Technology Stack

## Backend

- Python
- Django
- Django REST Framework
- FastAPI
- Gunicorn
- REST APIs
- Microservices Architecture

## AI & Generative AI

- Natural Language Processing
- Sentence Transformers
- Semantic Embeddings
- Cosine Similarity
- Vector Search
- Retrieval-Augmented Generation (RAG)
- LangChain
- OpenAI API
- LLM Integration

## Databases

- PostgreSQL
- ChromaDB

## Frontend

- HTML
- CSS
- JavaScript
- Tailwind CSS
- DaisyUI

## DevOps & Cloud

- Docker
- Docker Compose
- Nginx
- GitHub Actions
- CI/CD
- AWS EC2
- AWS IAM
- AWS SSM
- OIDC Authentication
- Linux
- HTTPS/TLS

---

# 🏗️ System Architecture

```text
                         User Browser
                              │
                              │ HTTPS
                              ▼
                         ┌─────────┐
                         │  Nginx  │
                         └────┬────┘
                              │
                  ┌───────────┴───────────┐
                  │                       │
                  ▼                       ▼
          Django + Gunicorn           FastAPI
          Web Application          AI Microservice
                  │                       │
                  ▼                       ▼
             PostgreSQL          AI / NLP Pipeline
                                          │
                                  ┌───────┴───────┐
                                  │               │
                                  ▼               ▼
                              ChromaDB       LLM Services
                            Vector Store      RAG Engine
```

---

# 🧠 AI Processing Pipeline

```text
Resume Upload
      │
      ▼
Text Extraction
      │
      ▼
Text Preprocessing
      │
      ▼
Embedding Generation
      │
      ▼
Semantic Similarity Analysis
      │
      ▼
Candidate Ranking
      │
      ▼
Vector Storage & Retrieval
      │
      ▼
LLM-Based Candidate Analysis
      │
      ▼
ATS Score + Skills + Recommendation + Feedback
```

---

# 🐳 Containerized Infrastructure

HireIQ is deployed as a multi-container application.

```text
Docker Compose
│
├── Django
│   └── Web Application & Business Logic
│
├── FastAPI
│   └── AI Processing & Inference
│
├── PostgreSQL
│   └── Relational Application Data
│
└── Nginx
    ├── Reverse Proxy
    ├── HTTPS Handling
    ├── Request Routing
    └── Static & Media File Serving
```

The infrastructure includes:

- Persistent Docker volumes
- Container health checks
- Service dependency management
- Internal Docker networking
- Automatic container restart policies

---

# ⚙️ CI/CD Pipeline

HireIQ uses an automated GitHub Actions pipeline for Continuous Integration and Continuous Deployment.

## 🔄 CI Workflow

```text
Push / Pull Request
        │
        ▼
Checkout Repository
        │
        ▼
Set Up Python Environment
        │
        ▼
Install Dependencies
        │
        ▼
Django System Checks
        │
        ▼
Validate Docker Compose
        │
        ▼
Build Docker Images
        │
        ▼
CI Success
```

## 🚀 Production Deployment

```text
Push to Main Branch
        │
        ▼
GitHub Actions
        │
        │ OIDC Authentication
        ▼
AWS IAM Role
        │
        │ Temporary Credentials
        ▼
AWS Systems Manager
        │
        ▼
EC2 Deployment
        │
        ├── Pull Latest Code
        ├── Build Docker Images
        ├── Start Services
        ├── Run Migrations
        ├── Collect Static Files
        ├── Restart Nginx
        └── Run Health Checks
```

The pipeline uses **OIDC federation and temporary AWS credentials**, eliminating the need to store permanent AWS access keys in GitHub.

---

# 🔐 Production Security

The production deployment includes:

- HTTPS/TLS encryption
- Automatic HTTP-to-HTTPS redirection
- Automated TLS certificate renewal
- Environment-based secret management
- AWS IAM role-based permissions
- OIDC authentication for CI/CD
- Private PostgreSQL container networking
- Private FastAPI service networking
- Nginx reverse proxy architecture
- Production health checks

---

# 📁 Project Structure

```text
HireIQ/
│
├── django_app/              # Django web application
│   ├── candidate_portal/    # Candidate intelligence workflows
│   ├── recruiter_portal/    # Recruiter workflows
│   ├── core/                # Django configuration
│   └── manage.py
│
├── ml_api/                  # FastAPI AI microservice
│   ├── main.py
│   ├── AI services
│   └── vector store logic
│
├── nginx/
│   └── nginx.conf           # Reverse proxy configuration
│
├── certbot/
│   └── www/                 # Certificate challenge files
│
├── .github/
│   └── workflows/
│       └── ci.yml           # CI/CD pipeline
│
├── docker-compose.yml       # Multi-container orchestration
├── requirements-django.txt
├── requirements-ml_api.txt
└── README.md
```

---

# ⚙️ Installation & Setup

## 1️⃣ Clone the Repository

```bash
git clone <your-repository-url>
cd HireIQ
```

## 2️⃣ Configure Environment Variables

Create a `.env` file in the project root.

```env
DB_NAME=your_database_name
DB_USER=your_database_user
DB_PASSWORD=your_database_password
DB_HOST=postgres
DB_PORT=5432

DJANGO_SECRET_KEY=your_secret_key
DJANGO_DEBUG=False
DJANGO_ALLOWED_HOSTS=localhost,127.0.0.1

ML_API_URL=http://ml_api:8001

OPENAI_API_KEY=your_api_key
```

> ⚠️ Never commit API keys, database passwords, or production secrets to version control.

## 3️⃣ Build Docker Images

```bash
docker compose build
```

## 4️⃣ Start the Application

```bash
docker compose up -d
```

## 5️⃣ Run Database Migrations

```bash
docker compose exec django python manage.py migrate
```

## 6️⃣ Collect Static Files

```bash
docker compose exec django python manage.py collectstatic --noinput
```

## 7️⃣ Verify Services

```bash
docker compose ps
```

---

# 📸 Application Preview

Add screenshots of the main workflows here.

Recommended screenshots:

- Recruiter Dashboard
- Candidate Screening Workspace
- Candidate Ranking Results
- Detailed ATS Analysis
- Semantic Talent Search
- AI Interview Planning
- Candidate Portal
- Recruiter AI Assistant

---

# 💡 Engineering Highlights

HireIQ demonstrates practical implementation of:

- AI-integrated backend engineering
- Django and FastAPI microservices
- Semantic search and embeddings
- Vector database integration
- Retrieval-Augmented Generation
- LLM-powered structured analysis
- REST API communication
- Multi-container Docker architecture
- Persistent storage
- Container health monitoring
- Nginx reverse proxy configuration
- HTTPS/TLS deployment
- Automated CI/CD
- Secure AWS authentication using OIDC
- IAM-based cloud authorization
- Remote deployment through AWS SSM

---

# 🚀 Future Enhancements

- Asynchronous AI task processing
- Redis caching
- Background task queues
- Automated interview evaluation
- Resume version comparison
- Advanced recruitment analytics
- Cloud object storage for resumes
- Centralized logging and monitoring
- Automated database backups
- Horizontal AI service scaling
- Expanded automated testing

---

# 🎯 Learning Outcomes

This project was built to gain practical experience in:

- Backend and microservices architecture
- AI integration in production applications
- Semantic search and vector databases
- RAG-based application development
- REST API design
- Docker-based deployment
- Cloud infrastructure
- CI/CD automation
- Secure cloud authentication
- Production HTTPS configuration
- Linux server administration

---

# 👨‍💻 Author

## Vineeth M Gowda

Computer Science & Engineering  
Dayananda Sagar College of Engineering

**GitHub:** Add your GitHub profile link  
**LinkedIn:** Add your LinkedIn profile link

---

# ⚠️ Responsible AI Disclaimer

HireIQ is an educational and engineering project designed to demonstrate AI-assisted recruitment workflows.

AI-generated candidate scores, recommendations, and analysis are intended to support human decision-making and should not be used as the sole basis for employment decisions.

---

⭐ If you find HireIQ interesting, consider starring the repository.

**Built with AI, backend engineering, and cloud infrastructure.**
