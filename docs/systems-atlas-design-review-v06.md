# Systems Atlas — Revision 06: Inside an Autonomous Build

**Date:** 10 November 2026  
**Status:** Interactive design exploration for owner review. No production deployment or PAF execution authority.  
**Files:** `prototypes/systems-atlas-portfolio-v06.html`, `case-studies/paf/CASE_STUDY_DRAFT.md` (editorial v0.2)

## Owner direction driving the revision

- Systems Atlas v0.4 established an approved portfolio-first visual foundation.
- FTT is one case study, not the brand or purpose of the portfolio.
- PAF v0.5 Review Room was visually coherent but too shallow: it demonstrated three decisions rather than explaining the framework and a real end-to-end development journey.
- Owner reports meaningful ongoing PAF usage across additional personal projects, especially the planning contracts and multi-slice development workflow. The earlier case study over-emphasised shortcomings relative to this practical value.
- Owner approved a deeper **Inside an Autonomous Build** exhibit, a positive but evidence-disciplined editorial revision, and integration into the existing HTML.

## What v0.6 contains

The portfolio homepage, navigation, FTT customer/staff simulator, selected-work list, background and contact section remain intact. The second exhibit has been redesigned with **six navigable movements**:

1. **The idea:** Three product decisions show how the initial Circuit Lab concept becomes precise user-visible rules.
2. **The contract:** Choose one of three real requirements and trace it through the approved product contract, technical design, work package and negative/acceptance case. Direct links continue into the relevant workbench or owning development slice.
3. **The workbench:** Inspect six native skills. A four-boundary map distinguishes project authority, native Cursor execution, PAF skills/SOP/knowledge and GitHub evidence.
4. **The build:** Scrub the six real Circuit Lab implementation PRs and inspect capability changes, recorded tests, review evidence and a progressively elaborated **illustrative**, non-playable board. Requirements R-007, R-014 and R-016 jump to their owning slice.
5. **The review:** Investigate the CL-02 reviewer-versus-contract dispute and the CL-06 saved-audio defect. Reveal claim → contract/counterexample → outcome and learning, with evidence limits intact.
6. **The outcome:** Recorded test totals, acceptance limits, practical adoption beyond the formal pilot and an original-to-vNext architecture comparison.

The design uses progressive disclosure and an editorial dark-green technical canvas instead of a dense network diagram or generic animated agents. The underlying data is local, deterministic and self-contained. **Nothing invokes agents, connects to private GitHub or simulates fake production activity.**

## Evidence accuracy

Source checks used the private PAF and Circuit Lab repositories and their recorded PRs and acceptance report. The embedded summaries are paraphrased and do not reproduce private source code.

| Historical record | What the site shows | Boundary |
| --- | --- | --- |
| CL-01 PR #3 | 38 unit / 3 Chromium checks, 4 initial levels | PR-reported tests, not a new run |
| CL-02 PR #4 | 59 / 18, tee/receiver progression | Design-preference versus copy-defect distinction |
| CL-03 PR #5 | 95 / 24, switch/diode | PR-reported |
| CL-04 PR #7 | 126 / 28, AND/OR | Gate feedback negatives from test record |
| CL-05 PR #9 | 212 / 33, 20 levels | Owner walkthrough separately pending |
| CL-06 PR #11 | 237 / 52, saved state, sound/accessibility | HIGH repair tested; separate final-head risky-delta review not recorded |
| MVP verification PR #13 | 237/237 unit, 52/52 Chromium and 20 replayable witnesses | Owner-only acceptance still open in recorded report |
| PAF synthetic evaluation | `ADOPT_FOR_CONTROLLED_USE` for limited scope | Not hosted CI or a measured comparative performance win |
| Owner practitioner report | PAF contracts and multi-slice workflow useful across other personal projects | Qualitative, not a controlled benchmark |

The five-by-five progression board is a **conceptual illustration**, not a playable version or exact layout of Circuit Lab levels.

## Browser verification

Headless Chromium, reading self-contained HTML as page content, at **1440×900**, **820×1024**, **390×844**, **320×720**. At all four widths:

- Intent selection changes the requirement continuity thread.
- Requirement selector changes contract text, owning task, PR and evidence.
- Product/technical/task/acceptance views switch correctly.
- All six PAF skills reveal their proper input, output and authority boundaries.
- Six-slice timeline, next/previous, board and cumulative reported tests update.
- Two review incidents, claim/contract/outcome tabs and next-evidence control work.
- PAF evolution toggles, stage back/next, and selected-work PAF navigation work.
- Existing FTT normal order/confirmation, cross-venue denial and suspended-venue scenarios still work.
- No JavaScript page errors and **no page-level horizontal overflow**.

Additional 1440px, 390px and 320px direct-link tests verify that R-014 → CL-06 is preserved and visibly highlighted.

**Not yet checked:** full keyboard/screen-reader experience, Lighthouse/Core Web Vitals, real devices, Safari/Firefox, systematic contrast/WCAG audit, stress testing and production deployment. Automated checks do not constitute owner acceptance or full accessibility compliance.

## Editorial and release boundaries

- Revised case-study tone leads with actual practitioner value and clear documented implementation evidence.
- Exact personal authorship wording is still intentionally held for later, as agreed.
- PAF's private source links are editorial references only; public-facing copy must not pretend those are accessible proof to general visitors.
- No PAF repository changes, new costs, agent runs, permission changes, commercial claims or live deployments.
- v0.6 is a **standalone replacement candidate**, built on the archived v0.5 source. It does not require merging the earlier stacked v0.4/v0.5 prototype PRs. Those remain historical review branches and should be resolved separately after owner review.

## Proposed next design review

Judge v0.6 on whether a non-specialist can understand **what PAF does, how the project uses it and why it is valuable** in two minutes, while an engineer can choose to explore the contracts and evidence in greater depth. Polish navigation, transitions, case-study attribution, accessibility and performance **after** that conceptual test passes.