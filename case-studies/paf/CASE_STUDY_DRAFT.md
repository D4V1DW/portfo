# PAF: Engineering a More Reliable Way to Build Software with AI Agents

## From deterministic guardrails to a practical, project-first development workbench

**Systems Atlas | Engineering case study | Editorial draft 0.1 | 10 November 2026**

**Project:** Personal AI Agent Framework (PAF)  
**Area:** AI-assisted software engineering · agent workflows · specification and verification · developer tooling  
**Implementation:** Python standard-library CLI and tests (preserved v0.4.3); Markdown-native agent skills, engineering procedures and knowledge base (vNext); Git/GitHub and Cursor Projects as execution environment  
**Evidence level:** Controlled synthetic evaluation and an observed multi-PR pilot; no claim of measurable superiority over native Cursor, verified cross-agent portability or trusted hosted CI  
**Role/attribution:** Personal project directed through AI-assisted engineering. Exact personal implementation and architectural contribution wording requires owner review before public publication.

> **Central question:** How do you give coding agents enough autonomy to deliver useful software without making the developer repeatedly explain requirements, approve routine steps or trust unverified claims of completion?

### The problem was not generating code

AI coding agents made it possible for me to explore and build software much more quickly. But more generated code did not automatically mean more reliable engineering.

The recurring difficulty was continuity: carrying a product idea from a lengthy discussion into precise technical requirements, then into implementation, review and acceptance without losing important decisions along the way.

A new agent might not have the conversation that shaped a design. A reviewer could recommend a change that contradicted an already-approved requirement. A successful test run could be reported for a previous commit rather than the code actually being merged. And a task described as *ready* could be mistaken for authority to deploy, merge or spend money.

These are not primarily prompt-writing problems. They are problems of **authority, evidence and the handoff between human judgment and automated work**.

PAF began as an attempt to address them across independent projects.

### First approach: make the critical checks deterministic

The original framework, preserved as version **0.4.3**, used a Python command-line layer alongside repository policies, routing rules, context packs and versioned installation metadata.

The intention was to put repeatable checks in software rather than rely on an AI model to remember every constraint. Before an approved task could be considered executable, the tooling could inspect lifecycle state, installed-framework integrity, permissions and declared side effects. Evidence checks could distinguish a matching PR/head reference from an outdated one, and failed tests from successful ones.

The important distinction was between **structural verification** and **genuine authorisation**. A local script can establish that a task record is well formed and that a referenced commit matches. It cannot invent a human approval, prove a hosted CI run occurred or make a sensitive action safe simply because a model says it is.

A bounded stabilisation pass found and repaired concrete fail-open behaviours, including a deleted installation lock file and unsupported or blank task states being able to bypass the intended readiness constraints.

The controlled synthetic evaluation later reported the decision **ADOPT_FOR_CONTROLLED_USE**. Ordinary coding tasks succeeded under both native and PAF-assisted configurations. The PAF combination added explicit denial behaviour for selected held, privileged and stale-evidence cases.

That is a useful finding, but a narrow one. It did **not** establish that PAF made every coding agent more capable, faster or cheaper. Hosted CI was unavailable; the tests were local or synthetic; cross-client compatibility was not established. The framework had shown specific safeguards, not universal reliability.

### The uncomfortable question: had the framework become part of the problem?

As the original system grew, it accumulated the kind of machinery it was meant to avoid: installation rules, state contracts, routers, validation commands, context-pack distribution and ongoing maintenance obligations.

Meanwhile, the actual day-to-day need was clearer. I wanted to discuss an idea, decide what it should do, hand the implementation to coding agents and have the work progress through reviewed, tested increments without constant intervention.

Building a second orchestration platform would not necessarily improve that experience. Cursor already offered native agent and project coordination capabilities. PAF would be more useful if it supplied the **missing engineering discipline around those capabilities**, rather than attempted to replace them.

This led to a deliberate architectural change: preserve the working deterministic core, but move new development toward a lighter, skills-led workbench.

### Start before the coding agent starts

The key design decision was to move the most important handoff **upstream**.

Instead of expecting a new coding agent to reconstruct product decisions from a long chat, PAF's planning contract turns agreed decisions into repository-owned authority:

**Discovery conversation → reviewed product and technical specifications → bounded work packages → acceptance scenarios → separately authorised implementation.**

That does not mean turning every early idea into bureaucratic documents. Exploration remains conversational. Formal documentation begins when a project is ready to move into development.

The planning process distinguishes decisions the owner has made from assumptions, rejected alternatives and unresolved material questions. It defines user-visible behaviour, failure modes, permissions and boundaries before those choices are delegated to a coding agent.

