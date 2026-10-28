# ISO/IEC 27001:2022 Gap Assessment

## Lantern Managed Services Ltd

**Prepared by:** Eugene Hayford
**Assessment type:** Pre-certification readiness gap assessment
**Standard:** ISO/IEC 27001:2022 and ISO/IEC 27002:2022
**Assessment period:** October 2026
**Version:** 1.0
**Classification:** Confidential, Lantern internal

---

> **Scenario notice.** Lantern Managed Services Ltd is a fictional organisation. This assessment is a demonstration of methodology and contains no real client, employee or commercial information. Scenario detail is defined in the accompanying document *Scenario Dossier: Lantern Managed Services Ltd*.

---

## Contents

1. Executive summary
2. Scope of assessment
3. Assessment methodology
4. Maturity scoring model
5. Summary of results
6. Management system findings (Clauses 4-10)
7. Annex A Theme 1 findings, Organizational controls
8. Annex A Theme 2 findings, People controls
9. Annex A Theme 3 findings, Physical controls
10. Annex A Theme 4 findings, Technological controls
11. Statement of Applicability: extract and exclusion rationale
12. Remediation roadmap
13. Assessor's opinion on certification readiness
14. Appendix A: Evidence requested and received
15. Appendix B: Limitations

---

## 1. Executive summary

Lantern Managed Services Ltd has a board-approved objective to achieve ISO/IEC 27001:2022 certification by Q3 2027. This assessment establishes the distance between the organisation's current state and the requirements of the standard.

**Overall readiness: 24%.** Lantern is not currently in a position to enter a Stage 1 certification audit and would not pass one. The organisation operates a number of effective technical controls, but it has no management system: no documented scope, no risk assessment methodology, no risk register, no Statement of Applicability, no internal audit function, and no management review. ISO/IEC 27001 certifies the management system, not the technology. Lantern's deficit is therefore structural rather than technical.

### The five findings that matter most

| # | Finding | Why it is critical |
|---|---|---|
| 1 | No information security risk management process exists (Clauses 6.1.2, 6.1.3, 8.2, 8.3) | This is the engine of the entire standard. Nothing else can be justified without it, and the Statement of Applicability cannot be produced. Certification is impossible until this exists. |
| 2 | Multi-factor authentication is not enforced on the RMM platform or the backup console (A.5.17, A.8.5) | These two systems grant administrative reach into approximately 3,200 endpoints across 140 client organisations. This is the highest-consequence technical gap in the business and is independently a major non-conformity risk. |
| 3 | Leaver access revocation is not reliably performed; former engineer accounts remained active for three months (A.5.18, A.6.5) | Demonstrable control failure with evidence of actual occurrence. An auditor finding a known, uncorrected failure of this kind will raise a major non-conformity. |
| 4 | No supplier security assessment process, despite material sub-processor dependency (A.5.19-A.5.22) | Lantern is itself a supplier under scrutiny yet applies no equivalent scrutiny to its own supply chain. Clients' questionnaires will surface this. |
| 5 | No documented incident response plan or security incident classification (A.5.24-A.5.28) | Required by the standard and, separately, by the incident reporting duties anticipated under the Cyber Security and Resilience Bill. |

### Commercial framing

The three tenders Lantern lost in the last 14 months represented an estimated £620k of annualised contract value. The remediation programme set out in Section 12 is estimated at **£78k-£96k in year one**, including certification body fees, and requires one dedicated part-time resource. On the organisation's own figures, the programme pays for itself against a single recovered tender.

---

## 2. Scope of assessment

This assessment was performed against the proposed ISMS scope:

> The provision of managed IT support, managed cloud, managed backup and IT project services to clients of Lantern Managed Services Ltd, including the people, processes, information and technology used to deliver those services from the Birmingham and Manchester offices and from remote working locations, and including Lantern's administrative access to client environments.

**In scope:** all 54 staff; both offices; remote working; Lantern's corporate IT estate; the RMM, PSA, documentation/credential vault and backup platforms; Lantern's delegated administrative access into client tenancies.

**Out of scope:** client-owned environments, except in respect of Lantern's access to and administration of them. Client-side controls are the clients' own responsibility and are not assessed here.

**Assessment covers:** ISO/IEC 27001:2022 Clauses 4 to 10, and all 93 Annex A controls.

---

## 3. Assessment methodology

The assessment followed a four-stage approach.

**Stage 1: Documentation review.** All available policy, procedure and record documentation was requested against a standard evidence list (Appendix A) and reviewed against the corresponding clause or control requirement.

**Stage 2: Structured interviews.** Interviews were held with the Managing Director, Technical Director, Operations Director, Finance Director, the Infrastructure Lead and two service desk team leaders. Interviews tested whether documented practice matched actual practice, and whether undocumented practice existed that could be formalised.

**Stage 3: Technical corroboration.** Configuration was sampled directly where practical, including Entra ID conditional access policies, Intune compliance policies, M365 audit log retention settings, RMM user list, and Partner Center delegated admin relationships. Interview assertions were not accepted without corroboration where corroboration was available.

**Stage 4: Scoring and finding development.** Each clause and control was scored against the maturity model in Section 4. Findings were raised where the score fell below the level required for certification, and each was assigned a severity, a recommended action, an owner and an effort estimate.

### Principles applied

- **Evidence over assertion.** A control claimed but not evidenced is scored as if absent. The standard requires documented information; an auditor will take the same position.
- **Effectiveness over existence.** A policy that exists but is not communicated, followed or reviewed does not satisfy the standard.
- **Proportionality.** Lantern is a 54-person organisation. Recommendations are scaled to that reality. Recommending an enterprise GRC platform to a company of this size would be poor advice, and recommendations avoid that error.

---

## 4. Maturity scoring model

| Score | Level | Definition | Certifiable? |
|---|---|---|---|
| 0 | Absent | No evidence of the control or requirement in any form. | No |
| 1 | Initial | Performed informally by individuals. Undocumented, inconsistent, dependent on specific people. | No |
| 2 | Developing | Partially documented or partially applied. Significant gaps in coverage or consistency. | No |
| 3 | Defined | Documented, communicated, consistently applied, and producing records. | **Yes (minimum certifiable level)** |
| 4 | Managed | As Defined, plus measured, reviewed, and with evidence of correction when it drifts. | Yes |
| 5 | Optimising | As Managed, plus subject to continual improvement with demonstrated changes over time. | Yes |

**Level 3 is the certification threshold.** Scores of 0-2 generate findings. The target state for Lantern across the board is Level 3, with Level 4 for the small number of controls carrying the highest consequence.

### Severity definitions

