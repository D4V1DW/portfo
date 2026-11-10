# PAF: Turning Ideas into Reliable Software with AI Agents

## A practical workbench for planning, coordinating and verifying multi-slice development

**Systems Atlas | Engineering case study | Editorial draft 0.3 | 10 November 2026**

**Project:** Personal AI Agent Framework (PAF)  
**Area:** AI-assisted engineering, developer tooling, specification, verification, autonomous workflows  
**Implementation:** Preserved Python 0.4.3 deterministic CLI; Markdown-native agent skills, SOPs, planning contract and knowledge base; Git/GitHub and Cursor as the execution environment  
**Evidence:** One formally documented end-to-end Circuit Lab pilot, a controlled synthetic evaluation, and qualitative experience using PAF across additional personal projects  
**Attribution:** Personal project directed through AI-assisted engineering. Exact individual implementation and architectural contribution wording awaits a later editorial review.

> **The central question:** How can a developer turn a complex product idea into a series of well-specified, reviewed and tested AI-assisted implementation slices, without manually coordinating every routine handoff?

### The opportunity: from fast coding to dependable delivery

AI coding agents can produce useful software at remarkable speed. I wanted to make that capability repeatable: start with an idea, work through its real product decisions, and then let a coding-agent workflow implement it in bounded stages while preserving the original intent.

The obstacle wasn't simply generating enough code. A new agent might not have the conversation that shaped a feature. A reviewer could challenge something the owner had deliberately specified. A test result could describe an old revision rather than the code about to merge. A task marked ready might be mistaken for permission to deploy or spend money.

PAF gives that process a practical structure. **Product decisions become durable contracts; agents get focused engineering guidance; implementation and review advance through explicit authority and evidence.** In my own development work, the planning contracts and multi-slice approach have become particularly valuable. They have made complex projects easier to coordinate without repeated explanation and manual handoffs.

### Begin upstream: turn discussion into a build contract

The most important part of the current framework happens *before* the coding agent starts.

PAF's planning contract turns a substantive product conversation into repository-owned source-of-truth documents. For a multi-feature application, these include an explicit product brief, user-visible requirements, technical interfaces, architectural decisions, dependency-aware work packages, an acceptance matrix, a short agent entrypoint and an owner-review readiness record.

The process distinguishes decisions already made from assumptions, unresolved material questions and reversible engineering choices. Requirements refer to observable behaviours and important negative cases. Task briefs reference those requirements instead of making up a second, sometimes contradictory specification. A fresh coding agent should be able to select the next authorised task from the repository without asking the owner to reconstruct the original conversation.

This is deliberately not a mandatory paperwork exercise for every initial idea. Exploration stays conversational. Formal planning begins when the user decides a project is worth implementing, and the documents are sized to the actual work.

### Give agents the right expertise at the right point

The current skills-first workbench is centred on **six native, on-demand agent skills**:

- **Plan and specify:** reconcile product decisions into implementable requirements, tasks and acceptance.
- **Coordinate an approved build:** check the finite grant, GitHub state and dependencies before progressing work.
- **Implement a vertical slice:** make one complete, bounded change with meaningful negative and regression tests.
- **Review and repair:** challenge the effective code diff against an agreed contract, not just the PR summary.
- **Diagnose and recover:** reconstruct the exact state of interrupted work before retrying or continuing.
- **Curate learning:** save genuinely reusable engineering lessons with provenance, applicability and limits.

Focused SOPs and a small knowledge index support those skills. An agent can retrieve a relevant technique for test selection, review, debugging or specification without loading a large generic prompt on every request.

PAF does not try to replace the developer's entire environment. **Cursor Projects supplies the running coordination. The target project owns its requirements. GitHub owns PR and merge evidence. PAF contributes the planning, skills, review principles and continuity discipline.** This distinction is central to why the newer workbench is easier to use.

### Keep the safeguards that software can verify

PAF originally began as a more formal, versioned, tool-neutral framework. The preserved **0.4.3** implementation includes a Python CLI with installation integrity, lifecycle/readiness, permission and evidence checks.

