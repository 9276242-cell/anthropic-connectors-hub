# SaaS Repositories Directory

Detailed catalog of Khan & Co. Enterprise SaaS platforms scheduled for submission to the Anthropic Claude Directory.

---

## 1. Health Safety and Environment (HSE)

* **Repository**: [`https://github.com/9276242-cell/hse`](https://github.com/9276242-cell/hse)
* **Local Working Path**: `/Users/anasmahmood/khanwco-repos/hse`
* **Target Connector Title**: `HSE Management Suite`
* **Target Category**: `Operations & Facilities` / `Productivity`
* **Core Functional Domains**:
  * Safety Incident Reporting (OSHA 300 compliance, immediate notification triggers)
  * Hazard Identification & Risk Assessment (HIRA matrices, corrective and preventive action tracking)
  * Digital Permit to Work (Hot work, confined space, height work authorizations)
  * Recurring Inspections & Equipment Audits (Scheduled cron reminders, checklists)
* **Connector Protocol Endpoints**:
  * Production SSE Transport: `https://hse.isoerp.com/mcp/sse`
  * OAuth Authorization: `https://auth.isoerp.com/oauth2/authorize?client_id=hse-claude`
  * OAuth Token: `https://auth.isoerp.com/oauth2/token`
* **Key Exposed Tools**:
  * `list_incidents` (Read only)
  * `create_incident_ticket` (Destructive action)
  * `get_hazard_matrix` (Read only)
  * `submit_inspection_finding` (Destructive action)
  * `export_osha_summary` (Read only)

---

## 2. ISA Audit Hub

* **Repository**: [`https://github.com/9276242-cell/isa`](https://github.com/9276242-cell/isa)
* **Local Working Path**: `/Users/anasmahmood/khanwco-repos/isa`
* **Target Connector Title**: `ISA Audit Hub`
* **Target Category**: `Finance & Accounting` / `Legal & Compliance`
* **Core Functional Domains**:
  * International Standards on Auditing (ISA 315, ISA 500, ISA 240, ISA 700 series)
  * Shariah Audit & Governance Workflows (AAOIFI standards, profit distribution verifications)
  * Materiality Determination & Sampling Worksheets (Statistical and non-statistical sample generators)
  * Audit Workpaper Management & Sign-off Workflows
* **Connector Protocol Endpoints**:
  * Production SSE Transport: `https://isa.isoerp.com/mcp/sse`
  * OAuth Authorization: `https://auth.isoerp.com/oauth2/authorize?client_id=isa-claude`
  * OAuth Token: `https://auth.isoerp.com/oauth2/token`
* **Key Exposed Tools**:
  * `lookup_auditing_standard` (Read only)
  * `calculate_materiality_thresholds` (Read only)
  * `generate_substantive_sample` (Read only)
  * `record_audit_finding` (Destructive action)
  * `approve_workpaper_step` (Destructive action)

---

## 3. ISOERP Core Platform

* **Repositories**: 
  * Backend & Web: [`https://github.com/9276242-cell/isoerp`](https://github.com/9276242-cell/isoerp)
  * MCP Gateway: [`https://github.com/9276242-cell/isoerp-mcp`](https://github.com/9276242-cell/isoerp-mcp)
* **Local Working Path**: `/Users/anasmahmood/khanwco-repos/isoerp` & `/Users/anasmahmood/khanwco-repos/isoerp-mcp`
* **Target Connector Title**: `ISOERP Enterprise System`
* **Target Category**: `Enterprise Software` / `Operations`
* **Core Functional Domains**:
  * Integrated Quality Management (ISO 9001 quality records, ISO 14001 environmental logs, ISO 27001 information security)
  * Multi-Tenant Supply Chain & Inventory Control
  * Document Control and Master Revision Registers
  * Enterprise User Roles, Granular Permissions, and Approval Queues
* **Connector Protocol Endpoints**:
  * Production SSE Transport: `https://gateway.isoerp.com/mcp/sse`
  * OAuth Authorization: `https://auth.isoerp.com/oauth2/authorize?client_id=isoerp-claude`
  * OAuth Token: `https://auth.isoerp.com/oauth2/token`
* **Key Exposed Tools**:
  * `search_quality_documents` (Read only)
  * `query_inventory_status` (Read only)
  * `create_corrective_action_request` (Destructive action)
  * `approve_purchase_order` (Destructive action)
  * `verify_tenant_compliance_badge` (Read only)

---

## 4. ISOERP North Star

* **Repository**: [`https://github.com/9276242-cell/isoerp-next`](https://github.com/9276242-cell/isoerp-next)
* **Local Working Path**: `/Users/anasmahmood/khanwco-repos/isoerp-next`
* **Target Connector Title**: `ISOERP North Star Executive Dashboard`
* **Target Category**: `Analytics & Reporting` / `Productivity`
* **Core Functional Domains**:
  * C-Suite Strategic KPI Tracking (Operational excellence, quality velocity, ESG metrics)
  * Continuous Improvement Analytics & Cross-Facility Benchmarking
  * Long-Term Transformation Milestones & Balanced Scorecards
* **Connector Protocol Endpoints**:
  * Production SSE Transport: `https://northstar.isoerp.com/mcp/sse`
  * OAuth Authorization: `https://auth.isoerp.com/oauth2/authorize?client_id=northstar-claude`
  * OAuth Token: `https://auth.isoerp.com/oauth2/token`
* **Key Exposed Tools**:
  * `get_executive_kpi_summary` (Read only)
  * `get_quality_maturity_score` (Read only)
  * `compare_facility_performance` (Read only)
  * `update_strategic_target` (Destructive action)
