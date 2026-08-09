# Knowledge Update Log

## 2026-08-09

- **Source Capture**: Preserved the leader's evolving feedback on PROVE principles, Scenario-generation sources, quality, Firenze incremental application, the `eSSD 커버리지 강화 sTF` dependency, and schedule.
- **Draft Record**: Added an executive discussion document containing only the leader's stated ideas and explicitly retained missing content as unresolved rather than filling it with Agent proposals.
- **Draft Clarification**: Recorded the confirmed full wording that intended verification on a real Device and correct judgment must be demonstrated through reproducible results.
- **Leader Wording**: Recorded the confirmed Test Scenario generation statement, including `FW 개발 산출물(FLAIR Docs)` as an input without making Scenario generation a mechanical document-to-Test conversion.
- **Draft Visualization**: Added a Mermaid representation of the leader's Verification Space model: Spec and FW-development-artifact Scenarios fill parts of each Space Area, while existing Test knowledge, Device information, and expert knowledge address the remaining Space and Gaps.
- **Leader Clarification**: Reframed Scenario generation as three strategies and clarified that PROVE supports the responsible expert engineer in filling the remaining Space rather than autonomously substituting for that expertise.
- **Leader Clarification**: Moved the `eSSD 커버리지 강화 sTF` Verification Space expected by 2026-08-31 into the main Scenario-generation statement and removed the redundant standalone subsection.
- **Draft Structure**: Combined current-state diagnosis, the ideal goal, and the still-undefined realistic goal under `현재 수준 진단과 단계적 목표`, then renumbered the following sections.
- **Leader Confirmation**: Aligned Scenario-generation subsections with the three approved strategies and moved Leveling, Graph, Feature visibility, and Gap analysis into a shared cross-strategy section.
- **Responsibility Clarification**: Assigned Verification Space and Space Area definition to the separate `eSSD 커버리지 강화 sTF`; PROVE consumes that definition to map existing Scenarios, identify Gaps, and fill the Space through its three strategies.
- **Draft Structure**: Reordered the opening narrative to ideal goal, current-state diagnosis, and realistic goal for executive communication.
- **Leader Goal**: Defined the unconstrained ideal as complete Device-verification Coverage through generated Scenarios and autonomous Scenario generation, real-Device verification, and result judgment without human intervention; kept current sTF constraints outside the ideal goal.
- **Leader Diagnosis**: Explained that accumulated Test Packages cannot serve as the denominator for Device Coverage because the complete combination space is undefined, and positioned the sTF-defined Verification Space as PROVE's practical input for Scenario and Gap management.
- **Draft Structure**: Split the current-state diagnosis into Coverage-calculation and human-free-autonomy limitations, avoiding forward references to Scenario-generation strategies that are introduced later.
- **Leader Correction**: Removed undefined Test Scenario and Device-result Quality criteria as a stated cause of human intervention; PROVE will pursue those Quality assurances rather than use their current status as a diagnosis premise.
- **Leader Boundary**: Distinguished independently generatable Scenario areas from areas requiring expert judgment, where the responsible engineer leads Scenario creation with PROVE support.
- **Diagnosis Precision**: Replaced an unsupported AI-generation limitation with the evidence-oriented statement that Spec and FW inputs alone cannot establish Scenario completeness across the defined verification domain.
- **Neutral Diagnosis**: Reframed Spec, FW artifacts, Legacy Test knowledge, and expert judgment as complementary inputs; located the limitation in their current lack of structure for independent PROVE combination rather than in FW artifact quality.
- **Current Direction**: Connected the autonomy limitation to extraction and structuring, expert-led collaboration where needed, reusable knowledge accumulation, and progressive expansion of PROVE's independent Scenario-generation scope.
- **Autonomy Link**: Made Test Scenario generation the first autonomy priority and linked it progressively to Test generation, real-Device execution, and result judgment.
- **Executive Draft Structure**: Removed the standalone core-sentence section, added a table of contents, and renumbered the draft from section 1.
- **Scenario Strategy Detail**: Expanded Specification, legacy Test Package, FW artifact, expert-supported Scenario generation, Coverage tracking, and generated-result Quality evaluation in the executive draft.
- **Legacy Leveling Evidence**: Recorded L1 through L7 Test Leveling as an existing analysis result and combined Requirement–Scenario linking, Leveling, and gap identification into one flow.
- **White-box Direction**: Added AI-assisted FW and Device implementation analysis as the basis for pursuing White-box-level Test Scenario generation.
- **Scenario Section Alignment**: Aligned the Specification and FW-based Scenario sections to parallel generation, deeper-analysis, and Coverage/application stages without removing content.
- **Expert Scenario Support**: Structured expert-supported Scenario generation around AI limits, Rule/Skill/Template assistance, IceT experience, and verification-engineer usability feedback.
- **Firenze Incremental Strategy**: Defined FLAIR-led Firenze inputs, preservation of existing Scenarios, Coverage-gap additions, and incremental extension for new customer requests and Milino; removed the now-duplicated Feedback section.
- **Scenario Schedule**: Set the overall Test Scenario schedule to 2026-08-03 through 2026-10-05 and retained sections 2.1, 2.2, and 2.3 as Gantt duration bars with adjustable overlap and dependencies.
- **Draft Structure**: Kept limitations in the current-state diagnosis and moved the sTF-defined Space approach and expert collaboration into `현실적인 목표와 접근`.
- **Draft Structure**: Reorganized the opening around two stable axes—Coverage and autonomous verification—each with ideal goal, current limitation, and realistic approach, preceded by a one-line summary.
- **Leader Framing**: Renamed the section to `PROVE의 목표와 점진적 추진 방향`, replaced `현실적인 접근` with `현재 추진 방향`, and stated that Coverage breadth and autonomy expand progressively from the currently defined scope.
- **Open Questions**: Added unresolved decisions for the Firenze Baseline and denominator, Scenario Leveling and Graph, the third FTL Source, sTF handoff, and customer-Spec Vector Database search quality.

