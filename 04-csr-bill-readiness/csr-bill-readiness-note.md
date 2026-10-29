# Cyber Security and Resilience Bill: Readiness Note

## Lantern Managed Services Ltd

**Prepared for:** Managing Director and leadership team
**Prepared by:** Eugene Hayford
**Reference:** LMS-REG-CSR-001
**Date:** 29 October 2026
**Version:** 1.0
**Classification:** Confidential, Lantern internal

---

> **Scenario notice.** Lantern Managed Services Ltd is a fictional organisation. The description of the Bill is based on public sources listed at the end of this note and reflects its position as at 29 October 2026. This note is not legal advice. The Bill is not yet law, and much of the detail will be set by secondary legislation and regulator guidance that has not been published.

---

## 1. Bottom line

1. **Lantern is very likely to be in scope** as a *relevant managed service provider* (RMSP), regulated by the Information Commissioner. The only exemption that could apply is for small enterprises, and Lantern's headcount of 54 puts it above the 50 staff limit. Because Lantern is close to that line, the position should be confirmed with legal advice once commencement regulations are published (Section 3).
2. **Nothing is required yet.** The Bill was still in the House of Lords at the date of this note. After Royal Assent, the duties are switched on by regulations, and full effect is widely expected around 2028. Lantern has roughly 12 to 24 months to prepare, which is enough if work starts now.
3. **The hardest duty is the 24 hour initial report.** Today Lantern would almost certainly miss it. It has no way of detecting an incident on its privileged platforms, no way of classifying one as significant and no named person to decide whether to report (Section 6).
4. **Most of the work is already planned.** Measured against the NCSC Cyber Assessment Framework, Lantern achieves none of the 14 principles today and partially achieves 5 (Section 5). The ISO/IEC 27001 programme and the risk register treatment plan already cover most of the gap. This note adds three actions specific to the Bill (TP-44 to TP-46).
5. **The financial exposure is real but should not be overstated.** The maximum penalty for the most serious breaches is the higher of £17 million or 4% of worldwide turnover. A regulator must take proportionality into account, and early enforcement is more likely to focus on organisations that have made no effort to comply. The stronger commercial point is that Lantern's clients will start asking about it in due diligence before any regulator does.

---

## 2. Where the Bill stands

| Date | Stage |
|---|---|
| 12 November 2025 | Introduced in the House of Commons |
| June 2026 | Commons Report Stage and Third Reading completed |
| 14 July 2026 | Lords Second Reading |
| 7 September 2026 | Lords Committee Stage completed; Bill reprinted as HL Bill 49 |
| 26 October 2026 | Lords Report Stage scheduled to begin |
| Still to come | Lords Third Reading, Commons consideration of Lords amendments, Royal Assent |
| After Royal Assent | Duties commenced by regulations; registration window of three months opens for RMSPs |

**At the date of this note the Bill had not received Royal Assent.** The outcome of Lords Report Stage was not confirmed when this note was written and should be checked on the Parliament bill page before the note is relied on.

### Changes during the Bill's passage that matter to Lantern

- A Government amendment at Lords Committee Stage means that, when deciding whether an incident is reportable, an organisation must consider whether any data relating to the service has been compromised. For an MSP holding client credentials, this widens the range of incidents that could need reporting.
- Proposals on AI systems, public sector scope and a review of the Computer Misuse Act were withdrawn or not moved at Committee Stage. A power for government to give directions about certain vendors was tabled but not moved and may return at Report.

---

## 3. Is Lantern in scope?

### The test

A relevant managed service provider is an organisation that meets all four parts of this test:

| # | Test | Lantern | Met? |
|---|---|---|---|
| 1 | Provides a managed service in the UK: ongoing management of a customer's IT systems under contract, with access to those systems (support, maintenance, monitoring or active administration) | Managed IT support, managed cloud and managed backup are all ongoing, contracted and involve administrative access to client systems | Yes |
| 2 | Is not designated as a critical supplier for that service | No designation | Yes |
| 3 | Is not a micro or small enterprise under Commission Recommendation 2003/361/EC | See below | Yes, on current figures |
| 4 | Is not subject to public authority oversight, or earns more than half its income commercially | Private company, all income commercial | Yes |

Lantern's project services (one-off migrations and deployments) are probably not a managed service on their own, because they are not ongoing. This does not change the outcome. Once an organisation is an RMSP, the duties apply to the systems it uses to provide its managed services, and the project team uses the same RMM, vault and tenancy access.

