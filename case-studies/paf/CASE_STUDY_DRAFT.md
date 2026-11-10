# PAF: Turning Ideas into Reliable Software with AI Agents

## A practical workbench for planning, coordinating and verifying multi-slice development

**Systems Atlas | Engineering case study | Editorial draft 0.2 | 10 November 2026**

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

### One end-to-end pilot: Circuit Lab

The first formally documented end-to-end pilot was **Circuit Lab**, a small browser game where players rotate circuit components to route power to receivers.

The game had a defined twenty-level campaign, a pure TypeScript simulation engine, explicit rules for propagation and logic gates, negative test cases, and a dependency-aware build plan. PAF guidance was available in the target repo; a native Cursor Project acted as the running coordinator.

Across six merged implementation PRs, Circuit Lab progressed from its first four playable wire puzzles to branching and multiple receivers, switches, diodes, AND/OR gates, twenty authored levels, save-state handling, responsive layouts and opt-in sound.

The final reported automated checks were strong:

| Verified project measure | Recorded result |
| --- | ---: |
| Implemented and merged development slices | **6** |
| Authored levels, each with a solution witness | **20** |
| Unit tests passing | **237 / 237** |
| Chromium end-to-end tests passing | **52 / 52** |
| Typecheck and static build | **Passed** |

The owner reported a positive initial playtest. The final verification report nevertheless retained separate owner-only checks for a full twenty-level walkthrough, hint quality, screen-reader feel, narrow-phone appearance and sound. These automated results are not a commercial release or a completed human acceptance certificate.

This was a meaningful practical demonstration: a complete small product was developed through a reviewed, sequential programme rather than six unrelated agent prompts. It is **not** a controlled experiment showing that PAF alone caused the result; native Cursor provided the actual coordination.

### Value beyond the recorded game pilot

Circuit Lab is the one deliberately documented end-to-end PAF pilot, but it is not the only project where I have used the method.

I've since used PAF's planning contracts and multi-slice development approach on a number of other personal engineering projects. **In day-to-day use, it has substantially streamlined the progression from an agreed idea to coherent implementation work.** Instead of repeatedly reconstructing scope for every agent session, the project documents and implementation stages provide continuity.

That's an important part of the project's value, even though I haven't run a controlled multi-project comparison or calculated a reliable percentage speed-up. It is a practitioner assessment grounded in repeated use, not an invented benchmark.

### Learning from the real review process

The pilot also produced concrete lessons that improved the workbench.

**Review caught genuine defects.** Fresh-context review identified an off-board validation gap, a logic-route problem and a high-severity stored-audio-preference issue. Focused fixes and regression tests followed. Review demonstrated its practical worth by challenging actual behaviour, not by providing ceremony.

**Review was not always right.** One agent objected to repeating a branching mechanic in Level 6 even though the accepted design expressly required it. A separate instructional sentence misstated a receiver position and really did need correction. PAF's revised review policy now distinguishes an objective contract defect from an optional design preference, preventing unproductive escalation.

**The final changed code matters.** Certain high/medium-risk repairs passed tests without a separately recorded independent review of the new risky delta. The later procedure recommends inspecting the actual repaired head, the counterexample and affected tests, proportionately rather than re-reviewing everything after each small copy edit.

**Workflow overhead should be challenged.** Several administrative closeout PRs and stale entrypoint docs created avoidable noise. PAF now emphasises keeping one authoritative task ledger and reconciling current project documentation at sensible programme boundaries.

**Unobservable costs must remain unknown.** Actual token usage, model routing and PAF-specific cost overhead were not reliably available from GitHub. The method now asks for observable usage rather than inventing savings or attributing an approximate cost to the framework.

The response to each issue was a contained improvement to existing skills and SOPs, not a new infrastructure layer.

### What the evidence establishes

PAF has two complementary forms of documented positive evidence: a restricted synthetic evaluation demonstrating selected fail-closed checks, and a real six-slice application build demonstrating a functional project-first development workflow.

