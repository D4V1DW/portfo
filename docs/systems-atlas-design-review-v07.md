# Systems Atlas — Design revision 0.7

**Date:** 10 November 2026  
**Status:** Review draft, not an approved public website  
**Prototype:** [`systems-atlas-portfolio-v07.html`](../prototypes/systems-atlas-portfolio-v07.html)  
**Case study:** [`case-studies/paf/CASE_STUDY_DRAFT.md`](../case-studies/paf/CASE_STUDY_DRAFT.md) (editorial 0.3)

## Why this replaces the previous PAF exhibit

The owner liked v0.6's visual ambition but found it **confusing to navigate** and felt its reliance on Circuit Lab undersold what the Personal AI Agent Framework (PAF) can actually do. v0.6 required visitors to learn six unfamiliar navigation stages, inspect multiple document representations and then infer the practical value. The game was a valid first dedicated end-to-end pilot, but it was too small to communicate the value of PAF's planning and coordination method on substantive applications.

The replacement is **readable in one natural scroll**: define a problem, plan dependent work, explore implementation, verify outcomes. There is one interactive work-package explorer; everything else is readable content with optional native HTML `<details>` for technical visitors.

## New evidence-led flagship: Birria Radar Discovery Integration

PAF planning contract generated a reviewable DI-01–DI-04 programme for an existing FastAPI, SQLite and server-rendered mobile-first app. The [programme requirement matrix](https://github.com/D4V1DW/birria-radar/blob/main/docs/programmes/discovery-integration/ACCEPTANCE.md) maps **DI-R01–DI-R12** to tasks and positive/negative cases. [Planning PR #27](https://github.com/D4V1DW/birria-radar/pull/27) was documentation-only, not a permission grant.

Four implementation PRs were subsequently merged:

- [#28 / DI-01](https://github.com/D4V1DW/birria-radar/pull/28): durable run lifecycle, request idempotency, reserve-before-charge, shared Serper/AI allowances; review found and repaired a high-risk paid-budget boundary issue.
- [#29 / DI-02](https://github.com/D4V1DW/birria-radar/pull/29): durable acquired/deferred candidate ledger, persistence-failure repair and owner-state preservation.
- [#30 / DI-03](https://github.com/D4V1DW/birria-radar/pull/30): coordinated manual/scheduled discovery, leases and shared quotas; reviewer identified high-risk allowance issue that was repaired.
- [#31 / DI-04](https://github.com/D4V1DW/birria-radar/pull/31): daily owner queue, source attestation/verified application boundary and unsent Compose handoff; stale attestation logic repaired.

PR #31 reports the combined **445 passing, 6 skipped** local test suite and a final fresh review with **0 HIGH/MEDIUM unresolved**. That is not a hosted provider pilot or owner product acceptance. Do not present it as a measured productivity improvement over native Cursor.

Additional evidence of the approach's broader utility is project use of PAF planning in [AI Conversation Lab](https://github.com/D4V1DW/ai-conversation-lab/blob/main/docs/PLANNING_READINESS.md) and other Birria Radar programmes. **Owner reports substantial practical workflow value**; do not invent percentage time savings. Circuit Lab remains the first deliberately controlled end-to-end PAF run, demoted to a supporting evidence card rather than the main story.

## Information architecture of PAF exhibit

1. **Promise / project context.** Lead with the workbench's practical value and an existing application's Discovery Integration, not six skill names or a game.
2. **Define.** The product problem and three non-negotiable semantics: durable candidate lineage, spend safety, no unapproved outreach.
3. **Plan.** Four dependent slices drawn from twelve requirements. Readable as a simple list, without additional controls.
4. **Build.** One interactive four-tab explorer. It updates a restrained architectural layer model and a matching evidence-rich detail card. Previous/next buttons are optional alternatives; tabs are normal focusable buttons.
5. **Verify.** Separate local test/review proof from hosted/provider/owner acceptance. Three optional incident disclosures show why the constraints matter.
6. **Under the hood.** Optional, native disclosure sections for planning contracts, skills, authority, deterministic safeguards and recovery.
7. **Beyond the example.** Show other relevant personal projects, with Circuit Lab as dedicated pilot, not proof of PAF causal speedup.

**Navigation principle:** no six-stage application inside the portfolio; no hidden primary content. The page itself is the route.

## Source / public safety

The portfolio repo is public, while the source engineering repositories may be private. The exhibit contains **only short editorial paraphrases, locally modelled graphics and recorded aggregate test evidence**. It must not embed private source/diffs, raw project/customer data, secrets, local machine paths or real API integrations. Claims derived from private source need owner approval before actual publication. User contribution wording remains owner-review pending.

## Browser verification

Headless Chromium through Playwright `page.set_content` using the standalone HTML. Viewports **1440, 820, 390 and 320 CSS px**, reduced-motion preference active.

At each viewport:
- Selected DI-01, DI-02, DI-03, DI-04 and verified corresponding PR labels, `aria-pressed` state, system-layer highlight and evidence.
- Verified previous/next and end-of-list disabled state.
- Expanded the first verification and first under-the-hood disclosure.
- Checked no page-level horizontal overflow and no page JavaScript exceptions.
- Saved comparison screenshots of the project context and the build explorer.

At 1440px: verified portfolio atlas PAF selection and the inherited FTT order → staff confirmation scenario still works.

**Not performed:** a complete WCAG audit, automated axe-core analysis, full keyboard-only traversal, NVDA/VoiceOver, browsers other than Chromium, live provider tests, production deployment, performance budget, or independent code/security review. These remain future productisation gates, not claims of completion.

## Acceptance and next step

This is a reviewable, substantially simpler creative replacement for v0.6. Owner should check whether Birria Radar now demonstrates the real scale and usefulness of PAF, and whether the optional architecture depth feels sufficient without dominating the story. Do not merge or deploy until that review. Retain prior v0.4–v0.6 for design history; avoid stacking new features on obsolete PAF navigation.