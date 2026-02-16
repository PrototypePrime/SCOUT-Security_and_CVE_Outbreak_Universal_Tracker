<div align="center">

# 🛡️ SCOUT

### **S**ecurity **C**VE & **O**utbreak **U**niversal **T**racker

**Transform vulnerability chaos into actionable intelligence with AI-powered risk analysis**

[![Docker Ready](https://img.shields.io/badge/Docker-Ready-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://hub.docker.com/r/prototype628426/scout-app)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-336791?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-Backend-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![React](https://img.shields.io/badge/React-Frontend-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://reactjs.org/)
[![License](https://img.shields.io/badge/License-Commercial-1abc9c?style=for-the-badge)](LICENSE)

![SCOUT Dashboard](https://img.shields.io/badge/🎯-CVE_Intelligence-orange?style=for-the-badge)
![AI Powered](https://img.shields.io/badge/🧠-AI_Powered-blueviolet?style=for-the-badge)
![Real Time](https://img.shields.io/badge/⚡-Real--Time-red?style=for-the-badge)

</div>

---

## 🎯 What is SCOUT?

SCOUT is a **self-hosted vulnerability intelligence platform** that eliminates alert fatigue by automatically analyzing and prioritizing CVEs based on **your actual infrastructure risk**.

### The Challenge

Security teams face overwhelming CVE volumes daily:
- 📊 **50+ new CVEs per day** across multiple sources
- ❓ **Generic CVSS scores** don't reflect YOUR actual exposure
- 🔍 **Hours of manual research** per critical vulnerability
- 📝 **Time-consuming reporting** for executives and stakeholders
- 🚨 **Alert fatigue** leads to missed critical threats

### The SCOUT Solution

SCOUT automates the entire vulnerability analysis workflow:

```
CVE Published → Auto-Ingested → AI Analyzed → Risk Scored → Alerts Sent → Reports Generated
    (NVD)          (Real-time)     (30 sec)      (0-100)      (Email/Push)    (PDF/IOC)
```

**Result**: Your team focuses only on vulnerabilities that actually threaten YOUR infrastructure.

---

## 👥 Who is SCOUT For?

<table>
<tr>
<td width="33%">

### 🎯 **SOC Analysts**
- **Triage** 100+ daily CVEs in minutes
- **Prioritize** based on org-specific risk
- **Generate** detection rules instantly
- **Track** exploit availability in real-time

</td>
<td width="33%">

### 🔧 **Security Engineers**
- **Map** vulnerabilities to your tech stack
- **Version matching** against assets
- **Patch prioritization** with risk scores
- **MITRE ATT&CK** technique tracking

</td>
<td width="33%">

### 📊 **CISOs / Managers**
- **Executive reports** with risk summaries
- **Trend analysis** of vulnerability exposure
- **Compliance** documentation (NIST, PCI-DSS)
- **Metrics** for board presentations

</td>
</tr>
</table>

---

## � Real-World Use Cases

### Use Case 1: SOC Analyst Daily Workflow

**Scenario**: Alex is a SOC analyst who needs to review 50+ new CVEs each morning.

**Without SCOUT**:
1. Manually check NVD, CISA KEV, ExploitDB (30 minutes)
2. Google each CVE for exploit code (10 min per CVE = 8+ hours)
3. Manually map to infrastructure (1 hour)
4. Write executive summary (30 minutes)

**Total Time**: ~10+ hours

**With SCOUT**:
1. Open dashboard → **50 CVEs auto-ingested and analyzed** ✅
2. Filter "High Risk to Our Org" → **3 critical matches** 🎯
3. Click "Deep Analysis" → **OSINT, exploits, IOCs in 30 seconds** 🧠
4. Click "Generate Report" → **Executive PDF ready** 📄

**Total Time**: ~15 minutes

**ROI**: 97% time savings, zero missed threats

---

### Use Case 2: Zero-Day Response

**Scenario**: A critical Apache Log4j vulnerability (Log4Shell) is announced.

**SCOUT Automated Response**:
1. **T+5 minutes**: CVE-2021-44228 auto-ingested from NVD
2. **T+10 minutes**: AI detects "apache" in your asset list → **Risk Score: 95/100** 🚨
3. **T+10 minutes**: Email alert sent to security team
4. **T+12 minutes**: Deep Analysis completes:
   - ✅ Public exploit available (ExploitDB)
   - ✅ Active exploitation detected (Twitter OSINT)
   - ✅ PoC code found on GitHub
   - ⚠️ No patch available yet
   - 🎯 MITRE: Initial Access (T1190)
5. **T+15 minutes**: Executive report generated with:
   - Affected assets: 12 Apache Tomcat servers (v2.14.1)
   - Recommended action: Immediate network segmentation
   - Detection rules: Sigma, Snort, YARA
   - IOCs: 47 known malicious IPs

**Result**: Your team has actionable intelligence within 15 minutes of CVE publication.

---

### Use Case 3: Patch Prioritization

**Scenario**: You have 200 outstanding vulnerabilities and limited patching resources.

**SCOUT Asset-Aware Scoring**:

| CVE | CVSS | SCOUT Risk | Why? |
|-----|------|------------|------|
| CVE-2023-1234 | **9.8 Critical** | **23/100** | Affects Python 2.7 → You use Python 3.11 ✅ |
| CVE-2023-5678 | **7.5 High** | **92/100** | Affects Nginx 1.18 → You run Nginx 1.18 on internet-facing DMZ 🚨 |
| CVE-2023-9012 | **5.3 Medium** | **78/100** | Affects PostgreSQL → You run it with PII data + no encryption ⚠️ |

**Without SCOUT**: Patch based on CVSS (wastes time on Python 2.7)  
**With SCOUT**: Patch Nginx 1.18 first (actual threat to your infrastructure)

---

### Use Case 4: Compliance & Audit Trail

**Scenario**: Annual PCI-DSS audit requires proof of vulnerability management.

**SCOUT Generates**:
- 📊 **Quarterly Reports**: All CVEs affecting payment systems
- 📈 **Trend Analysis**: Mean time to patch (MTTP) metrics
- 📝 **Audit Trail**: Timestamps for detection, analysis, remediation
- 🔍 **Asset Inventory**: Complete tech stack with versions
- ✅ **Evidence**: PDF reports with MITRE ATT&CK mappings

**Export Formats**: PDF, CSV, JSON for auditor review

---


## ✨ Feature Deep Dive

### 🔄 Multi-Source Intelligence Aggregation

SCOUT continuously monitors **15+ authoritative sources** in real-time:

| Source | Update Frequency | Data Type | Example |
|--------|------------------|-----------|---------|
| **NVD** (NIST) | Every hour | CVE database | CVE-2024-1234 with CVSS scores |
| **CISA KEV** | Every hour | Exploited vulns | Known exploited vulnerabilities |
| **ExploitDB** | Every 30 min | Public exploits | PoC code, exploit modules |
| **GitHub Advisories** | Every 30 min | Package vulns | npm, PyPI, RubyGems advisories |
| **OSV** | Every hour | Open source | Python, Go, Rust vulnerabilities |
| **RSS Feeds** (14+) | Every 15 min | Security news | BleepingComputer, Krebs, DarkReading |

**Deduplication Engine**: Automatically merges duplicate CVEs across sources.

---

### 🧠 AI-Powered Risk Analysis (3 Tiers)

#### Tier 1: Quick Scan (<1 second)
- **Input**: CVE-ID, CVSS score, description
- **Output**: Basic 0-100 risk score
- **Use Case**: Real-time feed scanning

#### Tier 2: Smart Analysis (5-10 seconds)
- **Input**: CVE + Your asset inventory
- **Processing**:
  - Version matching (e.g., "Nginx 1.18" vs "Nginx 1.14-1.20")
  - Attack vector analysis (network vs local)
  - MITRE ATT&CK technique mapping
- **Output**: Organization-specific risk score + recommended actions
- **Use Case**: Daily triage

#### Tier 3: Deep Analysis (30-60 seconds)
- **Input**: CVE + Web OSINT
- **Processing**:
  - GitHub exploit code search
  - Twitter/Reddit threat actor mentions
  - Patch availability verification
  - IOC extraction (IPs, domains, file hashes)
  - Detection rule generation (Sigma, YARA, Snort)
- **Output**: Full intelligence report with executive summary
- **Use Case**: Critical zero-day response

**Example Smart Analysis Output**:
```yaml
CVE: CVE-2024-1234
Title: "Apache Tomcat RCE via Deserialization"
Risk Score: 87/100

Reasoning:
  ✅ Affects: Apache Tomcat 9.0.0-9.0.85
  ✅ You run: Tomcat 9.0.72 (VULNERABLE)
  ✅ Exposure: Internet-facing (DMZ)
  ✅ Exploit: Public PoC available (GitHub)
  ✅ Active Exploitation: Detected in wild (CISA KEV)
  ⚠️ Patch: Available (upgrade to 9.0.86)
  
MITRE ATT&CK:
  - Initial Access: Exploit Public-Facing Application (T1190)
  - Execution: Command and Scripting Interpreter (T1059)
  
Recommended Actions:
  1. IMMEDIATE: Segment network (block external → Tomcat)
  2. URGENT: Apply patch 9.0.86 within 24 hours
  3. DEPLOY: Sigma detection rule (attached)
  4. MONITOR: IOCs list (12 malicious IPs)
```

---

### 📊 Organization-Aware Risk Scoring

Traditional CVSS doesn't consider YOUR environment. SCOUT does.

**Scoring Factors**:

| Factor | Weight | Example |
|--------|--------|---------|
| **Asset Criticality** | 25% | Production DB = 1.5x, Test VM = 0.5x |
| **Network Exposure** | 20% | Internet-facing = 1.5x, Air-gapped = 0.3x |
| **Vulnerability Type** | 20% | RCE = 1.4x (backend), XSS = 0.5x (backend) |
| **Exploit Availability** | 15% | Public PoC = +2.0, No exploit = +0 |
| **Compensating Controls** | 10% | WAF = 0.85x, EDR = 0.9x, Segmentation = 0.9x |
| **Patch Availability** | 10% | No patch = +0.5, Patch available = 0x |

**Example Calculation**:
```
Base CVSS: 7.5 (High)
+ Asset: Production web server (1.5x)
+ Exposure: Internet-facing (1.5x)
+ Type: SQL Injection on database backend (1.3x)
+ Exploit: Public PoC available (+2.0)
+ Controls: WAF deployed (0.85x)
+ Patch: Available (0x)

SCOUT Risk Score: 78/100 (High Priority)
```

---

### 🎯 SOC-Ready Report Generation

#### Executive PDF Reports
- **Audience**: CISOs, board members, non-technical stakeholders
- **Content**:
  - Risk summary (HIGH/CRITICAL count)
  - Top 10 vulnerabilities to your org
  - Trend graphs (CVEs over time)
  - Compliance metrics (MTTP, coverage)
- **Format**: Professional PDF with charts

#### Detection Rules (Auto-Generated)
```yaml
# Sigma Rule Example (SCOUT-generated)
title: Apache Log4j RCE Exploitation Attempt
id: scout-cve-2021-44228
status: experimental
description: Detects Log4Shell exploitation patterns
logsource:
  category: webserver
detection:
  selection:
    cs-uri-query|contains:
      - '${jndi:ldap://'
      - '${jndi:rmi://'
  condition: selection
level: critical
tags:
  - attack.initial_access
  - attack.t1190
  - cve.2021.44228
```

#### IOC Extraction
- **IP Addresses**: Command & Control servers
- **Domains**: Malicious infrastructure
- **File Hashes**: Exploit payloads (MD5, SHA256)
- **URLs**: Malicious download links

**Export**: CSV, JSON, STIX 2.1 for SIEM ingestion

---

### 🚨 Smart Alerting System

#### Email Alerts
- **Trigger**: Zero-day OR actively exploited OR risk score > threshold
- **Content**:
  - CVE summary
  - Risk score with reasoning
  - Affected assets
  - Recommended actions
- **Configuration**: Settings → Notifications → Email

#### Browser Push Notifications
- **Real-Time**: Instant alerts while dashboard is open
- **Customizable**: Severity thresholds (CRITICAL only, HIGH+, etc.)

#### Alert Examples:
```
🚨 CRITICAL ALERT

CVE-2024-9999: Zero-Day in Windows RDP
Risk Score: 98/100

Affects: 5 of your Windows Servers (2019, 2022)
Exploit: Active in wild (CISA KEV)
Patch: Not available

IMMEDIATE ACTION REQUIRED:
- Disable RDP on internet-facing servers
- Enable network-level authentication (NLA)
- Monitor for indicators: [12 IOCs attached]
```

---

### 🔍 Flexible Analysis Modes

#### 1. Feed Analysis (Automatic)
- SCOUT auto-analyzes new CVEs from all sources
- Filter by: Severity, Source, Date, Exploit Status
- One-click "Analyze" button for deeper insights

#### 2. Manual CVE Entry
```
Paste CVE-ID: CVE-2024-1234
  → SCOUT fetches from NVD
  → Runs Smart Analysis
  → Shows org-specific risk
```

#### 3. Advisory Text Analysis
```
Paste security advisory:
"Apache has released updates to address a critical
vulnerability in Tomcat versions 9.0.0 to 9.0.85..."

  → SCOUT extracts CVE, versions, patch info
  → Maps to your assets
  → Generates risk score
```

#### 4. URL Scraping
```
Input: https://example.com/security-advisory-2024-01
  → SCOUT crawls page
  → Extracts CVE details
  → Auto-analyzes
```

---

## 🚀 Quick Start (3 Minutes)

### Prerequisites
- **Docker Desktop** → [Download](https://www.docker.com/products/docker-desktop/)
- **Ollama** (optional, for AI) → [Download](https://ollama.ai)

### Installation

**Method 1: Docker Hub (Recommended)**

Pull the pre-built image directly from Docker Hub:

```bash
# 1. Create project directory
mkdir scout && cd scout

# 2. Download docker-compose.yml
curl -O https://raw.githubusercontent.com/PrototypePrime/SCOUT-Security_and_CVE_Outbreak_Universal_Tracker/main/docker-compose.yml

# 3. Download .env.example
curl -O https://raw.githubusercontent.com/PrototypePrime/SCOUT-Security_and_CVE_Outbreak_Universal_Tracker/main/.env.example
cp .env.example .env

# 4. Edit .env - Set ONE required variable
nano .env  # or notepad .env on Windows
```

**In `.env`, set**:
```env
SECRET_KEY=your_long_random_secret_key_for_jwt_signing
```

> 💡 **Generate**: `openssl rand -hex 32` (Linux/Mac) or use any 64-character random string

```bash
# 5. Launch SCOUT
docker-compose up -d

# 6. Wait 30 seconds, then access dashboard
```

**Method 2: Build from Source**

Clone the repository and build locally:

```bash
# 1. Clone repository
git clone https://github.com/PrototypePrime/SCOUT-Security_and_CVE_Outbreak_Universal_Tracker.git
cd SCOUT-Security_and_CVE_Outbreak_Universal_Tracker

# 2. Create environment file
cp .env.example .env

# 3. Edit .env - Set ONE required variable
nano .env  # or notepad .env on Windows
```

**In `.env`, set**:
```env
SECRET_KEY=your_long_random_secret_key_for_jwt_signing
```

> 💡 **Generate**: `openssl rand -hex 32` (Linux/Mac) or use any 64-character random string

```bash
# 4. Launch SCOUT
docker-compose up -d

# 5. Wait 30 seconds, then access dashboard
```

---

🌐 **Dashboard**: http://localhost:8000

**Login**: `admin` / `admin123`

> ⚠️ **IMPORTANT**: Change password immediately via **Settings → User Account**

---

## 🧠 AI Setup (Optional but Recommended)

SCOUT's risk analysis uses AI for contextual scoring. Two options:

### Option 1: Local AI (Ollama) — Privacy-First

```bash
# Install Ollama
# macOS: brew install ollama
# Linux: curl -fsSL https://ollama.ai/install.sh | sh
# Windows: Download from https://ollama.ai

# Pull a model (choose one):
ollama pull llama3.1:8b       # Faster (8GB RAM)
ollama pull mistral:7b        # Alternative
ollama pull gpt-oss:120b-cloud  # SCOUT default (requires 32GB+ RAM)

# SCOUT auto-connects to http://host.docker.internal:11434
# Change model: Settings → Connections → Model Name
```

### Option 2: Cloud AI

> ⚠️ Requires enterprise configuration. Contact support.

---

## ⚙️ Configuration

All settings in `.env`:

| Variable | Description | Required | Default |
|----------|-------------|----------|---------|
| `SECRET_KEY` | JWT signing key (64+ chars) | ✅ **YES** | *(must set)* |
| `OLLAMA_BASE_URL` | Local AI endpoint | No | `http://host.docker.internal:11434` |
| `SCOUT_EMAIL` | Alert sender email | No | *(optional)* |
| `SCOUT_EMAIL_PASSWORD` | Email app password | No | *(optional)* |

**Database is auto-configured by Docker** — no manual setup needed!

---

## 📋 Management Commands

| Action | Command | Description |
|--------|---------|-------------|
| **Start** | `docker-compose up -d` | Launch in background |
| **Stop** | `docker-compose down` | Stop all services |
| **Logs** | `docker-compose logs -f scout-app` | View real-time logs |
| **Restart** | `docker-compose restart` | Restart without data loss |
| **Update** | `docker-compose pull && docker-compose up -d` | Pull latest image |
| **Reset** | `docker-compose down -v && docker-compose up -d` | ⚠️ Deletes all data! |

---

## 🏗️ Architecture

```
┌──────────────────────────────────────────────────────────────┐
│                    🛡️ SCOUT Platform                          │
│                                                                │
│  ┌──────────────┐  ┌─────────────┐  ┌─────────────────────┐  │
│  │  React UI    │  │   FastAPI   │  │    AI Engine        │  │
│  │   (Vite)     │◄─│   Backend   │◄─│  (Ollama/Cloud)     │  │
│  │              │  │             │  │                     │  │
│  │  Dashboard   │  │  REST API   │  │  Risk Scorer        │  │
│  │  Analysis    │  │  JWT Auth   │  │  OSINT Enrichment   │  │
│  │  Settings    │  │  Scrapers   │  │  Report Generator   │  │
│  └──────────────┘  └──────┬──────┘  └─────────────────────┘  │
│                           │                                   │
│              ┌────────────┴────────────┐                      │
│              │   Data Scrapers         │                      │
│              ├─────────────────────────┤                      │
│              │ NVD │ CISA │ ExploitDB  │                      │
│              │ GitHub │ RSS │ OSV      │                      │
│              └────────────┬────────────┘                      │
└───────────────────────────┼───────────────────────────────────┘
                            │
                   ┌────────┴─────────┐
                   │   PostgreSQL 15  │
                   │   (scout-db)     │
                   │                  │
                   │  • Vulnerabilities│
                   │  • Assets         │
                   │  • Risk Scores    │
                   │  • User Settings  │
                   └──────────────────┘
```

---

## 🔧 Troubleshooting

<details>
<summary><b>❌ Can't connect to dashboard</b></summary>

**Check services**:
```bash
docker-compose ps
docker-compose logs -f scout-app
```

**Common fixes**:
- Port 8000 in use: Edit `docker-compose.yml` → `ports: "8001:8000"`
- Firewall blocking: Allow port 8000 in firewall
</details>

<details>
<summary><b>🧠 AI analysis shows 0/100 scores</b></summary>

**Check Ollama**:
```bash
ollama list  # Should show your model
curl http://localhost:11434/api/version
```

**Fix**:
```bash
# Pull model
ollama pull llama3.1:8b

# Update model in SCOUT: Settings → Connections → Model Name
```
</details>

<details>
<summary><b>📭 Empty vulnerability feed</b></summary>

**Wait 2-3 minutes** — scrapers run on startup.

**Still empty?**
```bash
docker-compose logs scout-app | grep scraper
docker-compose restart scout-app
```
</details>

---

## 🗺️ Roadmap

- [ ] **Slack/Teams Integration** - Native notifications
- [ ] **Multi-Tenant Support** - Manage multiple organizations
- [ ] **API Keys** - Programmatic access
- [ ] **Webhooks** - SIEM/SOAR integration
- [ ] **Dark Web Monitoring** - Expanded OSINT
- [ ] **Automated Patching** - Integration with patch management

---

## 📄 License

**Commercial License** — See [LICENSE](LICENSE)

---

<div align="center">

## 🎉 SCOUT vs Manual Process

| Task | Manual | SCOUT | Time Saved |
|------|--------|-------|------------|
| Daily CVE review | 2 hours | 5 minutes | **96%** |
| Zero-day analysis | 4 hours | 15 minutes | **94%** |
| Executive report | 1 hour | 30 seconds | **99%** |
| IOC extraction | 30 minutes | Instant | **100%** |

**Average ROI: 95% time savings**

---

**Built with ❤️ for Security Teams**

🛡️ SCOUT | Security CVE & Outbreak Universal Tracker

![Made for SOC](https://img.shields.io/badge/Made_for-SOC_Analysts-FF6B6B?style=for-the-badge)
![Powered by AI](https://img.shields.io/badge/Powered_by-AI-4ECDC4?style=for-the-badge)
![Self Hosted](https://img.shields.io/badge/Self--Hosted-Privacy_First-95E1D3?style=for-the-badge)

</div>