Those checks addressed genuine failure modes. A controlled stabilisation pass found that missing installation-lock information and blank or unsupported task states could bypass expected fail-closed behaviour; the code was repaired and given regression coverage. The subsequent synthetic comparison reported **ADOPT_FOR_CONTROLLED_USE** for its restricted local scope, including hard denials for selected held, privileged and stale-evidence cases.

The important design distinction is that a deterministic script can check structural facts but cannot invent human authorisation or pretend hosted CI ran. The original core retained value on those terms. It simply did not need to grow into a second universal orchestration platform.

### A useful simplification, not a change of ambition

As native agent tooling developed, PAF's direction shifted. Installation metadata, routers, context packs and formal task schemas had begun to occupy more of the maintenance surface than the everyday workflow needed.

The question became: **what genuinely helps a developer ship better work, and what should be left to existing tools?**

The answer was to preserve the useful deterministic core while making new development project-first and skills-led. An approved project plan, a finite execution grant, targeted review and a reliable handoff mattered more than building another daemon or task database. The framework could stay small while the projects built with it became larger.

That is the most important architectural evolution: *less framework machinery, more reusable engineering discipline*.

### In a substantial application: Birria Radar

The clearest illustration of PAF's practical use is not a standalone demonstration game. It is the ongoing development of **Birria Radar**, a real owner-facing lead-discovery application for a mobile catering business.

The product already existed. The engineering challenge was to integrate a more capable research and qualification process into the established FastAPI/SQLite application **without** disrupting the owner's existing data, evidence reviews or contact decisions.

The Discovery Integration programme was prepared through the PAF planning method. Twelve explicit requirements, each with acceptance and negative scenarios, were organised into four dependent work packages:

1. **DI-01 — Durable runs:** create and identify a research run before calling paid providers, enforce idempotency, reserve shared daily search and AI budgets, and avoid blindly repeating an uncertain chargeable call.
2. **DI-02 — Persistent candidate ledger:** retain acquired and deferred subjects beyond ephemeral research results, separate unknown from unsuitable, and preserve owner decisions and identity.
3. **DI-03 — Shared coordination:** unify manual and scheduled discovery under leases, existing quotas and backlog gates, with scheduling opt-in and no unauthorised spend.
4. **DI-04 — Owner decision flow:** surface a small daily review queue, protect Save/Dismiss state, check current publisher evidence and provide an unsent, owner-controlled contact handoff.

This decomposition mattered. Each slice established necessary foundations for the next, while the project-owned specification prevented a later implementation from treating a search hit as an approved opportunity or quietly sending an email.

The four corresponding implementation pull requests **#28–#31** were merged into the target repository. The final DI-04 record reported **445 passing local tests and six skipped**, with zero unresolved HIGH/MEDIUM findings in its recorded fresh review. It also documents specific review repairs: durable query-quantity reservations, safe treatment of ledger persistence failure and a current-source attestation check that does not trust stale approval flags.

The reported suite establishes significant local implementation and review coverage. It does **not** by itself establish hosted, real-provider or final owner acceptance. Those remained separate evidence tiers.

For me, this is the more revealing example of PAF: a substantial change to an existing product was converted from a broad intention into discrete, bounded engineering work with traceable decisions, coordinated implementation and review. It demonstrates the workflow at the scale that actually makes it useful.

### The dedicated end-to-end evaluation: Circuit Lab

Circuit Lab remains valuable, but for a different reason. It was the first deliberately documented end-to-end PAF pilot under a native Cursor Project coordinator, using six dependent development slices to build a browser game with twenty authored puzzles.

The final report recorded **237/237 unit tests**, **52/52 Chromium end-to-end tests**, a passing typecheck/build and executable solution witnesses for all twenty levels. A positive early owner playtest was reported, while full owner-only usability, phone, sound and screen-reader checks remained open.

That is a genuine, bounded verification milestone, not evidence that PAF alone caused a productivity gain. Cursor provided the active running coordinator and PAF supplied project-scoped contracts, skills and review practices. The pilot revealed practical issues that improved the workbench, including how to distinguish a reviewer preference from an actual specification defect and when a high-risk repair deserves fresh final-head review.

