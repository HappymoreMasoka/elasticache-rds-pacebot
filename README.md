# 🎓 PaceBot – AI Chatbot for Graduate Program Discovery

PaceBot is an intelligent chatbot built to help prospective students explore and apply to graduate programs at Pace University. It uses semantic search for program matching, a MySQL RDS database for persistent storage, and Redis (via ElastiCache) for caching to improve performance.

---

## 🌟 Features

- 💬 Conversational AI chatbot (text-based)
- 🔍 Semantic search for graduate programs using Sentence Transformers
- ✅ Application form collection and saving to Amazon RDS (MySQL)
- ⚡ Fast repeated search via Redis (Amazon ElastiCache)
- 📦 Modular Python code, easy to extend

---

## 🏗️ Architecture

                 ┌────────────────────┐
                 │     User Chat      │
                 └────────┬───────────┘
                          │
                          ▼
                ┌────────────────────┐
                │   PaceBot Logic    │
                └────────┬───────────┘
          ┌──────────────┴──────────────┐
          ▼                             ▼
┌────────────────────┐        ┌────────────────────┐
│    Redis Cache     │        │  MySQL RDS Storage  │
│  (via ElastiCache) │        │   (via Amazon RDS)  │
└────────────────────┘        └────────────────────┘


- **Chatbot**: Python-based logic that interacts with users
- **Semantic Search**: Using `sentence-transformers` to match user intent with program descriptions
- **Redis (ElastiCache)**: Stores past queries to avoid recomputing similar results
- **MySQL (RDS)**: Stores submitted applications persistently

---

## 🔧 Technologies Used

- Python 3.11
- [sentence-transformers](https://www.sbert.net/)
- [pymysql](https://pypi.org/project/PyMySQL/)
- [boto3](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html) (for optional AWS resource automation)
- Amazon RDS (MySQL)
- Amazon ElastiCache (Redis)
- Google Colab / VS Code for development


