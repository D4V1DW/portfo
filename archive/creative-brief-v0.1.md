# Interactive Engineering Portfolio
## Creative direction and For The Table exhibit brief | v0.1 | 10 November 2026

**Status:** Exploration and recommended direction, **not** an approved implementation specification or permission to write/deploy code.

## 1. Vision

Build a remarkable personal portfolio whose design and engineering demonstrate the same skills as the projects it describes. It should feel like an interactive exhibition of real systems, not a conventional developer template, AI-themed dashboard, scrolling animation reel or artificial game world.

**Working proposition:** *The systems behind the solution.*

Visitors should be able to understand a useful engineering outcome in under a minute, and then explore its architecture, decisions, tests and trade-offs through technically meaningful interactions. The site itself becomes an additional engineering showcase, with documented decisions, performance, accessibility, verification and honest attribution to AI-assisted implementation.

### Intended audiences
- Product and technical leaders evaluating AI Solutions Engineering, Applied AI or Solution Architecture capabilities.
- Engineers who want to inspect architecture and evidence.
- Professional peers and collaborators, without implying an active job search.

### Central design tension
**Ambition without obstruction.** Make the advanced experience extraordinary, but ensure an ordinary visitor on a phone, using assistive technology or arriving from a shared link can access every important conclusion directly.

## 2. Three genuinely different visual territories

### A. The Systems Atlas | **RECOMMENDED**

**Metaphor:** A beautifully produced technical atlas or museum of engineered systems.

**Aesthetic:** Architectural drawings, editorial photography and typography, warm off-white and charcoal, mineral green, carefully chosen copper accents, fine-line diagrams, sparse but expressive animation. Light and dark are art-directed to the content rather than applied as generic themes. Avoid neon cyan/purple, frosted-glass cards and generated-looking decorative gradients.

**Interaction:** A case study begins as an authored narrative, then opens into inspectable systems. Panels reveal component responsibilities; a trace animates through a system; visitors can compare scenarios and inspect supporting evidence. The design moves between overview and detail with a consistent spatial grammar.

**Signature moment:** A business problem transforms seamlessly into an architectural system diagram, then into a controlled, deterministic simulation. Each visual transformation answers an engineering question.

**Why this wins:** Unusual and memorable, but credible for AI solutions roles. It supports non-technical and technical audiences and adapts naturally to FTT, AXIOM, Birria Radar and PAF.

**Risk:** Too much editorial restraint could make the advanced work feel hidden. Remedy: an obvious but optional *Explore the system* affordance and one impressive interactive reveal near the start.

### B. The Operations Theatre

**Metaphor:** A live control room in which visitors observe business systems operating.

**Aesthetic:** Dark material palette, signal colours, precision instruments, operational typography, data flow timelines, fluid system animations, dramatic soundless transitions.

**Interaction:** Play, pause and scrub synthetic events; inject a fault; inspect event propagation, tenancy boundaries and recovery states. The entire website feels like an instrument panel.

**Signature moment:** A visitor follows an order through FTT in real time and sees its state evolve across the customer, API and staff surfaces.

**Strength:** High technical drama and demonstration potential.

**Risk:** Could become an archetypal AI dashboard, intimidate recruiters and overfit operational systems. Better used as a *component inside* the Systems Atlas than as the global design language.

### C. The Experimental Monograph

**Metaphor:** A remarkable digital publication in which each project is a distinct chapter.

**Aesthetic:** Oversized editorial typography, exquisite spacing, rich bespoke illustration, advanced page choreography, unexpected composition, highly controlled palettes. Strong influence from publication and contemporary graphic design rather than software dashboards.

**Interaction:** Scroll and navigation reveal layers of thought, annotated screenshots, decisions, and alternative architectures. Technical diagrams may unfold or reorganise as readers move between perspectives.

**Signature moment:** A physical-feeling transition from product experience to layered architectural drawings.

**Strength:** Visually distinctive and accessible to a broad audience.

**Risk:** Can be beautiful yet technically shallow. Needs meaningful simulators and architecture inspection to make the website itself a credible engineering showcase.

### Direction recommendation
Choose **A as the parent language**, incorporate **B selectively** for simulations and operational traces, and borrow **C's editorial ambition** for typography, choreography and project-specific art direction. This is a creative recommendation, **not yet an owner-approved decision**.

## 3. Proposed information architecture