### Practical value across projects

The dedicated Circuit Lab evaluation and the Birria Radar integration are different kinds of evidence. Neither captures the full reason I continue to use the framework.

I've used PAF's planning contracts and multi-slice process on several other personal projects. **In day-to-day use, the approach has substantially streamlined the progression from an exploratory discussion to coherent implementation work.** It is particularly helpful when a project spans multiple dependent phases or sessions, or when the software must preserve operational safeguards while evolving quickly.

In AI Conversation Lab, for example, the repo contains PAF-derived project requirements, stage-specific tasks, an explicit human evaluation protocol and boundaries on external model spend. Later Birria Radar programmes use the same contract-driven approach for market discovery and proactive inventory. Those examples show wider method adoption; their planning documents are not proof that every proposed phase has been implemented or accepted.

This is practitioner evidence, not a benchmark or a percentage productivity claim. The significant point is that PAF has become a reusable working method rather than a framework created only to pass its own tests.

### Review and recovery in actual development

Reliability is most tangible when a review catches something consequential or a running programme encounters a difficult state.

**Birria Radar's paid-call boundary was hardened.** A high-risk review identified a weakness in the reservation of Serper query allowance. The resulting change made quantity reservation durable before provider calls and added interruption, restart and near-limit tests. The objective was not more process; it was to prevent an expensive ambiguity in production-shaped code.

**Persistent state was treated as an invariant.** The DI candidate-ledger review identified a path that could report a completed run despite ledger persistence failure. A bounded repair changed the outcome to partial/failed with an explicit reason, preserving the difference between known success and incomplete work.

**Evidence was tied to the current publisher.** DI-04 tightened the owner's source-attestation check so that an earlier approval flag could not promote a changed source route to verified status. The change preserved manual source review and unsent communication authority.

**Circuit Lab uncovered procedural improvement opportunities.** Fresh review identified real defects, including a saved-audio-preference issue, but one reviewer also incorrectly challenged a Level 6 mechanic already approved in the design contract. PAF's later review procedure distinguishes objective failures from preferences. It also calls for proportionate final-head inspection after risky repairs and discourages repetitive housekeeping PRs.

The important lesson is that the framework should improve engineering judgement and evidence without becoming a second product to maintain. Difficult findings should lead to smaller, sharper contracts and procedures, not automatically to more infrastructure.

### What the evidence establishes

PAF has several complementary forms of positive evidence:

- A controlled synthetic evaluation demonstrated specific fail-closed checks under restricted conditions, with an **ADOPT_FOR_CONTROLLED_USE** outcome.
- The dedicated Circuit Lab pilot demonstrated a six-slice implementation programme reaching a locally verified twenty-level application under native Cursor coordination.
- Birria Radar's four-slice Discovery Integration demonstrates substantial use of the planning-and-implementation method in an existing application, with recorded PRs, real review repairs and a 445-passing-test local report.
- Further personal projects demonstrate that the planning contract has become part of my ongoing engineering practice.

These are meaningful results, but different proof tiers. There is no controlled calculation of PAF's improvement relative to native Cursor alone, no verified percentage time saving, no general portability guarantee and no claim that local tests stand in for hosted or owner acceptance.

**Those distinctions limit the claims, not the practical utility of the framework.**

### What I've taken from it

The strongest lesson is that autonomy works better when the important decisions have somewhere durable to live.

The developer retains ownership of requirements and material decisions. The repository carries those choices forward. Skills supply relevant technical judgment. Deterministic tools verify what software can actually check. The agent host coordinates approved work. GitHub records what happened, including incomplete evidence.

PAF is useful because it lets me spend more time thinking about the product and less time acting as a relay between agents. Its evolution has been about **making ambitious AI-assisted engineering easier to direct, review and resume**.

### Systems Atlas: From intent to implementation

The portfolio exhibit follows **Birria Radar's Discovery Integration**, not the smaller Circuit Lab demonstration. A visitor can read it from top to bottom: define the real product problem, see how twelve requirements became four dependent work packages, select a slice to inspect the actual engineering change and review evidence, and finish with the boundaries of its reported verification.