| Severity | Meaning |
|---|---|
| **Critical** | Would be raised as a major non-conformity. Blocks certification. Also represents live, material risk to the business. |
| **High** | Would be raised as a major or multiple minor non-conformities. Must be resolved before Stage 2. |
| **Medium** | Would be raised as a minor non-conformity. Should be resolved before Stage 2; may be acceptable with a corrective action plan. |
| **Low** | Observation or opportunity for improvement. Does not block certification. |

---

## 5. Summary of results

### By management system clause

| Clause | Requirement area | Score | Target | Gap |
|---|---|---|---|---|
| 4 | Context of the organisation | 1 | 3 | 2 |
| 5 | Leadership | 1 | 3 | 2 |
| 6 | Planning (incl. risk assessment & treatment) | 0 | 3 | 3 |
| 7 | Support (resources, competence, awareness, documented information) | 1 | 3 | 2 |
| 8 | Operation | 0 | 3 | 3 |
| 9 | Performance evaluation (monitoring, internal audit, management review) | 0 | 3 | 3 |
| 10 | Improvement (non-conformity, corrective action) | 0 | 3 | 3 |

**Management system average: 0.4 / 3.** This is the defining result of the assessment.

### By Annex A theme

| Theme | Controls | Avg. score | At Level 3+ | Below Level 3 |
|---|---|---|---|---|
| A.5 Organizational | 37 | 1.1 | 4 | 33 |
| A.6 People | 8 | 1.4 | 1 | 7 |
| A.7 Physical | 14 | 2.1 | 6 | 8 |
| A.8 Technological | 34 | 1.9 | 11 | 23 |
| **Total** | **93** | **1.6** | **22** | **71** |

### Findings by severity

| Severity | Count |
|---|---|
| Critical | 6 |
| High | 17 |
| Medium | 24 |
| Low | 9 |
| **Total** | **56** |

### Interpretation

The pattern is characteristic of a technically competent organisation that has never been asked to evidence what it does. Physical and technological controls score highest because engineers have implemented sensible configuration on their own initiative. Organizational controls and the management system clauses score near zero because nobody has ever been accountable for producing documented information.

This is good news commercially: Lantern is not rebuilding its technology. It is formalising, documenting and governing what largely already exists, and fixing a small number of genuine technical gaps.

---

## 6. Management system findings (Clauses 4-10)

### GAP-001: No documented ISMS scope
**Clause:** 4.3 | **Score:** 0 | **Severity:** Critical

**Finding.** No documented scope for the information security management system exists. The boundaries of the ISMS have never been defined in writing, and interested parties and their requirements (4.2) have not been identified or recorded.

**Impact.** A certification body cannot audit an undefined scope. Stage 1 would terminate at this point. Without a scope, Lantern also cannot determine which controls are applicable, which prevents production of the Statement of Applicability.

**Recommendation.** Adopt the scope statement proposed in Section 2, with formal management approval recorded. Document the internal and external issues (4.1) and the interested parties and their requirements (4.2) in a short context document.

**Owner:** Technical Director | **Effort:** 2 days | **Priority:** 1

---

### GAP-002: No information security risk management process
**Clauses:** 6.1.2, 6.1.3, 8.2, 8.3 | **Score:** 0 | **Severity:** Critical

**Finding.** Lantern has no risk assessment methodology, no defined risk criteria, no risk acceptance criteria, no risk register, and no risk treatment plan. Risk is discussed reactively at the leadership meeting after incidents and is not recorded.

**Impact.** This is the central requirement of ISO/IEC 27001. The standard requires a repeatable risk assessment process producing consistent, valid and comparable results, and a risk treatment process that determines necessary controls and compares them against Annex A. Without this, the Statement of Applicability has no basis, control selection cannot be justified, and certification is not achievable under any timeline.

**Recommendation.**
1. Define and document a risk assessment methodology, including the scales for likelihood and impact, the risk acceptance threshold, and the risk owner concept.
2. Obtain board agreement on risk appetite, meaning a written statement of what level of residual risk Lantern will accept.
3. Perform an initial asset-and-threat-based risk assessment across the scope.
4. Produce a risk treatment plan mapping each unacceptable risk to treatment and to Annex A controls.
5. Establish a quarterly review cycle with named risk owners.

*This work is delivered as a separate artefact: see the accompanying Risk Register and methodology.*

**Owner:** Technical Director | **Effort:** 10 days initial, 1 day/quarter ongoing | **Priority:** 1

---

### GAP-003: No Statement of Applicability
**Clause:** 6.1.3 d) | **Score:** 0 | **Severity:** Critical

**Finding.** No Statement of Applicability exists. Lantern has never recorded which of the 93 Annex A controls apply, the justification for inclusion, the implementation status, or the justification for any exclusion.

**Impact.** The Statement of Applicability is a mandatory document and the primary reference an auditor works from in Stage 1. Its absence is an automatic bar to certification.

**Recommendation.** Produce the Statement of Applicability as a direct output of the risk treatment process (GAP-002), not as a standalone exercise. An SoA produced independently of a risk assessment is a common and immediately detectable failure, because auditors test whether inclusion decisions trace to identified risks. A worked extract is provided in Section 11.

**Owner:** Technical Director | **Effort:** 3 days (following GAP-002) | **Priority:** 1

---

### GAP-004: No internal audit programme
**Clause:** 9.2 | **Score:** 0 | **Severity:** Critical

**Finding.** Lantern has never conducted an internal audit of information security. No audit programme, audit criteria, auditor competence criteria or audit records exist.

**Impact.** Clause 9.2 requires internal audits at planned intervals. A certification body will expect to see at least one completed internal audit cycle covering the full ISMS before Stage 2, together with evidence that findings were actioned.

**Recommendation.** Establish an annual internal audit programme covering all clauses and applicable controls across the cycle. Given Lantern's size, use an external contract auditor for independence. An internal auditor cannot audit their own work, and with 54 staff and one security-responsible individual, genuine internal independence is not achievable. Budget approximately £3,500-£5,000 annually.

**Owner:** Managing Director | **Effort:** 4 days/year + external cost | **Priority:** 2

---

### GAP-005: No management review of information security
**Clause:** 9.3 | **Score:** 0 | **Severity:** Critical

**Finding.** Information security is not a standing agenda item at any governance forum. The monthly leadership meeting addresses security only following an incident. No management review meeting the requirements of Clause 9.3 has taken place.

**Impact.** Clause 9.3 prescribes specific inputs (status of actions from previous reviews, changes in issues and interested-party requirements, performance and KPI data, audit results, risk assessment status, and opportunities for improvement) and requires documented outputs. Absence is a major non-conformity.

**Recommendation.** Add a quarterly ISMS management review to the leadership meeting cycle, using a standing agenda built directly from the Clause 9.3 input list. Minute it formally. The common failure here is holding the meeting but not recording it against the prescribed inputs; the agenda template should mirror the clause.

