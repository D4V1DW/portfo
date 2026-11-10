# Systems Atlas — Approved Creative Direction and First Design Probe

**Date:** 10 November 2026  
**State:** Systems Atlas visual direction **approved by owner**; concept design probe, **not** approved PAF implementation plan.  
**Companion artifact:** `systems_atlas_direction_01.html` (self-contained browser-based art-direction prototype, no build or dependencies).

## 1. The concept

**Systems Atlas** is an interactive engineering exhibition with editorial narrative and inspectable technical systems. Visitors can skim the work in under a minute or examine deeper decisions, simulations, real-world verification and limitations. The site is a distinct showcase of creative technical direction and AI-assisted delivery.

Central principle: **Make the complex legible.**

The visual language combines architectural diagrams with high-end editorial typography, warm mineral paper, mineral/sage green, charcoal and restrained copper accents. Avoid templated AI gradients, glass cards, gratuitous 3D, particle fields and a chatbot-centric homepage.

**Possible hero proposition (creative copy, not final personal brand):** “Ideas are easy. Systems are the work.”

## 2. First concrete design decisions

| Dimension | Direction | Why |
|---|---|---|
| Information architecture | Home → Selected work → individual exhibits → professional experience/method/colophon | Clarity for employers while supporting exploration |
| Primary interaction | An authored story transforms into a systems diagram and inspectable state trace | The interaction explains architecture rather than decorating it |
| Default mode | Readable editorial narrative without interaction | Recruiter-friendly and accessible |
| Optional mode | Deep architecture and deterministic visual scenarios | Engineers can inspect decisions and boundaries |
| Visual structure | Fine rules, reference-plate labels, bespoke SVG diagrams, editorial typography | Distinctive yet credible for applied AI/solutions |
| Motion | Spatial continuity and state transitions; reduced-motion equivalents | Purposeful rather than spectacle |
| Technology in concept probe | Dependency-free HTML/CSS/JS and SVG | Rapid art-direction validation; **not** a committed production stack |
| First featured project | For The Table | Best-established end-to-end technical delivery evidence |
| Birria Radar | Small honest preview; full exhibit after current development stabilises | No stale case study claims |
| Employer-owned work | High-level professional description, subject to publication and confidentiality review | Avoid accidental disclosure |

## 3. Companion concept prototype: what is and isn't implemented

The HTML file demonstrates an illustrative art direction and two screen classes:

1. **Landing**: professional identity, distinctive thesis, abstract original architectural drawing and a direct route to the first exhibit.
2. **For The Table**: editorial project introduction, 2D system schematic, a *manual step-through* synthetic order path, technical inspector and repository-recorded claim boundaries.

The simulation is deliberately deterministic and manual. It requires no real model, no FTT credentials, no external network calls and no project data. It illustrates the public-safe conceptual architecture: React UI → tenant-aware Node API → shared PostgreSQL → staff-facing order state. A simulated tenant boundary is **not** evidence that the real API is secure.

This is a **creative design probe**, not a portfolio MVP, live product integration, verified performance demonstration, accessibility certification or PAF coding run.

## 4. First FTT case study editorial spine

- **The problem:** Single-venue ordering looks simple; repeatable SaaS operation makes tenancy, permissions and operational lifecycle central.
- **The choice:** Shared application/API/database with venue-scoped boundaries; no custom infrastructure per venue.
- **The customer experience:** Venue entry, table selection, browse, order, status convergence.
- **The operations experience:** Staff fulfilment, status progression and lifecycle management.
- **The inspectable system:** Component map + deterministic event trace + one negative/boundary scenario, developed after technical fact-checking.
- **The evidence:** Hosted synthetic rehearsal accepted; source date and exact known SHA; accessible explanatory summary for viewers without private GitHub access.
- **The limits:** No commercial customer launch or traction claim. External email, offboarding, legal/commercial and remaining acceptance gates presented separately.
- **The lesson:** Translation from hospitality workflow to multi-tenant architecture and operations.

## 5. Quality requirements for the eventual build

The **build acceptance criteria** will be formalised separately using the current PAF planning contract. Proposed quality aims:

- Responsive at narrow mobile sizes, keyboard usable, meaningful text alternative to each interactive diagram, reduced-motion support, and tested with representative assistive technology.
- Story usable without animation; important material accessible even when scripts are disabled.
- Synthetic versus real evidence unambiguously labelled.
- Static-first delivery, with only essential interaction JavaScript and minimal tracking; measured performance and test provenance rather than fabricated metrics.
- True authored design with careful motion, typography and responsive behaviour. Advanced rendering only when it adds demonstrable comprehension.
- Attribution transparent about AI-assisted implementation and human direction/technical decisions.

## 6. First milestone and what comes after

**Design acceptance gate:** owner reviews the landing and FTT simulation, decides whether the design feels distinctive and professional, and notes material changes to voice, palette, complexity and interaction.

**Next after design acceptance:** inspect current portfolio repo, read the latest `planning/PLANNING_CONTRACT.md` at that time, create a documentation-only planning package in the chosen project repository and request a separate implementation approval. Do not treat acceptance of this creative direction as blanket authority to deploy a website or mutate source repositories.

**Implementation milestone, once approved:** polished public homepage, clear professional experience/about, complete evidence-backed FTT case study, accessible interactive FTT trace, work index for other projects, site engineering colophon, cross-device verification and deployment.

## 7. Decision ledger

- `DECIDED`: Systems Atlas is the parent visual/metaphorical language.
- `DECIDED`: Operations Theatre-style simulation appears only within relevant exhibits.
- `DECIDED`: First complete exhibit is For The Table.
- `DECIDED`: Birria Radar continues independently; revisit its exhibit after active development settles.
- `DECIDED`: No company-confidential product details without approval.
- `TECHNICAL_DEFAULT`: Prefer static-first content architecture, candidate Astro/MDX with React islands, to evaluate during formal planning.
- `OPEN_MATERIAL`: Owner reaction to this first actual design probe and choice of eventual target repository/domain.
- `OPEN_EVIDENCE`: Fresh FTT demo capture, screenshots with synthetic data, source verification for system-level details.
- `DEFERRED`: Full 3D/WebGPU, persistent site backend, generative chat, live connected simulation, other full case studies.

## Sources reviewed

- `D4V1DW/agent-framework/planning/PLANNING_CONTRACT.md`, read 10 November 2026.
- `D4V1DW/OrderApp/README.md` and `docs/pubflow/RELEASE_READINESS_BOARD.md`, read 10 November 2026.
- `D4V1DW/portfo/README.md`, read 10 November 2026.
- Creative brief `interactive_portfolio_creative_brief_v01.md` from prior design exploration.