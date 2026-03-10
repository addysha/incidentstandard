# IncidentStandard

> **The Global Workplace Safety Operating System**
>
> *Always There. Always Ready. Always For You.*

[![Status](https://img.shields.io/badge/status-in%20development-F4A23A?style=flat-square)](https://incidentstandard.com)
[![License](https://img.shields.io/badge/license-proprietary-1A6EBF?style=flat-square)](#license)
[![Stack](https://img.shields.io/badge/stack-React%20%7C%20Node.js%20%7C%20Python%20%7C%20AWS-2E8EE8?style=flat-square)](#tech-stack)
[![AI](https://img.shields.io/badge/AI-GPT--4o%20%7C%20RAG%20%7C%20Multi--Agent-18A46E?style=flat-square)](#ai-architecture)

---

## What Is This

IncidentStandard is an AI-powered, cloud-native SaaS platform that gives every organisation on earth - government, NGO, private company, or transport fleet - a single operating system for workplace safety.

The core doctrine behind every design decision:

> **"No employee should ever face an incident alone, unprepared, or unsupported."**

This repository contains the public-facing frontend and architecture documentation. Core backend services, AI orchestration layer, and API are maintained in a private repository.

---

## The Problem

Workplace safety tooling is broken in three ways:

- **Fragmented** - incident reporting, training, emergency response, and compliance live in separate tools that don't talk to each other
- **Expensive** - enterprise platforms like SAP EHS, Intelex, and Enablon charge per-user, per-module, and require long procurement cycles
- **Employee-last** - every existing tool is designed for compliance officers, not for the worker standing in front of an emergency

IncidentStandard solves all three.

---

## Core Features

### 🤖 AI-Guided Incident Reporting
No blank forms. No confused employees. The AI interviews the worker conversationally - asking yes/no and open questions - and writes the formal, compliant incident report in the background.

### ⚡ Real-Time Emergency Response
Typing `fire`, `explosion`, `chemical spill`, or `needle stick` activates a pre-built response stack in under 800ms. Emergency codes, first-response steps, local emergency numbers, and equipment locations - all surfaced before the report is complete.

### 📍 Live Evacuation & Safety Check
On CODE ORANGE activation, every registered employee receives a personalised alert - by name - with one-tap response: **Safe / Need Help / Not On Site**. H&S Officers see a live accountability dashboard in real time.

### 🚗 Driver SOS - Road Transport Vertical
A dedicated silent emergency protocol for lone drivers. One tap notifies police (with live GPS), dispatch, and operator simultaneously - the passenger sees nothing. Includes a lone-worker welfare check system with automatic police escalation at T+30 minutes.

### 📚 Training Platform & CPD Certificates
Pre-built training modules across all 21 incident categories. Auto-generated PDF certificates with CPD points, company logo, and digital signature. A full LMS replacement - built in.

### ⚖️ Compliance Intelligence Engine
GPS + organisation metadata → jurisdiction detected → applicable law surfaced automatically. ISO 45001, OSHA, UK HSE, EU-OSHA, AS/NZS 4801 - all built in. Compliance reports generated in correct regulatory language with notification deadlines auto-tracked.

### 🧠 AI Knowledge Repository
Every verified incident feeds an anonymised global knowledge base. Similar cases, proven corrective actions, and predictive risk patterns are surfaced automatically - creating compounding network effects as the platform grows.

---

## Incident Taxonomy

**445+ incident types across 21 categories** - the most comprehensive workplace incident taxonomy ever assembled.

| # | Category | Examples |
|---|----------|---------|
| 1 | Health & Medical | Needle stick, cardiac arrest, anaphylaxis |
| 2 | Fire & Explosion | Structure fire, gas explosion, arson |
| 3 | Electrical | Electrocution, arc flash, power outage |
| 4 | Chemical & Hazardous | Spill, gas leak, toxic exposure |
| 5 | Construction & Structural | Fall from height, scaffold collapse |
| 6 | Workplace Injuries | Laceration, crush injury, manual handling |
| 7 | Mental Health & Wellbeing | Acute distress, burnout, PTSD trigger |
| 8 | Workplace Conduct & HR | Harassment, discrimination, misconduct |
| 9 | Security & Crime | Robbery, intruder, bomb threat |
| 10 | Vehicle & Transport | Fleet accident, DUI, road rage |
| 11 | Natural Disasters | Earthquake, flood, severe weather |
| 12 | Equipment & Machinery | Entrapment, machinery failure, lockout |
| 13 | Cyber & Data | Ransomware, data breach, phishing |
| 14 | Aviation | Bird strike, runway incident, pressurisation |
| 15 | Marine & Maritime | Man overboard, vessel fire, grounding |
| 16 | Mining & Resources | Tunnel collapse, gas pocket, rockfall |
| 17 | Agriculture & Forestry | Pesticide exposure, tractor rollover |
| 18 | Education | Student injury, safeguarding, bullying |
| 19 | Food & Hospitality | Food poisoning, allergen, kitchen fire |
| 20 | Public Spaces & Events | Crowd crush, stage collapse, mass casualty |
| 21 | **🚗 Road Transport & Mobile Workforce** | Passenger assault, Driver SOS, cargo theft, lone worker |

---

## Four Access Portals

```
┌─────────────────────┐  ┌─────────────────────┐
│   👤 EMPLOYEE       │  │   🛡️ H&S OFFICER   │
│                     │  │                     │
│  · Report incidents │  │  · Case management  │
│  · Emergency guide  │  │  · Live evacuation  │
│  · Training + CPD   │  │  · Compliance rpts  │
│  · Welfare check-in │  │  · Analytics        │
└─────────────────────┘  └─────────────────────┘

┌─────────────────────┐  ┌─────────────────────┐
│   📊 AUTHORITY      │  │   ✅ CASE OFFICER  │
│                     │  │                     │
│  · KPI dashboards   │  │  · Verification     │
│  · Audit trail      │  │  · Quality control  │
│  · Reg. reporting   │  │  · Escalation mgmt  │
│  · Compliance score │  │  · KB contribution  │
└─────────────────────┘  └─────────────────────┘
```

---

## AI Architecture

IncidentStandard uses a **multi-agent orchestration layer** where specialist AI agents run in parallel on a shared incident context - not a single monolithic LLM call.

```
INCIDENT SUBMITTED
       │
       ▼
┌─────────────────────────────────────────────────┐
│           ORCHESTRATION LAYER                   │
│                                                 │
│  ┌──────────┐  ┌────────────┐  ┌─────────────┐ │
│  │ TRIAGE   │  │JURISDICTION│  │    MSDS     │ │
│  │  AGENT   │  │   AGENT    │  │   AGENT     │ │
│  │          │  │            │  │             │ │
│  │Classifies│  │GPS + org → │  │Chemical name│ │
│  │type +    │  │local law + │  │→ safety     │ │
│  │severity  │  │deadlines   │  │data sheet   │ │
│  └──────────┘  └────────────┘  └─────────────┘ │
│                                                 │
│  ┌──────────┐  ┌────────────┐  ┌─────────────┐ │
│  │COMPLIANCE│  │NOTIFICATION│  │ KNOWLEDGE   │ │
│  │  AGENT   │  │   AGENT    │  │   AGENT     │ │
│  │          │  │            │  │             │ │
│  │ISO/OSHA  │  │Email/push/ │  │RAG retrieval│ │
│  │clause    │  │SMS pipeline│  │similar cases│ │
│  │mapping   │  │orchestrator│  │+ actions    │ │
│  └──────────┘  └────────────┘  └─────────────┘ │
└─────────────────────────────────────────────────┘
       │
       ▼
  RESOLVED INCIDENT RECORD
```

**Models & Infrastructure:**
- `GPT-4o` - conversational report writing, dynamic question generation
- `Fine-tuned BERT` - incident type classification and keyword detection
- `Pinecone` - vector database for semantic case matching (RAG)
- `OpenAI Embeddings` - incident vectorisation pipeline

---

## Tech Stack

### Frontend
| Layer | Technology |
|-------|-----------|
| Web app | React 18 + TypeScript |
| Mobile app | React Native (iOS + Android) |
| State management | Zustand |
| Styling | Tailwind CSS |

### Backend
| Layer | Technology |
|-------|-----------|
| API gateway | Kong |
| Application services | Node.js (Express) microservices |
| AI / compliance services | Python FastAPI |
| Real-time | Socket.io + AWS API Gateway WebSocket |
| Job queues | Bull (Redis-backed) |

### Data
| Layer | Technology |
|-------|-----------|
| Primary database | PostgreSQL 15 (schema-per-tenant isolation) |
| Cache | Redis 7 |
| Vector store | Pinecone |
| Search | Elasticsearch |
| Analytics | ClickHouse |
| File storage | AWS S3 + CloudFront |

### Infrastructure
| Layer | Technology |
|-------|-----------|
| Cloud | AWS (multi-region: US / EU / APAC) |
| Containers | ECS Fargate |
| IaC | Terraform |
| CI/CD | GitHub Actions |
| Monitoring | Datadog |

---

## Emergency Response Architecture

Emergency activation target: **< 2 seconds end-to-end**

```
T+0ms    Keyword detected by NLP engine
T+200ms  Emergency code pushed to employee app (WebSocket)
T+400ms  H&S Officer alert - push notification + email
T+600ms  Building plans, equipment locations, MSDS retrieved
T+800ms  Jurisdiction engine → local emergency numbers surfaced
T+1000ms All officer/authority dashboards receive live alert
T+1500ms Personalised evacuation emails begin sending to all employees
T+2000ms Live safety check dashboard active - real-time accountability
```

---

## Compliance Standards Built In

| Standard | Jurisdiction | Coverage |
|----------|-------------|---------|
| ISO 45001 | International | Occupational H&S management |
| OSHA 29 CFR | United States | Federal workplace safety |
| UK HSE / RIDDOR | United Kingdom | Reporting + investigation |
| EU-OSHA 89/391 | European Union | Framework directive |
| AS/NZS 4801 | Australia / NZ | OHS management systems |
| ISO 14001 | International | Environmental management |
| GDPR | EU + adequacy countries | Data protection |

---

## Pricing

| Plan | Price | Duration | Users |
|------|-------|----------|-------|
| Organisation License | **$399** | 2 years | Unlimited employees + 5 officer accounts |

Flat. Global. No per-user fees. No add-ons. No procurement complexity.

---

## MVP Roadmap

- [x] Product architecture + technical design
- [x] Incident taxonomy (445+ types, 21 categories)
- [x] Frontend homepage + UI prototype
- [ ] **Phase 1** *(Months 1–4)* - Incident submission, H&S Officer dashboard, emergency code activation, org onboarding, 50 incident types, PDF reports
- [ ] **Phase 2** *(Months 5–9)* - Full AI conversational engine, live safety check, training + CPD, knowledge repository, jurisdiction intelligence, MSDS integration, Driver SOS
- [ ] **Phase 3** *(Months 10–18)* - 20+ languages, predictive analytics, API access, insurance partnerships, Slack / Teams / SAP integrations

---

## Repository Structure

```
incidentstandard/
├── frontend/               # React web application (public)
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   └── styles/
│   └── public/
├── docs/                   # Architecture documentation (public)
│   ├── architecture/
│   ├── taxonomy/
│   └── compliance/
├── design/                 # UI prototypes and design assets (public)
└── README.md

# Core backend, AI orchestration layer, and API
# are maintained in a private repository.
```

---

## Security & Compliance Targets

- **ISO 27001** - Information Security Management *(target: Year 2)*
- **SOC 2 Type II** - Security, availability, confidentiality *(target: Year 2)*
- **GDPR** - Privacy by design, data processing agreements in place
- AES-256 encryption at rest (AWS KMS)
- TLS 1.3 in transit
- Schema-per-tenant PostgreSQL isolation - no cross-tenant data access possible
- MFA required for all officer, authority, and case officer accounts

---

## Competitive Landscape

| Feature | IncidentStandard | SAP EHS / Intelex |
|---------|-----------------|-------------------|
| Incident types covered | 445+ across 21 categories | Sector-specific only |
| AI conversational reporting | ✅ Built in | ❌ Blank form |
| Road transport / driver safety | ✅ Category 21 + Driver SOS | ❌ Not offered |
| Live personalised safety check | ✅ Built in | ❌ Not offered |
| Training + compliance + emergency in one | ✅ Single platform | ❌ Separate tools |
| Flat pricing | ✅ $399 / 2 years | ❌ Per-user, per-module |
| Setup time | ✅ Self-serve, same day | ❌ Weeks of implementation |

---

## Contact

**Website:** [incidentstandard.com](https://incidentstandard.com)
**Status:** In active development - MVP targeting Q3 2025

---

## License

This repository contains public-facing frontend code and architecture documentation.

All source code, design assets, incident taxonomy, AI architecture, compliance frameworks, and associated intellectual property are proprietary and owned by IncidentStandard Ltd.

Unauthorised reproduction, distribution, or commercial use of any content in this repository is prohibited.

© 2025 IncidentStandard Ltd. All rights reserved.
