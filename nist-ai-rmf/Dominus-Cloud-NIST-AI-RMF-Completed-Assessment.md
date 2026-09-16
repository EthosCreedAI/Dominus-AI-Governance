# Dominus Cloud — NIST AI RMF Conversational AI Assessment

**System:** Dominus Cloud  
**Assessment status:** Completed baseline assessment  
**Framework:** NIST AI Risk Management Framework (AI RMF)  
**Scope:** Current private/test deployment  
**System owner:** King E. Creed  
**Assessment date:** September 15, 2026

> This document records the current state of Dominus Cloud against a practical NIST AI RMF-based assessment. NIST AI RMF is a voluntary risk-management framework, so this is an **AI RMF alignment/risk assessment**, not a NIST certification or legal compliance determination. “Not yet” items are documented gaps rather than claims that a control currently exists.

## Status Key
- **PASS** — Implemented, documented, tested, or supported by current evidence.
- **PARTIAL** — Some implementation/evidence exists, but the control or documentation is incomplete.
- **NOT YET** — Not currently implemented, documented, or formally tested.
- **OBSERVED** — Observed during normal/informal use but not tested through a repeatable formal procedure.

# 1. GOVERN

## Responsibility

### Has responsibility for the AI system been identified?
**PASS.** I am currently the sole owner and responsible party for Dominus Cloud. The application is not publicly available. Access is limited to me and a small number of test users whom I authorize, and I can grant or revoke access.

### Is responsibility assigned for security?
**PASS.** I currently manage the AWS environment, access, credentials, infrastructure, and security decisions.

### Is responsibility assigned for privacy?
**PASS.** As the sole owner/operator, privacy responsibility currently belongs to me.

### Is responsibility assigned for AI incidents?
**PARTIAL.** I would currently handle an AI-related incident, but I have not yet created a formal AI incident-response process or incident template.

### Is responsibility assigned for approving major AI capability changes?
**PASS.** I approve major changes myself. I research proposed updates, implement them, and test them before deciding whether to keep them.

### Are decisions involving new models documented?
**PARTIAL.** Model options and architecture are reflected in the application, code, and repository documentation, but I do not yet maintain a dedicated model-change decision log.

### Are external AI providers documented?
**PASS.** OpenRouter and ElevenLabs are documented. Users bring their own provider API keys through Settings. A self-hosted Gemma model path on AWS is also documented.

## Intended Use

### Is the intended purpose documented?
**PASS.** Dominus Cloud is a privacy-conscious conversational AI application intended to provide conversational assistance, information, guidance, memory/retrieval, voice interaction, notes/knowledge functionality, and related AI-assisted workflows.

### Are prohibited or unsupported uses documented?
**NOT YET.** I have not yet written a prohibited-use or unsupported-use policy.

### Are users warned against relying on the assistant outside its intended purpose?
**NOT YET.** No formal warning has been written yet.

### What should Dominus never decide autonomously?
**DEFINED.** Dominus should not act as the primary decision-maker for a person. It may provide information, guidance, suggestions, and practical assistance, but final decisions should remain with the user. It should not present itself as having absolute decision-making authority.

### Is there a process for deciding whether new uses materially change risk?
**NOT YET.** No formal process has been created yet.

## AI Inventory

### Are all AI models used documented?
**PARTIAL.** OpenRouter model selection and the AWS-hosted/self-hosted Gemma model path are documented. I do not yet maintain a dedicated inventory containing every specific model and version.

### Are local/self-hosted and external models distinguished?
**PASS.** The project distinguishes external OpenRouter models from self-hosted OpenAI-compatible model options and the AWS-hosted Gemma model.

### Are speech-to-text technologies documented?
**PASS.** The repository documents speech-to-text paths, including browser speech recognition and ElevenLabs Scribe. Whisper has also been used for transcription in my current voice implementation/testing.

### Are text-to-speech providers documented?
**PASS.** ElevenLabs TTS is documented.

### Are embedding and memory systems documented?
**PARTIAL.** TencentDB/TDAI memory functionality, vector search, memory recall, and conversation capture are documented, but I have not fully characterized or formally inventoried the underlying memory behavior and exact model/embedding implementation.

