# WorkSpace Platform Architecture

## Overview
WorkSpace is an AI-native operating system built around the full business lifecycle of small R&D providers — from spotting an opportunity to delivering the work and getting paid. Context never lost. Human always in control.

## 4 Core Layers

| Layer | Purpose |
|-------|---------|
| **Context Layer** | Org memory, mission memory, files, contacts, prior work, templates, and structured knowledge |
| **Agent Layer** | 8 specialized AI operators with persistent memory, tool access, and approval checkpoints |
| **Workflow Layer** | Pipeline, outreach, proposals, project execution, invoicing, and reporting |
| **Trust Layer** | Governance, audit logs, approvals, provenance, RBAC, and policy-aware controls |

## 5 Core Workspaces

| Workspace | Purpose | Key Objects |
|-----------|---------|-------------|
| **Mission Room** | One place for each pursuit, project, or research effort | chat, tasks, docs, decisions, stakeholders |
| **Pipeline Hub** | Manage leads, agencies, primes, nonprofits, and universities | accounts, contacts, opportunities, follow-ups |
| **Knowledge Vault** | Store reusable institutional context | playbooks, capability statements, resumes, notes |
| **Delivery Hub** | Execute awarded work | milestones, risks, deliverables, updates |
| **Finance Desk** | Reduce back-office drag | invoices, payments, subcontractor records |

> **The Mission Room is the primary object.** A Mission could be a prospect pursuit, proposal effort, awarded contract, research initiative, or partnership. Each room has chat, docs, tasks, timeline, stakeholders, agent actions, and decisions in one persistent place.

## 5 Signature Workflows

### 01. Lead → Meeting
1. You describe capabilities, target sectors, and ideal buyers
2. **Scout** identifies likely customers and partnership pathways
3. **Liaison** drafts personalized outreach and follow-up sequences
4. ✅ **You review and approve** before anything is sent
5. System tracks replies and preps meeting briefs

### 02. Opportunity → Proposal
1. You upload an RFP, BAA, grant notice, or partner request
2. **Proposal Analyst** extracts requirements and builds compliance matrix
3. **Proposal Analyst** drafts outline, technical approach, and team sections
4. ✅ **You review and approve** the submission package
5. System archives with full provenance and audit trail

### 03. Award → Delivery
1. **Program Coordinator** converts scope into milestones, tasks, and dependencies
2. ✅ **You approve** the execution plan
3. System tracks progress and generates status reports
4. **Operations Clerk** drafts invoices at milestone completion
5. ✅ **You approve** billing and external communications

### 04. Research → Commercialization
1. You upload literature, notes, and technical findings
2. **Research Associate** summarizes evidence and maps applications
3. **Research Associate** packages capability narrative for funders or agencies
4. **Liaison** drafts partner outreach and commercialization pitches
5. ✅ **You review** all outputs before external audiences see them

### 05. Admin → Cash
1. **Operations Clerk** generates invoice drafts from completed milestones
2. ✅ **You approve** the invoice before send
3. System tracks payment status and sends reminders
4. **Operations Clerk** handles subcontractor records and timesheets
5. System maintains full audit trail for every financial action

## 8 AI Employees

| Agent | Role | Human Checkpoint |
|-------|------|-----------------|
| 🔭 Scout | Find leads, partners, opportunities | Approve target list |
| ✉️ Liaison | Draft outreach and follow-ups | Approve send |
| 🎯 Capture Lead | Organize pipeline and win themes | Approve pursuit strategy |
| 📋 Proposal Analyst | Build compliance matrix and draft sections | Approve submission package |
| 🗂️ Program Coordinator | Convert scope into execution plan | Approve milestones |
| 🧾 Operations Clerk | Draft invoices, reminders, admin tasks | Approve billing & actions |
| 🔬 Research Associate | Summarize technical evidence | Approve client-facing outputs |
| 🧭 Mentor Agent | Guide overwhelmed founders | — |

### Agent Architecture
**Supervisor + Specialist model.** One orchestration layer handles planning, memory retrieval, tool invocation, approvals, and result packaging. Every run stores inputs, retrieved context IDs, actions taken, outputs, confidence notes, and approval requirements.

## Tech Stack

| Layer | Recommendation | Why It Fits |
|-------|---------------|-------------|
| Frontend | Next.js + TypeScript | Strong product velocity, app-router patterns |
| Design System | Tailwind CSS + Component Library | Fast iteration and consistency |
| Backend API | NestJS or FastAPI | Modular services and workflow endpoints |
| Database | PostgreSQL | Core system of record |
| Vector / Retrieval | pgvector → dedicated DB later | MVP-simple and cost-aware |
| Agent Orchestration | LangGraph or Temporal | Durable, inspectable multi-step workflows |
| Async Jobs | BullMQ / Redis | Document parsing and long-running agent tasks |
| Auth | Clerk or Auth0 | Fast MVP setup, room to grow |
| Storage | S3-compatible | File attachments, proposal docs, exports |
| Billing | Stripe | Fast SaaS monetization path |
| Observability | OpenTelemetry + eval harness | Agent debugging and trust |

## Post-MVP: Tokenized Skills Marketplace

| Asset Type | Example | Model |
|-----------|---------|-------|
| Skill Pack | SBIR proposal extractor | One-time or subscription |
| Workflow Template | University-industry teaming flow | Subscription |
| Agent Persona | Grant-writing analyst | Usage-based or seat |
| Verified Data Connector | Agency opportunity feed | Subscription |
| Playbook | Deep-sea R&D commercialization guide | One-time |