**Owner:** Managing Director | **Effort:** 0.5 days/quarter | **Priority:** 2

---

### GAP-006: No non-conformity or corrective action process
**Clause:** 10.2 | **Score:** 0 | **Severity:** High

**Finding.** There is no process for recording non-conformities, performing root cause analysis, or tracking corrective action to closure. The known failure of leaver access revocation (GAP-021) illustrates the consequence: a control failure was identified informally and no corrective action was recorded or verified.

**Recommendation.** Implement a simple corrective action register capturing: the non-conformity, immediate containment, root cause, corrective action, owner, due date, and effectiveness verification. A spreadsheet is sufficient at Lantern's scale. Retrospectively log known issues, including the leaver access failure, so that the record demonstrates the process working.

**Owner:** Technical Director | **Effort:** 1 day setup | **Priority:** 2

---

### GAP-007: Information security policy obsolete and uncommunicated
**Clause:** 5.2 | **Score:** 1 | **Severity:** High

**Finding.** A four-page information security policy dated 2019 exists. It has not been reviewed since issue, does not reference the current organisation or services, has no documented approval, and is not communicated to staff. Six of seven interviewees were unaware of its existence.

**Impact.** Clause 5.2 requires a policy that is appropriate to the purpose of the organisation, includes a commitment to continual improvement, is communicated within the organisation, and is available to interested parties.

**Recommendation.** Rewrite as a concise top-level policy (2-3 pages) signed by the Managing Director, supported by a small set of topic-specific policies. Communicate at all-hands, require acknowledgement, and set an annual review date with a named owner.

**Owner:** Managing Director | **Effort:** 3 days | **Priority:** 2

---

### GAP-008: Information security roles and responsibilities undefined
**Clauses:** 5.1, 5.3, A.5.2 | **Score:** 1 | **Severity:** High

**Finding.** No information security roles are formally defined or assigned. The Technical Director performs the function in practice alongside a full operational workload, without a documented mandate, defined authority or allocated time.

**Impact.** Clause 5.3 requires that responsibilities and authorities for relevant roles are assigned and communicated. Beyond the compliance point, this is a genuine single point of failure: the organisation's entire security function depends on one individual's discretionary capacity.

**Recommendation.** Formally appoint an Information Security Manager role with a documented mandate, defined authority and allocated time, realistically 0.4 FTE during implementation. Either appoint internally with backfill for operational duties, or recruit. Define supporting responsibilities for asset owners, risk owners and incident coordinators in a responsibility matrix.

**Owner:** Managing Director | **Effort:** Resourcing decision | **Priority:** 1

---

### GAP-009: No security objectives or measurement
**Clauses:** 6.2, 9.1 | **Score:** 0 | **Severity:** High

**Finding.** No information security objectives have been established, and no monitoring or measurement of security performance takes place.

**Recommendation.** Define 5-7 measurable objectives aligned to identified risks, each with a metric, target, frequency and owner. Candidate objectives for Lantern: privileged account MFA coverage (target 100%), leaver access revocation within 4 hours (target 100%), critical patch deployment within 14 days (target 95%), security awareness completion (target 95%), restore test success rate (target 100% quarterly), supplier assessments current (target 100%).

**Owner:** Technical Director | **Effort:** 2 days | **Priority:** 3

---

### GAP-010: Documented information not controlled
**Clause:** 7.5 | **Score:** 1 | **Severity:** Medium

**Finding.** Documentation exists across SharePoint, the documentation platform and individual OneDrive accounts with no version control, no approval record, no review dates and no retention rules. Multiple versions of the same procedure were found in circulation.

**Recommendation.** Establish a single controlled ISMS document library in SharePoint with a document register recording owner, version, approval date and review date. Apply a consistent header block to all ISMS documents.

**Owner:** Operations Director | **Effort:** 3 days | **Priority:** 3

---

### GAP-011: Competence and awareness requirements not defined
**Clauses:** 7.2, 7.3, A.6.3 | **Score:** 1 | **Severity:** Medium

**Finding.** Security awareness consists of an annual phishing simulation with 61% completion and no follow-up for non-completers. No competence requirements are defined for security-relevant roles, and no training records are maintained beyond the simulation platform's own reporting.

**Recommendation.** Define competence requirements for security-relevant roles. Implement quarterly role-appropriate awareness training, with enhanced content for engineers holding privileged client access. Track completion to 95% with escalation to line managers. Maintain records as documented information.

**Owner:** Operations Director | **Effort:** 4 days setup | **Priority:** 3

---

## 7. Annex A Theme 1 findings, Organizational controls (A.5)

### GAP-012: No supplier information security process
**Controls:** A.5.19, A.5.20, A.5.21, A.5.22 | **Score:** 0 | **Severity:** Critical

**Finding.** Lantern performs no security assessment of its suppliers. Finance maintains a payment list; there is no supplier register recording what data each supplier processes, no security requirements in supplier agreements, no assessment before onboarding, and no ongoing monitoring.

This is materially significant. Lantern's RMM, PSA, documentation/credential vault and backup platforms are all third-party SaaS. The credential vault holds administrative passwords for 140 client environments. A compromise of that supplier is functionally a compromise of Lantern's entire client base, and Lantern has never assessed it.

**Impact.** A.5.19-A.5.22 cover supplier relationships, security within supplier agreements, ICT supply chain security, and monitoring and review of supplier services. All four are at zero. Separately, Lantern's own clients increasingly ask this exact question in their questionnaires. The organisation demands assurance from no one while being asked for it by everyone.

**Recommendation.**
1. Build a supplier register classifying suppliers by criticality and data access.
2. Define tiered due diligence: full assessment for critical suppliers, light-touch for the rest.
3. Assess all critical suppliers, beginning with the credential vault platform.
4. Insert security schedules into supplier agreements at next renewal.
5. Establish annual reassessment for critical suppliers.

*A worked example is delivered as a separate artefact: see the accompanying Third-Party Risk Assessment.*

**Owner:** Finance Director with Technical Director | **Effort:** 8 days initial | **Priority:** 1

---

### GAP-013: No incident management process
**Controls:** A.5.24, A.5.25, A.5.26, A.5.27, A.5.28 | **Score:** 1 | **Severity:** Critical

**Finding.** No documented incident response plan exists. Security events are handled through the standard service desk ticket queue with no security classification, no severity model, no defined escalation path, no response roles and no post-incident review. There is no evidence collection procedure, meaning any incident requiring forensic or regulatory substantiation would be compromised from the outset.

**Impact.** Five Annex A controls are affected. The consequence extends well beyond certification: the Cyber Security and Resilience Bill introduces 24- and 72-hour incident reporting duties for managed service providers brought into scope. Lantern currently has no mechanism capable of meeting a 24-hour reporting obligation, because it has no means of recognising that a reportable incident has occurred.