### The small enterprise question

This is the only part of the test where Lantern's position is not clear cut.

Under Recommendation 2003/361/EC, an enterprise is **small** if it has **fewer than 50 staff** *and* either annual turnover *or* balance sheet total of **no more than €10 million**. The headcount test must always be met. Lantern's turnover of £8.4 million is below €10 million, so the financial test alone would not take it out of the small category. **The answer depends entirely on headcount.**

| Factor | Position for Lantern | Effect |
|---|---|---|
| Headcount today | 54 full time equivalent staff | Above 50, so not small |
| How staff are counted | The Recommendation counts annual work units: full time staff over the year, with part time and seasonal staff as fractions. Apprentices and students on vocational training are excluded | Lantern has 2 apprentices on the service desk. Excluding them gives 52, still above 50 |
| Two consecutive years | The Recommendation says an enterprise only gains or loses a size status if it crosses a threshold in two consecutive accounting periods | Lantern's average for the year to March 2026 was 51 and is projected at 54 for the year to March 2027. On these figures it crossed the line in both periods |
| Linked or partner enterprises | The Recommendation adds together the figures of linked and partner companies. The Bill does not say whether this rule applies | Lantern has no parent company or significant shareholdings, so this does not change anything |
| Currency | The thresholds are in euros and no sterling conversion has been set | Not relevant to Lantern, because headcount is decisive |

**Conclusion.** On current figures, Lantern is a medium enterprise and therefore an RMSP. The margin is small. A reduction of three or four FTE, or a different reading of how apprentices or contractors are counted, could change the answer.

**Recommendation.** Lantern should not plan around the exemption. Even if it ended up just under the line, its clients would still expect the same standard, and the regulator can designate small providers as critical suppliers. Lantern should get a short written legal opinion on its status once the commencement regulations and Information Commissioner guidance are published (TP-46).

---

## 4. What the duties are expected to be

| Duty | What the Bill says | Still to be decided |
|---|---|---|
| Registration | Register with the Information Commissioner within three months of the duty commencing; report changes within 7 days | Registration process, fee and information required |
| Security measures | Take appropriate and proportionate measures to manage risks to the systems used to provide the managed service, and to prevent and minimise the impact of incidents | Any specific requirements set by regulations; regulator guidance, which is widely expected to use the NCSC Cyber Assessment Framework |
| Incident reporting | Initial notification to the Information Commissioner within **24 hours** of becoming aware of a significant incident, and a full notification within **72 hours**. Both copied to the NCSC | Exact thresholds for a "significant" incident; reporting format |
| Customer notification | After the full notification, take reasonable steps to identify UK customers likely to be adversely affected and notify them, explaining the incident and why they are affected | Form of the notice, any deadline |
| Information and inspection | Respond to regulator information requests and inspections | Regulator approach |
| Cost recovery | Regulator may recover its regulatory costs from regulated organisations | Fee levels |
| Penalties | More serious breaches: up to the higher of £17 million or 4% of worldwide turnover. Less serious: up to the higher of £10 million or 2%. Regulators must take account of mitigation, history and impact | Enforcement approach |

Two points are worth stating plainly.

- **Reporting is triggered by awareness, not confirmation.** The 24 hours starts when Lantern becomes aware of a significant incident, not when it has finished investigating. Incidents with the potential for significant impact must be reported even if the impact has not happened yet.
- **This duty sits alongside UK GDPR, it does not replace it.** A breach of client personal data could require a report to the Information Commissioner under the CSR regime, notification of each affected client as their processor under UK GDPR, and in turn reports by those clients to the ICO as controllers. Lantern will need one process that handles all three.

---

## 5. Readiness against the NCSC Cyber Assessment Framework

The Bill does not yet name a standard, so this note uses the NCSC Cyber Assessment Framework (CAF) as the benchmark. It is the framework used under the existing NIS Regulations and the one regulators are most likely to adopt. Each principle is rated using the CAF's own terms and linked back to the gap assessment, risk register and treatment plan.