Beyond those records, I regard its planning and staged delivery method as highly valuable in my own work across projects. That experience is legitimate, but it is a different kind of evidence from a measured causal comparison.

It would be inaccurate to claim universal agent portability, a known PAF-versus-native-Cursor performance benefit, trustworthy hosted CI for the earlier evaluation, or precise cost savings. **Those are boundaries on the claims, not reasons to discount what the framework already enables.**

### What I've taken from it

The strongest lesson is that autonomy works better when the important decisions have somewhere durable to live.

The developer retains ownership of requirements and material decisions. The repository carries those choices forward. Skills supply relevant technical judgment. Deterministic tools verify what software can actually check. The agent host coordinates approved work. GitHub records what happened, including incomplete evidence.

PAF is useful because it lets me spend more time thinking about the product and less time acting as a relay between agents. Its evolution has been about **making ambitious AI-assisted engineering easier to direct, review and resume**.

### Systems Atlas: Inside an Autonomous Build

The accompanying interactive exhibit makes this workflow tangible rather than displaying a conventional agent-flow diagram.

Visitors begin with the original Circuit Lab idea, trace a real requirement into specifications and acceptance, inspect the workbench's skills and authority boundaries, travel through six documented implementation slices, and investigate the difference between a genuine defect and an unsupported review preference. The final stage exposes the reported results and their remaining limits.

The interactions are labelled documentary reconstructions and illustrative models. They do not execute live agents, expose private source code or claim to be runtime telemetry.

---

## Editorial evidence and publication notes (remove from the public-facing article)

**Status:** v0.2 editorial draft, reviewed against the selected GitHub source documents on 10 November 2026. No new PAF test, paid agent run, Circuit Lab full owner acceptance or independent benchmarking was conducted for this revision.

**Primary private-source records:**
- [PAF README / implementation status](https://github.com/D4V1DW/agent-framework/blob/main/README.md)
- [Original PAF architecture/specification](https://github.com/D4V1DW/agent-framework/blob/main/PERSONAL_AI_AGENT_FRAMEWORK_SPEC.md)
- [Controlled evaluation results](https://github.com/D4V1DW/agent-framework/blob/main/docs/PAF-GOOD-ENOUGH-RESULTS.md) and [Pass A hardening PR #15](https://github.com/D4V1DW/agent-framework/pull/15)
- [Planning redesign PR #17](https://github.com/D4V1DW/agent-framework/pull/17), [skills-first implementation PR #19](https://github.com/D4V1DW/agent-framework/pull/19) and [post-pilot procedure revision PR #21](https://github.com/D4V1DW/agent-framework/pull/21)
- [Circuit Lab pilot retrospective](https://github.com/D4V1DW/agent-framework/blob/main/docs/vnext/CIRCUIT_LAB_PILOT_RETROSPECTIVE.md)
- [Circuit Lab build plan](https://github.com/D4V1DW/circuit-lab/blob/main/docs/BUILD_PLAN.md) and [final automated acceptance report](https://github.com/D4V1DW/circuit-lab/blob/1c5060b211fdeed660582965790992408502c43d/docs/MVP_ACCEPTANCE_REPORT.md)
- Circuit Lab development PRs [#3](https://github.com/D4V1DW/circuit-lab/pull/3), [#4](https://github.com/D4V1DW/circuit-lab/pull/4), [#5](https://github.com/D4V1DW/circuit-lab/pull/5), [#7](https://github.com/D4V1DW/circuit-lab/pull/7), [#9](https://github.com/D4V1DW/circuit-lab/pull/9), [#11](https://github.com/D4V1DW/circuit-lab/pull/11).

**For owner review before publication:** Confirm exact individual authorship/contribution framing; assess which details and screenshots are appropriate to disclose from private project repositories; verify later source status before public launch; remove this editorial appendix and any private-only links from the visitor-facing edition. The broader project's effectiveness is explicitly owner-reported, not a lab measurement.