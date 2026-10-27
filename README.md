<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0F2027,50:2C5364,100:00C6FF&height=230&section=header&text=Jitesh%20Mohapatra&fontSize=50&fontColor=ffffff&animation=fadeIn&fontAlignY=36&desc=AI%20Developer%20%C2%B7%20Backend%20Engineer%20%C2%B7%20DevOps&descSize=18&descAlignY=58" width="100%" />

<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=22&duration=3000&pause=800&color=00C6FF&center=true&vCenter=true&width=800&lines=Building+AI-powered+products;Python+%2F+Django+Backend+Engineer;Docker+Compose+%E2%86%92+CI%2FCD+%E2%86%92+Production;Computer+Vision+%7C+NLP+%7C+LLM+Agents;Shipping+reliably%2C+one+merge+at+a+time" alt="Typing SVG" />

<br/>

![Profile Views](https://komarev.com/ghpvc/?username=YOUR_GITHUB_USERNAME&label=Profile%20Views&color=00c6ff&style=for-the-badge)
![Followers](https://img.shields.io/github/followers/YOUR_GITHUB_USERNAME?style=for-the-badge&color=2C5364&logo=github)
![Open to Work](https://img.shields.io/badge/Open%20to-Work-brightgreen?style=for-the-badge)

</div>

---

## 👨‍💻 About Me

```python
class Jitesh:
    role     = "AI Developer @ Bariflo Labs"
    location = "Bhubaneswar, Odisha 🇮🇳"
    focus    = ["Computer Vision", "NLP / LLM Agents", "Python Backend", "DevOps"]
    deploys  = "Docker Compose + GitHub Actions CI/CD"
    learning = ["LangGraph", "Multi-Agent Systems", "Multi-Tenant SaaS"]

    def mission(self):
        return "Turn AI prototypes into reliable, deployed products."
```

- 🤖 **AI** — Computer Vision, NLP, OCR / document intelligence, LLM agents, RAG
- 🐍 **Backend** — Django / DRF, Flask, REST APIs, PostgreSQL, Redis, Celery
- 🚢 **DevOps** — Dockerized stacks on Linux servers, GitHub Actions pipelines, env-based config
- 📡 **IoT** — MQTT device pipelines, monitoring dashboards

---

## 🧰 Tech Stack

<div align="center">

**Languages & Backend**<br/>
<img src="https://skillicons.dev/icons?i=python,django,flask,fastapi,postgres,redis,js,react,vite&perline=9" />

**DevOps & Cloud**<br/>
<img src="https://skillicons.dev/icons?i=docker,githubactions,linux,git,github,azure,aws,bash,nginx&perline=9" />

**AI / ML & Data**<br/>
<img src="https://skillicons.dev/icons?i=opencv,pytorch,tensorflow,pandas,numpy,matplotlib&perline=6" />

</div>

<details>
<summary><b>➕ More tools (click to expand)</b></summary>
<br/>

![LangChain](https://img.shields.io/badge/LangChain-00A67E?style=for-the-badge)
![LangGraph](https://img.shields.io/badge/LangGraph-6C63FF?style=for-the-badge)
![YOLO](https://img.shields.io/badge/YOLO-111111?style=for-the-badge)
![Azure Custom Vision](https://img.shields.io/badge/Azure%20Custom%20Vision-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![Celery](https://img.shields.io/badge/Celery-37814A?style=for-the-badge&logo=celery&logoColor=white)
![MQTT](https://img.shields.io/badge/MQTT-660066?style=for-the-badge&logo=mqtt&logoColor=white)
![Twilio](https://img.shields.io/badge/Twilio-F22F46?style=for-the-badge&logo=twilio&logoColor=white)
![Telegram](https://img.shields.io/badge/Telegram%20Bots-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)
![Google Drive API](https://img.shields.io/badge/Google%20Drive%20API-4285F4?style=for-the-badge&logo=googledrive&logoColor=white)
![Amazon S3](https://img.shields.io/badge/Amazon%20S3-569A31?style=for-the-badge&logo=amazons3&logoColor=white)

</details>

---

## 🚢 DevOps & Scalable Deployment

I deploy production services with **Docker Compose** and automate delivery with **GitHub Actions**, so a merge to `main` reaches the server without manual steps.

### 🔄 CI/CD Pipeline

```mermaid
flowchart LR
    A([👨‍💻 Push / PR]) --> B[GitHub Actions]
    B --> C{Lint & Tests}
    C -- pass --> D[🐳 Build Image]
    C -- fail --> X([❌ Stop & Notify])
    D --> E[Push to Registry]
    E --> F[🔐 SSH to Server]
    F --> G[docker compose up -d]
    G --> H{Health Check}
    H -- ok --> I([✅ Live])
    H -- fail --> R([↩️ Rollback])

    style A fill:#2C5364,color:#fff,stroke:#00C6FF
    style I fill:#1b8a5a,color:#fff,stroke:#1b8a5a
    style X fill:#b3261e,color:#fff,stroke:#b3261e
    style R fill:#b36b00,color:#fff,stroke:#b36b00
```

### 🏗️ Production Architecture

```mermaid
flowchart TB
    U([🌐 Client / Mobile App]) --> API
    subgraph Server["🖥️ Linux Server · Docker Compose"]
        API[Django / DRF API<br/>gunicorn]
        W[Celery Worker]
        DB[(PostgreSQL)]
        R[(Redis)]
        API --- DB
        API --- R
        W --- R
        W --- DB
    end
    GH[GitHub Actions] -. deploys .-> Server

    style Server fill:#0F2027,color:#fff,stroke:#00C6FF
    style API fill:#092E20,color:#fff
    style W fill:#37814A,color:#fff
    style DB fill:#336791,color:#fff
    style R fill:#DC382D,color:#fff
```

### ✅ What I Practice

| Area | Approach |
|---|---|
| 🐳 **Containerization** | Multi-service stacks (API, worker, DB, cache, broker) in Docker Compose |
| ⚙️ **CI/CD** | GitHub Actions: test → build → deploy on push to `main` |
| 🔐 **Config & Secrets** | `.env` files + GitHub Secrets, never committed |
| 💾 **Persistence** | Named volumes for PostgreSQL and media / object storage |
| ⏱️ **Async Workloads** | Celery workers + Redis for background and scheduled jobs |
| 🩺 **Reliability** | Restart policies, health checks, log inspection |
| 📈 **Scalability** | Stateless services, worker scaling via `docker compose up --scale` |
| 🏷️ **Releases** | Image tagging for quick rollback |

<details>
<summary><b>📦 Example: Docker Compose stack</b></summary>

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
<summary><b>⚙️ Example: GitHub Actions deploy workflow</b></summary>

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

<details>
<summary><b>🛠️ Handy Docker Compose commands I use</b></summary>

```bash
docker compose up -d --build         # build & start
docker compose logs -f api           # follow API logs
docker compose up -d --scale worker=3  # scale workers
docker compose exec api python manage.py migrate
docker compose ps                    # service health
```

</details>

---

## 🧩 What I Build

<table>
<tr>
<td width="50%" valign="top">

### 📄 Document Intelligence
OCR and PDF parsing pipelines, receipt management and multi-bank reconciliation engines.

### 👁️ Computer Vision
Object detection with YOLO and Azure Custom Vision models.

</td>
<td width="50%" valign="top">

### 🤖 AI Agents & Automation
LLM workflows, RAG, Telegram bots and webhook-driven automation.

### 🌐 Production Backends
REST APIs served from Dockerized stacks with automated deploys and IoT (MQTT) data pipelines.

</td>
</tr>
</table>

---

## 📊 GitHub Analytics

<div align="center">

<img height="180" src="https://github-readme-stats.vercel.app/api?username=YOUR_GITHUB_USERNAME&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" />
<img height="180" src="https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_GITHUB_USERNAME&layout=compact&theme=tokyonight&hide_border=true" />

<img src="https://github-readme-streak-stats.herokuapp.com/?user=YOUR_GITHUB_USERNAME&theme=tokyonight&hide_border=true" />

<img src="https://github-readme-activity-graph.vercel.app/graph?username=YOUR_GITHUB_USERNAME&theme=tokyo-night&hide_border=true&area=true" width="100%" />

<img src="https://github-profile-trophy.vercel.app/?username=YOUR_GITHUB_USERNAME&theme=tokyonight&no-frame=true&row=1&column=6" />

</div>

---

## 📫 Let's Connect

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/YOUR_LINKEDIN)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:YOUR_EMAIL)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/YOUR_GITHUB_USERNAME)

*Open to AI engineering, backend and DevOps-focused roles and collaborations.*

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:00C6FF,50:2C5364,100:0F2027&height=120&section=footer" width="100%" />

</div>
