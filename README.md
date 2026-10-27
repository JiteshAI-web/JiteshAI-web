<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0F2027,50:2C5364,100:00C6FF&height=230&section=header&text=Jitesh%20Mohapatra&fontSize=50&fontColor=ffffff&animation=fadeIn&fontAlignY=36&desc=Cloud%20%26%20DevOps%20Engineer%20%C2%B7%20Backend%20%C2%B7%20AI%20Enthusiast&descSize=18&descAlignY=58" width="100%" />

<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=22&duration=3000&pause=800&color=00C6FF&center=true&vCenter=true&width=850&lines=Cloud+%26+DevOps+Engineer;Docker+Compose+%E2%86%92+CI%2FCD+%E2%86%92+Production;Deploying+scalable+backends+on+the+cloud;Strong+interest+in+AI+%7C+LLM+Agents+%7C+Computer+Vision;Shipping+reliably%2C+one+merge+at+a+time" alt="Typing SVG" />

<br/>

![Profile Views](https://komarev.com/ghpvc/?username=JiteshAI-web&label=Profile%20Views&color=00c6ff&style=for-the-badge)
![Followers](https://img.shields.io/github/followers/JiteshAI-web?style=for-the-badge&color=2C5364&logo=github)
![Open to Work](https://img.shields.io/badge/Open%20to-Work-brightgreen?style=for-the-badge)

</div>

---

## 👨‍💻 About Me

```python
class Jitesh:
    role      = "Cloud & DevOps Engineer · AI Developer @ Bariflo Labs"
    location  = "Bhubaneswar, Odisha 🇮🇳"
    core      = ["Cloud Deployment", "Docker Compose", "CI/CD", "Python Backend"]
    passion   = ["Applied AI", "LLM Agents", "Computer Vision", "RAG"]
    learning  = ["LangGraph", "Multi-Agent Systems", "Multi-Tenant SaaS"]

    def mission(self):
        return "Build, containerize and ship reliable cloud systems, with AI at the core."
```

- ☁️ **Cloud & DevOps:** Dockerized production stacks on Linux servers, GitHub Actions CI/CD, Azure and AWS services
- 🐍 **Backend:** Django / DRF, Flask, REST APIs, PostgreSQL, Redis, Celery
- 🤖 **AI (strong interest):** Computer Vision, NLP, OCR / document intelligence, LLM agents, RAG
- 📡 **IoT:** MQTT device pipelines and monitoring dashboards

---

## ☁️ Cloud, DevOps & Scalable Deployment

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
docker compose up -d --build           # build & start
docker compose logs -f api             # follow API logs
docker compose up -d --scale worker=3  # scale workers
docker compose exec api python manage.py migrate
docker compose ps                      # service health
```

</details>

---

## 🌍 Live Production Deployments

Applications I have built, deployed and maintained on production servers under **bc-pl.com**.

| # | Application | Live URL | What I Did | CI/CD |
|---|---|---|---|---|
| 1 | 🛠️ **CMMS** — Maintenance Management Web App | [cmms.bc-pl.com](https://cmms.bc-pl.com) | Delivered & deployed | ✅ GitHub Actions |
| 2 | 📱 **IOCL Mobile App Backend** | [ioclmobileapp.bc-pl.com](https://ioclmobileapp.bc-pl.com) | Deployed (Docker) | ✅ GitHub Actions |
| 3 | ✍️ **BFL Sign** — Document Signing Platform | [bflsign.bc-pl.com](https://bflsign.bc-pl.com) | Deployed | — |
| 4 | 🏦 **Reconciliation Platform** | [reconciliation.bc-pl.com](https://reconciliation.bc-pl.com) | Deployed | — |
| 5 | 🌐 **Varanga** | [varanga.bc-pl.com](https://varanga.bc-pl.com) | Deployed | — |
| 6 | 📡 **IoT Master Dashboard** | [register.bc-pl.com](https://register.bc-pl.com) | Deployed | — |
| 7 | 🧾 **Invoice Management** | [invoice.bc-pl.com](https://invoice.bc-pl.com) | Deployed | — |

### 📲 Mobile App Delivery (APK)

I generate and deliver production **Android APK builds** for:

![HRMS](https://img.shields.io/badge/HRMS%20App-APK-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![IOCL](https://img.shields.io/badge/IOCL%20App-APK-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![CMMS](https://img.shields.io/badge/CMMS%20App-APK-3DDC84?style=for-the-badge&logo=android&logoColor=white)

### 🤖 Telegram Bots

Built Telegram bots for **account management**: automated account handling, notifications and user interaction directly in Telegram, backed by the same Dockerized backend infrastructure.

```mermaid
flowchart LR
    Dev([👨‍💻 Code]) --> GH[GitHub]
    GH --> CI[GitHub Actions]
    CI --> SRV[🖥️ bc-pl.com Server<br/>Docker Compose]
    SRV --> W1[cmms.bc-pl.com]
    SRV --> W2[ioclmobileapp.bc-pl.com]
    SRV --> W3[reconciliation · invoice · bflsign<br/>varanga · register]
    W2 --> APK[📱 APKs: HRMS · IOCL · CMMS]
    SRV --> TG[🤖 Telegram Bots]

    style SRV fill:#0F2027,color:#fff,stroke:#00C6FF
    style CI fill:#2088FF,color:#fff
    style APK fill:#3DDC84,color:#000
    style TG fill:#26A5E4,color:#fff
```

---

## 🧰 Tech Stack

<div align="center">

**☁️ Cloud & DevOps**<br/>
<img src="https://skillicons.dev/icons?i=docker,githubactions,linux,git,github,azure,aws,bash,nginx&perline=9" />

**🐍 Backend & Data**<br/>
<img src="https://skillicons.dev/icons?i=python,django,flask,fastapi,postgres,redis,js,react,vite&perline=9" />

**🤖 AI / ML**<br/>
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

## 🤖 AI: Where My Interest Runs Deep

I bring a cloud engineer's discipline to AI: models and agents are only useful when they are deployed, monitored and scalable.

<table>
<tr>
<td width="50%" valign="top">

### 📄 Document Intelligence
OCR and PDF parsing pipelines, receipt management and multi-bank reconciliation engines.

### 👁️ Computer Vision
Object detection with YOLO and Azure Custom Vision models.

</td>
<td width="50%" valign="top">

### 🧠 LLM Agents & RAG
LLM workflows, retrieval-augmented generation, and currently exploring LangGraph and multi-agent systems.

### 🔗 Automation
Telegram bots and webhook-driven workflows connecting AI to real business processes.

</td>
</tr>
</table>

---

## 📊 GitHub Analytics

<div align="center">

<img height="180" src="https://github-readme-stats.vercel.app/api?username=JiteshAI-web&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" />
<img height="180" src="https://github-readme-stats.vercel.app/api/top-langs/?username=JiteshAI-web&layout=compact&theme=tokyonight&hide_border=true" />

<img src="https://github-readme-streak-stats.herokuapp.com/?user=JiteshAI-web&theme=tokyonight&hide_border=true" />

<img src="https://github-readme-activity-graph.vercel.app/graph?username=JiteshAI-web&theme=tokyo-night&hide_border=true&area=true" width="100%" />

<img src="https://github-profile-trophy.vercel.app/?username=JiteshAI-web&theme=tokyonight&no-frame=true&row=1&column=6" />

</div>

---

## 📫 Let's Connect

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/YOUR_LINKEDIN)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:YOUR_EMAIL)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/JiteshAI-web)

*Open to Cloud / DevOps engineering roles with a strong AI focus.*

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:00C6FF,50:2C5364,100:0F2027&height=120&section=footer" width="100%" />

</div>
