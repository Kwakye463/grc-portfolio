# Third-Party Risk Assessment: Corvane Software Ltd

## Credential vault and IT documentation platform

**Prepared for:** Lantern Managed Services Ltd
**Prepared by:** Eugene Hayford
**Assessment reference:** TPRA-001
**Supplier tier:** Tier 1 (Critical)
**Assessment type:** Initial due diligence of an existing supplier
**Assessment period:** October 2026
**Version:** 1.0
**Classification:** Confidential, Lantern internal

---

> **Scenario notice.** Lantern Managed Services Ltd and Corvane Software Ltd are both fictional organisations. Corvane's evidence, responses and attestation results were constructed to resemble what a typical SaaS supplier provides, so that the assessment shows realistic judgement rather than a pass or fail exercise. No real supplier is described. Scenario detail for Lantern is in *Scenario Dossier: Lantern Managed Services Ltd*.

---

## Contents

1. Executive summary
2. Why this supplier was assessed first
3. Supplier tiering across Lantern's supply chain
4. Supplier profile
5. Assessment method
6. Domain assessment
7. Findings
8. Shared responsibility: what Lantern controls
9. Residual risk and options
10. Recommendation and conditions
11. Contract requirements for renewal
12. Ongoing monitoring
13. Appendix A: Security questionnaire and responses
14. Appendix B: Evidence log
15. Appendix C: Limitations

---

## 1. Executive summary

Corvane Software Ltd provides the documentation platform and credential vault that Lantern's engineers use to store client network documentation and the administrative credentials for all 140 client environments. A compromise of Corvane, or of Lantern's account on it, would give an attacker a route into every client Lantern supports. It is the single most sensitive supplier relationship Lantern has.

Lantern has used Corvane since 2019 without ever assessing it. This assessment was raised by gap finding GAP-012 and by risk R-008 in the risk register, which was the only risk still above appetite after its planned treatment.

**Overall supplier assurance: Adequate, with gaps.** Corvane holds ISO/IEC 27001:2022 certification and a SOC 2 Type II report, encrypts customer data at rest and in transit, and supports MFA, SSO and audit log export. Its security programme is credible for a company of its size. Four gaps matter to Lantern:

| # | Gap | Why it matters to Lantern |
|---|---|---|
| 1 | Breach notification to customers is contracted at 72 hours | Lantern will need to make an initial report within 24 hours once the Cyber Security and Resilience Bill applies. It cannot meet that if it hears about a supplier breach three days late. |
| 2 | Encryption keys are held and managed only by Corvane | Corvane staff or an attacker inside Corvane's environment could in principle decrypt stored credentials. There is no customer managed key option. |
| 3 | The SOC 2 report contains two exceptions, both in access and change control | These are the same weaknesses Lantern was criticised for in its own gap assessment. They are minor but need follow up. |
| 4 | Ownership changed in 2025 | A private equity acquisition brings a risk of product consolidation, price changes or reduced investment in security. |

**The most important finding is on Lantern's side, not Corvane's.** Lantern's own account on the platform does not enforce MFA, does not use SSO, has no IP restriction and gives three engineers permanent access to every credential. Lantern also stores far more in the vault than it needs to. Once the migration to granular delegated admin (GDAP) is complete, Lantern will no longer need tenant wide Global Administrator passwords stored anywhere.

**Recommendation: retain Corvane, subject to conditions.** Moving to another supplier would not change the risk much, because any vault holding the same credentials carries the same consequence if breached. The better lever is to reduce what the vault holds and harden Lantern's use of it. Doing both brings R-008 from 15 (High) today to a target of 6 (Medium), which is within Lantern's appetite for client trust risks. Until that work finishes, the residual risk stays at 10 (High) and needs formal interim acceptance by the Managing Director, which this report asks for in Section 10.

---

## 2. Why this supplier was assessed first

Lantern has four Tier 1 suppliers: the RMM platform, the PSA and ticketing platform, the backup platform and Corvane. Corvane was assessed first for three reasons.

1. **Concentration of secrets.** The RMM gives reach into client endpoints, but Corvane holds the credentials needed to reach client cloud tenancies, firewalls, hypervisors and line of business systems. It is the only system where a single breach exposes every type of client access at once.
2. **Weakest existing assurance.** The backup supplier already has a data processing agreement in place. Corvane has never been asked for any evidence.
3. **Renewal timing.** Corvane's contract renews on 31 March 2027, so there is a contractual window to fix the gaps found here.

---

## 3. Supplier tiering across Lantern's supply chain

