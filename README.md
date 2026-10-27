<div align="center">

# Jitesh Mohapatra

### AI Developer · Python Backend Engineer · DevOps & Scalable Deployment

<img src="https://readme-typing-svg.herokuapp.com?font=Poppins&size=22&duration=3000&pause=1000&center=true&vCenter=true&width=900&lines=Building+AI-powered+products;Python+%2F+Django+Backend+Engineer;Dockerized+Deployments+with+CI%2FCD;Computer+Vision+%7C+NLP+%7C+LLM+Agents;Shipping+to+production+reliably" alt="Typing SVG" />

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=postgresql&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)

</div>

---

## 👋 About Me

I build intelligent applications and take them all the way to production: from model and API development to containerized, automated, repeatable deployments.

- 🤖 **AI:** Computer Vision, NLP, OCR / document intelligence, LLM agents, RAG
- 🐍 **Backend:** Django / DRF, Flask, REST APIs, PostgreSQL, Redis, Celery
- 🚢 **DevOps:** Docker Compose deployments on Linux servers, GitHub Actions CI/CD, environment-based config
- 🌱 **Exploring:** LangGraph, multi-agent systems, multi-tenant SaaS architecture

---

## 🚢 DevOps & Scalable Deployment

I deploy production services with **Docker Compose** and automate delivery with **GitHub Actions**, so every merge to `main` can reach the server without manual steps.

### CI/CD Pipeline

```mermaid
flowchart LR
    A[👨‍💻 Push / PR] --> B[GitHub Actions]
    B --> C{Lint & Tests}
    C -- pass --> D[Build Docker Image]
    C -- fail --> X[❌ Stop & Notify]
    D --> E[Push to Registry]
    E --> F[SSH into Server]
    F --> G[docker compose pull & up -d]
    G --> H[Health Check]
    H -- ok --> I[✅ Live]
    H -- fail --> R[↩️ Rollback]
```

### What I Practice

| Area | Approach |
|---|---|
| **Containerization** | Multi-service stacks (API, worker, DB, cache, broker) defined in Docker Compose |
| **CI/CD** | GitHub Actions: test → build → deploy on push to `main` |
| **Config & Secrets** | `.env` files and GitHub Secrets, never committed to the repo |
| **Persistence** | Named volumes for PostgreSQL and media/object storage |
| **Async Workloads** | Celery workers + Redis for background and scheduled jobs |
| **Reliability** | Restart policies, health checks, log inspection via `docker logs` |
| **Scalability** | Stateless services, worker scaling with `docker compose up --scale` |
| **Releases** | Zero-manual-step deploys, image tagging for rollback |

<details>
<summary><b>📦 Example: Docker Compose stack (click to expand)</b></summary>

```yaml
services:
  api:
    build: .
    command: gunicorn config.wsgi:application --bind 0.0.0.0:8000
    env_file: .env
    depends_on: [db, redis]
    restart: unless-stopped
    ports: ["8000:8000"]

  worker:
    build: .
    command: celery -A config worker -l info
    env_file: .env
    depends_on: [db, redis]
    restart: unless-stopped

  db:
    image: postgres:16
    env_file: .env
    volumes: [pgdata:/var/lib/postgresql/data]
    restart: unless-stopped

  redis:
    image: redis:7-alpine
    restart: unless-stopped

volumes:
  pgdata:
```

</details>

<details>
<summary><b>⚙️ Example: GitHub Actions deploy workflow (click to expand)</b></summary>

```yaml
name: CI/CD

on:
  push:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with: { python-version: "3.12" }
      - run: pip install -r requirements.txt
      - run: python manage.py test

  deploy:
    needs: test
    runs-on: ubuntu-latest
    steps:
      - name: Deploy over SSH
        uses: appleboy/ssh-action@v1
        with:
          host: ${{ secrets.SERVER_HOST }}
          username: ${{ secrets.SERVER_USER }}
          key: ${{ secrets.SERVER_SSH_KEY }}
          script: |
            cd /opt/app
            git pull origin main
            docker compose up -d --build
            docker image prune -f
```

</details>

---

## 🛠️ Tech Stack

**Languages & Backend**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![DRF](https://img.shields.io/badge/DRF-A30000?style=for-the-badge)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![Celery](https://img.shields.io/badge/Celery-37814A?style=for-the-badge&logo=celery&logoColor=white)

**DevOps & Cloud**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![AWS S3](https://img.shields.io/badge/AWS%20S3-569A31?style=for-the-badge&logo=amazons3&logoColor=white)

**Data & Messaging**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![MQTT](https://img.shields.io/badge/MQTT-660066?style=for-the-badge&logo=mqtt&logoColor=white)

**AI / ML**

![OpenCV](https://img.shields.io/badge/OpenCV-27338e?style=for-the-badge&logo=opencv&logoColor=white)
![YOLO](https://img.shields.io/badge/YOLO-111111?style=for-the-badge)
![Azure AI](https://img.shields.io/badge/Azure%20AI%20%7C%20Custom%20Vision-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-00A67E?style=for-the-badge)
![LangGraph](https://img.shields.io/badge/LangGraph-6C63FF?style=for-the-badge)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)

**Frontend & Integrations**

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Telegram](https://img.shields.io/badge/Telegram%20Bots-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)
![Twilio](https://img.shields.io/badge/Twilio-F22F46?style=for-the-badge&logo=twilio&logoColor=white)
![Google Drive](https://img.shields.io/badge/Google%20Drive%20API-4285F4?style=for-the-badge&logo=googledrive&logoColor=white)

---

## 🧩 What I Build

- 📄 **Document intelligence:** OCR and PDF parsing pipelines, receipt management, reconciliation engines
- 👁️ **Computer vision:** object detection (YOLO), Azure Custom Vision models
- 🤖 **AI agents & automation:** LLM workflows, RAG, Telegram bots, webhook-driven automation
- 🌐 **Production backends:** REST APIs served from Dockerized stacks with automated deploys
- 📡 **IoT & monitoring:** MQTT-based device data pipelines and dashboards

---

## 🏗️ How I Ship

```mermaid
flowchart TB
    subgraph Dev[Development]
        A[Feature Branch] --> B[Pull Request]
    end
    subgraph CI[GitHub Actions]
        B --> C[Lint · Test · Build]
    end
    subgraph Prod[Server · Docker Compose]
        C --> D[API]
        C --> E[Celery Worker]
        D --- F[(PostgreSQL)]
        D --- G[(Redis)]
        E --- G
    end
```

---

## 📊 GitHub Stats

<div align="center">

<img height="170" src="https://github-readme-stats.vercel.app/api?username=YOUR_GITHUB_USERNAME&show_icons=true&theme=tokyonight&hide_border=true" />
<img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_GITHUB_USERNAME&layout=compact&theme=tokyonight&hide_border=true" />

</div>

---

## 📫 Let's Connect

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/YOUR_LINKEDIN)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:YOUR_EMAIL)

*Open to AI engineering, backend, and DevOps-focused roles and collaborations.*

</div>
