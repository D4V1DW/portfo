# Systems Atlas — Portfolio Revision 04

**Date:** 10 November 2026  
**State:** Interactive design prototype. Not production code, not a complete case study, not a PAF build grant.  
**Companion:** `systems_atlas_portfolio_v04.html`

## Purpose of this revision

Bring the site back to its intended identity: **David Willsher's personal engineering portfolio**, rather than a For The Table marketing or technical-support site. Use the newly drafted For The Table case study to make its first exhibit substantive without letting that project dictate the entire site's visual structure.

## Design decisions

- **Portfolio-first opening.** Introduces professional identity and technical approach before project content. The central atlas previews four different disciplines; no project is selected by default.
- **Distinct, non-templated visual language.** Retains the accepted mineral-paper/forest/serif typography and architectural-grid art direction. No external assets, CDN fonts, AI-brand gradient or generic glass cards.
- **Clear content hierarchy.** Perspective → Selected work → Engineering approach → FTT case study → Professional experience → Contact.
- **FTT as a contained exhibit.** The case study's business constraints, tenure boundaries and release evidence are reflected in concise editorial chapters. It remains one project among four.
- **Flowchart replaced with concrete interaction.** Rather than a crowded 11-node diagram, a synthetic customer phone and staff device show the experience, a central order object shows state, and a reversible reveal presents three essential engineering boundaries.
- **Causal scenarios.** Visitors can submit a synthetic order and have staff confirm it, attempt a blocked cross-venue request, or try ordering from a suspended venue. These are deterministic illustrations, **not** network calls, security tests or telemetry.
- **Evidence honesty.** The public case study differentiates a documented hosted synthetic rehearsal from a commercial launch, and labels what remains unproven.
- **Other projects receive appropriate weight.** AXIOM and PAF are previewed, and Birria Radar is explicitly in ongoing development. Detailed exhibits will be authored when grounded case studies exist.

## Verified in this prototype

Using headless Chromium with HTML loaded directly into the browser document, the following passed at widths **1440, 820, 390 and 320 CSS pixels**:

- Atlas project selection updates the preview title.
- Selected-work expansion reveals the correct project detail.
- Synthetic normal order: submit → staff queue populated → staff confirmation → customer confirmed.
- Cross-venue attempt: simulated denial; no staff order created.
- Suspended venue: simulated ordering unavailable; no staff order created.
- Reversible architecture reveal updates its expanded state.
- No runtime JavaScript exceptions during these interactions.
- No page-level horizontal overflow.

**Not tested/claimed:** Actual product integrations, production hosting, Web Vitals, third-party accessibility audit, screen reader behaviour, all browsers, multi-session order persistence, SEO implementation, or performance on low-end devices. The interactions are deliberately client-only.

## Deliberate limitations and next design challenge

This is a much stronger **portfolio frame and first chapter**, but not the final aspirational immersive experience. The spatial transition from customer experience into system infrastructure remains a major creative challenge. Today the architecture reveal unfolds another panel; later experiments should evaluate 2.5D or advanced rendering only if they measurably improve comprehension. A compelling story has more value than decorative rendering complexity.

The full FTT case-study document remains the editorial source. The HTML prototype uses selected elements, not a complete publication-ready narrative. The exact personal attribution is still for owner review.

## GitHub handling

Safe to place in the existing **public draft branch** of `D4V1DW/portfo` because this document and HTML contain no company-owned source code, credentials or customer records. Remain **draft/unmerged**. No portfolio deployment or production FTT mutation. Preserve earlier HTML and Markdown probes as an archive.

## Next practical design gate

Review the homepage, the balance between projects, the work index, and whether the FTT interaction is comprehensible and visually calmer. Only after the overall direction is accepted should the project move to formal PAF specification and a staged implementation programme.