Tiering decides how much assurance Lantern asks for. It is based on three questions: what data the supplier can reach, what access it gives into client environments, and how badly Lantern's service would be hit if the supplier failed.

### Tiering criteria

| Tier | Definition | Assurance required |
|---|---|---|
| Tier 1 (Critical) | Holds client credentials or client data, or provides privileged access into client environments, or failure would stop service to all clients | Full assessment before contract and every year: questionnaire, certification and attestation review, contract security schedule, exit plan |
| Tier 2 (Significant) | Holds Lantern personal data or confidential business data, or failure would disrupt internal operations | Light assessment every two years: certification check, DPA, short questionnaire |
| Tier 3 (Low) | No access to Lantern or client data and little operational impact | Standard terms and a check at onboarding only |

### Initial supplier register (by service, not vendor name)

| Supplier service | Data or access | Tier | Assessment status |
|---|---|---|---|
| Credential vault and documentation (Corvane) | Client admin credentials, client network documentation | 1 | This assessment |
| RMM platform | Remote access and script execution on c.3,200 client endpoints | 1 | Q1 2027 |
| PSA and ticketing | Client contact data, ticket history, system detail | 1 | Q1 2027 |
| Backup platform | Client backup data including special category data | 1 | Q2 2027 (DPA already in place) |
| Microsoft 365 and Azure | Lantern corporate data, Azure workloads | 1 | Reviewed through Microsoft's published ISO certificates and SOC reports; no questionnaire, because a hyperscaler will not complete one |
| Payroll and HR system | Employee personal data | 2 | Q2 2027 |
| IT asset disposal provider | Decommissioned devices containing data | 2 | Q2 2027 |
| Accountancy firm | Financial records | 2 | Q3 2027 |
| Manchester co-working provider | Physical access to the Manchester workspace | 2 | Q2 2027 (linked to GAP-029) |
| Office cleaning, stationery, catering | None | 3 | Standard terms |

The hyperscaler line is deliberate. Large cloud providers do not answer individual customer questionnaires, so the proportionate approach is to rely on their independent reports and focus Lantern's effort on how Lantern configures them.

---

## 4. Supplier profile

| Attribute | Detail |
|---|---|
| Legal entity | Corvane Software Ltd, registered in England and Wales |
| Founded | 2014 |
| Ownership | Acquired in May 2025 by a US based private equity backed software group |
| Headcount | About 180 staff, of whom about 25 work in engineering security and operations |
| Product used by Lantern | Corvane IT Docs, Professional tier |
| Lantern users | 41 named users (engineers, service desk team leaders, Technical Director) |
| Contract start | April 2019 |
| Current term ends | 31 March 2027, renews annually |
| Annual cost to Lantern | About £14,800 |
| Hosting | AWS London region (eu-west-2) for production; encrypted backups replicated to AWS Ireland (eu-west-1) |
| Data processed for Lantern | Client network documentation, configuration notes, client administrative credentials, client contact names and email addresses |
| Lantern's role | Lantern is a processor for its clients; Corvane is therefore Lantern's sub-processor |

---

## 5. Assessment method

The assessment followed five steps.

1. **Tiering and scoping.** Confirmed Corvane as Tier 1 and agreed the services and data in scope.
2. **Evidence request.** Requested Corvane's ISO/IEC 27001 certificate and Statement of Applicability, SOC 2 Type II report, most recent penetration test summary, data processing agreement, sub-processor list, incident history and business continuity summary.
3. **Questionnaire.** Sent a 30 question security questionnaire built around ten domains. The questions are mapped to ISO/IEC 27001:2022 Annex A and to the NCSC supply chain security principles. The full questionnaire and Corvane's responses are in Appendix A.
4. **Clarification call.** Held a 45 minute call with Corvane's Head of Security and Compliance to test responses and follow up on the SOC 2 exceptions.
5. **Lantern side review.** Reviewed how Lantern itself has configured and uses the platform, because many of the controls that matter are in Lantern's hands, not the supplier's.

### Rating scale

Each domain is rated on the evidence, not on the supplier's answers alone.

| Rating | Meaning |
|---|---|
| Strong | Control is in place and independently verified (certification scope, SOC 2 test with no exception, or test evidence) |
| Adequate | Control is in place and plausible, but evidence is partial or self reported |
| Weak | Control is missing, limited, or verified with exceptions that affect Lantern |
| Not evidenced | Supplier could not or would not provide evidence |

### What counts as evidence

