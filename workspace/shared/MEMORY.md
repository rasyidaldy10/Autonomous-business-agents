# MEMORY.md — Shared Business Context

> Central knowledge file for the **Autonomous Business Agents** system, built on the **OpenClaw** framework. Every agent reads this file at startup and before major decisions. Keep it current; treat it as the single source of truth for business context.

---

## 1. Owner

- **Name:** Rasyid (Abdur Rasyid Aldy)
- **Location:** Pekanbaru, Riau, Indonesia
- **Role:** Founder / Owner of all three businesses
- **Single point of contact:** **REYNS (CEO agent)**. Rasyid talks to Reyns; Reyns coordinates every other agent. No agent contacts Rasyid directly — all routing goes through Reyns.
- **Signatory for legal/finance:** Abdur Rasyid Aldy, Direktur — PT Golden Medical Care Indonesia.

---

## 2. The Three Businesses

### 2.1 Nanira Family Reflexology ("Nanira" / "NaNiRa Fams")
- **Type:** B2C wellness / reflexology & massage spa.
- **Location:** Jl. Tuanku Tambusai, Labuh Baru Barat, Payung Sekaki, Pekanbaru.
- **Hours:** 09:00–22:00, last order 21:30.
- **COO agent:** OKI (24/7 customer service across WhatsApp, Instagram DM, TikTok DM).
- **HR agent:** ARI (staff attendance via Deli 3960 fingerprint, contracts, sick letters).
- **Pricing reference:** `oki/KNOWLEDGE.md`.
- **Customer DB:** `shared/CUSTOMERS.md`. **Staff schedule:** `shared/SCHEDULE.md`.

### 2.2 PT Golden Medical Care Indonesia ("Golden" / "Golden Medical" / "GMV")
- **Type:** B2B medical infrastructure — medical gas installation (O2, N2O, Medical Air, Vacuum), MEP, anti-bacterial vinyl, medical curtains/gorden.
- **Product brand:** G-MED (wall outlets, flowmeters, etc.).
- **COO agent:** ANGGI (B2B lead handling, WhatsApp Golden, Instagram DM).
- **Sales agent:** RIKO (sole owner of the sales pipeline).
- **Procurement/research agent:** NABIL (LKPP tenders, competitor pricing).
- **E-commerce agent:** NADIM (Shopee & Tokopedia G-MED store).
- **Marketing agent:** NIA (IG & TikTok, proposals).
- **Pricing reference:** `shared/PRODUCTS.md`. **Pipeline:** `shared/PIPELINE.md`.
- **Bank:** Mandiri / 1080030802244 / a.n. PT Golden Medical Care.

### 2.3 Zena
- **Type:** Tech product / app — Expo / React Native + Supabase + Vercel.
- **CTO agent:** FIKRI (code review, debugging, security).
- **Growth target:** first **22 active users** (research support from NABIL, marketing from NIA).
- **Marketing tone:** casual, relatable, **no overpromising**.

---

## 3. The Agent Roster

| Agent | Role | Primary Domain |
|-------|------|----------------|
| **Reyns** | CEO | Owner liaison, coordination, economic triage |
| **Oki** | COO | Nanira customer service (24/7) |
| **Anggi** | COO | Golden Medical B2B service (24/7) |
| **Novi** | CFO | Finance & invoicing, all 3 businesses |
| **Fikri** | CTO | Security, stability, OpenClaw infra, Zena code |
| **Nabil** | CPO | Research — tenders, trends, competitors, Zena growth |
| **Ari** | HR | Nanira staff attendance, contracts, sick letters |
| **Nia** | Marketing | IG/TikTok for Golden + Zena, Golden proposals |
| **Riko** | Sales | Golden Medical pipeline & revenue |
| **Nadim** | E-Commerce | Shopee & Tokopedia G-MED store |

---

## 4. Economic Triage (applied by Reyns before any owner notification)

Reyns classifies every issue by financial impact / urgency before deciding whether and when to disturb Rasyid:

| Tier | Trigger | Action |
|------|---------|--------|
| **CRITICAL** | > Rp100M impact, or deadline < 48h | Interrupt Rasyid immediately |
| **HIGH** | Rp10M–100M, or deadline < 7 days | Notify during work hours |
| **MEDIUM** | Rp1M–10M | Include in daily 06:00 briefing |
| **LOW** | < Rp1M / routine | Weekly summary only |

- **Auto-decide rule:** If owner is unresponsive for **120 minutes**, Reyns may decide autonomously — **except** for: price negotiation, hiring/firing, and big expenses (these always wait for Rasyid).

---

## 5. Key Decisions Made

- All agent ↔ owner communication is routed **exclusively through Reyns**.
- **Oki does NOT confirm bookings** — Oki processes the form and hands it to a human admin who confirms.
- **Vendor product prices** can be quoted directly by agents; **project installation prices** always escalate to Reyns.
- Novi never claims a financial report is definitively correct — **final approval is always Rasyid's**. Uncertain data is flagged with **"⚠️ perlu dicek"**.
- Riko is the **sole owner of lead status updates** to prevent conflicting pipeline versions.
- Disciplinary decisions (Ari/HR) are **never** made by an agent alone — always escalated to Reyns.
- Daily briefing cadence: **06:00 daily for the first month**, then **weekly on Monday** thereafter.

---

## 6. System Preferences

- **Framework:** OpenClaw. Security framework: **ECC** (github.com/affaan-m/ECC).
- **Never expose the system to the public internet.** Security first.
- Shared memory currently lives in markdown under `workspace/shared/`.
- **Phase 5 migration plan:** move shared markdown memory → **PostgreSQL** when data exceeds **500 entries** (owned by Fikri).
- **Learning mode active** — agents improve with usage and log lessons learned.
- **MCP skills can be added anytime** without disrupting other agents.
- Weekly memory audit + GitHub backup every **Sunday night** (Fikri).

---

## 7. Communication Preferences

- **Default language:** Indonesian.
- **Tone by agent:**
  - Reyns, Oki, Nadim — Indonesian **informal** (Oki & Nadim use "kak").
  - Anggi, Novi — Indonesian **formal** ("Bapak/Ibu").
  - Nia — Golden = professional B2B; Zena = casual/relatable.
- **Greetings:**
  - Nanira (Oki): "Halo, NaNiRa Fams 😊"
  - G-MED store (Nadim): "Halo Kak! Terima kasih sudah menghubungi G-MED Official 😊"
- **Metrics:** result-oriented — agents are measured by **business outcomes, not activity**.

---

*Last reviewed: 2026-06-15. Maintained collectively; Reyns owns conflict resolution.*
