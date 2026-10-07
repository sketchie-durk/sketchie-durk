# 🏗️ Rocdwels ERP

Construction management ERP built for **Rocdwels Nigeria Ltd** — projects, job costing, requisitions, suppliers, and site operations in one system.

<p align="left">
  <img src="https://img.shields.io/badge/status-active--development-orange" alt="status" />
  <img src="https://img.shields.io/badge/frontend-Lovable-8A2BE2" alt="frontend" />
  <img src="https://img.shields.io/badge/backend-Supabase-3ECF8E?logo=supabase&logoColor=white" alt="backend" />
  <img src="https://img.shields.io/badge/deployed-Vercel-000000?logo=vercel&logoColor=white" alt="deployed" />
  <img src="https://img.shields.io/badge/domain-erp.rocdwels.ng-blue" alt="domain" />
  <img src="https://img.shields.io/badge/license-Proprietary-red" alt="license" />
</p>

---

## 📋 Overview

Rocdwels ERP replaces spreadsheet-based tracking with a live, connected system: every project has a budget broken into cost codes, every requisition checks against remaining budget, and every job cost entry rolls up into real actuals-vs-budget reporting.

**Live:** [erp.rocdwels.ng](https://erp.rocdwels.ng)

---

## 🧩 Modules

| Module | Status | Description |
|---|:---:|---|
| Projects | ✅ Live | Project setup, budget, PM assignment, timeline |
| Job Cost Sheets | 🚧 In Progress | Cost-code-linked expense tracking with approval workflow |
| Requisitions | 🚧 In Progress | Line-item material/labour/equipment requests |
| Suppliers | ✅ Live | Vendor directory |
| Daily Site Reports | ✅ Live | Weather, headcount, progress notes, photos |
| Variation Orders | ✅ Live | Contract change tracking |
| Milestones | ✅ Live | Phase-level progress tracking |
| Documents | ✅ Live | Project document storage |
| Team Chat | ✅ Live | In-app communication |
| Staff & RBAC | ✅ Live | Role-based access (admin / PM / supervisor / accountant) |

---

## 🛠️ Tech Stack

<p align="left">
  <img src="https://img.shields.io/badge/Lovable-frontend-8A2BE2" />
  <img src="https://img.shields.io/badge/Supabase-database%20%26%20auth-3ECF8E?logo=supabase&logoColor=white" />
  <img src="https://img.shields.io/badge/PostgreSQL-database-336791?logo=postgresql&logoColor=white" />
  <img src="https://img.shields.io/badge/Vercel-hosting-000000?logo=vercel&logoColor=white" />
  <img src="https://img.shields.io/badge/DomainKing-DNS-1a1a2e" />
</p>

- **Frontend:** Lovable (React-based)
- **Backend / DB / Auth:** Supabase (Postgres)
- **Hosting:** Vercel
- **DNS:** DomainKing → Vercel nameservers
- **Domain:** `erp.rocdwels.ng`

---

## 🗂️ Data Model

Core relational chain:

```
Project → Cost Codes (budget) → Requisition → Approval → Purchase Order
                                                              ↓
                                              Job Cost Sheet ← (actual spend)
                                                              ↓
                                              Budget rollup (actual vs committed vs remaining)
```

See [`rocdwels-erp-data-model.md`](./rocdwels-erp-data-model.md) for full schema, table-by-table field definitions, and build order.

---

## 🚧 Roadmap

- [ ] `cost_codes` table — per-project budget breakdown by category
- [ ] Link Job Cost Sheets to cost codes (replace free-text category)
- [ ] Requisition line items (multi-item, qty × unit cost)
- [ ] Live budget-remaining check on requisition/cost sheet submission
- [ ] Budget rollup triggers (Postgres functions, not client-side)
- [ ] Dashboard: budgeted vs actual vs committed per project/cost code
- [ ] Requisition → Purchase Order → Job Cost Sheet auto-linking

---

## 👤 Maintainer

Built and maintained by **Voss** ([@vxssroot](https://github.com/vxssroot)) as an ongoing consulting engagement with Rocdwels Nigeria Ltd.

---

## 📄 License

Proprietary — built for Rocdwels Nigeria Ltd. Not for redistribution.