The resulting project repository becomes the durable source of truth. Task briefs link to requirement IDs; tests link to expected behaviour; the build plan tracks dependencies and holds; the agent entrypoint tells a fresh worker where to look. A previous ChatGPT conversation should not be required to continue an approved task.

For cloud-based or project-first execution, required skills must actually be present in the target workspace. A reference to another private repository is not proof that an agent can read those files.

### A workbench built from six focused skills

The revised PAF workbench contains six native, on-demand skills:

| Skill | Responsibility |
| --- | --- |
| Plan and specify | Convert an agreed product idea into coherent requirements, tasks and verifiable acceptance |
| Coordinate an approved build | Select eligible work, respect dependency and permission boundaries, and advance only within a finite owner grant |
| Implement a vertical slice | Deliver a bounded change with meaningful tests, negative cases and evidence |
| Review and repair | Challenge the actual effective diff against requirements, including counterexamples and test quality |
| Diagnose and recover | Reconstruct reliable state after interruption or uncertain failure without dangerous blind retries |
| Curate learning | Capture a genuinely reusable lesson with provenance, limits and later retrieval |

These are supported by focused operating procedures and a small indexed engineering knowledge base.

The workbench is intentionally not another server, background daemon, AI gateway or task database. The host does the actual running. GitHub owns commits and PR state. The project owns its product requirements. PAF contributes procedures and context.

It also differentiates **one approved slice** from a **finite autonomous programme**. An agent can continue through authorised dependent tasks where the user has explicitly granted that authority, but a Markdown file alone cannot run tasks after the host has stopped.

### Testing it on a real build: Circuit Lab

The most useful evaluation was a separate, intentionally small browser game called **Circuit Lab**, built around rotating circuit components to route power through authored puzzles.

The project had a clear 20-level design, a pure simulation engine, negative cases and a dependency-aware build plan. A native Cursor Project acted as the coordinator, with project-scoped PAF guidance available to the implementation and review process.

Across six dependent implementation PRs, the project progressed from four playable levels to a 20-level catalogue, branching circuits, switches, diodes, logic gates, progress persistence, keyboard interaction, narrow-screen layout and opt-in sound.

The final documented automated verification reported:

- **6** merged implementation PRs;
- **20** authored levels with executable solution witnesses;
- **237/237** passing unit tests;
- **52/52** passing Chromium end-to-end tests;
- passing typecheck and static build.

Those are observed project results, not a controlled experiment proving PAF caused them. Native Cursor Projects provided the running coordinator. The individual effects of the PAF skills, automatic skill invocation and comparative development cost were not isolated. The owner reported a positive quick playtest, while full 20-level, screen-reader, phone and sound acceptance remained separately open in the final report.

### The best findings came from things that went wrong

The pilot was more informative because it was not frictionless.

**Review found real defects.** Fresh-context review identified an off-board validation gap, a logic-route design problem and a high-severity saved-audio-preference issue. Focused corrections and regression tests followed. This was evidence that independent challenges could find useful problems, not a claim that review was infallible.

**Review also overreached.** One reviewer repeatedly treated an approved Level 6 design as defective because it reused a branching mechanic from Level 5. The actual written contract allowed that design. A separate piece of level-introduction text was genuinely wrong. The distinction mattered: an agent's design preference should not become a blocking requirement simply because it arrives in a review.

**The final commit matters.** Some repaired medium- and high-severity changes passed tests without a separate final-head review of the risky delta. A green affected suite is not the same thing as a fresh reviewer inspecting the code that will be merged.

**Documentation can become overhead.** The build generated several documentation-only closeout PRs, and some entrypoint files still described earlier planning states after the implementation was merged. Process documentation needs to stay aligned with actual GitHub state, without becoming a second project to maintain.

**Costs were not observable.** The pilot appeared to use more of the chosen low-cost model than expected, but GitHub history could not establish token spend, model routing or cost attributable to PAF. The correct result was **unknown**, not an invented efficiency claim.

These findings prompted narrow policy changes: require contract-grounded review findings, use risk-proportional final-head re-review, avoid repetitive administrative PRs, reconcile project state at programme end and account only for model usage the host actually exposes.

### What PAF proved, and what it did not

PAF has evidence of useful deterministic safety checks and a working skills-led process exercised in a real project. It also demonstrates that a native coordinator can progress through multiple dependent PRs when the plan and owner permissions are explicit.

But important limits remain. The controlled comparison did not quantify a performance or cost improvement over native Cursor. Hosted CI was not available for the framework validation. Cross-tool behaviour with other agents was not established. Automatic skill invocation was not proven in all workspace configurations, and future-agent compliance with the revised review procedures has not been behaviourally regression-tested.

