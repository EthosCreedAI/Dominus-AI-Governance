# EU AI Act — Dominus Conversational AI Assessment

**Systems:** Dominus Cloud; Dominus Gemma iOS  
**Framework:** Regulation (EU) 2024/1689  
**Assessment status:** Completed baseline assessment  
**Assessment date:** September 15, 2026

> Assessment aid based on the systems' current state. Not legal advice or a legal certification.

# STEP 1 — TERRITORIAL APPLICABILITY

- **Is the system placed on the EU market?** NO.
- **Is the system made available to users within the EU?** NO.
- **Is an organization operating the system in the EU?** NO.
- **Could system output be used within the EU?** Not under the current private/test deployment.

**Assessment: OUT OF SCOPE CURRENTLY.** Reassess before an EU rollout or other material change in territorial applicability.

# STEP 2 — ROLE

- **Provider:** YES — I am the creator/provider of Dominus.
- **Deployer:** YES — I also use/deploy the system myself.
- **Importer:** NO under the current deployment.
- **Distributor:** NO under the current deployment.
- **Product manufacturer:** NO.
- **Other:** None identified.

# STEP 3 — INTENDED PURPOSE

- **General productivity:** YES.
- **Personal assistance:** YES.
- **Knowledge retrieval:** YES.
- **Voice interaction:** YES.
- **Employment decisions:** NO.
- **Education decisions:** NO.
- **Credit decisions:** NO.
- **Healthcare decisions:** NO.
- **Law enforcement:** NO.
- **Migration/border decisions:** NO.
- **Biometric identification:** NO.
- **Other regulated use:** None identified.

# STEP 4 — PROHIBITED PRACTICES SCREEN

- **Harmful manipulation or deception?** NO.
- **Exploitation of vulnerable persons in a prohibited manner?** NO.
- **Prohibited social scoring?** NO.
- **Prohibited criminal-risk prediction?** NO.
- **Prohibited biometric practices?** NO.
- **Prohibited emotion-recognition use?** NO.
- **Other prohibited practices?** None identified.

**Result:** No prohibited practice identified in the current intended use.

# STEP 5 — HIGH-RISK SCREEN

**Assessment: NOT IDENTIFIED AS HIGH-RISK.**

**Reason:** Dominus is currently intended for general conversational assistance, productivity, knowledge retrieval, and voice interaction. It is not intended for employment, education, credit, healthcare, law enforcement, migration/border, biometric-identification, or other high-risk decision-making uses.

# STEP 6 — CONVERSATIONAL AI TRANSPARENCY

- **Is the user informed that they are interacting with AI?** YES.
- **Is that disclosure understandable?** YES.
- **Is disclosure presented early enough?** YES — the AI nature is apparent in the interface.
- **Is the interface designed so users are not intentionally led to believe they are communicating with a human?** YES.
- **Does voice mode clearly remain identifiable as AI interaction?** YES.
- **Is AI-generated output identifiable where legally required?** YES for the current conversational interface; reassess any additional Article 50 marking/disclosure requirements if the system enters EU scope or gains new generated-media capabilities.

# STEP 7 — GENERATED CONTENT

- **Does the system generate text?** YES.
- **Does the system generate synthetic audio?** YES — ElevenLabs can provide AI-generated voice output.
- **Does it generate images?** NO.
- **Does it generate video?** NO.
- **Are machine-readable marking requirements applicable?** POTENTIALLY APPLICABLE if/when the system enters EU scope; requires reassessment for the specific generated-content functionality.
- **Are generated-content disclosures applicable?** POTENTIALLY APPLICABLE if/when the system enters EU scope.
- **Could output constitute a deepfake?** NO under the current functionality/intended use.
- **Could output be published as public-interest information without human review?** NO.

# STEP 8 — DATA AND PRIVACY

## Dominus Cloud

- **Are external AI providers documented?** YES — including OpenRouter and ElevenLabs.
- **Are international data transfers identified?** NOT APPLICABLE to the current U.S.-only/private deployment; reassess before international/EU deployment.
- **Is conversation retention documented?** NOT YET. Conversations are currently retained unless deleted, but no formal retention policy exists.
- **Are user deletion mechanisms available?** PARTIAL — a trash/delete mechanism removes conversations from the user-facing application, but complete deletion across the memory layer/indexes has not yet been verified.
- **Is cloud storage documented?** YES.
- **Are external speech services documented?** YES.