### Are third-party AI dependencies inventoried?
**PARTIAL.** Major dependencies are documented throughout the project, including OpenRouter, ElevenLabs, AWS services, the memory system, and Gemma/self-hosted model support. I have not yet created a dedicated governance vendor/dependency inventory.

## Policies

### Is there a privacy policy?
**NOT YET.** No dedicated privacy policy has been created.

### Is there a security policy?
**PARTIAL.** Technical security controls exist, including encrypted API-key storage, AWS Secrets Manager, authentication, secure session cookies, and encrypted database infrastructure. I have not yet created a standalone security policy.

### Is there an AI acceptable-use/content policy?
**NOT YET.**

### Is there an incident-response process?
**NOT YET.**

### Is there a model/provider change-management process?
**PARTIAL.** I research and test changes before adopting them, but I have not created a formal written procedure.

### Is there a process for reviewing high-impact new features?
**PARTIAL.** I personally research and test new capabilities, but there is not yet a formal repeatable governance review process.

### Is there a written data-retention policy?
**NOT YET.** Current conversation/memory retention is effectively indefinite unless data is deleted, but I have not created a formal retention policy.

# 2. MAP

## System Context

### What does the assistant do?
Dominus Cloud provides conversational AI, persistent conversations, memory retrieval, voice interaction, model selection, notes/knowledge functionality, and related AI-assisted workflows.

### Who uses it?
Currently I use the system and may authorize a small number of test users. It is not open to the general public.

### Where is it deployed?
Dominus Cloud can run locally and has an AWS deployment architecture using ECS Fargate, an Application Load Balancer, CloudFront, PostgreSQL on RDS, ECR, Secrets Manager, and an on-demand GPU worker for the self-hosted Gemma model.

### What decisions can it influence?
Dominus can influence user thinking through information, suggestions, explanations, and guidance. It is not intended to be the final authority or primary decision-maker.

### What should it never decide autonomously?
Final consequential decisions should remain with the user. Dominus is intended to assist rather than replace human judgment.

## Data Flow

### What information enters the system?
User prompts, conversation history, system instructions, retrieved memories/context, profile information, notes/knowledge content, voice transcriptions, and model/provider configuration can enter the system.

### What stays only on the user's device?
In the current cloud architecture, the user's device primarily provides the interface/client experience. Conversations are stored server-side in AWS rather than only on the user's device. A more detailed client-side data inventory has not yet been documented.

### What enters AWS?
Conversation and application data used by the deployed Dominus environment is handled by the AWS-hosted system. Persistent conversations are stored server-side.

### What enters PostgreSQL?
Persistent application information includes conversations and other server-side application state. The repository also documents server persistence for imported notes/files used by the knowledge workspace.

### What is sent to OpenRouter?
My current understanding is that model requests can include the system prompt, current conversation, prior/retrieved memory or context, and current user message as assembled for the model request.

### What is sent to a speech provider?
When an external voice provider is used, information required for transcription or text-to-speech is transmitted to that provider.

### What enters the memory system?
Conversation information can be captured and later recalled by TencentDB/TDAI. The exact rules determining what becomes long-term memory have not yet been fully characterized.

### Are files uploaded?
The repository includes file/note persistence functionality in the SpiderLoco knowledge workspace. File-upload behavior for the conversational chat interface itself is not treated as established simply from unrelated agent projects.

### Where do persisted knowledge files go?
The documented SpiderLoco workflow can persist imported files/notes in PostgreSQL.

### How long is information retained?
**Current state:** Indefinitely unless deleted. A formal retention policy has not yet been established.

## User Data

### Can users submit personal information?
**YES.**

### Can users submit financial information?
**YES.** The conversational interface does not currently prevent it.

### Can users submit health information?
**YES.** The conversational interface does not currently prevent it.

### Can users submit confidential business information?
**YES.**

### Can voice conversations contain sensitive information?
**YES.**

### Does the system distinguish sensitive data from ordinary conversation?
**NOT YET.** I have not implemented data-classification logic that automatically treats sensitive information differently from ordinary conversational data.

## Memory and Retrieval

### What becomes long-term memory?
**PARTIAL.** Dominus uses TencentDB/TDAI memory functionality and can remember information. I have not yet fully tested or characterized the rules it uses to determine what is retained or recalled.

