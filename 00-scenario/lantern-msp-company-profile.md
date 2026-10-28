# Scenario Dossier: Lantern Managed Services Ltd

**Document type:** Portfolio scenario definition
**Author:** Eugene Hayford
**Version:** 1.0
**Date:** October 2026

---

> **Note on this document.** Lantern Managed Services Ltd is a fictional organisation created for the purpose of demonstrating governance, risk and compliance methodology. It does not represent any real company, and no confidential or client information is used anywhere in this portfolio. The scenario is deliberately constructed to contain realistic control weaknesses so that assessment findings are meaningful rather than contrived.

---

## 1. Purpose of this dossier

Every assessment in this portfolio (the ISO/IEC 27001:2022 gap assessment, the risk register, the third-party risk review and the Cyber Security and Resilience Bill readiness note) is performed against this single organisation. This document is the shared factual basis for all of them.

Defining the scenario formally before assessing it mirrors real practice: an assessor cannot produce defensible findings without first establishing scope, context, and the interested parties, as required by ISO/IEC 27001:2022 Clauses 4.1-4.3.

---

## 2. Organisation at a glance

| Attribute | Detail |
|---|---|
| Legal entity | Lantern Managed Services Ltd |
| Trading name | Lantern MSP |
| Incorporated | 2016, England & Wales |
| Headcount | 54 FTE |
| Head office | Birmingham, UK (leased 2nd-floor office, serviced building) |
| Secondary site | Manchester (8 staff, co-working space) |
| Annual turnover | £8.4m |
| Sector | IT managed services / outsourced IT |
| Clients | 140 UK SMEs and mid-market organisations |
| Certifications held | Cyber Essentials (basic), renewed annually |
| Certifications sought | ISO/IEC 27001:2022, board-approved target of Q3 2027 |

---

## 3. What Lantern actually does

Lantern provides outsourced IT to organisations with 20-400 staff. Four service lines:

**3.1 Managed IT support.** Service desk (first to third line), endpoint management, patching, user lifecycle administration. Lantern holds privileged administrative access into client environments via a remote monitoring and management (RMM) platform. This is the single most security-significant fact about the business.

**3.2 Managed cloud.** Administration of client Microsoft 365 and Azure tenancies. Lantern staff hold Global Administrator or delegated admin rights in approximately 110 client tenancies.

**3.3 Managed backup.** Backup-as-a-service for client data, held in a third-party UK-region cloud backup platform under Lantern's contract.

**3.4 Project services.** Migrations, infrastructure refresh, Microsoft 365 deployments. Project-based, non-recurring.

### Client base composition

| Client sector | Approx. share | Notes |
|---|---|---|
| Professional services (legal, accountancy) | 34% | High confidentiality sensitivity; several process special category data |
| Manufacturing & logistics | 26% | Includes two clients with operational technology environments |
| Healthcare (private clinics, dental groups) | 18% | Special category health data; clients subject to NHS DSPT in two cases |
| Charities & not-for-profit | 12% | Price-sensitive, limited internal IT |
| Other / retail | 10% | N/A |

---

## 4. Why Lantern is pursuing ISO 27001 now

Three drivers, in order of board priority:

1. **Lost revenue.** Lantern was excluded from three tenders in the last 14 months where ISO/IEC 27001 certification was a mandatory supplier requirement. Estimated lost contract value: £620k annualised.
2. **Client security questionnaires.** The sales team now receives 4-6 security questionnaires per month from prospects and existing clients at renewal. These are answered ad hoc by the Technical Director, taking roughly 3 hours each, with inconsistent answers between submissions.
3. **Regulatory exposure.** The Cyber Security and Resilience Bill explicitly brings managed service providers into the regulated population. Lantern's legal advisers have flagged that the company is likely to fall in scope and will face incident reporting duties and turnover-linked penalties.

---

## 5. Governance and structure

### 5.1 Leadership

| Role | Name (fictional) | Security-relevant responsibility |
|---|---|---|
| Managing Director | A. Okonkwo | Budget holder; chairs monthly leadership meeting |
| Technical Director | R. Mehta | De facto security owner; no formal security role defined |
| Operations Director | S. Whitfield | Service desk, SLAs, staffing |
| Finance Director | J. Clarke | Procurement, insurance, supplier contracts |
| Head of Sales | D. Fletcher | Owns client relationships and questionnaire responses |

There is **no information security manager, no CISO, and no formally appointed data protection officer.** The Technical Director absorbs security work alongside a full operational workload.

### 5.2 Teams

- Service Desk: 19 staff across three tiers
- Infrastructure & Cloud: 11 engineers
- Projects: 7 consultants
- Sales & Account Management: 9
- Finance, HR & Admin: 5
- Leadership: 3

### 5.3 Governance forums

- **Leadership meeting:** monthly. Security appears on the agenda only when an incident has occurred.
- **Technical review:** weekly, engineering only. Focuses on service delivery, not risk.
- There is **no risk committee, no management review of security, and no documented risk appetite.**

---

## 6. Technology estate

### 6.1 Lantern's own environment

