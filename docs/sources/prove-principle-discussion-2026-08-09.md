---
type: Source
title: PROVE Principle and Firenze Application Discussion
description: Leader discussion input for PROVE principles, Scenario generation, quality, Firenze application, and schedule revision.
tags: [prove, principle, scenario, quality, firenze, incremental, verification-space]
status: draft
generated: { by: openai-codex/gpt-5, at: "2026-08-09T00:00:00+09:00" }
---

# Context

The PROVE leader received feedback requiring the plan to explain its underlying principle, not only its Agents, Workstreams, or implementation steps. The following points are evolving discussion input rather than approved decisions.

# Leader Input

## Ideal Goal

- Ultimately reach a level at which PROVE can cover 100% of all Device Features without human intervention.
- Define Coverage and create verification that fills it.
- This cannot be achieved at the current stage; the reasons must be explained.

## Realistic Goal

- A realistic near-term PROVE goal must be defined.

The leader confirmed that current-state diagnosis, the ideal goal, and the realistic goal should be presented together under `현재 수준 진단과 단계적 목표`, while the realistic goal remains to be defined.

The leader clarified that PROVE does not define the Verification Space. A separate `eSSD 커버리지 강화 sTF` defines the Verification Space and its Space Areas; PROVE consumes the defined Space, identifies existing Scenarios and remaining Gaps, and fills it through the three Scenario-generation strategies. For executive communication, the ideal goal is presented before the current-state diagnosis, followed by the realistic goal.

The leader confirmed that the ideal goal must remain unconstrained by the current Verification Space or sTF responsibility. It states the ultimate objectives of defining total Device-verification Coverage and satisfying it completely with generated Test Scenarios, then autonomously generating Scenarios, executing actual Device verification, and judging results without human intervention. Current limitations and the pragmatic sTF-based approach remain separate in the diagnosis.

The leader approved a simplified diagnosis: Device Coverage 100% requires a defined total verification domain, but the combinations of Feature, Device state, operation order, error conditions, FW policy, and customer requirements are not currently defined as one complete domain. Existing Test Packages are accumulated Tests rather than that complete denominator. The separate sTF therefore defines a traceable Verification Space, which PROVE consumes to identify existing Scenarios and Gaps and fill the Space through its three strategies.

The leader confirmed that the current-state diagnosis should mirror the two ideal goals: `Device Coverage 100% 산정의 한계` and `인간 개입 없는 자율 검증의 한계`. The autonomy diagnosis must not refer to numbered strategies before they are introduced; it directly describes the areas that documents and existing Tests cannot fill and the expert-engineer involvement still required.

The leader removed the statement that Test Scenario and real-Device result Quality criteria are not yet defined from the autonomy diagnosis. PROVE will attempt to assure Device verification results and Quality as far as possible, so that topic is not used here as a reason that human intervention is currently required.

The leader clarified that the current boundary should distinguish areas where PROVE can generate Test Scenarios independently from areas requiring expert judgment. In the latter areas, the Space Area expert leads Scenario creation with PROVE support; they are not described as outside PROVE altogether.

The leader approved replacing the unsupported claim that all required Scenarios cannot be generated automatically with the more precise limitation: Specification and FW artifacts provide functional requirements and implementation information but do not contain all Legacy verification intent, Device state, or expert judgment, so Scenarios generated from those artifacts alone cannot be judged to fill the complete defined verification domain.

The leader refined this limitation to avoid implying fault in FW artifacts or the FW organization. Specification and FW artifacts provide functional requirements, Device state, FW policy, and implementation information; Legacy verification intent and expert judgment are complementary inputs. The current limitation is that those verification inputs are not yet fully structured or documented for PROVE to combine and judge independently.

The leader approved a corresponding current direction: extract and structure information from Spec, FW artifacts, and Legacy Test knowledge; generate independently where structured information is sufficient; collaborate with the responsible expert where judgment is required; and retain the resulting intent and expertise in reusable form to expand PROVE's independent scope progressively.

The leader connected Scenario generation to the broader autonomy goal: greater human involvement in Test Scenario creation limits verification-process autonomy because Scenarios guide downstream Test generation, real-Device execution, and result judgment. PROVE therefore prioritizes Scenario-generation autonomy and progressively connects validated Scenarios to those downstream activities.

The leader accepted separating diagnosis from response. The current-state section now contains only the Coverage-denominator and Scenario-completeness limitations. The realistic-goal section contains the two current approaches: using the sTF-defined Verification Space and collaborating with the responsible Space Area expert where PROVE cannot generate independently.