The strongest conclusion is therefore deliberately bounded: **a controlled, useful engineering workbench with observed benefits and known gaps**, not a universal autonomous development platform.

### What I learned

The most important design lesson was that **more autonomy does not mean fewer boundaries**.

It means moving decisions to the right place. The human defines material product and operational authority. The project repository preserves that authority. Deterministic tools check what can be checked mechanically. AI agents perform implementation and judgment-intensive review. The running host provides coordination. GitHub provides the observable record of what happened.

A second lesson was to avoid confusing process with progress. A framework can be internally consistent while consuming more time than it saves. A reviewer can be diligent yet wrong. A test suite can be green while an external acceptance step remains undone.

The next stage of maturity is not necessarily another framework feature. It is learning, through further real development, which pieces meaningfully improve outcomes and which should be removed.

### Systems Atlas: the exhibit opportunity

The portfolio experience should not present PAF as six boxes connected by arrows.

A stronger interactive exhibit would let visitors investigate a **recorded development episode**: the approved task contract, a PR's actual changes, a review finding, the counterexample, the repair and the remaining acceptance boundary.

A particularly revealing moment would contrast two findings: a genuine high-severity defect that deserves a repair, and a plausible-sounding design preference that conflicts with the accepted spec. The visitor could inspect the evidence and see why the correct decisions differ.

This would make the core idea tangible: the value is not that AI can produce code, but that complex AI-assisted work can be **directed, challenged and verified without pretending uncertainty has disappeared**.

---

## Editorial evidence and publication notes (remove from public-facing article)

**Status:** Draft case study, prepared through read-only GitHub review on 10 November 2026. No new framework test, live Cursor agent run or Circuit Lab acceptance was performed as part of this writing.

**Primary source records** (most source repositories are private; these links are for authorised editorial verification, not public proof):
- [PAF root README](https://github.com/D4V1DW/agent-framework/blob/main/README.md)
- [PAF initial architecture/specification](https://github.com/D4V1DW/agent-framework/blob/main/PERSONAL_AI_AGENT_FRAMEWORK_SPEC.md)
- [Good-enough evaluation and limitations](https://github.com/D4V1DW/agent-framework/blob/main/docs/PAF-GOOD-ENOUGH-RESULTS.md)
- [Pass A deterministic hardening PR #15](https://github.com/D4V1DW/agent-framework/pull/15)
- [Planning redesign PR #17](https://github.com/D4V1DW/agent-framework/pull/17)
- [Skill-first implementation PR #19](https://github.com/D4V1DW/agent-framework/pull/19)
- [Host validation report](https://github.com/D4V1DW/agent-framework/blob/main/docs/vnext/HOST_VALIDATION.md)
- [PAF native skills](https://github.com/D4V1DW/agent-framework/tree/main/.agents/skills)
- [Circuit Lab pilot retrospective](https://github.com/D4V1DW/agent-framework/blob/main/docs/vnext/CIRCUIT_LAB_PILOT_RETROSPECTIVE.md)
- [Policy refinement PR #21](https://github.com/D4V1DW/agent-framework/pull/21)
- [Circuit Lab task ledger](https://github.com/D4V1DW/circuit-lab/blob/main/docs/BUILD_PLAN.md)
- [Circuit Lab MVP verification report](https://github.com/D4V1DW/circuit-lab/blob/1c5060b211fdeed660582965790992408502c43d/docs/MVP_ACCEPTANCE_REPORT.md)
- Circuit Lab implementation PRs [#3](https://github.com/D4V1DW/circuit-lab/pull/3), [#4](https://github.com/D4V1DW/circuit-lab/pull/4), [#5](https://github.com/D4V1DW/circuit-lab/pull/5), [#7](https://github.com/D4V1DW/circuit-lab/pull/7), [#9](https://github.com/D4V1DW/circuit-lab/pull/9), [#11](https://github.com/D4V1DW/circuit-lab/pull/11).

**Before publication:**
1. Confirm precise personal contribution and whether first-person role language is appropriate; no claim that all source was hand-written.
2. Decide which terms, screenshots and specific numbers from private projects are appropriate to disclose; avoid publishing private source, credentials, internal paths or proprietary work.
3. Confirm current pilot/host evidence if subsequent agent-framework work adds materially different proof.
4. Remove editorial notes and private source links, or replace with public-safe evidence.
5. Make sure any interactive demonstration uses labelled, curated historical evidence or synthetic reconstructions; do not imply it is a live running autonomous agent or independent review where it is not.