## Dominus Gemma iOS

- **Is processing actually local?** YES for the local configuration.
- **Are microphone permissions documented?** YES.
- **Is local persistence documented?** YES.
- **Does enabling an external API alter the privacy assessment?** YES — using OpenRouter causes relevant data to leave the device.
- **Does enabling external TTS alter the privacy assessment?** YES — using an external TTS API introduces an external data flow.

# STEP 9 — HUMAN OVERSIGHT

- **Can the user reject an AI response?** YES. Users remain responsible for their own decisions and may ignore/reject AI guidance.
- **Can a human administrator disable functionality?** YES.
- **Can problematic models be removed?** YES — models can be changed/disabled and users can switch models.
- **Can memory be corrected or deleted?** NOT YET as a complete user-facing memory-management capability.
- **Can a user identify an AI error?** PARTIAL — users can recognize/reject incorrect output, but no formal error-reporting workflow exists.
- **Are system limitations communicated?** YES.

# STEP 10 — TECHNICAL DOCUMENTATION

- **System purpose:** DOCUMENTED.
- **Architecture:** DOCUMENTED.
- **Models:** DOCUMENTED.
- **Model providers:** DOCUMENTED.
- **Data flows:** DOCUMENTED.
- **Storage:** DOCUMENTED.
- **External services:** DOCUMENTED.
- **Known limitations:** DOCUMENTED.
- **Testing:** PARTIAL — current evidence is primarily development/ad hoc testing rather than a formal test program.
- **Security controls:** DOCUMENTED.
- **Human oversight:** DOCUMENTED in this assessment and related governance material.
- **Version:** Repository/version history provides technical versioning, but a dedicated governance release record can be strengthened.
- **Release date:** Can be strengthened through a dedicated governance release record.
- **Responsible owner:** DOCUMENTED — I am the current sole owner/operator.

# STEP 11 — LOGGING AND TRACEABILITY

- **Are significant system errors logged?** PARTIAL — the interface can surface general errors such as networking failures, but detailed administrative logging is not yet sufficient.
- **Can incidents be investigated?** PARTIAL.
- **Can model/provider changes be traced?** NOT YET reliably after the fact.
- **Can deployments be traced to versions?** PARTIAL through repository/deployment history; a formal governance traceability record has not been established.
- **Can security events be investigated?** PARTIAL / NOT FORMALIZED.
- **Are logs privacy-conscious?** NOT YET FORMALLY ASSESSED.

# STEP 12 — CONTINUOUS REVIEW

I will reassess the system when:
- A model changes.
- A provider changes.
- New memory functionality is introduced.
- File ingestion is introduced or materially changed.
- Agentic/tool capabilities are introduced.
- New users or broader public access are introduced.
- Intended purpose changes.
- The system enters a regulated domain.
- The system is offered or used in the EU.

# FINAL ASSESSMENT

**EU AI ACT APPLICABILITY:** OUT OF SCOPE CURRENTLY based on the present private/test deployment and stated lack of EU market/users/operation. Reassess if deployment circumstances change.

**ROLE:** Provider and deployer for assessment purposes.

**RISK CLASSIFICATION:** Not identified as high-risk under the current intended purpose. No prohibited practice identified.

**TRANSPARENCY OBLIGATIONS:** The system clearly presents itself as AI. Generated-content/technical marking obligations should be reassessed if the system enters EU scope or its media-generation capabilities change.

**HIGH-RISK REQUIREMENTS:** Not applicable based on the current intended purpose and current territorial assessment.

**OPEN ACTIONS:**
1. Create a formal conversation/data-retention policy.
2. Verify deletion across PostgreSQL, TencentDB/TDAI memory, indexes, and backups.
3. Add user-facing memory correction/deletion controls.
4. Improve administrative logging and incident traceability.
5. Add model/provider traceability after the fact.
6. Formalize incident reporting/investigation.
7. Reassess territorial applicability and Article 50 obligations before EU availability.