**Recommendation.**
1. Write an incident response plan defining classification, severity levels, roles, escalation and communication.
2. Add a security incident category and severity field to the PSA so incidents are identifiable and reportable.
3. Define evidence preservation steps for the service desk, specifically what not to do.
4. Run a tabletop exercise against a realistic scenario: compromise of an engineer's RMM credentials.
5. Establish mandatory post-incident review with lessons recorded.

**Owner:** Technical Director | **Effort:** 6 days | **Priority:** 1

---

### GAP-014: No information asset inventory
**Controls:** A.5.9, A.5.10 | **Score:** 1 | **Severity:** High

**Finding.** Endpoints are inventoried in Intune. No inventory exists of information assets (the data Lantern holds and processes), nor of the systems holding it. Asset ownership is not assigned.

**Recommendation.** Build an information asset register recording asset, description, owner, classification, location, retention period and the systems involved. Use the asset table in the scenario dossier as the starting point. Assign a named owner to each asset.

**Owner:** Technical Director | **Effort:** 4 days | **Priority:** 2

---

### GAP-015: No information classification scheme
**Controls:** A.5.12, A.5.13 | **Score:** 0 | **Severity:** High

**Finding.** No classification scheme exists. Staff have no basis for determining handling requirements, and client data, HR records and marketing material are handled identically.

**Recommendation.** Adopt a four-tier scheme (Public, Internal, Confidential, Secret) with a one-page handling matrix covering storage, transmission, sharing and disposal for each tier. Apply M365 sensitivity labels to enforce where practical. Keep it to four tiers; schemes with more tiers are consistently ignored by staff.

**Owner:** Technical Director | **Effort:** 3 days | **Priority:** 3

---

### GAP-016: Access control policy absent; privileged access ungoverned
**Controls:** A.5.15, A.5.16, A.5.18 | **Score:** 1 | **Severity:** Critical

**Finding.** No access control policy exists. Access is granted on request at engineer discretion with no formal approval, no role-based model, and no periodic review. Specific failures identified:

- Shared engineer credentials are in use for six client tenancies, defeating individual accountability entirely.
- Three engineers hold permanent full access to the credential vault with no break-glass model and no justification recorded.
- Forty-one clients remain on legacy full delegated admin rather than granular delegated admin, granting standing privilege substantially exceeding operational need.
- No access review has ever been performed.

**Impact.** Privileged access is the defining risk of a managed service provider. Lantern's current position of standing, shared and unreviewed administrative access into 140 client environments is the most consequential organisational weakness identified in this assessment.

**Recommendation.**
1. Write an access control policy defining least privilege, approval, and review.
2. Eliminate shared credentials; issue individual accounts for all six affected tenancies.
3. Complete the granular delegated admin migration for the remaining 41 clients.
4. Implement just-in-time elevation for credential vault access with break-glass accounts monitored and alerted.
5. Institute quarterly access reviews with documented sign-off by system owners.

**Owner:** Technical Director | **Effort:** 15 days | **Priority:** 1

---

### GAP-017: No threat intelligence process
**Control:** A.5.7 | **Score:** 1 | **Severity:** Medium

**Finding.** Threat information reaches the organisation informally through engineers' personal reading. No structured process exists for collecting, analysing or acting on threat intelligence relevant to Lantern or its clients' sectors.

**Recommendation.** Subscribe to NCSC Early Warning (free for UK organisations) and the relevant vendor advisory feeds for the RMM and backup platforms. Assign weekly review to the Infrastructure Lead with a standing item at the technical review meeting. Record actions taken.

**Owner:** Infrastructure Lead | **Effort:** 1 day setup | **Priority:** 4

---

### GAP-018: Business continuity planning inadequate
**Controls:** A.5.29, A.5.30 | **Score:** 1 | **Severity:** High

**Finding.** The business continuity plan is a single page prepared for a 2018 insurance renewal. No business impact analysis has been performed, no recovery time or recovery point objectives are defined, and no continuity or recovery testing has taken place. Lantern's own backups are not restore-tested.

**Recommendation.** Perform a business impact analysis across the four service lines. Define RTO and RPO per service. Rewrite the continuity plan and ICT readiness procedures against those objectives. Test annually; begin immediately with a restore test of Lantern's own backups, which is both the fastest to execute and currently an untested assumption.

**Owner:** Operations Director | **Effort:** 8 days | **Priority:** 2

---

### GAP-019: Legal and contractual requirements not identified
**Controls:** A.5.31, A.5.32, A.5.33, A.5.34 | **Score:** 1 | **Severity:** High

**Finding.** No register of applicable legal, statutory, regulatory and contractual requirements exists. Twenty-two client contracts predate 2019 and lack UK GDPR Article 28 processor terms. No data protection officer or equivalent accountable role has been designated, and records of processing activities under Article 30 are not maintained.

**Recommendation.** Build a legal and regulatory register covering UK GDPR, the Data Protection Act 2018, PECR, the NIS Regulations 2018 and the anticipated Cyber Security and Resilience Bill. Remediate the 22 legacy contracts as a priority, since these represent live regulatory exposure independent of certification. Produce Article 30 records. Designate an accountable data protection role.

**Owner:** Finance Director with external legal support | **Effort:** 6 days + legal cost | **Priority:** 2

---

### GAP-020: Cloud services security not addressed
**Control:** A.5.23 | **Score:** 1 | **Severity:** Medium

**Finding.** No process governs the acquisition, use or exit of cloud services. Business units have procured SaaS without security review. No cloud exit strategy exists for any critical platform, including the credential vault, where exit would be operationally severe.

**Recommendation.** Define a cloud service acquisition process including security review, data location verification and exit planning. Document exit strategies for the four critical platforms.

**Owner:** Technical Director | **Effort:** 4 days | **Priority:** 3

---

## 8. Annex A Theme 2 findings, People controls (A.6)

### GAP-021: Termination process fails to revoke access
**Controls:** A.6.5, A.5.18 | **Score:** 1 | **Severity:** Critical

**Finding.** The offboarding process does not reliably remove access. Two former engineers' RMM accounts were found active three months after their departure. Both accounts retained administrative capability across client estates. No corrective action was recorded following this discovery, and no verification step has been added to prevent recurrence.

**Impact.** This is the most serious finding in the assessment because it is a *demonstrated* failure rather than a theoretical gap, and it remains uncorrected. An auditor presented with this evidence will raise a major non-conformity. In risk terms, former employees retained administrative access to 140 client environments.

**Recommendation.**
1. Document a leaver checklist covering every system, with the RMM, credential vault, backup console, Partner Center and PSA explicitly enumerated.
2. Assign accountability to HR for initiating and to the Technical Director for verifying completion.
3. Set a maximum revocation window of four hours from employment end.
4. Perform an immediate audit of all accounts across all four critical platforms against the current HR roster, and record the result.
5. Log this as a non-conformity under the new corrective action process with root cause analysis and effectiveness verification.