| CAF principle | Rating | Evidence | Linked to |
|---|---|---|---|
| A1 Governance | Not achieved | No security role, no management review, security only discussed after incidents | GAP-005, GAP-008; R-013; TP-06 |
| A2 Risk management | Partially achieved | Risk register drafted (v1.1) with methodology and appetite, but not yet approved or reviewed in a cycle | GAP-002; TP-07 |
| A3 Asset management | Not achieved | No information asset register | GAP-014 |
| A4 Supply chain | Partially achieved | Tier 1 assessment completed for the credential vault supplier (TPRA-001); other critical suppliers not yet assessed | GAP-012; R-008; TP-23, TP-24 |
| B1 Service protection policies and processes | Not achieved | 2019 policy, never reviewed or communicated | GAP-007 |
| B2 Identity and access control | Not achieved | No MFA on RMM or backup console, leaver accounts left active, shared and standing privileged access | GAP-016, GAP-021, GAP-030; R-001 to R-003; TP-01 to TP-04, TP-41 |
| B3 Data security | Partially achieved | Encryption in place; no classification, no DLP, backups untested | GAP-015, GAP-035, GAP-037; R-006, R-009 |
| B4 System security | Partially achieved | Intune and Defender in place; no change control over mass script execution; vulnerability management informal | GAP-031, GAP-033; R-004, R-014 |
| B5 Resilient networks and systems | Partially achieved | SaaS and Azure resilience; no BIA or tested continuity plan; flat office network | GAP-018, GAP-034; R-018 |
| B6 Staff awareness and training | Partially achieved | Annual phishing test only, 61% completion | GAP-011; R-015 |
| C1 Security monitoring | Not achieved | No SIEM, no alerting on privileged platforms | GAP-032; R-010; TP-36, TP-37 |
| C2 Proactive security event discovery | Not achieved | No threat hunting or threat intelligence process | GAP-017; R-014 |
| D1 Response and recovery planning | Not achieved | No incident response plan, no notification process | GAP-013; R-011, R-021; TP-26 |
| D2 Lessons learned | Not achieved | No post incident reviews | GAP-013 |

**Summary: 0 achieved, 5 partially achieved, 9 not achieved.**

This lines up closely with the ISO/IEC 27001 gap assessment, which is expected: the two frameworks ask for most of the same things. The practical consequence is that Lantern should run **one programme, not two**. The ISO/IEC 27001 roadmap, with the additions in Section 7, is the CSR Bill readiness programme.

---

## 6. The 24 hour test

To show where the reporting duty would fail, the scenario below follows the highest scored risk in the register (R-001): an attacker uses a stolen engineer password to log in to the RMM platform and pushes ransomware to client endpoints.

### Today

| Time | What happens | Problem |
|---|---|---|
| Day 1, 02:10 | Attacker logs in to the RMM with a stolen password. No MFA is required | GAP-030 |
| Day 1, 02:25 | Attacker runs a script across 40 client devices. Nothing alerts | No monitoring (GAP-032) |
| Day 1, 08:45 | Two clients ring the service desk about locked files. Logged as two separate tickets | No incident classification (GAP-013) |
| Day 1, 11:30 | An engineer spots the pattern and tells the Technical Director, who is on a client site | No defined escalation or deputy (R-013) |
| Day 1, afternoon | Engineers work to contain. Nobody considers whether the event must be reported | No notification process; nobody owns the decision |
| Day 2 | Containment continues. Some RMM logs have been overwritten at platform defaults | Evidence lost (A.5.28) |
| Day 3 | A client asks whether Lantern has reported to the regulator. Report not yet made | **24 hour deadline missed by about two days** |

The clock started when Lantern's engineer recognised the pattern at 11:30 on day 1, at the latest. Arguably it started earlier, when the first client call came in. Either way it was missed.

### Target state

| Time from awareness | What happens | Enabled by |
|---|---|---|
| 0 | Sentinel alert on mass script execution and new device sign in | TP-36, TP-37 |
| Within 30 minutes | On call engineer triages, opens a security incident in the PSA with a severity rating | TP-27 |
| Within 1 hour | Incident coordinator (Technical Director or named deputy) convened; containment starts; evidence preserved | TP-26, TP-28 |
| Within 4 hours | Reporting decision taken using the significant incident criteria, by a named decision maker | TP-44 |
| Within 24 hours | Initial notification sent to the Information Commissioner, copied to the NCSC, using a prepared template | TP-45 |
| Within 72 hours | Full notification sent | TP-45 |
| After full notification | Affected clients identified from the contact register and notified, using the client notice template. Personal data breach notices to clients as processor sent without undue delay in parallel | TP-45 |
| Within 4 weeks | Post incident review with lessons recorded | TP-26 |

### Dependency on suppliers