| Layer | Detail |
|---|---|
| Identity | Microsoft Entra ID; 54 user accounts, 9 shared/service accounts |
| Productivity | Microsoft 365 E3 (E5 for leadership only) |
| Endpoints | 61 Windows laptops, 4 macOS, Intune-managed; 7 unmanaged "lab" devices |
| Server estate | Azure (3 subscriptions); one legacy on-prem Hyper-V host in Birmingham |
| Network | Office Wi-Fi with a single shared PSK; no network segmentation between corporate and lab |
| Email security | Microsoft Defender for Office 365 Plan 1 |
| Endpoint security | Microsoft Defender for Endpoint P1 |
| Logging | Entra and M365 audit logs retained 90 days; no SIEM |
| MFA | Enforced for all staff on M365; **not enforced on the RMM platform or the backup console** |

### 6.2 Client-facing tooling

| System | Purpose | Risk note |
|---|---|---|
| RMM platform (SaaS) | Remote access and script execution across ~3,200 client endpoints | Highest-value target in the business; shared engineer credentials in use for 6 client tenancies |
| PSA / ticketing (SaaS) | Tickets, time, client contact data | Contains client contact PII and system documentation |
| Documentation platform (SaaS) | Client network documentation and credential vault | Stores client administrative passwords |
| Backup platform (SaaS, UK region) | Client backup data | Sub-processor; DPA in place |
| Microsoft Partner Center | Delegated admin into client tenancies | Granular delegated admin partially rolled out; 41 clients still on legacy full delegated admin |

### 6.3 Known weak points (as understood by the Technical Director, undocumented)

- Engineer offboarding is inconsistent; two former engineers' RMM accounts were found active three months after leaving.
- No formal change control. Scripts are pushed to client estates at engineer discretion.
- The credential vault has no break-glass procedure and three engineers hold permanent full-vault access.
- Backups of Lantern's own data are not tested for restoration.
- No incident response plan exists in written form.

---

## 7. Information assets and data flows

| Asset | Classification (proposed) | Owner | Why it matters |
|---|---|---|---|
| Client administrative credentials | Secret | Technical Director | Compromise grants access to 140 client environments |
| Client backup data | Confidential | Infrastructure Lead | Includes special category data for healthcare clients |
| Client network documentation | Confidential | Infrastructure Lead | Attack roadmap if exposed |
| Ticketing data | Confidential | Operations Director | Client PII, system detail |
| Employee HR records | Confidential | HR Administrator | Special category data (health, right to work) |
| Commercial contracts & pricing | Confidential | Finance Director | Competitive harm |
| Marketing material | Public | Head of Sales | N/A |

### Data protection positioning

Lantern acts as a **data processor** for client data handled under managed services, and as a **data controller** for its own employee and prospect data. Client contracts include Article 28 processor terms in 118 of 140 cases; the remaining 22 are on pre-2019 contracts that have never been refreshed.

---

## 8. Current state of the information security management system

| ISO 27001 element | Current state |
|---|---|
| Documented scope | None |
| Information security policy | A 4-page policy written in 2019, never reviewed, not communicated |
| Risk assessment methodology | None |
| Risk register | None |
| Statement of Applicability | None |
| Asset inventory | Partial. Endpoints tracked in Intune, but no information asset register |
| Supplier register | Finance holds a payment list; no security assessment of suppliers |
| Incident log | Tickets only; no security incident classification |
| Internal audit | None |
| Management review | None |
| Security awareness training | Annual phishing simulation only; 61% completion |
| Business continuity plan | One page, written for a 2018 insurance renewal |

---

## 9. Interested parties and their requirements (Clause 4.2)

| Interested party | Requirement |
|---|---|
| Clients | Confidentiality of data, service availability, evidence of control via certification and questionnaires |
| Prospective clients | ISO 27001 certification as tender precondition |
| Regulators (ICO; prospective CSR Bill regulator) | Lawful processing; prospective incident reporting duties as an MSP |
| Employees | Lawful handling of HR data, clear security expectations |
| Insurers | Demonstrable controls to maintain cyber liability cover |
| Shareholders | Protection of enterprise value, avoidance of regulatory penalty |
| Suppliers / sub-processors | Contractual clarity on security obligations |

---

## 10. Proposed ISMS scope statement

> The information security management system covers the provision of managed IT support, managed cloud, managed backup and IT project services to clients of Lantern Managed Services Ltd, including the people, processes, information and technology used to deliver those services from the Birmingham and Manchester offices and from remote working locations, and including Lantern's administrative access to client environments.
>
> Exclusions: client-owned environments are outside the boundary of this ISMS except in respect of Lantern's own access to, and administration of, them.

---

## 11. How this dossier is used across the portfolio

| Artefact | Uses this dossier for |
|---|---|
| 01: ISO 27001:2022 gap assessment | Scope, context, current-state baseline, Statement of Applicability |
| 02: Risk register | Asset list, threat context, existing control state |
| 03: Third-party risk assessment | Supplier inventory and data flow into sub-processors |
| 04: CSR Bill readiness note | MSP scope determination, incident reporting capability |

---

*End of document.*