**Owner:** Operations Director with HR | **Effort:** 3 days + immediate audit | **Priority:** 1

---

### GAP-022: Screening not performed consistently
**Control:** A.6.1 | **Score:** 1 | **Severity:** High

**Finding.** Pre-employment screening is limited to reference checks performed inconsistently. No identity verification, right to work documentation retention, or criminal record checking is performed, despite engineers holding administrative access to healthcare clients processing special category data.

**Recommendation.** Define a screening standard proportionate to role. For roles with privileged client access, include identity verification, right to work, employment history verification and a basic DBS check. Apply to new hires; perform a risk-based retrospective review for existing privileged staff.

**Owner:** Operations Director with HR | **Effort:** 3 days | **Priority:** 2

---

### GAP-023: Employment terms lack security obligations
**Controls:** A.6.2, A.6.4, A.6.6 | **Score:** 2 | **Severity:** Medium

**Finding.** Employment contracts contain a general confidentiality clause but no specific information security responsibilities and no acknowledgement of security policy. No disciplinary process addresses security policy violation. Confidentiality agreements with contractors are inconsistent.

**Recommendation.** Add an information security schedule to employment contracts setting out responsibilities and continuing obligations after termination. Define security violations within the disciplinary policy. Standardise contractor NDAs.

**Owner:** Operations Director | **Effort:** 2 days | **Priority:** 3

---

### GAP-024: Remote working not governed
**Control:** A.6.7 | **Score:** 2 | **Severity:** Medium

**Finding.** Remote working is widespread but ungoverned. No remote working policy exists. Technical controls (Intune compliance, conditional access, disk encryption) are largely in place and effective, but there is no documented requirement, no guidance on home network security or physical security of devices, and no restriction on working from public networks.

**Recommendation.** Write a remote working policy documenting the controls already enforced and adding guidance on physical security, home networks and public Wi-Fi. This is primarily a documentation exercise; the technical position is sound.

**Owner:** Technical Director | **Effort:** 2 days | **Priority:** 4

---

### GAP-025: No security event reporting mechanism for staff
**Control:** A.6.8 | **Score:** 1 | **Severity:** Medium

**Finding.** Staff have no defined route to report security events or suspected weaknesses. Reports reach the Technical Director informally. There is no assurance of non-punitive treatment, which interviews suggested is a live concern among junior service desk staff.

**Recommendation.** Establish a single reporting route: a dedicated mailbox and a Teams channel. State explicitly and in writing that good-faith reporting carries no adverse consequence. Communicate at all-hands and in awareness training. Track reports as a security metric.

**Owner:** Technical Director | **Effort:** 1 day | **Priority:** 3

---

## 9. Annex A Theme 3 findings, Physical controls (A.7)

The physical control theme is Lantern's strongest area, largely because the Birmingham building is a managed serviced office with its own access control and the organisation holds minimal on-premises infrastructure. Eight controls nonetheless fall below Level 3.

### GAP-026: Legacy on-premises host inadequately secured
**Controls:** A.7.1, A.7.2, A.7.3, A.7.4 | **Score:** 2 | **Severity:** High

**Finding.** The legacy Hyper-V host in Birmingham is located in an unlocked communications cupboard accessible to all building tenants' cleaning contractors. No access logging, no environmental monitoring, no CCTV coverage. The host remains in service running two legacy client workloads.

**Recommendation.** Preferred option: migrate the two remaining workloads to Azure and decommission the host, removing the control requirement entirely. This is likely cheaper than remediating the physical environment and reduces scope. If migration is not viable within 6 months, fit a locking rack cabinet with keyed access and a signed access log as an interim measure.

**Owner:** Infrastructure Lead | **Effort:** 10 days (migration) | **Priority:** 2

---

### GAP-027: Clear desk and clear screen not enforced
**Control:** A.7.7 | **Score:** 1 | **Severity:** Medium

**Finding.** No clear desk or clear screen policy. Walkthrough observed client documentation left on desks overnight and three unlocked unattended workstations. Screen lock timeout is configured at 15 minutes via Intune, which is long for a shared office environment.

**Recommendation.** Issue a clear desk and clear screen policy. Reduce the Intune screen lock timeout to 5 minutes. Provide lockable pedestals. Include in awareness training and verify by periodic walkthrough.

**Owner:** Operations Director | **Effort:** 2 days | **Priority:** 3

---

### GAP-028: Secure disposal of media and equipment not evidenced
**Controls:** A.7.10, A.7.14 | **Score:** 1 | **Severity:** Medium

**Finding.** Decommissioned endpoints are wiped by engineers using inconsistent methods with no certificates of destruction retained. Several decommissioned devices were observed in storage awaiting disposal with no record of their status or data state.

**Recommendation.** Define a media and equipment disposal procedure. Use a certified ITAD provider for disposal and retain destruction certificates as documented information. Maintain a disposal log linking asset tag to disposal evidence.

**Owner:** Infrastructure Lead | **Effort:** 2 days | **Priority:** 3

---

### GAP-029: Manchester site controls not assessed
**Controls:** A.7.1, A.7.2 | **Score:** 1 | **Severity:** Medium

**Finding.** The Manchester co-working space has never been assessed. Access control, visitor management and physical security arrangements are those of the co-working provider, who has not been assessed as a supplier. Eight staff work from this location with access to client environments.

**Recommendation.** Assess the Manchester location against the same physical control requirements. Include the co-working provider in the supplier register (GAP-012). Document the shared responsibility position.

**Owner:** Operations Director | **Effort:** 2 days | **Priority:** 3

---

## 10. Annex A Theme 4 findings, Technological controls (A.8)

### GAP-030: MFA absent on the two highest-privilege platforms
**Controls:** A.8.5, A.5.17 | **Score:** 1 | **Severity:** Critical

**Finding.** Multi-factor authentication is enforced for all staff on Microsoft 365 via conditional access. It is **not** enforced on the RMM platform or the backup console. Both support MFA natively and it has not been enabled.

**Impact.** The RMM platform provides remote access and script execution across approximately 3,200 client endpoints. The backup console controls client backup data including healthcare clients' special category data. Single-factor authentication on these platforms means a single credential compromise (phishing, reuse or infostealer) yields administrative control of Lantern's entire client base. Attacks against MSP remote management tooling are a well-established and actively exploited pattern.

This is the highest-consequence technical finding in the assessment and is remediable within days at no licence cost.

**Recommendation.**
1. Enable and enforce MFA on the RMM platform immediately. Treat as an emergency change.
2. Enable and enforce MFA on the backup console immediately.
3. Prefer phishing-resistant methods (FIDO2 or certificate-based) for all privileged platform access rather than SMS or push approval.
4. Audit every remaining externally reachable administrative interface for MFA coverage and document the result.

