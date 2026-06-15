# 🏢 Autonomous Business Agents

> A production multi-agent AI system that autonomously runs day-to-day operations across 3 businesses — built on OpenClaw, Anthropic Claude API, and WhatsApp.

![Status](https://img.shields.io/badge/Status-In%20Development-orange)
![Agents](https://img.shields.io/badge/Agents-10%20Active-blue)
![Framework](https://img.shields.io/badge/Framework-OpenClaw-purple)
![AI](https://img.shields.io/badge/AI-Anthropic%20Claude-red)
![Platform](https://img.shields.io/badge/Platform-WhatsApp%20%7C%20Instagram%20%7C%20TikTok-green)

---

## 🧠 What Is This?

This project is a **10-agent autonomous AI system** designed to replace manual coordination across three real businesses:

| Business | Type | Agent Coverage |
|---|---|---|
| **Nanira Family Reflexology** | B2C — wellness & reflexology | Customer service, bookings, HR, retention |
| **PT Golden Medical Care Indonesia** | B2B — medical gas installation | Sales pipeline, lead qualification, proposals |
| **Zena** | B2C/B2B — AI finance app | Growth research, content marketing |

Instead of hiring multiple staff members, each role is handled by a dedicated AI agent — from CEO orchestration down to e-commerce management.

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────┐
│                  RASYID (Owner)                  │
│              WhatsApp CEO Number                 │
└──────────────────────┬──────────────────────────┘
                       │
              ┌────────▼────────┐
              │   REYNS (CEO)   │  ← Single point of contact
              │  Orchestrator   │     Economic triage system
              └────────┬────────┘     CRITICAL/HIGH/MEDIUM/LOW
                       │
        ┌──────────────┼──────────────┐
        │              │              │
┌───────▼──────┐ ┌─────▼──────┐ ┌───▼────────────┐
│  OPERATIONS  │ │  REVENUE   │ │  SUPPORT       │
│              │ │            │ │                │
│ Oki (Nanira) │ │ Riko(Sales)│ │ Novi (CFO)     │
│ Anggi(Golden)│ │ Nia(Mktg)  │ │ Fikri (CTO)    │
│ Ari (HR)     │ │ Nadim(Ecom)│ │ Nabil (CPO)    │
└──────────────┘ └────────────┘ └────────────────┘
```

### Communication Flow
- All agent communication routes through **Reyns (CEO)**
- Reyns applies **economic triage** before escalating to owner
- Agents communicate peer-to-peer for coordination (Nabil → Nia, Riko → Nia)
- Shared memory files keep all agents synchronized

---

## 👥 The 10 Agents

| Agent | Role | Mode | Key Responsibility |
|---|---|---|---|
| **Reyns** | CEO | Always on | Single owner contact, economic triage, orchestration |
| **Oki** | COO Nanira | 24/7 | WhatsApp customer service, booking processing, retention |
| **Anggi** | COO Golden | 24/7 | B2B inquiry handling, lead qualification |
| **Novi** | CFO | On-call | Invoice generation (RAB & installment), financial reports |
| **Fikri** | CTO | Monitoring | Security audits (ECC/AgentShield), Zena code review |
| **Nabil** | CPO | Heartbeat | LKPP tender scraping, trend research, Zena growth |
| **Ari** | HR | Heartbeat | Attendance monitoring (fingerprint), contract reminders |
| **Nia** | Marketing | On-call | Content calendar, MiroFish simulation, Golden proposals |
| **Riko** | Sales | Heartbeat | Pipeline management (value × probability prioritization) |
| **Nadim** | E-Commerce | Heartbeat | Shopee & Tokopedia management, review monitoring |

---

## 🆕 Key Design Decisions

### Economic Triage System
Reyns classifies every event by economic value before interrupting the owner:

| Priority | Criteria | Action |
|---|---|---|
| 🔴 CRITICAL | >Rp100M / deadline <48h / crisis | Interrupt owner immediately |
| 🟠 HIGH | Rp10-100M / deadline <7 days | Notify during working hours |
| 🟡 MEDIUM | Rp1-10M / routine important | Include in daily 06:00 briefing |
| ⚪ LOW | <Rp1M / handled autonomously | Weekly summary only |

### Result-Oriented Metrics
Every agent is measured by business outcomes, not activity:
- Riko: deals closed & revenue generated (not leads logged)
- Oki: customer retention rate (not messages replied)
- Nia: proposals sent & conversion rate (not content pieces made)

### Pipeline Prioritization
Sales pipeline ordered by `value × closing probability`, not date received:
```
Priority Score = Estimated Value (Rp) × Closing Probability (%)
```

### Human-in-the-Loop (Intentional)
Approval gates are deliberately kept for high-stakes decisions in early phases — loosened progressively as trust is established with each agent.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Agent Framework** | OpenClaw (self-hosted) |
| **AI Model** | Anthropic Claude (Sonnet 4.5 / Opus 4.6) |
| **Server** | Hostinger KVM VPS — Ubuntu 24.04, Malaysia datacenter |
| **WhatsApp API** | Fonnte (3 numbers: Nanira, Golden, CEO) |
| **Security** | ECC / AgentShield (github.com/affaan-m/ECC) |
| **Content Simulation** | MiroFish (github.com/666ghj/MiroFish) |
| **Image Generation** | Pollinations.ai (free, no API key) |
| **Database (Zena)** | Supabase (migrating to self-hosted PostgreSQL in Phase 5) |
| **Process Manager** | PM2 |
| **Version Control** | GitHub |

---

## 📁 Repository Structure

```
autonomous-business-agents/
├── workspace/
│   ├── shared/
│   │   ├── MEMORY.md          # Business context & decisions
│   │   ├── CUSTOMERS.md       # Nanira customer database
│   │   ├── PIPELINE.md        # Golden sales pipeline (value-prioritized)
│   │   ├── PRODUCTS.md        # Golden Medical pricing database
│   │   └── SCHEDULE.md        # Staff attendance & schedules
│   ├── reyns/
│   │   └── SOUL.md            # CEO agent prompt & rules
│   ├── oki/
│   │   ├── SOUL.md            # COO Nanira agent prompt
│   │   └── KNOWLEDGE.md       # Nanira pricelist & knowledge base
│   ├── anggi/
│   │   └── SOUL.md
│   ├── novi/
│   │   └── SOUL.md
│   ├── fikri/
│   │   └── SOUL.md
│   ├── nabil/
│   │   └── SOUL.md
│   ├── ari/
│   │   └── SOUL.md
│   ├── nia/
│   │   └── SOUL.md
│   ├── riko/
│   │   └── SOUL.md
│   └── nadim/
│       └── SOUL.md
└── README.md
```

---

## 🚀 Deployment Setup

### Prerequisites
- VPS with Ubuntu 24.04 (minimum 4GB RAM)
- Node.js 20+
- Docker
- Anthropic API key
- Fonnte API key (WhatsApp integration)

### Quick Start

```bash
# 1. Clone repository
git clone https://github.com/rasyidaldy10/autonomous-business-agents.git
cd autonomous-business-agents

# 2. Install OpenClaw
git clone https://github.com/openclaw-ai/openclaw.git
cd openclaw && npm install

# 3. Configure environment
cp .env.example .env
nano .env
# Add: ANTHROPIC_API_KEY, FONNTE_API_KEY, FONNTE_DEVICE_IDs

# 4. Create agent workspaces
mkdir -p workspace/{reyns,oki,anggi,novi,fikri,nabil,ari,nia,riko,nadim,shared}

# 5. Upload SOUL.md files to each agent workspace

# 6. Start with PM2
npm install -g pm2
pm2 start npm --name openclaw -- start
pm2 save && pm2 startup
```

---

## 📊 Rollout Phases

| Phase | Agents | Status | Milestone |
|---|---|---|---|
| **Phase 1** | Oki (COO Nanira) | 🔄 In Progress | WhatsApp auto-reply live |
| **Phase 2** | Reyns + Ari | ⏳ Planned | CEO orchestration + HR automation |
| **Phase 3** | Anggi + Riko + Nia | ⏳ Planned | Golden Medical full automation |
| **Phase 4** | Novi + Nabil + Fikri + Nadim | ⏳ Planned | Finance, research, e-commerce |
| **Phase 5** | All agents + Mission Control | ⏳ Planned | Full integration + live dashboard |

---

## 🔐 Security

- All agent configs stored in isolated workspace directories
- Weekly security audits via **AgentShield** (ECC framework)
- No sensitive data in repository (API keys via environment variables)
- Firewall configured — only ports 22, 80, 443 exposed
- Automated weekly backups to GitHub

---

## 📈 Business Impact (Target Metrics)

| Metric | Target |
|---|---|
| Admin hours saved per week | 20+ hours |
| WhatsApp response time (Oki) | < 5 minutes, 24/7 |
| Golden proposals per week | 5+ automated |
| Lead follow-up rate | 100% (zero missed) |
| Staff attendance accuracy | 100% automated |

---

## 🗺️ Architecture Principles

1. **Single point of contact** — Owner only talks to Reyns. No notification overload.
2. **Economic prioritization** — System understands money value. A Rp2B tender > a Rp500K marketplace chat.
3. **Result-oriented agents** — Measured by revenue impact, not activity count.
4. **Start lean, add later** — Agents launch with minimal tools, expanded via MCP as needs emerge.
5. **Human-in-the-loop by design** — Approval gates loosen progressively as agent trust is established.

---

## 👨‍💻 Author

**Rasyid** — Solo entrepreneur & AI systems builder, Pekanbaru, Indonesia

- 🏢 Owner: Nanira Family Reflexology, PT Golden Medical Care Indonesia, Zena
- 🔗 GitHub: [@rasyidaldy10](https://github.com/rasyidaldy10)
- 📱 Built for: Real business operations + Singapore tech portfolio

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

*Built with OpenClaw · Powered by Anthropic Claude · Deployed on Hostinger VPS*