### Can users inspect stored memories?
**PARTIAL.** The application has context-window visibility showing categories/token-related information about context being injected. It is not currently a full content-level long-term-memory viewer or management interface.

### Can users delete conversations?
**PASS.** Yes. Conversation deletion is available.

### Does deleting a conversation remove every related copy from the memory layer?
**NOT YET VERIFIED.** I have not tested whether deleting a conversation also removes associated information from TencentDB/TDAI or derived indexes.

### Can one user's information be retrieved for another user?
**INFORMAL TEST PASSED.** I designed the application to prevent users from seeing each other's data. Limited testing with separate accounts has not exposed another user's information. Larger-scale/formal isolation testing has not yet been performed.

### Can irrelevant memories contaminate responses?
**NOT YET FORMALLY TESTED.**

### Does retrieval expose information outside the current conversation?
**YES — INTENDED FEATURE.** Cross-conversation retrieval is intentional, making retrieval scope and account isolation important controls.

## Third-Party Services

### Is OpenRouter involved?
**YES.**

### Which underlying provider receives prompts?
It depends on the model selected through OpenRouter.

### Is ElevenLabs involved?
**YES.** Users can provide their own ElevenLabs API key for voice functionality.

### What provider policies apply to transmitted data?
**NOT YET DOCUMENTED** in this governance assessment.

### What happens if OpenRouter becomes unavailable?
**OBSERVED / PARTIAL MITIGATION.** I have experienced OpenRouter outages. When unavailable, the model request may simply fail to respond rather than degrade gracefully. I added a Gemma model hosted on AWS as an alternative model path. Formal automated failover has not been established.

# 3. MEASURE

## Hallucination and Accuracy

### Has factual accuracy been tested?
**INFORMAL ONLY.** I have tested Dominus through normal conversational use and memory-recall use, but not through a formal factual-accuracy test suite.

### Have intentionally misleading questions been tested?
**NOT YET.**

### Have out-of-knowledge questions been tested?
**NOT YET SYSTEMATICALLY.**

### Does the assistant communicate uncertainty?
**NOT FORMALLY EVALUATED.**

### Are hallucination failures documented?
**NOT YET.**

## Prompt Injection

### Has direct prompt injection been tested?
**INFORMAL TEST PASSED.** I manually attempted to persuade the model to reveal its system prompt. It refused despite repeated attempts. This was an informal test rather than a repeatable documented test suite.

### Has indirect prompt injection been tested?
**NOT YET.** I have not tested malicious instructions embedded inside retrieved notes or other content.

### Can retrieved notes override system instructions?
**NOT YET TESTED.**

### Can malicious retrieved/uploaded content manipulate the assistant?
**NOT YET TESTED.**

### Can a user make the system expose protected context?
**LIMITED MANUAL TEST PASSED.** My direct attempts to obtain the system prompt were unsuccessful. Broader protected-context extraction testing has not yet been performed.

## Memory Isolation

### Can one account retrieve another account's information?
**INFORMAL TEST PASSED.** Limited testing with separate users/accounts has not resulted in cross-user data exposure. I would want larger-scale testing before public deployment.

### Can deleted conversations still appear through memory?
**NOT YET TESTED.**

### Can a conversation retrieve unrelated private information?
**NOT YET FORMALLY TESTED.**

### Are memory boundaries tested?
**PARTIAL.** Basic cross-user isolation has been tested informally, but a formal isolation test suite does not exist.

## Voice Risk

### Has speech-to-text accuracy been evaluated?
**INFORMAL / PARTIAL.** Transcription works in normal use and has been tested through actual conversation, but it still requires tuning.

### Has background speech/noise been tested?
**INFORMAL / PARTIAL.** Yes, through real-world use. Background noise and echoes can still interfere with voice capture. The pipeline is not yet perfected at isolating only the intended user's voice.

### Has noisy-environment performance been evaluated?
**INFORMAL / PARTIAL.** Some real-world testing has occurred, but no formal benchmark has been documented.

### Can another person's speech be incorrectly accepted?
**RISK PRESENT / NEEDS MORE TESTING.** The voice system still needs improvement to reliably isolate only the intended user's voice.

### Are sensitive voice recordings retained?
**NO, BASED ON CURRENT IMPLEMENTATION.** To my knowledge, I have not implemented storage of raw user voice recordings. Voice is transcribed rather than intentionally archived as audio.