- **Landing:** A highly art-directed opening, immediate professional positioning, brief introduction and a single standout interactive preview. Direct links to projects and professional background remain visible.
- **Work / Exhibitions:** Four primary projects, starting with For The Table. Each has a 60-second summary, deeper story, interactive system and verifiable evidence. Supporting projects can appear as shorter studies.
- **Experience:** Sorcero and healthcare analytics history, articulated with care. No internal screenshots, unpublished product ideas, employer code, customer information or confidential architecture without appropriate permission.
- **Method:** How projects are defined, designed, built, evaluated and delivered with AI-assisted tools. Describe the user's actual role in requirements, architecture, implementation oversight, testing and decisions rather than falsely claiming all code was authored unaided.
- **Colophon / The Site Itself:** An explicit behind-the-scenes engineering account: accessibility, performance, system design, graphics choices, verification and trade-offs. This is the website's own technical showcase without a standard fifth project card.

Do not center the website around a chatbot, a CV download, or a loud “hire me” CTA. Provide a discreet contact route and professional links.

## 4. For The Table: the first exhibit

**Working title:** *From a table to a multi-tenant system.*

**Honest status:** Application implementation and hosted synthetic operational rehearsal accepted in the repository's September release record. **Not** a commercially launched product, no real customer traction claimed. Remaining external-commercial, email, offboarding and other launch gates must stay visible.

### The visitor journey

**00 | The premise (15–30 seconds)**
A compelling opening illustration of a venue at work, not a generic photo collage. Explain the problem: independent hospitality venues need a lightweight ordering experience without bespoke per-venue infrastructure. One sentence on what was delivered, with visible proof-tier label.

**01 | The product (30–60 seconds)**
Show the actual synthetic customer ordering and venue operations surfaces. Optionally link to the existing isolated read-only public owner demo. Still images/video fallback if the external demo is unavailable.

**02 | The system (1–2 minutes)**
Reveal the architecture: React platform, Node/Express API, PostgreSQL shared database, authenticated roles and venue tenancy boundaries. Every node has concise responsibilities, with deeper detail on demand. Explain the important design decision: onboarding a new venue should not require new infrastructure or code.

**03 | The interactive trace (2–3 minutes)**
A separate, **clearly labelled deterministic educational simulation** (not connected to live FTT):
1. Choose a synthetic venue and table.
2. Place a synthetic order.
3. Trace UI request, tenant-aware API validation, persistence and staff-facing order state.
4. Advance the order through fulfilment and observe customer status convergence.
5. Switch to a second tenant to illustrate the intended data boundary, referencing actual repository tests/release evidence for the real boundary. A visual simulation by itself does **not** prove security isolation.
6. Explore one bounded failure or exception, for example an invalid state transition, with explanatory copy and retry/reset controls.

**04 | The decisions and trade-offs (1–2 minutes)**
Why shared service/shared database; anonymous customer entry; role boundaries; hosted operation; what was deliberately left outside the first commercial release.

**05 | Evidence and limits (30–60 seconds)**
A transparent evidence board with source documents, acceptance claims, exact recorded software versions, test/verification provenance, and separate “not commercially verified” items. The public should never need access to a private repository to understand the evidence, and no proprietary source needs to be released.

**06 | The takeaway**
Explain lessons about translating a domain problem into a repeatable operational platform. Provide a quick return path to the project index and professional experience.

### Demo/claim boundaries
- The portfolio's scenario explorer is a **synthetic simulation** implemented from a versioned scenario contract. It never writes to FTT production or accesses owner credentials.
- Real application screenshots must come from synthetic/test accounts and be manually reviewed for privacy, brand and legal suitability.
- “Hosted rehearsal accepted” is a claim supported by the repository record, not a fresh real-world customer launch.
- If an external FTT demo is used, clearly distinguish it from the portfolio simulator and avoid embedding secret-bearing URLs or privileged controls.

## 5. Design and interaction principles

1. **Every effect has a purpose.** Animation must convey hierarchy, causality, state change or spatial continuity, not merely spectacle.
2. **Two depths of reading.** A visitor can skim each case in about 60 seconds; a technical reader can spend 10 minutes exploring without losing orientation.
3. **Honest evidence.** Label simulated, mocked, tested, hosted-verified, owner-observed, and commercial outcomes distinctly.
4. **Visible authorship.** Explain contributions and the use of coding agents accurately. Don't imply the site or project was handcrafted without AI.
5. **Strong mobile design.** Touch-first interactive states should not be a clumsy miniature of the desktop exhibit.
6. **No forced animation or audio.** Honor reduced-motion preferences, offer pause/reset for complex traces, and preserve the content in text.
7. **Independent of employer property.** Generic professional descriptions only until company publication permissions are clear.

## 6. Tentative technical approach (for later PAF evaluation)