A secondary, optional section explains the planning contracts, six native skills, project authority and deterministic safeguards. Circuit Lab is retained as the dedicated pilot alongside other evidence of practical framework use.

The interactive details are editorial reconstructions grounded in private repository records. They are not live agents, actual project telemetry or publicly exposed private source files.

---

## Editorial evidence and publication notes (remove from the public-facing article)

**Status:** v0.3 editorial draft, reviewed against the selected GitHub source documents on 10 November 2026. No new PAF test, paid agent run, Circuit Lab full owner acceptance or independent benchmarking was conducted for this revision.

**Primary private-source records:**
- [Birria Radar Discovery Integration programme](https://github.com/D4V1DW/birria-radar/blob/main/docs/programmes/discovery-integration/README.md), [twelve requirements](https://github.com/D4V1DW/birria-radar/blob/main/docs/programmes/discovery-integration/PRODUCT_SPEC.md), [acceptance matrix](https://github.com/D4V1DW/birria-radar/blob/main/docs/programmes/discovery-integration/ACCEPTANCE.md) and [build plan](https://github.com/D4V1DW/birria-radar/blob/main/docs/programmes/discovery-integration/BUILD_PLAN.md)
- Birria Radar implementation PRs [#28](https://github.com/D4V1DW/birria-radar/pull/28), [#29](https://github.com/D4V1DW/birria-radar/pull/29), [#30](https://github.com/D4V1DW/birria-radar/pull/30), [#31](https://github.com/D4V1DW/birria-radar/pull/31)
- [AI Conversation Lab planning readiness](https://github.com/D4V1DW/ai-conversation-lab/blob/main/docs/PLANNING_READINESS.md) and [Birria Radar market-discovery planning PR #40](https://github.com/D4V1DW/birria-radar/pull/40)
- [PAF README / implementation status](https://github.com/D4V1DW/agent-framework/blob/main/README.md)
- [Original PAF architecture/specification](https://github.com/D4V1DW/agent-framework/blob/main/PERSONAL_AI_AGENT_FRAMEWORK_SPEC.md)
- [Controlled evaluation results](https://github.com/D4V1DW/agent-framework/blob/main/docs/PAF-GOOD-ENOUGH-RESULTS.md) and [Pass A hardening PR #15](https://github.com/D4V1DW/agent-framework/pull/15)
- [Planning redesign PR #17](https://github.com/D4V1DW/agent-framework/pull/17), [skills-first implementation PR #19](https://github.com/D4V1DW/agent-framework/pull/19) and [post-pilot procedure revision PR #21](https://github.com/D4V1DW/agent-framework/pull/21)
- [Circuit Lab pilot retrospective](https://github.com/D4V1DW/agent-framework/blob/main/docs/vnext/CIRCUIT_LAB_PILOT_RETROSPECTIVE.md)
- [Circuit Lab build plan](https://github.com/D4V1DW/circuit-lab/blob/main/docs/BUILD_PLAN.md) and [final automated acceptance report](https://github.com/D4V1DW/circuit-lab/blob/1c5060b211fdeed660582965790992408502c43d/docs/MVP_ACCEPTANCE_REPORT.md)
- Circuit Lab development PRs [#3](https://github.com/D4V1DW/circuit-lab/pull/3), [#4](https://github.com/D4V1DW/circuit-lab/pull/4), [#5](https://github.com/D4V1DW/circuit-lab/pull/5), [#7](https://github.com/D4V1DW/circuit-lab/pull/7), [#9](https://github.com/D4V1DW/circuit-lab/pull/9), [#11](https://github.com/D4V1DW/circuit-lab/pull/11).

**For owner review before publication:** Confirm exact individual authorship/contribution framing; assess which details and screenshots are appropriate to disclose from private project repositories; verify later source status before public launch; remove this editorial appendix and any private-only links from the visitor-facing edition. The broader project's effectiveness is explicitly owner-reported, not a lab measurement.