# WorkSpace 90-Day MVP Roadmap

## Product Thesis
Give small, mission-driven STEM providers the context, agents, workflows, and trust layer they need to compete with larger firms — in one workspace.

## Target Users (Phase 1 Beachhead)
Small STEM service providers in research support, technical consulting, engineering services, ocean-tech, space-tech support, university-affiliated labs, and niche public-sector subcontracting.

### User Roles

| Role | Job to Be Done | Pain Point |
|------|---------------|------------|
| Founder / Owner | Win new business and manage cash flow | Too much time on outreach and admin |
| Capture / BD Lead | Identify leads, contacts, and partner pathways | Fragmented pipeline and weak relationship memory |
| Proposal Manager | Turn opportunities into compliant submissions | Requirements and reusable content are scattered |
| Program Operator | Coordinate awarded work, status, and reporting | Too many disconnected tools |
| Researcher / Analyst | Produce technical insight and reusable knowledge | Research context is siloed and easily lost |

---

## Phase 1: Days 1–30 — Foundation & Proof of Workflow
**Deliverable:** Functional workspace with first AI outreach workflow running end-to-end

- [ ] Finalize product requirements, IA, and core data model
- [ ] Auth, organizations, workspaces, mission rooms, and file ingestion
- [ ] Memory primitives for mission, client, contact, and document context
- [ ] Scout + Liaison agent workflows for lead-to-meeting
- [ ] Basic CRM: account, contact, opportunity, activity, follow-up

## Phase 2: Days 31–60 — Proposal & Delivery Workflows
**Deliverable:** Proposal-ready platform — upload RFP → get compliant draft in minutes

- [ ] Proposal Studio: requirement extraction, compliance matrix, draft generation
- [ ] Delivery Hub: milestones, tasks, status updates, and decisions
- [ ] Approval queue, audit trail, and action logs
- [ ] Template library: outreach, capability statements, proposal sections
- [ ] Agent evaluation, latency, and human-acceptance metrics

## Phase 3: Days 61–90 — Monetization & Pilot Readiness
**Deliverable:** 3–5 paying pilot customers using WorkSpace to win real R&D work

- [ ] Finance Desk: invoice drafts, status tracking, and reminders
- [ ] Billing, plan limits, and usage metering (Stripe)
- [ ] Pilot admin dashboard with success metrics
- [ ] Marketplace alpha for invite-only skill packs
- [ ] Onboard 3–5 pilot customers in targeted verticals

---

## MVP Success Metrics

| Dimension | Metric |
|-----------|--------|
| Adoption | Weekly active teams, missions created, agent runs per workspace |
| Revenue Impact | Meetings booked, proposals started, proposals submitted, time-to-first-opportunity |
| Efficiency | Hours saved on outreach, proposal prep, and admin |
| Trust | Approval rate, edit rate after AI draft, rollback frequency |
| Retention | 30-day workspace retention, template reuse, memory recall usage |
| Monetization | Paid conversion, ARPU, attach rate for premium workflows |

---

## Vibe Coding Build Order (12 Steps)

1. **Define a tight PRD** — 1-page spec, no marketplace or tokens
2. **Generate domain model** — User, Org, Workspace, Mission, Account, Opportunity, EmailDraft, Invoice, Approval
3. **Build Next.js app shell** — Dashboard, Missions, Pipeline, Proposal Studio, Invoices, Approvals with dummy data
4. **Design Mission Room UI** — 4 tabs: Overview, Tasks, Documents, Messages
5. **Add simple NestJS backend** — DTOs and controllers, in-memory storage first
6. **Connect frontend to backend** — useMissions hook, /api/missions stub, navigation
7. **Add first AI workflow** — Scout + Liaison outreach draft with approval modal
8. **Add approval and audit trail** — status fields, approvedById, /api/audit endpoint
9. **Add proposal outline extraction** — file upload → mock AI → structured outline rendered
10. **Add invoice flow** — Draft/Sent/Paid lifecycle with edit lock
11. **Add auth and workspace isolation** — JWT, organizationId filtering, owner vs member
12. **Add rate limits and guards** — max 3 AI drafts/day, max 5 outline calls/day

### Golden Rules
- One feature per prompt — never ask for the whole app at once
- Run locally after each step before moving forward
- Use Git after every step so you can revert bad vibes
- Delay marketplace, tokens, and analytics until core MVP is stable

---

## Recommended Immediate Deliverables
1. PRD with screen map, workflows, and acceptance criteria
2. Relational schema and event model
3. Clickable frontend shell
4. API contract for first two workflows
5. Pilot plan for 3–5 early customers in one focused vertical
