# Systems Atlas — PAF interactive exhibit concept

**Date:** 10 November 2026  
**Status:** Editorial / interaction design notes only; no build authority  
**Case-study source:** [PAF case study draft](CASE_STUDY_DRAFT.md)

## Portfolio role

FTT demonstrates product architecture and a customer-to-operational flow. PAF should demonstrate **engineering judgement about AI-assisted development**. The exhibit must therefore look and behave **differently** from the FTT customer/staff simulator. It must not become a generic agent flowchart, live chatbot, fake agent control dashboard or animation of six skill names.

## Signature experience: The Review Room

A visitor is placed in the decision seat at a specific recorded development handoff.

**Scene 1 — The contract**  
Present a compact, beautifully typeset acceptance fragment: a proposed feature, precise requirement, and what the owner has approved. Show a small, real-scenario-inspired preview of a puzzle board. One click reveals how a requirement maps to implementation and negative tests.

**Scene 2 — A disputed review**  
A reviewer flags the repeated tee/branching pattern in Circuit Lab Level 6 as an alleged defect. The visitor can compare the accepted design contract with the concern, then select an interpretation. The exhibit shows why this objection is a **design preference** and should not block authorised work. Separately reveal the real level-introduction copy error that *did* need correction.

**Scene 3 — A genuine defect**  
Switch to the stored-audio-preference issue from the CL-06 review. Show the expected versus problematic behaviour, a minimal counterexample and the recorded repair with relevant tests. Avoid fabricated line-by-line diffs; use curated non-secret excerpts or synthetic reconstructions clearly labelled.

**Scene 4 — Trust the actual head**  
After the repair, move the PR head marker. Show what changed: the tests cover the new code, but the earlier review was of a different SHA. Explain the remaining proof gap and the later policy change requiring risk-proportional final-head review of the risky delta.

**Scene 5 — The bounded outcome**  
End with the observable Circuit Lab deliverables, plus the outstanding owner acceptance and unknown model cost. Explain that Cursor provided the native running coordinator; PAF supplied skills, project contracts and review policy. A visitor can optionally open "Why the framework got smaller" to compare early v0.4.3 safeguards with the vNext approach.

## Visual language

- Preserve the Systems Atlas editorial foundation: quiet off-white/mineral palette, strong display typography, disciplined spacing and fine-grained technical details.
- Use **large, legible evidence cards**, an unfolding reading surface and elegantly animated comparison states. Do not render a dense network of connected boxes.
- Avoid fake terminal output, superficial text typing effects, random agent avatars and fabricated "live" cost or review statistics.
- Desktop may show contract and finding side by side; mobile should use one focused pane at a time.
- The interaction must remain understandable with keyboard, reduced motion and no animation. Important labels and evidence never depend only on colour.

## Content and evidence requirements

| Exhibit moment | Grounded public-safe source | Claim to avoid |
| --- | --- | --- |
| Approved level design versus reviewer preference | Circuit Lab CL-02 PR #4 and PAF retrospective | That every reviewer finding was objective |
| Audio preference defect and fix | Circuit Lab CL-06 PR #11 | That tests alone prove a separate final-head review |
| Whole pilot outcome | Circuit Lab MVP acceptance report PR #13 | That owner acceptance or deployment was completed |
| Safety layer motivation | PAF controlled results / PR #15 | That PAF broadly outperformed native Cursor |
| vNext planning/skills | PAF PRs #17/#19/#21 | That Markdown is a running daemon or automatic host enforcement |

The repository records supporting these examples are private. Before creating public exhibit content, extract only agreed non-sensitive factual excerpts or make appropriately labelled synthetic recreations. Do not embed private source files in the portfolio or rely on private GitHub links as visitor evidence.

## Revision v0.5 design target

Build **one outstanding interactive episode**, not an entire theatrical agent simulator. The preferred first slice is the contrast between **reviewer preference and actual contract defect**, because it is unusual, understandable to a non-specialist, and central to the story. If it works well, add genuine defect repair and final-head evidence.

## Open editorial decision

Exact personal contribution/attribution will be reviewed later, as with the FTT case study. Do not write claims about manual coding, agent model choice or autonomy duration without evidence.