**Owner:** Technical Director | **Effort:** 3 days | **Priority:** 1 (immediate)

---

### GAP-031: No change management process
**Control:** A.8.32 | **Score:** 0 | **Severity:** Critical

**Finding.** No change control exists. Engineers write and deploy scripts to client estates through the RMM at their own discretion, without peer review, testing, approval, scheduling or rollback planning. There is no change record.

**Impact.** A single erroneous script executes simultaneously across thousands of client endpoints. The absence of change control on a platform with this blast radius is, in the assessor's view, the most significant *operational* risk in the business, distinct from but comparable to the MFA finding. It is also a control that clients' own auditors will ask about directly.

**Recommendation.**
1. Define a change management process with change categories: standard, normal and emergency.
2. Require peer review and documented approval for any script executing against more than one client estate.
3. Mandate testing against an internal pilot group before broad deployment.
4. Require rollback plans for normal changes.
5. Record all changes in the PSA with linkage to the originating ticket.

**Owner:** Infrastructure Lead | **Effort:** 6 days | **Priority:** 1

---

### GAP-032: Logging insufficient and no monitoring
**Controls:** A.8.15, A.8.16 | **Score:** 1 | **Severity:** High

**Finding.** Entra ID and M365 audit logs are retained for 90 days. RMM, backup console and credential vault logs are retained at platform defaults and are not centrally collected. There is no SIEM, no log correlation, and no alerting on security-relevant events. Nobody reviews logs unless investigating a specific incident.

**Impact.** Lantern cannot detect misuse of its own privileged access, which is the threat that matters most. Credential vault access is not alerted. The leaver access failure (GAP-021) persisted for three months precisely because no monitoring existed to surface it.

**Recommendation.**
1. Extend log retention to 12 months minimum across all four critical platforms.
2. Deploy centralised log collection. At Lantern's scale Microsoft Sentinel with a tightly scoped data connector set is proportionate; budget £800-£1,400/month.
3. Define a minimum alert set: credential vault access, privileged role assignment, MFA method changes, impossible travel on admin accounts, mass script execution, backup deletion or policy change.
4. Assign daily alert triage to the Infrastructure team with documented handling.

**Owner:** Infrastructure Lead | **Effort:** 12 days + ongoing cost | **Priority:** 2

---

### GAP-033: Vulnerability management informal
**Control:** A.8.8 | **Score:** 2 | **Severity:** High

**Finding.** Patching of client estates is automated through the RMM and performs reasonably. Lantern's own internal estate is less consistent, and the seven unmanaged lab devices are not patched at all. There is no vulnerability scanning, no defined remediation SLA by severity, and no exception process with risk acceptance.

**Recommendation.** Define remediation SLAs by severity, for example critical within 7 days, high within 14, medium within 30. Implement vulnerability scanning across the internal estate. Bring the lab devices under management or segregate them onto an isolated network. Establish a documented exception process with time-limited, risk-owner-approved acceptances.

**Owner:** Infrastructure Lead | **Effort:** 8 days | **Priority:** 2

---

### GAP-034: Network segregation absent
**Controls:** A.8.20, A.8.21, A.8.22 | **Score:** 1 | **Severity:** High

**Finding.** The Birmingham office operates a single flat network with one shared Wi-Fi pre-shared key used by staff, visitors and the seven unmanaged lab devices. There is no segregation between corporate endpoints, lab equipment and guest access. The PSK has not been rotated since 2023 and is known to former employees.

**Recommendation.** Implement VLAN segregation: corporate, lab, guest. Replace the shared PSK with WPA2/3-Enterprise authenticating against Entra ID for the corporate network. Provide an isolated guest network with a rotating credential. Rotate the existing PSK immediately as an interim measure.

**Owner:** Infrastructure Lead | **Effort:** 6 days | **Priority:** 2

---

### GAP-035: Backup arrangements untested
**Control:** A.8.13 | **Score:** 2 | **Severity:** High

**Finding.** Client backups are performed through the managed backup platform and monitored for job success. Restore testing is performed only when a client requests a restore. Lantern's *own* corporate data backup has never been restore-tested. No backup policy defines retention, immutability requirements or test frequency.

**Impact.** Backup job success is not evidence of restorability. For an organisation whose commercial proposition includes managed backup, an untested restore capability is both a certification gap and a reputational exposure.

**Recommendation.** Write a backup policy defining scope, retention, immutability and testing frequency. Implement quarterly sampled restore testing for client backups and for Lantern's own data, with documented results. Verify that immutability or air-gap protection is enabled against ransomware-driven backup deletion.

**Owner:** Infrastructure Lead | **Effort:** 5 days + quarterly | **Priority:** 2

---

### GAP-036: Cryptography not governed
**Controls:** A.8.24, A.5.17 | **Score:** 2 | **Severity:** Medium

**Finding.** BitLocker is enforced on Windows endpoints via Intune and TLS is in use for all external services, so the technical position is sound. However, no cryptographic policy defines approved algorithms or key lengths, and there is no key management procedure. Credential vault recovery keys are held in a single location with no documented custody arrangement.

**Recommendation.** Write a brief cryptographic policy specifying approved algorithms, minimum key lengths and prohibited legacy protocols. Document key management for the credential vault recovery keys including split custody and secure storage.

**Owner:** Technical Director | **Effort:** 3 days | **Priority:** 3

---

### GAP-037: No data leakage prevention
**Control:** A.8.12 | **Score:** 1 | **Severity:** Medium

**Finding.** No DLP controls are configured. M365 E3 licensing provides DLP capability which has not been enabled. Staff can freely forward client data to personal email or copy to removable media.

**Recommendation.** Enable M365 DLP policies targeting the Confidential and Secret classifications once the classification scheme (GAP-015) exists. Begin in audit mode to establish a baseline before enforcing, to avoid disrupting legitimate workflows. Restrict removable media via Intune.

**Owner:** Technical Director | **Effort:** 5 days | **Priority:** 3 (dependent on GAP-015)

---

### GAP-038: Secure development practices undefined
**Controls:** A.8.25-A.8.31 | **Score:** 1 | **Severity:** Medium

**Finding.** Lantern does not develop software products, but engineers write automation scripts executed across client estates. These are not version-controlled, peer-reviewed or tested, and no separation exists between development and production execution.

**Recommendation.** Treat operational scripting as development. Place scripts in a version-controlled repository with mandatory peer review. Establish a pilot group for testing before production execution. This integrates directly with the change management recommendation (GAP-031) and should be delivered as one piece of work.

**Owner:** Infrastructure Lead | **Effort:** 5 days | **Priority:** 3