### Is the user informed when microphone access is active?
**PARTIAL.** The application includes a voice-state interface, but microphone disclosure/indicator behavior has not been formally evaluated as a governance control.

## Privacy

### Has each external data transfer been identified?
**PARTIAL.** Major external paths such as OpenRouter and ElevenLabs are known, but I have not created a complete formal data-flow register.

### Has unnecessary data collection been removed?
**NOT FORMALLY EVALUATED.**

### Are credentials protected?
**PASS.** Provider API keys use encrypted storage and infrastructure secrets use AWS Secrets Manager.

### Are conversation-storage controls tested?
**PARTIAL.** Conversation persistence and deletion work in normal use, but complete deletion across every memory/index/storage layer has not been verified.

### Is local-device storage protected appropriately?
**NOT FORMALLY EVALUATED.** The cloud application primarily stores conversations server-side. Client-side/browser storage has not undergone a formal assessment.

## Security

### Has authentication been tested?
**PARTIAL.** Authentication is implemented and used, but I have not performed a formal authentication security test suite.

### Has session handling been tested?
**PARTIAL.** Secure session functionality is implemented, but formal session-security testing has not been completed.

### Can active sessions be forcibly invalidated after credential compromise?
**NOT YET.**

### Has API-key protection been tested?
**PARTIAL.** API-key encryption is implemented. Formal security testing of the control has not yet been completed.

### Are secrets excluded from the public source repository?
**PASS.** The public repository is sanitized and does not intentionally include live API keys or deployment credentials.

### Has cross-user access been tested?
**INFORMAL TEST PASSED.** Limited testing has shown separate users do not see one another's data. Larger-scale/formal testing remains future work.

### Has input validation been tested?
**NOT YET FORMALLY TESTED.** The application has undergone normal/ad hoc use, but not enough malformed-input testing to make a definitive security claim.

### Have dependency vulnerabilities been scanned?
**NOT YET.**

### Are security dependencies regularly updated?
**NOT YET FORMALIZED.** I do not yet have a regular security-dependency patching/update process.

### Is rate limiting or abuse prevention implemented?
**NOT YET.**

## Availability and Resilience

### Has a formal uptime/reliability target been defined?
**NOT YET.** Dominus Cloud is still in active development, so I have not committed to a production uptime target.

### Has model-provider outage behavior been tested?
**OBSERVED.** I have experienced real OpenRouter outages. Requests may fail to produce a response. A self-hosted Gemma model exists as an alternative path, but automated graceful failover has not been formally established.

### Has database failure behavior been tested?
**INFORMAL / PARTIAL.** When the database/network path has problems, the application can surface a general invalid/network-style error. It does not yet provide polished graceful degradation or a clear diagnosis.

### Has ECS/container restart behavior been tested?
**OBSERVED / PARTIAL.** Based on normal use, the application appears to recover cleanly after infrastructure/container restarts without losing persistent conversation information. I have not run a formal repeatable restart test.

### Has external TTS failure been formally tested?
**NOT YET.**

### Has the Gemma alternative model path been tested?
**PASS FOR BASIC FUNCTIONALITY.** The Gemma model on AWS has been installed and works. Formal automated failover testing between OpenRouter and Gemma has not been completed.

### Has backup restoration been tested?
**NOT YET.**

# 4. MANAGE

## Risk Prioritization

### Is likelihood scored for identified risks?
**NOT YET.**

### Is impact scored?
**NOT YET.**

### Is an overall risk level assigned?
**NOT YET.**

### Are mitigations documented?
**PARTIAL.** Technical mitigations exist, but a formal risk register with mitigation entries has not yet been completed.

### Is a risk owner assigned?
**PASS.** I am currently the owner of identified system risks.

### Is risk status tracked?
**NOT YET FORMALIZED.**

## Model Failure

### Can a problematic model be disabled?
**PASS.** Model/provider configuration is selectable, and optional external capabilities can be disabled or left unconfigured.

### Can the system switch providers safely?
**PARTIAL.** The architecture supports different models/providers, but switching has not undergone formal safety/regression testing.

### Can another AI path remain available if OpenRouter fails?
**PARTIAL / FUNCTIONAL.** A Gemma model is installed on AWS and works as an alternative model path. Automatic failover is not formalized.