## 2026-08-02

- **Decision**: Elevated Governance of every generated artifact to the priority immediately after Test Scenario extraction and required explicit stage Inputs, versioned Outputs, Evidence-based Review Records, and downstream Input lineage.
- **Draft Plan**: Integrated the eleven reviewed work items into seven two-month Workstreams, five Evidence-based Milestone Reviews, dependency flow, required and deferred scope, and immediate TF decisions.
- **Decision**: Confirmed initial execution Hardware and removed Hardware selection or procurement from Milestone Review 1 while retaining configuration and Capability recording for Traceability.
- **Draft Clarification**: Replaced custom shorthand with the common terms Workstream and Milestone Review, written in full, and expanded each with ownership boundaries, key work, review inputs, questions, deliverables, and completion Evidence.
- **Source Capture**: Preserved the complete review input for two-month work items 6–11 and the consolidated workstream map so review can continue across context compression.
- **Decision**: Established Test Scenario as PROVE's most important long-term asset.
- **Decision**: Established Test Case generation, selection, and evaluation as the core means of filling Scenario-defined verification space.
- **Decision**: Classified Test Script language and runtime as replaceable implementation choices.
- **Decision**: Allowed compatible Test state reuse while prohibiting hidden execution-order dependencies.
- **Decision**: Required sequence-dependent Failures to be reproduced, minimized, causally analyzed, and promoted into verification assets when meaningful.
- **Decision**: Aligned immutable Verification Baselines with each Main and Deri project's own formal development gates rather than every individual change.
- **Decision**: Defined a Baseline as a version-reference manifest with inheritance and delta overlays, not a copied asset set.
- **Decision**: Limited Legacy code and Library analysis to the paths required for Scenario and Verification Knowledge extraction; a complete dependency graph is not a project outcome.
- **Decision**: Required Source-specific Scenario Candidates to be preserved while they are mapped non-destructively to Canonical Scenarios or Variants.
- **Decision**: Required bidirectional, versioned Traceability across Sources, mapping decisions, Scenarios, Cases, executions, Evidence, verdicts, and follow-up actions.
- **Decision**: Separated generated Test qualification into executable, Scenario-intent, verdict, and operational areas rather than one undifferentiated score.
- **Decision**: Established IceT retention of control and Evidence through Reset, Error, and abnormal Device states as a Platform invariant rather than an individual Test property.
- **Decision**: Assigned executable Test candidate selection to each verification team according to its R&R, product scope, purpose, time budget, Hardware, and Tool constraints rather than imposing one enterprise-wide execution list.
- **Draft Update**: Recorded the currently known SWE, cSSD verification, eSSD verification, and United States FTE roles while leaving incomplete organizational details open.
- **Draft Update**: Added eSSD-specific Hardware and extensive customer, OCP-version, TP, and Deri input characteristics.
- **Decision**: Established one common PROVE system and one shared logical Knowledge and Traceability plane rather than independently authoritative PROVE instances for each verification team.
- **Governance**: Deferred detailed Workspace, View, selection, ownership, promotion, and conflict rules for later design with experts from each verification team.
- **Governance**: Separated verification-organization R&R from common PROVE architecture and added a standard team-review template for SWE, cSSD verification, eSSD verification, and FTE experts.
- **Decision**: Defined Applicability as mapping a user's verification Requirements through applicable verification assets to executable Tests and real environments, not merely matching a Test to Hardware.
- **Decision**: Established the versioned Verification Request as the top-level Traceability unit for all derived Requirements, Scenarios, Cases, Execution Plans, runs, Evidence, and verdicts.
- **Decision**: Separated execution-level Test Verdict from evidence-based Failure Disposition and required every Test Fail to trigger the PROVE Failure Analysis Agent.
- **Decision**: Distinguished the PROVE Failure Analysis Agent from BRAIN, which receives Device Failures after PROVE Disposition.
- **Decision**: Required immutable capture of first-Failure Evidence before intervention and assigned adaptive reproduction planning to the PROVE Failure Analysis Agent.
- **Decision**: Established a stable, versioned Failure Analysis Record for each observed Test Fail and kept later similarity clustering separate from individual occurrence history.
- **Decision**: Allowed PROVE Device Disposition through direct Device Evidence or reasonable exclusion of Non-device causes without requiring internal SSD root-cause proof before BRAIN handoff.
- **Decision**: Separated Verification Knowledge applicability scope from operational Trust State so organization or project context is not treated as a quality rank.
- **Decision**: Distinguished operational Knowledge Trust State from OKF documentation lifecycle status.
- **Decision**: Allowed immediate, explicitly labeled experimental use of Draft Knowledge while prohibiting its direct use for official Coverage, verdict, Test Package, or Gate Baseline claims.
- **Decision**: Prohibited Knowledge-producing Agents from self-promotion and assigned initial Verified promotion to the accountable expert for the target scope with independent evaluation Evidence.
- **Decision**: Required version-preserving Knowledge revocation, Traceability-based impact analysis, corrected versions, and revalidation instead of deletion or historical overwrite.
- **Decision**: Established Verification Request, Agent Workflow Run, Test Execution Run, and Failure Analysis Record as distinct linked trace units and prohibited retry or resume from overwriting prior Attempts.
- **Decision**: Defined PROVE reproducibility as audit reconstruction, operational replay, and verification-result equivalence rather than universal byte-identical LLM output.
- **Decision**: Required versioned Artifact-based Agent Handoffs, durable Checkpoints, linked resume Attempts, upstream-change invalidation, and bounded traceable Retry.
- **Decision**: Adopted a minimal Test lifecycle of immutable ID and Version, Draft/Validated/Deprecated status, and Validation Evidence; official adoption is established by Package or Gate Baseline Manifest reference.
- **Draft Proposal**: Proposed protected annotated Git tags over a canonical Baseline manifest commit, with database indexing for search and impact analysis.
- **Draft Proposal**: Added semantic and state-aware Test Case generation for TF discussion, combining verification meaning, state transitions, controlled exploration, and execution feedback.
- **Draft Proposal**: Added standards-informed Test Design, Scenario, Case, and Script terminology.
- **Draft Proposal**: Separated reusable Verification Patterns from unified Test Library implementations.
- **Draft Update**: Captured the two-mission model with Test Specification and FLAIR input paths.
- **Draft Update**: Reframed Global Test Package integration as gradual validated convergence.
- **Draft Update**: Recorded the IceT, heterogeneous hardware, Test Package, and team-library structure.
- **Draft Update**: Added Firenze Pilot and FLAIR–PROVE–BRAIN working models.
- **Draft Update**: Added the 2/4/6-month framework and the first-two-week working target for Coverage Method Review.
- **Governance**: Kept all new operating details in `draft` because the leader's working model may evolve.

## 2026-07-27

- **Decision**: Established Verification Knowledge and measurable Coverage as the stable PROVE core.
- **Decision**: Required independent evaluation of Verification Intent and defect-detection preservation.
- **Decision**: Deliberately deferred Coverage-axis definition to PROVE verification experts.
- **Decision**: Classified IceT, SkyTower, languages, models, and agent frameworks as replaceable enabling tools.
- **Update**: Added mandatory Core Value guidance for all contributors, subprojects, and Agents.

## 2026-07-26

- **Creation**: Established the PROVE Root Knowledge Bundle using OKF v0.2.
- **Creation**: Captured the initial project vision, charter, scope, team, and directional roadmap.
- **Creation**: Defined draft SSD verification, AI autonomy, and traceability principles.
- **Creation**: Added initial capability, system context, workflow, and integration maps.
- **Creation**: Recorded Test Quality and Coverage as an unresolved core framework.
- **Creation**: Added governance, decision, agent, risk, and open-question documents.
- **Creation**: Added templates for independent subproject knowledge repositories.
