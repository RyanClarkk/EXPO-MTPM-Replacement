# EXPO MTPM Replacement

*AISAVING-137 | AI Savings Improvement Rapid Prototyping | GDMS M365 GovCloud*

---

## Overview

This project replaces the existing EXPO MTPM tool — a legacy SharePoint list used by program management stakeholders to track program performance metrics (TPMs/WPMs) across GDMS projects.

The replacement is a database-backed web application with a modern dashboard frontend, hosted within the existing GDMS M365 GovCloud environment. It was selected for rewriting because the effort is minimal — low cost, low risk, and ideal for testing modernization processes.

> *The current SharePoint/Power BI tool was a temporary migration of convenience — not a purposeful design. The new system is designed from scratch.*

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React (TypeScript) |
| API | ASP.NET Core Web API (.NET 8) |
| Database | Azure SQL Database (PaaS managed service) |
| Auth | MSAL + Microsoft Identity Platform (Azure AD) |
| Hosting | Azure App Service — GDMS M365 GovCloud |
| Source Control | GDMS GitLab |

*All components hosted within the GDMS M365 GovCloud tenant. No data leaves the boundary.*

---

## Project Status

| Story | Title | Status |
|---|---|---|
| [AISAVING-129] | Document EXPO Replacement Requirements and Data Migration Assessment | ${\color{green}\text{✅ Done}}$ |
| [AISAVING-130] | Technical Evaluation and Environment Setup | ${\color{orange}\text{🔄 In Progress}}$ |
| [AISAVING-131] | Build EXPO Replacement Prototype | ${\color{orange}\text{🔄 In Progress}}$ |
| [AISAVING-132] | Develop EXPO Replacement Application | ${\color{gray}\text{📋 Backlog}}$ |
| [AISAVING-133] | Conduct User Acceptance Testing | ${\color{gray}\text{📋 Backlog}}$ |
| [AISAVING-134] | Execute EXPO Data Migration | ${\color{gray}\text{📋 Backlog}}$ |
| [AISAVING-135] | Deploy EXPO Replacement to Production | ${\color{gray}\text{📋 Backlog}}$ |
| [AISAVING-136] | Develop Training Materials and Manage User Transition | ${\color{gray}\text{📋 Backlog}}$ |

---

## Repository Structure

```
expo-mtpm-replacement/
├── src/
│   ├── ExpoMtpm.Api/          ASP.NET Core Web API (.NET 8)
│   └── expo-mtpm-ui/          React TypeScript frontend
├── database/
│   └── migrations/            Entity Framework Core migrations
├── docs/
│   ├── EXPO_MTPM_Requirements_final_draft.docx
│   └── EXPO_MTPM_TechStack_Decision.pdf
└── README.md
```

---

## Key Requirements

- **Scale:** ~10,000 total users, 250 concurrent across all of GDMS
- **Auth:** Azure AD — no separate login required
- **Power BI:** Existing dashboard must remain functional; dev team configures database for external Power BI connection
- **Migration:** Full data migration required — all existing EXPO history must carry over. Clean start is not acceptable.
- **RAG Logic:** Threshold-based for WPMs; CPK-based for TPMs (owned by Griffin Buscavage)

---

## Points of Contact

| Role | Name |
|---|---|
| Customer / Primary User Contact | Richard Patch |
| RAG Calculation Owner | Griffin Buscavage |
| Developers | Ryan Clark, Davis Blanch |
| Product Owner / Manager | Dan Harlan |

---

## Estimated Cost Savings

| Category | Basis | Estimate |
|---|---|---|
| Maintenance savings | None assumed — new application | $0 |
| Performance savings | 365 users × 15 min/user × $90/hr | $8,212 |
| Data entry savings | 450 projects × 10 records/month × 15 min/record × $90/hr | $101,250 |
| **Total annual savings** | | **$109,462** |

*Figures provided by Dan Harlan following discussion with Richard Patch (June 2026). Growth assumption: 150 new projects/year at ~3 users per project.*

---

## Acceptance Criteria

- ${\color{green}\text{✅ AC 1}}$ — Requirements formally documented and approved by Richard Patch *(signed off June 23, 2026)*
- ${\color{green}\text{✅ AC 2}}$ — Requirements gate passed — prototype development may begin
- ${\color{gray}\text{⬜ AC 3}}$ — All existing EXPO data migrated and verified prior to go-live
- ${\color{gray}\text{⬜ AC 4}}$ — UAT conducted; all critical/high defects resolved
- ${\color{gray}\text{⬜ AC 5}}$ — Replacement deployed to production
- ${\color{gray}\text{⬜ AC 6}}$ — Training materials provided to users
- ${\color{gray}\text{⬜ AC 7}}$ — Legacy EXPO SharePoint tool decommissioned

---

*EXPO MTPM Replacement — General Dynamics Mission Systems | AISAVING Jira Project*
