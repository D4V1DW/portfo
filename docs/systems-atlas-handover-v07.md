# Systems Atlas — handover after v0.7

**Scope:** Interactive personal engineering portfolio for David Willsher, *not* a marketing site for any one product.

## Current design

- **Global look:** approved Systems Atlas editorial/architectural language (warm off-white, forest green, copper, display serif and technical details). Portfolio-first hero and selected-work overview remain.
- **FTT:** customer/staff synthetic simulator plus evidence-grounded long-form engineering story. No live production integration and not an FTT replacement site.
- **PAF:** v0.7 replaces the confusing v0.6 six-stage Circuit Lab journey. It is a linear case-study exhibit based on the substantial **Birria Radar Discovery Integration** programme. One clear interactive explorer reveals DI-01–04 architectural decisions and verification. Supporting optional details explain planning, skills, authority, recovery, and test boundaries.
- **Other projects:** AXIOM and Birria Radar have homepage previews but not yet full standalone exhibits. Birria Radar appears in the PAF chapter as proof of the development process; any future *separate Birria Radar case study* should explain the product and research/evidence workflow, not repeat the PAF story.

## GitHub and publication state

The owner has merged the previous v0.6 design PR #5 into `D4V1DW/portfo` main. The v0.7 replacement is proposed on a separate draft branch and should not automatically be merged or deployed. The public repo's source file visibility is not evidence of an actual site launch.

## Evidence rules

- **PAF value:** user strongly reports practical use and substantially easier multi-slice development across projects. This is legitimate qualitative practitioner experience, not a formal speed comparison.
- **Flagship:** Birria Radar DI planning PR #27 and implementation PRs #28–#31, all merged; 12 requirements; 4 work packages; final recorded DI-04 local suite 445 passed/6 skipped, fresh review 0 HIGH/MEDIUM outstanding. Do not equate local tests with hosted/provider/owner acceptance.
- **Circuit Lab:** first dedicated end-to-end pilot (6 merged PRs, 20 authored levels, 237 unit + 52 Chromium passed), now supporting evidence not main exhibit; no measured PAF-versus-native-Cursor advantage.
- **Workflow:** native Cursor Projects can coordinate when actually available. PAF provides planning contracts, project skills, SOP/knowledge and context; no PAF daemon. Project and owner authorities remain higher priority.
- **Sensitive material:** no confidential source, secrets, employer intellectual property or private user data on public website.

## Before further additions

1. Get owner review on v0.7 navigation and PAF narrative before another feature/exhibit.
2. Review case-study attribution (deferred by agreement) and update internal evidence references as needed.
3. Validate accessibility, keyboard/screen readers, responsive devices, performance and production hosting in a later explicitly scoped development programme.
4. Once PAF is approved, consider AXIOM as the next distinctly interactive case study.

## Relevant current files

- `prototypes/systems-atlas-portfolio-v07.html` — self-contained design prototype.
- `case-studies/paf/CASE_STUDY_DRAFT.md` — editorial v0.3.
- `docs/systems-atlas-design-review-v07.md` — evidence, verification and limitations.
- `docs/systems-atlas-handover-v07.md` — this file.