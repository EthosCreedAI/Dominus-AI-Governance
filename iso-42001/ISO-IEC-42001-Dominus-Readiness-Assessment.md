# ISO/IEC 42001 — Dominus AI Management System Readiness Assessment

**Systems:** Dominus Cloud; Dominus Gemma iOS  
**Assessment status:** Completed baseline readiness/alignment assessment  
**Assessment date:** September 15, 2026

> This is an ISO/IEC 42001 alignment/readiness assessment for portfolio and governance purposes. It is not an ISO certification or claim of certified conformity.

# 1. SCOPE AND CONTEXT

### Is the AI system's purpose and scope documented?
**YES.** Dominus Cloud and Dominus Gemma iOS are documented through their READMEs and governance assessments. Their current scope is conversational AI/personal assistance, including relevant voice, memory, knowledge, model, storage, and infrastructure capabilities.

### Are the parts of the system covered by governance identifiable?
**YES.** The current governance work covers the Dominus conversational AI systems, their AI models/providers, memory, data/storage, voice functionality, infrastructure, security controls, and human oversight.

# 2. LEADERSHIP, OWNERSHIP, AND RESPONSIBILITY

### Is responsibility for the AI system documented?
**YES.** I am the current sole owner/operator and responsible party.

### Is an AI governance/policy statement established?
**NOT YET.** A standalone AI governance policy has not yet been created.

# 3. AI RISK MANAGEMENT

### Is there a repeatable process to identify, assess, prioritize, and treat AI risks?
**NOT YET.** Risk identification has begun through the NIST AI RMF, EU AI Act, and ISO/IEC 42001 assessments, but a formal repeatable risk-management process and scored risk register have not yet been established.

### Are risk ownership and responsibilities identifiable?
**YES.** I currently own the system risks.

# 4. DATA MANAGEMENT

### Are formal rules established for data minimization, retention, classification, and handling?
**NOT YET / INFORMAL.** Technical data handling exists, but formal policies for minimization, retention, sensitive-data classification, and handling have not yet been established.

### Is data retention formally defined?
**NOT YET.** Current retention is effectively indefinite unless data is deleted.

### Can users delete conversations?
**YES at the user-facing level.** Complete deletion across memory/index/backup layers has not yet been verified.

### Is sensitive data automatically classified and treated differently?
**NOT YET.**

# 5. MONITORING AND CONTINUAL IMPROVEMENT

### Is the AI system periodically reviewed and improved?
**YES.** I now review the system and its governance as part of ongoing development and these framework assessments.

### Is there a formal recurring review cadence?
**NOT YET.** The practice has begun, but a scheduled governance review interval has not been established.

# 6. AI IMPACT ASSESSMENT

### Have intended and unintended impacts on users or other affected parties been formally assessed?
**NOT YET.** Risks and limitations have been discussed through the other governance assessments, but a dedicated formal AI impact assessment has not yet been completed.

# 7. OBJECTIVES AND MEASUREMENT

### Have AI governance objectives been established?
**NOT YET.**

### Are measurable targets established for reliability, privacy, security, incidents, or other governance outcomes?
**NOT YET.** No formal uptime target or other governance KPI has been established while the system remains in active development.

# 8. COMPETENCE AND AWARENESS

### Is the knowledge/competence needed to responsibly operate and govern the AI system documented?
**PARTIAL.** I am actively building technical and governance competence and have documented system architecture and governance assessments, but I have not yet created a formal competence/skills requirement record for the AI management system.

# 9. OPERATIONAL CONTROLS

### Are major AI/provider changes reviewed before adoption?
**PARTIAL.** I personally research and test changes before adopting them, but there is no formal change-management procedure or decision log.

### Are problematic models/features capable of being disabled?
**YES.** Models/providers can be changed or disabled and optional functionality can be turned off/unconfigured.

### Is human oversight retained?
**YES.** Dominus is intended as an informational/guidance tool rather than the primary decision-maker. Users remain responsible for final decisions.

### Is cross-user isolation addressed?
**PARTIAL / INFORMAL TEST PASSED.** Limited testing has shown separate users do not see one another's data, but larger-scale/formal isolation testing has not yet been completed.

# 10. DOCUMENTED INFORMATION