---

### GAP-039: Capacity management informal
**Control:** A.8.6 | **Score:** 2 | **Severity:** Low

**Finding.** Azure capacity is monitored through platform alerting and managed reactively. No documented capacity planning process exists, though no capacity-related incident has occurred.

**Recommendation.** Document the existing monitoring arrangements and add a quarterly capacity review to the technical review agenda. Primarily a documentation exercise.

**Owner:** Infrastructure Lead | **Effort:** 1 day | **Priority:** 4

---

### GAP-040: Web filtering not configured
**Control:** A.8.23 | **Score:** 1 | **Severity:** Low

**Finding.** No web filtering is in place. Defender for Endpoint P1 includes web content filtering capability which has not been enabled.

**Recommendation.** Enable Defender for Endpoint web content filtering with blocking of known malicious and high-risk categories. No additional licence cost.

**Owner:** Infrastructure Lead | **Effort:** 1 day | **Priority:** 4

---

## 11. Statement of Applicability: extract and exclusion rationale

The full Statement of Applicability must be produced as an output of the risk treatment process (GAP-002, GAP-003). The following extract demonstrates the required structure and the standard of justification an auditor will expect.

| Control | Title | Applicable | Justification | Implementation status | Related risk |
|---|---|---|---|---|---|
| A.5.7 | Threat intelligence | Yes | MSP targeting is an active threat pattern; awareness of RMM-platform-specific threats is operationally necessary | Not implemented (GAP-017) | R-014 |
| A.5.15 | Access control | Yes | Privileged access to 140 client environments is the organisation's principal risk | Partially implemented (GAP-016) | R-001, R-003 |
| A.5.17 | Authentication information | Yes | Credential vault holds client administrative credentials | Partially implemented (GAP-030) | R-001 |
| A.5.19 | Information security in supplier relationships | Yes | Four critical SaaS suppliers hold or access client data | Not implemented (GAP-012) | R-008 |
| A.5.24 | Incident management planning | Yes | Required by standard; anticipated statutory reporting duty under the CSR Bill | Not implemented (GAP-013) | R-011 |
| A.6.5 | Responsibilities after termination | Yes | Demonstrated control failure with privileged access retained post-employment | Partially implemented (GAP-021) | R-002 |
| A.7.4 | Physical security monitoring | Yes | Legacy on-premises host remains in service in a shared building | Not implemented (GAP-026) | R-017 |
| A.8.5 | Secure authentication | Yes | MFA gap on RMM and backup platforms | Partially implemented (GAP-030) | R-001 |
| A.8.13 | Information backup | Yes | Backup is a contracted service line and a ransomware recovery dependency | Partially implemented (GAP-035) | R-009 |
| A.8.32 | Change management | Yes | Script execution across ~3,200 client endpoints without control | Not implemented (GAP-031) | R-004 |
| A.7.9 | Security of assets off-premises | Yes | Remote working is standard; endpoints leave both offices routinely | Implemented: Intune compliance and BitLocker enforced | R-016 |
| A.8.1 | User endpoint devices | Yes | 65 managed endpoints across two sites and remote locations | Implemented: Intune managed, compliance policies enforced | R-016 |

### Note on exclusions

Lantern should expect to declare **very few exclusions**. The 2022 revision of the standard consolidated 114 controls into 93, and the resulting set is broadly applicable to most organisations. Plausible exclusion candidates for Lantern are limited to controls concerning development environments and application security testing, *and even these are arguable* given the operational scripting activity identified in GAP-038, which is why this assessment treats that scripting as development activity rather than excluding the controls.

The common failure here is excluding controls on the basis that they are difficult or not currently implemented. Exclusion must rest on genuine inapplicability to the scope, and an auditor will test the justification directly. "We do not do this" is not a justification; "this activity does not occur within the defined scope" is.

---

## 12. Remediation roadmap

The programme is sequenced on three principles: fix live material risk immediately regardless of certification value; build the management system before the controls, because control selection depends on the risk assessment; and schedule dependencies correctly so work is not repeated.

### Phase 0: Immediate (weeks 1-2)

Executed independently of the certification programme because the risk is live now.

| Action | Finding | Owner |
|---|---|---|
| Enforce MFA on the RMM platform | GAP-030 | Technical Director |
| Enforce MFA on the backup console | GAP-030 | Technical Director |
| Full account audit across all four critical platforms against HR roster | GAP-021 | Technical Director |
| Rotate the office Wi-Fi PSK | GAP-034 | Infrastructure Lead |
| Eliminate shared credentials on the six affected client tenancies | GAP-016 | Infrastructure Lead |

*Effort: approximately 8 days. Cost: nil. This phase removes the two highest-consequence exposures identified in the assessment.*

### Phase 1: Foundation (months 1-3)

| Workstream | Findings | Effort |
|---|---|---|
| Appoint Information Security Manager with defined mandate and time | GAP-008 | Resourcing decision |
| Define ISMS scope and organisational context | GAP-001 | 2 days |
| Develop risk assessment methodology and risk appetite statement | GAP-002 | 4 days |
| Perform initial risk assessment and produce risk register | GAP-002 | 6 days |
| Produce risk treatment plan and Statement of Applicability | GAP-002, GAP-003 | 3 days |
| Rewrite information security policy and supporting topic policies | GAP-007 | 3 days |
| Build information asset register with assigned owners | GAP-014 | 4 days |
| Establish document control | GAP-010 | 3 days |

**Phase 1 is the critical path.** No subsequent work can be properly justified until the risk assessment exists.

### Phase 2: Core controls (months 3-7)

| Workstream | Findings | Effort |
|---|---|---|
| Access control policy, privileged access remediation, granular delegated admin migration, quarterly access reviews | GAP-016 | 15 days |
| Leaver process redesign with verification and four-hour SLA | GAP-021 | 3 days |
| Incident response plan, PSA classification, tabletop exercise | GAP-013 | 6 days |
| Change management process and script version control | GAP-031, GAP-038 | 11 days |
| Supplier register, tiered due diligence, critical supplier assessments | GAP-012 | 8 days |
| Legal and regulatory register; remediate 22 legacy contracts | GAP-019 | 6 days + legal |
| Network segregation and WPA2/3-Enterprise | GAP-034 | 6 days |
| Backup policy and restore testing | GAP-035 | 5 days |
| Business impact analysis and continuity plan rewrite | GAP-018 | 8 days |
| Screening standard | GAP-022 | 3 days |

### Phase 3: Supporting controls and evidence generation (months 6-10)

