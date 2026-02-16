<div align="center">

# 🛡️ SCOUT

### Security CVE & Outbreak Universal Tracker

**An AI-powered vulnerability intelligence platform that continuously monitors, analyzes, and prioritizes security threats for your organization.**

![Docker](https://img.shields.io/badge/Docker-Ready-blue?logo=docker)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-336791?logo=postgresql&logoColor=white)
![License](https://img.shields.io/badge/License-Commercial-green)

</div>

---

## � What is SCOUT?

SCOUT is a self-hosted vulnerability intelligence platform built for security teams and SOC analysts. It aggregates CVE data from multiple authoritative sources, applies AI-powered risk analysis tailored to your infrastructure, and delivers actionable intelligence — all through a modern web dashboard.

**Key Capabilities:**

- **Multi-Source Aggregation** — Pulls from NVD, CISA KEV, ExploitDB, GitHub Advisories, OSV, and 14+ security RSS feeds in real-time.
- **AI-Powered Risk Analysis** — Three analysis tiers (Quick, Smart, Deep) using local Ollama or cloud AI models for contextual risk scoring.
- **Organization-Aware Scoring** — Maps vulnerabilities against your declared assets (tech stack, versions, exposure levels) to calculate a 0-100 risk score unique to your environment.
- **Deep Analysis with Web Intelligence** — Automated OSINT enrichment searches for active exploits, PoC code, threat actor activity, and patch availability.
- **MITRE ATT&CK Mapping** — Automatic technique and tactic mapping for every analyzed vulnerability.
- **SOC-Ready Reports** — Executive PDF reports, detection rules (Sigma/YARA/Snort), IOC extraction, and remediation timelines.
- **Smart Alerts** — Auto-prioritizes zero-days and actively exploited vulnerabilities. Email and push notification support.
- **One-Click Analysis** — Analyze any CVE directly from the feed with a single click, or paste/upload advisory text.
- **URL Scraping** — Point SCOUT at any security advisory URL and it extracts and analyzes the vulnerability details.

---

## � Quick Start

### Prerequisites
- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed and running

### 1. Clone & Configure
```bash
git clone https://github.com/PrototypePrime/SCOUT-Security_and_CVE_Outbreak_Universal_Tracker.git
cd SCOUT-Security_and_CVE_Outbreak_Universal_Tracker
cp .env.example .env
```

Edit `.env` and set **at minimum** these two values:
```env
POSTGRES_PASSWORD=your_secure_database_password
SECRET_KEY=a_long_random_string_for_jwt_signing
```

### 2. Launch
```bash
docker-compose up -d
```

### 3. Access Dashboard
Open **http://localhost:8000** in your browser.

**Default login:** `admin` / `admin123`

> ⚠️ Change the default password immediately after first login via the User Management panel.

---

## 🧠 AI Configuration

SCOUT supports two AI backends. Configure either (or both) in your `.env` file:

### Local AI (Ollama) — Recommended for Privacy
1. Install [Ollama](https://ollama.ai) on your host machine
2. Pull a model: `ollama pull qwen2.5:7b`
3. SCOUT auto-connects via `http://host.docker.internal:11434`
4. You can change the model from **Settings → AI Model** in the dashboard

### Cloud AI — Recommended for Quality
Set your API key in `.env`:
```env
SCOUT_CLOUD_API_KEY=your-cloud-api-key
SCOUT_CLOUD_API_URL=https://api.example.com/v1/chat/completions
```

> You can switch between Local and Cloud AI at any time from the Settings panel.

---

## ⚙️ Configuration Reference

All configuration is done through the `.env` file:

| Variable | Description | Default |
|---|---|---|
| `POSTGRES_PASSWORD` | Database password | `scout_password` |
| `POSTGRES_USER` | Database username | `scout` |
| `SECRET_KEY` | JWT authentication key | *(change this!)* |
| `OLLAMA_BASE_URL` | Local Ollama endpoint | `http://host.docker.internal:11434` |
| `SCOUT_CLOUD_API_KEY` | Cloud AI API key | *(optional)* |
| `SCOUT_CLOUD_API_URL` | Cloud AI endpoint | *(optional)* |
| `SCOUT_EMAIL` | Alert notification email | *(optional)* |
| `SCOUT_EMAIL_PASSWORD` | Email app password | *(optional)* |

---

## 📋 Management

| Action | Command |
|---|---|
| Start | `docker-compose up -d` |
| Stop | `docker-compose down` |
| View logs | `docker-compose logs -f scout-app` |
| Update to latest | `docker-compose pull && docker-compose up -d` |
| Reset database | `docker-compose down -v && docker-compose up -d` |

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────┐
│              SCOUT Container                │
│  ┌─────────┐  ┌──────────┐  ┌───────────┐  │
│  │ React UI│  │ FastAPI  │  │ AI Engine │  │
│  │ (Vite)  │──│ Backend  │──│ (Ollama/  │  │
│  │         │  │          │  │  Cloud)   │  │
│  │         │  │          │  │  Cloud)   │  │
│  └─────────┘  └────┬─────┘  └───────────┘  │
│                    │                        │
│         ┌──────────┴──────────┐             │
│         │    Scrapers         │             │
│         │ NVD│CISA│ExploitDB  │             │
│         │ GitHub│RSS│OSV       │             │
│         └─────────────────────┘             │
└──────────────────┬──────────────────────────┘
                   │
          ┌────────┴────────┐
          │   PostgreSQL    │
          │   (scout-db)    │
          └─────────────────┘
```

---

## 🔧 Troubleshooting

| Issue | Solution |
|---|---|
| Can't connect to dashboard | Ensure port 8000 is free: `docker-compose logs scout-app` |
| AI analysis not working | Check Ollama is running: `ollama list`, or verify cloud API key |
| Database connection error | Check PostgreSQL health: `docker-compose ps` |
| Empty vulnerability feed | Wait 2-3 minutes — scrapers run on startup |

---

## 📄 License

Commercial license. See [LICENSE](LICENSE) for details.