### Is system purpose documented?
**YES.**

### Is architecture documented?
**YES.**

### Are models and providers documented?
**YES / PARTIAL.** Major model paths/providers are documented; a formal versioned model inventory can still be added.

### Are data flows and storage documented?
**YES at the architecture level;** a dedicated formal data-flow register can be strengthened.

### Are external services documented?
**YES.**

### Are known limitations documented?
**YES / PARTIAL.** Limitations are documented through project/governance material, with additional formalization still possible.

### Is testing documented?
**PARTIAL.** Development and ad hoc testing have informed known limitations, but a formal repeatable AI test program has not yet been established.

### Are security controls documented?
**YES.** Existing documentation covers controls such as encrypted API keys, authentication/session controls, AWS Secrets Manager, and infrastructure security.

### Is responsible ownership documented?
**YES.**

# 11. SECURITY, INCIDENTS, AND TRACEABILITY

### Is there a formal AI/security incident-response process?
**NOT YET.**

### Are significant system errors logged?
**PARTIAL.** Users can receive general error indicators such as networking errors, but detailed administrative logging and traceability are not yet sufficient.

### Can incidents be investigated?
**PARTIAL.**

### Can model/provider changes be traced after the fact?
**NOT YET reliably.**

### Can compromised sessions be forcibly invalidated?
**NOT YET.**

### Are dependency vulnerabilities formally scanned?
**NOT YET.**

### Is there a regular security dependency update process?
**NOT YET.**

### Is rate limiting/abuse prevention implemented?
**NOT YET.**

### Is suspicious behavior formally monitored?
**NOT YET.**

# 12. RESILIENCE AND RECOVERY

### Has provider outage behavior been observed?
**YES.** OpenRouter outages have occurred; requests may fail to respond.

### Is an alternative model path available?
**YES.** A working Gemma model is hosted on AWS as an alternative model path.

### Is automated graceful failover established?
**NOT YET.**

### Does the system recover from ECS/container restarts?
**OBSERVED / PARTIAL.** In normal use, it appears to recover without losing persistent conversations, but no formal repeatable recovery test has been completed.

### Has database failure behavior been evaluated?
**PARTIAL.** General network/error feedback may appear, but graceful degradation and diagnosis are not yet mature.

### Has backup restoration been tested?
**NOT YET.**

# 13. MEMORY AND VOICE CONTROLS

### Is long-term memory behavior fully characterized?
**NOT YET.** TencentDB/TDAI memory works, but its exact retention/retrieval behavior has not been fully tested or characterized.

### Can users fully inspect, correct, and delete long-term memories?
**NOT YET.** Context-window information offers partial visibility, but a complete memory-management interface does not exist.

### Has deletion from the memory layer been verified?
**NOT YET.**

### Has speech-to-text been tested?
**PARTIAL / INFORMAL.** It works in normal conversation, but background noise and echoes still require tuning.

### Are raw voice recordings intentionally retained?
**NO, based on the current implementation and owner knowledge.** Voice is transcribed rather than intentionally archived as raw audio.

# 14. CURRENT READINESS DECISION

## PARTIALLY ALIGNED / MANAGEMENT SYSTEM STILL BEING FORMALIZED

Dominus already has meaningful technical documentation, system ownership, human oversight, security controls, model/provider architecture, and an active governance review effort.

The principal gaps before claiming mature ISO/IEC 42001 alignment are management-system controls rather than simply application features:

1. Create a formal AI policy.
2. Establish measurable AI governance objectives.
3. Create a repeatable AI risk-management process and risk register.
4. Create a formal AI impact assessment process.
5. Establish data-retention, classification, minimization, and handling policies.
6. Establish incident-response and investigation procedures.
7. Create formal model/provider change management and traceability.
8. Establish formal monitoring, vulnerability scanning, dependency maintenance, and abuse prevention.
9. Create repeatable testing and recovery procedures.
10. Verify memory deletion and provide stronger memory transparency/correction controls.
11. Establish a recurring management review and continual-improvement cadence.
12. Maintain versioned governance records as the systems change.

**Current conclusion:** Appropriate as a baseline ISO/IEC 42001 readiness/alignment assessment for continued private development and governance maturation. This document does not represent ISO certification.