| Workstream | Findings | Effort |
|---|---|---|
| Centralised logging and alerting | GAP-032 | 12 days |
| Vulnerability management SLAs and scanning | GAP-033 | 8 days |
| Classification scheme and DLP | GAP-015, GAP-037 | 8 days |
| Awareness training programme | GAP-011 | 4 days |
| Security objectives and metrics | GAP-009 | 2 days |
| Legacy host migration and decommission | GAP-026 | 10 days |
| Clear desk, disposal, Manchester assessment, remaining physical | GAP-027, 028, 029 | 6 days |
| Cryptographic policy, cloud acquisition, threat intel, web filtering, capacity | GAP-036, 020, 017, 040, 039 | 10 days |

### Phase 4: Operate and audit (months 9-14)

| Activity | Finding |
|---|---|
| Operate the ISMS and accumulate records, with a minimum of 3 months of evidence before Stage 2 | N/A |
| Establish corrective action process and log retrospective non-conformities | GAP-006 |
| First internal audit cycle, full scope, external contract auditor | GAP-004 |
| First quarterly ISMS management review against Clause 9.3 inputs | GAP-005 |
| Close internal audit findings with verified corrective action | GAP-006 |

### Phase 5: Certification (months 14-18)

| Activity |
|---|
| Select UKAS-accredited certification body and schedule |
| Stage 1 audit: documentation and readiness review |
| Remediate Stage 1 findings |
| Stage 2 audit: implementation and effectiveness |
| Certification decision |

**A note on evidence timing.** A certification body will expect to see the ISMS operating, not merely documented. Risk reviews, access reviews, management reviews and internal audit must have actually occurred and produced records. This is why Phase 4 cannot be compressed, and why the Q3 2027 target is achievable only if Phase 1 begins within the next month.

### Indicative cost: year one

| Item | Estimate |
|---|---|
| Information Security Manager (0.4 FTE internal allocation or part-time hire) | £24,000-£32,000 |
| External internal-audit provider | £3,500-£5,000 |
| Certification body (Stage 1 + Stage 2, organisation of this size) | £9,000-£13,000 |
| Centralised logging (Sentinel, 12 months) | £10,000-£17,000 |
| Legal support for contract remediation and DPA refresh | £4,000-£7,000 |
| Screening (DBS and verification, ongoing) | £1,500 |
| Awareness training platform | £2,500-£4,000 |
| Contingency (15%) | £8,000-£12,000 |
| **Total** | **£78,000-£96,000** |

Notable for its absence: significant technology spend. The majority of Lantern's technical gaps are closed by configuring capability already licensed under existing Microsoft 365 and Defender agreements. The cost of this programme is predominantly **people and time**, not tooling. That should be stated plainly to the board, because the instinct at this point is frequently to buy a platform instead of assigning an owner.

---

## 13. Assessor's opinion on certification readiness

**Lantern cannot achieve ISO/IEC 27001:2022 certification on its current trajectory, and the Q3 2027 target is at risk, but it is achievable if Phase 1 begins within one month.**

Three observations for the board.

**First, the deficit is organisational, not technical.** Lantern's engineers have built a reasonable technical environment without being asked to. Physical and technological controls average 2.1 and 1.9 respectively, against an organizational control average of 1.1 and a management system average of 0.4. The organisation does not need to rebuild its technology. It needs someone whose job is information security, and a system for recording what it already does.

**Second, the single biggest risk to the programme is resourcing.** The Technical Director cannot deliver this alongside a full operational workload, and attempting it is the most common way that certification programmes of this size fail. The appointment in GAP-008 is not an administrative detail; it is the dependency on which everything else rests.

**Third, two findings should be actioned this week irrespective of certification.** The MFA gap on the RMM and backup platforms (GAP-030) and the absence of change control over mass script execution (GAP-031) both represent live exposure with a plausible path to a client-impacting incident. Neither is expensive to address. If the board deferred the entire certification programme and did nothing else from this report, these two should still be fixed.

### Realistic timeline

| Milestone | Target |
|---|---|
| Phase 0 complete | November 2026 |
| Information Security Manager appointed | December 2026 |
| Risk assessment and SoA complete | February 2027 |
| Core controls implemented | June 2027 |
| ISMS operating with evidence | September 2027 |
| Internal audit complete | November 2027 |
| Stage 1 | January 2028 |
| Stage 2 and certification | March 2028 |

This is approximately **two quarters later than the board's stated Q3 2027 target.** The target could be met only by appointing a dedicated resource immediately and running Phases 1 and 2 in parallel with external implementation support. That is a legitimate option and would cost an additional £25k-£40k; it is a commercial decision about how much the three lost tenders are worth.

---

## 14. Appendix A: Evidence requested and received

| Evidence item | Requested | Received | Note |
|---|---|---|---|
| Information security policy | Yes | Yes | 2019, unreviewed |
| ISMS scope document | Yes | No | Does not exist |
| Risk assessment methodology | Yes | No | Does not exist |
| Risk register | Yes | No | Does not exist |
| Statement of Applicability | Yes | No | Does not exist |
| Asset inventory | Yes | Partial | Intune endpoint export only |
| Supplier register | Yes | Partial | Finance payment list |
| Access control policy | Yes | No | Does not exist |
| Access review records | Yes | No | Never performed |
| Incident response plan | Yes | No | Does not exist |
| Incident records | Yes | Partial | Unclassified PSA tickets |
| Internal audit reports | Yes | No | Never performed |
| Management review minutes | Yes | No | Never performed |
| Business continuity plan | Yes | Yes | 2018, one page |
| Training records | Yes | Partial | Phishing platform only, 61% |
| Entra conditional access export | Yes | Yes | Reviewed |
| Intune compliance policy export | Yes | Yes | Reviewed |
| RMM user list | Yes | Yes | Reviewed, see GAP-021 |
| Partner Center delegated admin report | Yes | Yes | Reviewed, see GAP-016 |
| Employment contract template | Yes | Yes | Reviewed |
| Sample client contracts | Yes | Yes | 10 sampled, 2 pre-2019 |

**Evidence availability: 11 of 22 items either absent or partial.** This ratio is itself a finding and is characteristic of an organisation at Level 0-1 maturity.

---

## 15. Appendix B: Limitations

1. **Point in time.** This assessment reflects the position during October 2026. Control state may change.
2. **Sampling.** Contract review was based on a sample of 10 of 140 client contracts. Findings regarding legacy contracts are extrapolated and should be confirmed by full review.
3. **Reliance on representations.** Where technical corroboration was not practicable, findings rely on representations made during interview. Items so reliant: backup restore testing history, screening practice, and incident history.
4. **No technical testing.** This is a controls assessment, not a penetration test or vulnerability assessment. Absence of findings regarding technical vulnerabilities should not be read as assurance of their absence.
5. **Client environments excluded.** Controls within client-owned environments were not assessed.
6. **Not a certification audit.** This assessment is not performed by a UKAS-accredited certification body and confers no certification or guarantee of certification outcome.

---

*End of report.*