Lantern can only report what it knows. If the incident started at a supplier, the 24 hour clock depends on how fast that supplier tells Lantern. The third-party assessment of the credential vault supplier (TPRA-001) found a contractual notification window of 72 hours. Action TP-42 requires 24 hours at renewal. The same requirement should be built into every Tier 1 supplier contract as each is assessed.

---

## 7. Actions

Most of the readiness work is already in the risk register treatment plan. The table shows the actions that matter most for the Bill, with three new actions added to the register (TP-44 to TP-46).

### Existing actions that the Bill depends on

| Action | What it delivers for the Bill | Due |
|---|---|---|
| TP-06 Appoint an Information Security Manager | Someone who owns the duty (A1) | Dec 2026 |
| TP-01, TP-02, TP-41 MFA on RMM, backup console and vault | Removes the most likely cause of a reportable incident (B2) | Nov 2026 |
| TP-26 Incident response plan with notification decision tree | The process the 24 hour duty needs (D1) | Mar 2027 |
| TP-27 Security incident category in the PSA | Recognising an incident as an incident (D1) | Mar 2027 |
| TP-28 Tabletop exercise | Proves the process works, including the report (D1) | May 2027 |
| TP-36, TP-37 Sentinel and alerting | Detection, which starts the clock in a controlled way (C1) | Sep 2027 |
| TP-22 Legal and regulatory register | Tracks the Bill and its regulations (A1) | Mar 2027 |
| TP-23, TP-24, TP-42 Supplier register, assessments and 24 hour notification terms | Supply chain (A4) | Mar to May 2027 |

### New actions added to the risk register

| Action | Description | Owner | Due |
|---|---|---|---|
| TP-44 | Name the person accountable for CSR Bill compliance and the reporting decision, with a deputy. Draft significant incident criteria for Lantern based on the Bill and update them when the regulations are published. Prepare a registration pack (company details, services, contacts) so Lantern can register in the first month of the window | Managing Director | 31 Mar 2027 |
| TP-45 | Build notification templates (initial notice, full notice, client notice) and a client notification register recording, for each of the 140 clients, the services Lantern provides, the systems it manages and who to contact in an incident | Operations Director | 31 Mar 2027 |
| TP-46 | Obtain a written legal opinion on Lantern's RMSP status, including headcount counting, once commencement regulations and Information Commissioner guidance are published. Review the client contract template so incident notification terms match the new duty | Managing Director | 30 Jun 2027 |

### Optional, recommended

- **Adopt the government's Cyber Governance Code of Practice at board level.** It is voluntary, but it gives the leadership team a simple structure for the governance gaps under A1, and it signals intent to clients and the regulator.
- **Move from Cyber Essentials to Cyber Essentials Plus.** An independent technical audit is a low cost way to show progress on B2 and B4 before ISO/IEC 27001 certification is in place.

---

## 8. Decision requested

The leadership team is asked to:

1. **Note** that Lantern is very likely to be regulated as a relevant managed service provider, subject to legal confirmation.
2. **Agree** that CSR Bill readiness will be delivered through the existing ISO/IEC 27001 programme rather than as a separate project.
3. **Approve** actions TP-44 to TP-46 and add CSR Bill readiness as a standing item at the quarterly ISMS management review until the duties commence.

---

## Sources

- UK Parliament, [Cyber Security and Resilience (Network and Information Systems) Bill, bill page](https://bills.parliament.uk/bills/4035)
- Cyber Security and Resilience Bill tracker, [Lords Report Stage, October 2026](https://www.cybersecurityandresiliencebill.com/blog/cyber-security-resilience-bill-lords-report-stage-october-2026)
- Cyber Security and Resilience Bill tracker, [Relevant managed service provider](https://cybersecurityandresiliencebill.com/glossary/relevant-managed-service-provider) and [Micro or small enterprise](https://cybersecurityandresiliencebill.com/glossary/micro-or-small-enterprise)
- HCR Law, [Initial insights on the Cyber Security and Resilience (Network and Information Systems) Bill](https://www.hcrlaw.com/news-and-insights/initial-insights-on-the-cyber-security-and-resilience-network-and-information-systems-bill/)
- Foot Anstey, [Cyber Security and Resilience Bill: broader scope, tougher obligations](https://www.footanstey.com/our-insights/articles-news/cyber-security-resilience-bill-broader-scope-tougher-obligations/)
- Commission Recommendation 2003/361/EC concerning the definition of micro, small and medium-sized enterprises

---

*End of note.*