### Can an unsafe optional feature be disabled without shutting down the entire system?
**PASS.** Optional provider-dependent features can be disabled/unconfigured without making every part of the application unusable.

## Privacy/Security Incident Management

### Can compromised provider credentials be revoked?
**PASS.** Users can remove/change their provider API keys from Settings.

### Can affected sessions be forcibly invalidated?
**NOT YET.**

### Can exposed information be deleted?
**PARTIAL.** Conversation deletion exists. Complete deletion across all memory/index/backup layers has not been verified.

### Can potentially affected users be identified?
**PARTIAL.** The current system is private/test-oriented with controlled access. A formal incident-impact identification process has not been created for a larger user base.

### Is an incident documented after resolution?
**NOT YET.**

### Is there a formal incident-response process?
**NOT YET.**

## Continuous Monitoring

### Are failures and suspicious behavior actively monitored?
**NOT YET FORMALIZED.** I do not yet have a formal security/AI monitoring and alerting program for suspicious behavior.

### Are AI-provider changes reviewed?
**PARTIAL.** I personally research and test changes, but I do not maintain a formal provider-review record.

### Are model changes reassessed?
**PARTIAL.** I test changes during development, but a formal AI risk reassessment procedure has not been established.

### Are security dependencies updated on a defined schedule?
**NOT YET.**

### Are new capabilities added to the risk inventory?
**NOT YET.** This assessment is the beginning of formalizing the risk inventory.

### Is this risk assessment periodically reviewed?
**NOT YET.** No recurring review cadence has been established.

## Go / No-Go Decision

### Does the system perform its intended purpose?
**PASS FOR CURRENT PRIVATE/TEST USE.** Dominus Cloud functions as a conversational AI system with the core capabilities for which it is currently being developed and tested.

### Are all critical risks mitigated?
**NOT YET DETERMINED.** Formal risk scoring has not yet been completed.

### Are known limitations documented?
**PARTIAL.** Technical limitations, architecture choices, and hardening considerations are documented. This assessment adds governance limitations and gaps.

### Is residual risk acceptable?
**ACCEPTED FOR LIMITED PRIVATE/TEST USE.** As system owner, I currently accept the residual risk for my limited private/test deployment. This is not acceptance for unrestricted public production deployment.

### Has deployment been approved?
**YES — LIMITED PRIVATE/TEST DEPLOYMENT.** I have approved the current system for my own private/test use and limited authorized testing.

### Is Dominus Cloud approved for unrestricted public production use?
**NO.**

# 5. CURRENT ASSESSMENT DECISION

## GO WITH CONDITIONS — PRIVATE/TEST USE ONLY

Dominus Cloud is currently acceptable for continued private development and limited authorized testing under my ownership.

This assessment does **not** represent approval for unrestricted public production deployment.

Priority gaps before broader production use:

1. Create privacy, acceptable-use, retention, security, and incident-response policies.
2. Create a formal AI/model/provider inventory.
3. Complete a data-flow and third-party provider register.
4. Characterize and test TencentDB/TDAI memory retention, retrieval, isolation, and deletion behavior.
5. Create repeatable hallucination, prompt-injection, memory-isolation, input-validation, and voice tests.
6. Verify deletion across conversation storage, memory indexes, and backups.
7. Add security monitoring, abuse prevention/rate limiting, vulnerability scanning, and dependency-update procedures.
8. Improve graceful failure behavior for provider/database outages.
9. Test backup restoration and infrastructure recovery.
10. Create a formal risk register with likelihood, impact, mitigation, owner, and status.
11. Establish a recurring governance reassessment cadence before public deployment.

# 6. ASSESSMENT SUMMARY

Dominus Cloud already contains meaningful technical controls and architecture-level safeguards. The largest remaining gaps are formal governance processes, repeatable testing, documented policies, monitoring, and risk-management evidence expected before a broader production deployment.

This document distinguishes between controls already implemented, controls observed informally, controls partially implemented, and controls not yet created or formally tested. It should be updated as those gaps are addressed.

---

*Portfolio and risk-management artifact based on the current Dominus Cloud implementation and a practical NIST AI RMF structure. Not legal advice, a NIST certification, or a regulatory certification.*