The leader then accepted an axis-first executive structure. `Coverage 정의 및 충족` and `인간 개입 없는 자율 검증` each present their ideal goal, current limitation, and realistic approach without switching between the two axes. The section begins with one summary line for each axis before the detailed subsections.

The leader replaced `현실적인 접근` with `현재 추진 방향` and framed the section as `PROVE의 목표와 점진적 추진 방향`. Coverage breadth and autonomy level begin from the currently defined scope and expand progressively rather than implying that the ideal goal is reduced.

The leader explicitly labeled the two organizing perspectives as `무엇을 얼마나 검증할 것인가(Coverage 관점)` and `어디까지 인간 개입 없이 검증할 것인가(AI 자율 검증)`.

## Test Scenario Generation

The PROVE leader confirmed the following core wording:

> PROVE는 Spec과 FW 개발 산출물(FLAIR Docs)의 문장을 기계적으로 Test Scenario로 변환하지 않는다. 해당 프로젝트의 Spec과 FW 개발 산출물, 기존 Test Package에서 추출한 검증 의도와 노하우, Device 상태 및 구현 정보, Verification Space, 그리고 검증 전문가의 지식을 함께 분석하여 검증 의미 중심의 Test Scenario를 생성한다.

The leader further clarified the intended spatial model:

- The outer rectangle represents the complete Verification Space.
- The Verification Space contains multiple Space Areas.
- Project Specification-based and FW-development-artifact-based Scenarios fill portions of each Area.
- Existing Test Package intent and knowledge, Device state and implementation information, and verification-expert knowledge are analyzed together to fill the remaining Space and Gaps.

The leader subsequently clarified the allocation within each Space Area:

- Specification-based Test Scenarios are generated using verification intent and knowledge extracted from existing Test Packages.
- FW-development-artifact-based Test Scenarios are generated using Device state and implementation information.
- The remaining gray Space and Gaps contain only the area to be filled using verification-expert knowledge.

The leader then confirmed the three-strategy wording:

1. Generate Test Scenarios from the target project's Specifications and verification intent and knowledge extracted from existing Test Packages.
2. Generate Test Scenarios from FW development artifacts and Device state and implementation information.
3. For the remaining area, PROVE helps the expert engineer responsible for the Space Area create the Test Scenarios rather than claiming to fill the expert area independently.

The leader confirmed that the separate Verification Space subsection should be absorbed into the main Scenario-generation statement. The controlling initial Space is the Verification Space that the `eSSD 커버리지 강화 sTF` is expected to establish and confirm by 2026-08-31, and the three strategies generate Scenarios to fill its Space Areas.

The leader accepted restructuring the detailed Scenario-generation section to match the three strategies:

1. Specification and existing Test Package intent and knowledge;
2. FW development artifacts and Device state and implementation information;
3. PROVE support for the responsible expert engineer to fill the remaining Space.

Scenario Leveling, Feature serial and parallel and combination Graph analysis, Feature-level verification visibility, and filled-versus-missing Space analysis apply across all three strategies rather than belonging to only one input path.

### Specification-Based

- Extract Requirements from the Specifications used by the target project.
- Mechanical line-by-line Scenario generation from Specification text is not considered meaningful.

### Existing Test-Based

- Extract Scenarios from each team's existing Test Cases and understand how the Scenarios are constructed.
- Identify the verification knowledge embedded in the extracted Scenarios.
- Define Scenario levels.
- Represent serial, parallel, and combinational Feature relationships as a Graph.
- Use this analysis to identify and fill Scenarios missing from the current Test Package.

### Specification and FTL Combination

- Combine Feature meaning with state-aware FTL information.
- Run a proof of concept across at least the following candidate sources:
  - FTL policy documents, including Confluence and later FLAIR;
  - direct inspection of FTL code;
  - an additional source that has not yet been decided.

### Verification Space

- Use the Verification Space being developed by the `eSSD 커버리지 강화 sTF`.
- Generate Scenarios capable of filling the Space based on the sTF definition expected on 2026-08-31.

### Remaining Knowledge

- Determine how to extract tacit knowledge held by verification engineers.
- Consider Rules, Skills, and Templates, including IceT-related examples, as extraction mechanisms.

## Quality

- Define how PROVE guarantees the quality of generated results.

## Inputs