A supplier's answer to a questionnaire is a claim. An ISO/IEC 27001 certificate shows that a management system exists and has been audited, but only within its stated scope, so the scope was checked against the service Lantern actually uses. A SOC 2 Type II report is stronger because an auditor tested the operation of controls over a period, but the exceptions and the complementary user entity controls (the controls the customer is expected to run) matter as much as the opinion.

---

## 6. Domain assessment

### 6.1 Governance and certification
**Rating: Strong**

Corvane holds ISO/IEC 27001:2022 certification issued by a UKAS accredited certification body, valid to February 2028. The certificate scope covers "development, operation and support of the Corvane IT Docs platform", which matches the service Lantern uses. Corvane provided an extract of its Statement of Applicability under NDA. It has a named Head of Security and Compliance reporting to the CTO, and security is reviewed quarterly by its executive team.

The SOC 2 Type II report covers 1 July 2025 to 30 June 2026 and gives an unqualified opinion on the Security and Availability criteria. A bridge letter covers the gap from 1 July to 30 September 2026.

### 6.2 Data protection and data location
**Rating: Adequate**

Production data is held in the AWS London region. Encrypted backups are replicated to AWS Ireland, which is covered by the UK adequacy regulations for the EEA. Corvane uses two US based sub-processors: a customer support ticketing platform and a transactional email service. The UK Addendum to the EU Standard Contractual Clauses is used for both. Corvane confirmed that customer vault contents are never sent to either one, but support tickets raised by Lantern's engineers can contain screenshots, which could include client information if engineers are careless.

The data processing agreement is dated 2019 and refers to the EU GDPR rather than the UK GDPR. It needs updating.