**Recommended starting architecture:** A static-first, content-driven application such as Astro with TypeScript and embedded React components for selected interactive exhibits. MDX or equivalent typed case-study content; authored SVG and lightweight 2D animation for diagrams; optional WebGL only for a specific effect that materially improves comprehension. No always-on backend or LLM is necessary for the first release.

**Alternatives:** Next.js/React if interactions and app-state complexity justify a unified React runtime; a fully custom WebGL experience if a validated interaction requires it. Neither should be selected simply because it feels more “advanced.”

**Platform features:** CSS View Transitions as progressive enhancement, with fallback; optional animations loaded only where needed. WebGPU is experimental/enhanced-only because support is not universal, never a requirement for core comprehension.

**Testing:** Playwright keyboard and browser coverage; accessibility inspection against WCAG 2.2 AA intent; reduced-motion, touch and screen-reader testing; visual regression snapshots; privacy/security and broken-link checks; Core Web Vitals targets: LCP <= 2.5s, INP <= 200ms, CLS <= 0.1 at the 75th percentile where field measurements are available. Define separate lab budgets and device/browser matrix during planning.

**Deployment:** Static hosting, publicly cacheable assets, no secrets in client bundles, no direct access to employer systems or personal project databases. Repository and hosting choice are still open. The existing `D4V1DW/portfo` repository presently has only a minimal README and should not automatically be presumed the new permanent project home.

## 7. First publishable milestone

**Scope:** Landing with exceptional design, clear Experience/About, project index placeholders, fully written FTT case study, FTT 2D interactive trace, evidence board, responsive UI, simple technical colophon, operational domain/deployment. Other projects have short honest summaries until their exhibits are ready. No account system, open-ended AI chat, 3D navigation, WebGPU requirement or live FTT backend connection.

**Acceptance:**
- Understand the owner's professional focus and the FTT outcome from the landing/case-study opening without interacting.
- Run, pause, reset and keyboard-navigate the synthetic FTT trace; the simulation is deterministic and clearly labelled.
- See a truthful statement of what is verified and what remains before commercial launch.
- Access the core case study with JavaScript unavailable or advanced animations disabled (subject to final technical design), and use it with reduced motion.
- Test critical journeys on common mobile widths and at least two browser engines; record device-specific gaps honestly.
- Document measurable performance, accessibility, test, AI-assisted development and source-attribution evidence.
- Reach a finished publishable site rather than an indefinite design prototype.

## 8. Decision log

| Topic | State | Current disposition |
| --- | --- | --- |
| Portfolio itself as an engineering showcase | DECIDED | Yes, ambition is explicit |
| First full exhibit | DECIDED | For The Table |
| Birria Radar timing | DECIDED | Wait for ongoing development to settle before full showcase |
| Employer prototypes | DECIDED | Treat as potentially useful professional experience, but no confidential publication |
| Global visual direction | RECOMMENDED, AWAITING OWNER REVIEW | Systems Atlas with selective Operations Theatre/Monograph elements |
| Exact technology stack | TECHNICAL DEFAULT | Astro + React islands, subject to technical validation |
| Target repository / hosting / domain | OPEN | Decide at formal PAF planning stage |
| Original interactive graphics / advanced 3D | DEFERRED | Add only with a distinct user benefit and performance budget |
| FTT scenario evidence and actual screenshot set | OPEN EVIDENCE WORK | Inspect/capture controlled real/demo materials before publication |

## 9. Next step

Review the three creative directions and agree a primary art direction. Then create a small visual design exploration of the landing plus the first FTT architecture/trace scene, rather than writing all implementation tasks prematurely. Once that concept is accepted, invoke the current PAF planning contract again, inspect the actual chosen target repo, and produce the authoritative documentation-only planning PR for separate owner approval. Do **not** start code execution or spending from this brief alone.

### Source evidence consulted
- `D4V1DW/agent-framework/planning/PLANNING_CONTRACT.md`, read 10 Nov 2026.
- `D4V1DW/OrderApp/README.md` and `docs/pubflow/RELEASE_READINESS_BOARD.md`, read 10 Nov 2026.
- `D4V1DW/portfo/README.md`, read 10 Nov 2026.
- Browser documentation: https://developer.mozilla.org/en-US/docs/Web/API/View_Transition_API and https://developer.mozilla.org/en-US/docs/Web/API/WebGPU_API
- Performance guidance: https://developers.google.com/search/docs/appearance/core-web-vitals
- Accessibility guidance: https://www.w3.org/WAI/WCAG22/Techniques/css/C39