- Customer Specifications prepared by `Solution 개발 혁신` are an input candidate.
- Because of NDA risk, use the prepared Vector Database rather than transmitting raw customer documents.
- Search accuracy must be evaluated.
- Review the `Agent TAG` work associated with TL 정인호.

## Firenze Application

- Firenze already uses FLAIR, and current AI analysis indicates that FLAIR Docs explain most of the human-authored FW Source Code; verify this further and use Confluence or related documents for missing information.
- Preserve existing Test Scenarios that already correspond to Requirements and generate new Scenarios only for Coverage gaps identified by PROVE.
- Most new-Feature Test Cases in Firenze are currently understood to be complete, so apply PROVE by finding and filling omissions rather than replacing the existing Test Package.
- For new customer requests and the later Milino Project, preserve existing Scenarios, compare them with new Feature Requirements, and incrementally add only missing Scenarios.
- The former executive-draft Feedback section is absorbed into this Firenze strategy and the earlier Verification Space discussion; unresolved numeric scope remains in Open Questions.

## Schedule

- Start Test Scenario work on 2026-08-03.
- End the overall Test Scenario schedule on 2026-10-05 while retaining the previously defined intermediate target dates.
- Complete section 2.1 by 2026-08-21.
- For sections 2.2 and 2.3, complete the PoC by 2026-08-21, Rule and Skill development by 2026-08-28, the Quality assurance framework by 2026-09-04, and advancement by 2026-09-18.
- Display work as Gantt duration bars bounded by the provided start and completion targets; actual overlap and detailed dependency relationships may be adjusted during execution.

## Autonomous Verification Wording

- Remove the statement that verification intent and expert knowledge are accumulated to expand the area PROVE can perform independently.
- Separate the Test Scenario discussion from the autonomous-verification discussion in both the current limitations and the current direction.
- Keep Test Scenario generation as the first autonomy priority, followed by progressive connection to Test generation, real-Device execution, and result judgment.

## Document Structure

- Remove the standalone `현재 정리된 핵심 문장` section.
- Start numbered sections at 1 instead of 0 and add a table of contents.
- Retain `PROVE 원리와 Firenze 적용 방향` as the working title while the document continues to cover both subjects.

## Detailed Test Scenario Generation Strategy

- Extract Requirements from the project Specification and Test Scenarios from existing Test Packages.
- L1 through L7 Test Leveling has already been performed on extracted legacy Test Scenarios, and Requirement backtracing identified missing verification areas by Feature. The existing Level definitions will be provided later rather than newly invented in this document.
- Combine Requirement and Scenario extraction with Leveling and gap identification as one continuous analysis flow.
- Align sections 2.1 and 2.2 to the same three-stage structure: base generation method, deeper analysis, and Coverage or application validation, without removing their distinct content.
- Analyze Command, Reset, and other operation sequences as serial and parallel Graphs to extract verification-engineer know-how and candidate Scenario-generation rules.
- Track both Specification-function Coverage and Coverage of refined Scenario-generation rules such as Leveling, then add missing Scenarios alongside the operating Test Package.
- Generate FW-informed Scenarios from FW Code, FLAIR Docs, FTL policy, Confluence, and Device function, state, policy, and implementation information.
- Use AI to address the practical difficulty of engineers directly analyzing Feature-related FW Code and implementation information, pursuing White-box-level Scenarios that reflect internal Device implementation rather than only externally observable behavior.
- Stop and notify when ambiguous Specification language cannot be resolved through Device policy and implementation information.
- Consider deeper AI-assisted exploration of Verification Space areas identified as Risk, such as MFND Reset, using related FTL Code and documents.
- Validate the FW-informed strategy and its Coverage tracking through a PoC; the exact method is not yet decided.
- Use Rules, Skills, and Templates to help Space Area experts express experience-based verification knowledge that AI alone cannot currently generate.
- Improve the usability of those Rules, Skills, and Templates through verification-engineer feedback and active participation in real workflows.
- Compare PROVE-generated Scenarios and executable Scripts with overlapping human-authored Test Package assets, require preservation of existing verification intent, add newly identified gaps, and execute generated Scripts in the real environment.
- Exact Level definitions, comparison similarity, equivalence, and execution acceptance thresholds are not yet decided.

# Related Feedback

The same revision must answer:

- How Extra verification beyond an existing Specification and Test Package is identified and managed.
- How new project Specifications and incremental changes are reflected.
- What portion of Firenze SSD Verification PROVE will cover out of a defined 100.
- How the Verification Space itself is defined.