### 6.3 Customer facing access control and authentication
**Rating: Strong (supplier capability) / Weak (Lantern's configuration)**

The platform supports SAML single sign on, enforced MFA at account level (authenticator app or FIDO2 security key), role based access down to folder level, IP allow listing, and a time limited "request access" workflow for sensitive credentials. These are good capabilities.

Lantern uses almost none of them. See Section 8.

### 6.4 Encryption and key management
**Rating: Adequate**

Customer data is encrypted at rest with AES-256. Each customer account has its own data encryption key, which is itself encrypted by a key held in AWS Key Management Service. Corvane controls the KMS keys. TLS 1.2 or above is enforced in transit, with TLS 1.3 preferred.

Corvane does not offer customer managed keys or client side (zero knowledge) encryption. This means stored credentials can be decrypted inside Corvane's environment. Corvane's controls restrict this: production data access needs approval, is time limited and is logged, and Corvane staff can only see a customer's data when the customer grants a support access window. These controls are tested in the SOC 2 report. The underlying design still means Lantern is trusting Corvane's people and processes with the plaintext.

### 6.5 Secure development and vulnerability management
**Rating: Adequate**

Corvane follows a documented secure development process with code review, dependency scanning and static analysis in its build pipeline. A CREST accredited firm carried out a penetration test in March 2026. The summary letter reports no critical findings, one high finding (fixed and retested) and three medium findings with remediation due by December 2026. Corvane runs a public vulnerability disclosure programme but no bug bounty.

The SOC 2 report contains one exception in this area: for 2 of 40 sampled production changes, approval was recorded after deployment rather than before. Corvane's management response says the approval tooling has since been changed to block deployment without prior approval.

### 6.6 Logging and monitoring
**Rating: Strong**

Corvane monitors its own platform 24 hours a day through an outsourced security operations service. Customer facing audit logs record every credential view, copy, edit and export, with user, time and IP address. Logs are kept for 90 days in the platform and can be streamed by webhook or pulled through an API to a customer's SIEM. That means Lantern can send these events to Microsoft Sentinel when it is deployed (risk register action TP-36).

### 6.7 Incident response and breach notification
**Rating: Weak**

Corvane has a documented incident response plan tested annually. It reported one incident in the last three years: a credential stuffing campaign in 2025 against customer accounts that had not enabled MFA. No platform compromise took place. Corvane notified affected customers within 48 hours.

The weakness is contractual. The data processing agreement commits Corvane to notify Lantern of a personal data breach "without undue delay and in any event within 72 hours of becoming aware". Lantern itself must tell its own clients without undue delay as their processor, and once the Cyber Security and Resilience Bill applies it is expected to need to make an initial report to its regulator within 24 hours. A 72 hour supplier notification window can consume the whole of Lantern's own reporting window before Lantern knows anything has happened.

Corvane said on the call that in practice it would aim to notify within 24 hours, but would not commit to this in the current contract.

### 6.8 Business continuity and resilience
**Rating: Adequate**

The platform runs across three AWS availability zones in London. Corvane states a recovery time objective of 4 hours and a recovery point objective of 1 hour, and tests failover twice a year. Uptime over the last 12 months was 99.95% according to its public status page. Corvane offers an offline encrypted export that customers can download on a schedule, which Lantern does not currently use.

Lantern's real continuity exposure is different: if Corvane is unavailable during a major client incident, engineers cannot reach client credentials. There is no break glass copy held anywhere else.

### 6.9 Sub-processors and supply chain
**Rating: Adequate**

Corvane publishes its sub-processor list and gives 30 days' notice of changes by email to the account owner. Lantern's account owner is a former employee, so notices have been going to an unmonitored mailbox. Corvane assesses its own suppliers annually, which the SOC 2 report confirms.

### 6.10 Contract, financial stability and exit
**Rating: Weak**

Lantern accepted Corvane's standard online terms in 2019. There is no security schedule, no right to audit beyond receiving the SOC 2 report, no service credit for a security incident and no commitment on how long data is kept after termination.

On exit, Corvane provides a full export in JSON and CSV. Stored passwords are exported in plaintext inside an encrypted archive, so the export itself becomes a highly sensitive object that needs careful handling. Corvane deletes customer data within 30 days of termination and will provide a deletion certificate if asked.

The 2025 acquisition is a moderate concern. Corvane's latest filed accounts at Companies House show it was profitable before the acquisition, and the new parent group has kept the brand and the team so far. Acquisitions of this kind often lead to price rises or product consolidation within two to three years, which makes a tested exit plan more important.

### Domain summary

| Domain | Rating |
|---|---|
| 6.1 Governance and certification | Strong |
| 6.2 Data protection and data location | Adequate |
| 6.3 Customer facing access control (supplier capability) | Strong |
| 6.3 Customer facing access control (Lantern configuration) | Weak |
| 6.4 Encryption and key management | Adequate |
| 6.5 Secure development and vulnerability management | Adequate |
| 6.6 Logging and monitoring | Strong |
| 6.7 Incident response and breach notification | Weak |
| 6.8 Business continuity and resilience | Adequate |
| 6.9 Sub-processors and supply chain | Adequate |
| 6.10 Contract, financial stability and exit | Weak |

---

## 7. Findings

Findings are split by who has to act. "Supplier" findings need Corvane to change something, usually through the contract. "Lantern" findings are fully within Lantern's control.

### TPR-01: Breach notification window too long
**Owner of fix:** Supplier (via contract) | **Severity:** High

Corvane is contracted to notify personal data breaches within 72 hours. Lantern needs to know within 24 hours to meet its own obligations to clients and its expected CSR Bill reporting duty.

**Action.** At renewal, require notification of any security incident affecting Lantern's data within 24 hours of Corvane becoming aware, with a named contact and an agreed initial information set. Until then, register Lantern's security mailbox with Corvane's status and incident notification service so that Lantern at least receives public incident notices immediately.

---

### TPR-02: No customer controlled encryption
**Owner of fix:** Supplier (product roadmap) | **Severity:** Medium

Corvane holds all keys. Lantern cannot prevent decryption inside Corvane's environment.

**Action.** Ask Corvane to state in writing whether customer managed keys or client side encryption are on its roadmap, and record the answer. This finding is the main reason the impact of R-008 cannot be reduced by supplier controls alone, and it drives the recommendation in Section 9 to reduce what is stored in the vault.

---

### TPR-03: SOC 2 exceptions in change and access control
**Owner of fix:** Supplier | **Severity:** Low

Two exceptions: changes approved after deployment (2 of 40 samples), and one engineer's production access not removed within the required time after a role change.

**Action.** Request evidence that both remediations are working (a screenshot of the blocking deployment rule, and the latest quarterly access review sign off). Check that neither exception reappears in the next SOC 2 report, due around October 2027.

---

### TPR-04: Data processing agreement out of date
**Owner of fix:** Supplier and Lantern | **Severity:** Medium

The DPA dates from 2019 and refers to the EU GDPR. It does not reflect the UK GDPR or the current sub-processor list.

**Action.** Sign Corvane's current UK DPA, which Corvane confirmed exists. Add this to the legal and regulatory register (TP-22).

---

### TPR-05: No security terms in the contract
**Owner of fix:** Supplier and Lantern (contract) | **Severity:** Medium

Standard online terms only. No security schedule, no audit rights, no exit assistance.

**Action.** Negotiate the security schedule in Section 11 at the March 2027 renewal. Corvane said on the call that it has an enterprise addendum for larger customers, which is a reasonable starting point.

---

### TPR-06: MFA not enforced on Lantern's account
**Owner of fix:** Lantern | **Severity:** Critical

MFA is available but not enforced at account level. 6 of Lantern's 41 users have never enabled it, including one with full vault access. This is exactly the weakness exploited in Corvane's 2025 credential stuffing incident.

**Action.** Enforce MFA for all users immediately, preferring FIDO2 keys for anyone with access to credentials. Treat as an emergency change alongside TP-01 (added to the treatment plan as TP-41).

---

### TPR-07: SSO not used, so leavers keep access
**Owner of fix:** Lantern | **Severity:** High

Lantern's users log in with separate Corvane passwords. Disabling a leaver in Entra ID does not remove their Corvane access. This repeats the failure found in GAP-021.

**Action.** Configure SAML SSO with Entra ID and disable local password login, so that one disablement removes access everywhere. Covered by TP-09 and TP-13 once added to their scope.

---

### TPR-08: Standing full access and no IP restriction
**Owner of fix:** Lantern | **Severity:** High

Three engineers have permanent access to every credential. Access is possible from any IP address. The platform's "request access" workflow for sensitive credentials is not used.

**Action.** Remove standing full access. Use folder level permissions by client and team. Turn on the request access workflow for tenant administrator and firewall credentials. Restrict access to Lantern's office and VPN IP ranges, with a monitored break glass account. Covered by TP-16.

---

### TPR-09: The vault holds more than it needs to
**Owner of fix:** Lantern | **Severity:** High

The vault stores Global Administrator passwords for Microsoft 365 tenancies, shared local administrator passwords for client devices and firewall credentials for all clients. Once GDAP migration is complete (TP-15), engineers will reach client tenancies through their own Entra ID identities with time limited roles, so tenant wide admin passwords no longer need to be stored. Shared local administrator passwords can be replaced with Windows LAPS, which keeps a unique, rotating password on each device inside the client's own tenancy.

**Action.** After GDAP migration, remove stored Global Administrator credentials from the vault, keeping only sealed break glass accounts held by each client. Deploy Windows LAPS across managed client devices. This is the single most effective way to lower the impact of a Corvane breach, and it is entirely in Lantern's hands.

---

### TPR-10: Audit logs not collected and notices not received
**Owner of fix:** Lantern | **Severity:** Medium

Corvane audit logs are available but nobody looks at them. Sub-processor and security notices go to a former employee's mailbox.

**Action.** Change the account owner and notice address to a monitored security mailbox now. Stream audit logs to Sentinel when it is deployed (TP-36), with alerts on bulk export, unusual volume of credential views and access from new locations (TP-37).

---

### TPR-11: No exit plan and no offline copy
**Owner of fix:** Lantern | **Severity:** Medium

No exit plan exists, and there is no copy of critical credentials available if Corvane is down during an incident.

**Action.** Write an exit plan covering export, secure handling of the plaintext export, migration and confirmation of deletion (TP-32). Use the scheduled encrypted offline export for a limited break glass set only, stored in a sealed and audited location.

### Findings summary

| ID | Finding | Owner of fix | Severity | Linked actions |
|---|---|---|---|---|
| TPR-01 | Breach notification window too long | Supplier | High | TP-42 |
| TPR-02 | No customer controlled encryption | Supplier | Medium | Roadmap request |
| TPR-03 | SOC 2 exceptions | Supplier | Low | Evidence request |
| TPR-04 | DPA out of date | Both | Medium | TP-22 |
| TPR-05 | No security terms in contract | Both | Medium | TP-42 |
| TPR-06 | MFA not enforced on Lantern's account | Lantern | Critical | TP-41 |
| TPR-07 | SSO not used | Lantern | High | TP-09, TP-13 |
| TPR-08 | Standing full access and no IP restriction | Lantern | High | TP-16 |
| TPR-09 | Vault holds more than it needs to | Lantern | High | TP-15, TP-43 |
| TPR-10 | Logs not collected, notices not received | Lantern | Medium | TP-41, TP-36, TP-37 |
| TPR-11 | No exit plan or offline copy | Lantern | Medium | TP-32 |

Six of the eleven findings, including the only Critical one, are Lantern's own. This is common in third-party assessments and is the main lesson of this one: a supplier's certificate says nothing about how its customer has configured the service.

---

## 8. Shared responsibility: what Lantern controls

The SOC 2 report lists complementary user entity controls. These are controls Corvane assumes its customers operate, and its own controls are only effective if they do. Lantern's position against each is below.

| Corvane expects the customer to | Lantern today |
|---|---|
| Enforce MFA for all users | Not enforced; 6 users without MFA |
| Remove access promptly when users leave | Not done reliably; no SSO |
| Assign access on least privilege | Three users with full access to everything |
| Review user access periodically | Never done |
| Monitor audit logs for suspicious activity | Not done |
| Keep account contact details current | Account owner left Lantern in 2024 |
| Protect exported data | No procedure |

Lantern meets none of the seven. If an attacker reached client credentials through Lantern's account today, the cause would almost certainly be on Lantern's side of this table, not Corvane's.

---

## 9. Residual risk and options

### Effect on risk R-008

R-008 in the risk register is scored using the register's methodology (likelihood x impact, 1 to 5 each). Lantern's appetite for Client Trust and Privileged Access risks is a maximum score of 6.

| Stage | Likelihood | Impact | Score | Rating | Within appetite? |
|---|---|---|---|---|---|
| Before this assessment (register v1.0 current) | 3 | 5 | 15 | High | No |
| After Lantern side hardening (TPR-06, 07, 08, 10) and contract changes | 2 | 5 | 10 | High | No |
| After also reducing what the vault holds (TPR-09) | 2 | 3 | 6 | Medium | Yes |

**Why likelihood does not go lower than 2.** Corvane is a well run supplier, but credential vaults for MSPs are an attractive target and Lantern cannot see inside Corvane's environment. "Unlikely" is a fair score. "Rare" would need evidence Lantern does not have.

**Why impact only drops once the vault holds less.** No change to Corvane's controls or Lantern's login settings changes what an attacker gets if the vault itself is breached. Only reducing the contents changes the consequence. Once tenant administrator passwords are gone and device passwords are unique per device through LAPS, a breach would expose firewall credentials and documentation. That is serious, but it no longer opens every client's Microsoft 365 tenancy at once. This is scored as Moderate (3) rather than Severe (5).

### Options considered

| Option | Description | Residual score | Cost and effort | Assessment |
|---|---|---|---|---|
| A. Accept as is | Keep Corvane and change nothing | 15 | None | Not acceptable. Above appetite and the Lantern side weaknesses are cheap to fix. |
| B. Change supplier | Move to a vault with client side encryption | About 10 | Migration of 140 clients' documentation, retraining, likely higher licence cost; about 25 to 35 engineer days | Reduces one supplier risk but does nothing about Lantern's configuration or what the vault holds. Impact stays at 5. |
| C. Retain, harden and reduce (recommended) | Keep Corvane, fix Lantern's configuration, renegotiate the contract, and remove stored tenant admin credentials once GDAP is complete | 6 | Mostly configuration work already in the treatment plan, plus LAPS deployment (about 8 engineer days) | Brings the risk within appetite. Most actions are already planned for other reasons. |

Option B is worth revisiting only if Corvane refuses the contract changes at renewal or if the post acquisition owner materially reduces investment in the product.

---

## 10. Recommendation and conditions

**Recommendation: retain Corvane (Option C), with the following conditions.**

| # | Condition | Owner | Due |
|---|---|---|---|
| 1 | Enforce MFA for every Lantern user on the platform | Technical Director | 6 November 2026 |
| 2 | Change the account owner and notice address to the security mailbox | Technical Director | 6 November 2026 |
| 3 | Sign Corvane's current UK DPA | Finance Director | 31 December 2026 |
| 4 | Configure SSO with Entra ID and disable local login | Infrastructure Lead | 29 January 2027 |
| 5 | Remove standing full access, apply folder permissions, turn on request access and IP restriction | Technical Director | 30 April 2027 |
| 6 | Agree a security schedule including 24 hour incident notification at renewal | Finance Director | 31 March 2027 |
| 7 | Remove stored tenant administrator credentials after GDAP migration and deploy Windows LAPS | Infrastructure Lead | 30 July 2027 |
| 8 | Write and test the exit plan | Technical Director | 30 July 2027 |

If Corvane will not agree condition 6 by the renewal date, Lantern should renew for 12 months only and begin Option B in parallel.

### Interim risk acceptance requested

Until condition 7 is complete, R-008 remains at a residual score of 10, above the appetite of 6. Under the risk register methodology, only the Managing Director can accept a High risk. The Managing Director is asked to accept this residual risk on an interim basis until **30 July 2027**, on the basis that conditions 1 and 2 are completed by 6 November 2026. The acceptance should be minuted at the next leadership meeting and recorded in the risk register.

### Changes made to the risk register

The risk register has been updated to version 1.1 to reflect this assessment. R-008 now has a target score of 6 (likelihood 2, impact 3), which is within appetite, and three new actions have been added to the treatment plan: TP-41 (enforce MFA and fix the account owner), TP-42 (security schedule at renewal) and TP-43 (remove tenant admin credentials and deploy LAPS).

---

## 11. Contract requirements for renewal

The following should form a security schedule to Corvane's contract. They are written to be proportionate to a contract worth about £15,000 a year. Lantern should expect Corvane to resist some of them and should prioritise items 1 to 4.

1. **Incident notification.** Notify Lantern of any security incident affecting Lantern's data, or the confidentiality, integrity or availability of the service, within 24 hours of becoming aware, followed by updates at agreed intervals.
2. **Certification and assurance.** Maintain ISO/IEC 27001 certification covering the service, and provide each new SOC 2 Type II report and bridge letter on request.
3. **Data location.** Keep production data and backups in the UK or in countries covered by UK adequacy regulations, and give 30 days' notice of any change.
4. **Sub-processors.** Give 30 days' notice of new sub-processors, with a right for Lantern to object and to terminate without penalty if the objection is not resolved.
5. **Security standards.** Encrypt data at rest and in transit to current industry standards, and restrict and log all staff access to customer data.
6. **Vulnerability management.** Fix critical vulnerabilities within 7 days and high within 30 days, and share an annual penetration test summary.
7. **Exit assistance.** Provide a full export in a documented format within 10 working days of request, and certify deletion within 30 days of termination.
8. **Audit.** Answer one reasonable security questionnaire a year, and provide further information following any incident affecting Lantern.

---

## 12. Ongoing monitoring

| Activity | Frequency | Owner |
|---|---|---|
| Full reassessment (questionnaire, SOC 2, certificate) | Annually, before renewal | Technical Director |
| Review new SOC 2 report and bridge letter | When issued | Information Security Manager |
| Review sub-processor change notices | When received | Information Security Manager |
| Review Corvane status page incidents | Monthly | Infrastructure Lead |
| Review audit log alerts in Sentinel | Daily, once TP-37 is live | Infrastructure Lead |
| Check Companies House filings and ownership news | Annually | Finance Director |

### Triggers for an early reassessment

- Corvane reports a security incident affecting any customer.
- Corvane changes ownership, hosting provider or data location.
- A new SOC 2 report contains exceptions in access, change or encryption controls.
- Lantern changes what it stores on the platform.
- Credible public reports of vulnerabilities in the platform.

---

## 13. Appendix A: Security questionnaire and responses

Ratings reflect the evidence seen, not the answer alone. "SR" means self reported with no supporting evidence.

| # | Domain | Question | Corvane response (summary) | Evidence | Rating |
|---|---|---|---|---|---|
| 1 | Governance | Do you hold ISO/IEC 27001 certification, and does its scope cover the service we use? | Yes, 2022 version, scope covers the IT Docs platform | Certificate, SoA extract | Strong |
| 2 | Governance | Do you have an independent attestation of control operation? | SOC 2 Type II, Security and Availability | SOC 2 report, bridge letter | Strong |
| 3 | Governance | Who is accountable for security? | Head of Security and Compliance, reports to CTO | Org chart | Strong |
| 4 | Governance | How often are security policies reviewed? | Annually | SOC 2 tested | Strong |
| 5 | People | Are staff screened before employment? | Identity, right to work, references, basic criminal record check for production access roles | SOC 2 tested | Strong |
| 6 | People | Do staff receive security training? | On joining and annually, with phishing simulations | SOC 2 tested | Strong |
| 7 | Data | Where is our data stored and backed up? | AWS London, backups AWS Ireland | Trust centre, call | Adequate |
| 8 | Data | Which sub-processors can access our data? | AWS (hosting), US support platform, US email service | Sub-processor list | Adequate |
| 9 | Data | What transfer mechanism is used for non UK sub-processors? | UK Addendum to EU SCCs | DPA | Adequate |
| 10 | Data | Is our data used for any other purpose, including product analytics or AI training? | No. Usage metadata only, no vault contents | SR | Adequate |
| 11 | Access | Do you support SSO and enforced MFA? | SAML SSO, account level MFA enforcement, FIDO2 | Product docs, tested in trial account | Strong |
| 12 | Access | Can access be restricted by IP address? | Yes, Professional tier and above | Product docs | Strong |
| 13 | Access | How do your staff access customer data? | Only through a customer granted support window; production access approved, time limited and logged | SOC 2 tested (one exception) | Adequate |
| 14 | Encryption | How is data encrypted at rest? | AES-256, per customer data keys wrapped by AWS KMS | Architecture whitepaper | Adequate |
| 15 | Encryption | Who controls the encryption keys? | Corvane | Call | Weak |
| 16 | Encryption | Do you offer customer managed keys or client side encryption? | No, under consideration | Call | Weak |
| 17 | Encryption | What protocols protect data in transit? | TLS 1.2 minimum, 1.3 preferred | External scan by assessor | Strong |
| 18 | Development | Describe your secure development process. | Code review, SAST, dependency scanning in pipeline | SOC 2 tested (one exception) | Adequate |
| 19 | Development | When was the last independent penetration test? | March 2026, CREST accredited firm | Summary letter | Adequate |
| 20 | Development | Do you run a vulnerability disclosure programme? | Yes, public VDP, no bug bounty | Website | Adequate |
| 21 | Vulnerability | What are your patching timescales? | Critical 72 hours, high 14 days | SR | Adequate |
| 22 | Logging | Do you monitor the platform for threats? | 24/7 outsourced SOC | SOC 2 tested | Strong |
| 23 | Logging | What audit logs can we access and for how long? | All credential actions, 90 days, API and webhook export | Product docs, trial account | Strong |
| 24 | Incident | Do you have a tested incident response plan? | Yes, tested annually | SOC 2 tested | Strong |
| 25 | Incident | How quickly will you notify us of a breach? | Within 72 hours under DPA; aim for 24 hours in practice | DPA | Weak |
| 26 | Incident | Have you had any security incidents in the last three years? | One credential stuffing campaign against customer accounts in 2025, no platform breach | Customer notice, call | Adequate |
| 27 | Continuity | What are your RTO and RPO? | 4 hours and 1 hour | SR, status page history | Adequate |
| 28 | Continuity | How often is failover tested? | Twice a year | SOC 2 tested | Strong |
| 29 | Exit | How do we get our data back if we leave? | Full JSON and CSV export; passwords in plaintext within an encrypted archive | Product docs | Adequate |
| 30 | Exit | How long is data retained after termination? | Deleted within 30 days; certificate on request | DPA | Adequate |

---

## 14. Appendix B: Evidence log

| Evidence | Received | Date | Notes |
|---|---|---|---|
| ISO/IEC 27001:2022 certificate | Yes | Valid to Feb 2028 | Scope checked against service used |
| Statement of Applicability extract | Yes, under NDA | 2026 | No exclusions relevant to Lantern |
| SOC 2 Type II report | Yes, under NDA | Period Jul 2025 to Jun 2026 | Unqualified opinion, two exceptions |
| SOC 2 bridge letter | Yes | Covers to 30 Sep 2026 | No material changes reported |
| Penetration test summary | Yes | March 2026 | Summary letter only; full report not shared |
| Data processing agreement | Yes | 2019 | Out of date (TPR-04) |
| Sub-processor list | Yes | Current | Three sub-processors |
| Architecture and encryption whitepaper | Yes | 2026 | Confirms supplier held keys |
| Business continuity summary | Yes | 2026 | Two page summary only |
| Incident history | Yes, verbally and by customer notice | 2025 incident | Confirmed on call |
| Lantern account configuration export | Yes, from Lantern's admin console | October 2026 | Basis for TPR-06 to TPR-10 |
| Companies House filings | Yes, public | Latest accounts | Pre acquisition, profitable |

---

## 15. Appendix C: Limitations

1. **Reliance on supplier evidence.** Lantern has no right to audit Corvane directly. The assessment relies on Corvane's certification, its SOC 2 report and its answers. Self reported answers are marked SR in Appendix A.
2. **Full penetration test report not seen.** Only the summary letter was provided, which is normal practice but limits what can be concluded about the open medium findings.
3. **Point in time.** This assessment reflects October 2026. Supplier controls and ownership may change.
4. **No technical testing of Corvane.** The assessor did not test Corvane's systems, which would breach its terms of service. Testing was limited to an external TLS check and features available in a trial account.
5. **Lantern side review was configuration only.** It did not include a review of how individual engineers handle credentials outside the platform.

---

*End of report.*
