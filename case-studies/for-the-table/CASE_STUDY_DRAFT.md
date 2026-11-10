# For The Table
## Engineering a multi-tenant ordering platform for independent hospitality venues

**Portfolio case study | Editorial draft 0.1 | 10 November 2026**

**Project status:** Application implementation and substantial hosted engineering acceptance completed. Commercial launch and first-customer activation remain outstanding.

**My role:** Independent product direction, requirements and architecture decisions, AI-assisted engineering coordination, iterative review and acceptance. **Owner confirmation required before publication** for the exact personal contribution wording.

**Technology:** React, TypeScript, Vite, Node.js/Express, PostgreSQL, Railway, Stripe Billing (tested in sandbox), and supporting operational services.

> **The central question:** How do you give an independent pub a useful digital ordering experience without asking it to adopt an entirely new point-of-sale, payment or operational system?

### The problem

Many digital ordering products make life simpler for the customer by moving complexity somewhere else: another staff dashboard, a new payment provider, duplicated accounting, extra onboarding, or a new process to manage every transaction.

For The Table started with a more constrained proposition: provide a lightweight mobile ordering layer that fits around the systems a venue already uses.

A customer should be able to enter a venue-specific experience, identify their table, browse the menu and place an order. Staff should see and confirm that order without having to run a second, elaborate fulfilment workflow. The venue should continue taking payment through its existing arrangements.

That product constraint drove the architecture and, just as importantly, several decisions about what **not** to build.

### Designing the smallest useful customer journey

The intended normal flow is deliberately short:

**Venue entry → choose table → short-lived session → browse and order → staff confirm → venue fulfils and takes payment.**

I chose a venue-level entry model rather than requiring a unique QR code for every table. Table selection is part of the customer journey, not an authentication mechanism. That reduces venue setup and maintenance while keeping the routing context explicit.

I also resisted building a mandatory customer account. The initial release model uses a short-lived anonymous session and bounded server-side anti-abuse controls. An earlier mobile-phone verification proposal was deliberately dropped after comparing its security benefit with the extra customer friction and operational cost. The model explicitly accepts residual misuse risk rather than pretending that a QR code proves physical presence.

The design preserves a particularly useful constraint: **one routine staff action, Confirm order**. Exceptional rejection and operational controls still exist, but staff should not need to work through a long sequence of status buttons just to serve an ordinary order.

This decision reduces features, but raises the quality bar: the remaining workflow needs to be reliable, clear and fast.

### A shared multi-tenant architecture

For The Table uses one shared application platform, one Node/Express API and one PostgreSQL database to serve multiple independent venues.

Tenant identity is associated with venue-specific records and membership/session boundaries. The intention is that bringing on another venue should be a data-driven onboarding process, not a new deployment, database, code branch or set of per-customer secrets.

The architecture separates three perspectives:

**Customer:** A low-friction ordering interface tied to a venue and table.

**Venue staff and owner:** Authorised operational and administrative capabilities scoped to their venue.

**Platform operations:** Higher-trust tools for account lifecycle, support, diagnostics and administration.

That separation was more important than merely making the interface appear multi-tenant. Real PostgreSQL tests and adversarial authorisation checks were used to exercise tenant boundaries, including invitation handling and cross-venue mutations.

The architecture also distinguishes business lifecycle from user authority. Whether a venue is trialling, active, past due or suspended should affect the appropriate operational capabilities without granting anyone additional cross-tenant privileges.

### Rejecting attractive complexity

Several technical directions were intentionally excluded from the initial product.

**Not an EPOS replacement.** The venue's existing till remains authoritative for sales and payments.

**Not a new consumer payment rail.** Stripe Connect-style customer prepayment was explored but rejected for initial ordering because it introduced onboarding, reconciliation, fee and refund complexity. Stripe remains relevant to the separate business-to-business SaaS subscription. The subscription lifecycle has been tested in sandbox mode; live commercial billing has not been activated.

**Not a customer identity product.** Ordinary ordering does not require an account, password, phone number or enduring customer profile.

**Not a heavyweight kitchen workflow engine.** The normal venue workflow remains intentionally small.

These were not decisions to avoid engineering work. They were trade-offs intended to make the solution usable and commercially plausible for its actual audience.

### Engineering the less visible parts

The project became more interesting as its release requirements matured.

**Authorisation and tenant safety.** Reviews identified and repaired important boundary issues. These included preventing a synthetic demonstration identity from inheriting real platform powers, ensuring staff-invitation mutations remain tenant-scoped, and protecting owner-role records against unauthorised edits. The release security programme records targeted fixes and residual limitations, not a claim of formal penetration testing or certification.

**Safe demonstrations.** The public owner demonstration uses a synthetic persona with server-enforced read-only authority. It is intended to let visitors explore the genuine owner interface without exposing real venue data or allowing writes. That is a useful example of treating a demonstration as a security boundary rather than just a disabled-button UI.

**Recovery.** Operational work established two distinct recovery paths: portable, off-provider PostgreSQL logical backups and Railway PostgreSQL point-in-time recovery. The September 2026 closeout documents isolated restore drills for both. These are concrete recovery tests, not a guarantee that every future incident can be resolved within a particular service-level target.

**Deployment and observability.** The application, API and database were deployed and checked against known revisions, with health, migration and release-evidence checks. The project also documented a deployment dependency on GitHub Actions, including a later account allowance issue that blocked hosted CI. That infrastructure limit must not be presented as a passing CI run.

These decisions show a system moving beyond feature completeness towards actual operational accountability.

### Validation and what it proves

The clearest milestone came from a hosted operational rehearsal, accepted on **29 September 2026**.

Using a realistic **synthetic** venue/customer lifecycle, the rehearsal exercised owner onboarding, venue configuration, menu publication, customer entry, order submission, staff fulfilment, customer status convergence, repeat ordering, suspension, reinstatement and restored operation.

The release record states that this did not require bespoke customer code, an individual deployment, manually inserted data, or founder-only SQL recovery.

Separate work documented security acceptance, real-PostgreSQL tenancy tests, restore drills, and sandbox Stripe subscription flows.

**What this establishes:** Substantial implementation, verification and hosted operational readiness for the chosen product model.

**What it does not establish:** A commercially launched service, paying customer traction, production live-mode Stripe billing, completed external legal/operational approval, or a measured business outcome.

The first-customer launch still requires real delivery checks for invitations/password reset, remaining account-termination and data-return work, legal/company activation and a final live-commercial acceptance pass.

### Working with AI coding agents

AI coding agents were part of the implementation workflow. The important distinction is between generating code and taking responsibility for a solution.

The engineering process involved defining product constraints, resolving competing requirements, specifying implementation boundaries, reviewing changes against expected behaviour, requiring targeted and regression tests, and keeping release decisions separate from feature completion.

This case study should not imply that every line of source was manually authored. The role I want to demonstrate is **solution ownership and technical judgement in an AI-assisted development environment**, supported by the resulting architecture and evidence.

*Editorial check before publication:* Confirm the exact decisions personally made, where collaborators or agents contributed, and the degree of hands-on implementation.

### What I would do differently

A central lesson is that scope discipline is an engineering capability. Some initially appealing ideas—phone verification, customer prepayment and detailed fulfilment steps—would have increased cost or friction without clearly improving the product's core proposition.

Another is that a production-shaped architecture is not the same thing as commercial release readiness. The work needed to prove tenant isolation, recovery, billing boundaries, support and access control only becomes visible when the project is held against a real operating model.

Finally, AI-assisted implementation can produce a large amount of working software quickly, but the quality of the result still depends on specification, verification and restraint. The most useful progress was not adding another feature. It was turning an ambitious application into a bounded, testable system.

### Explore the system

The accompanying Systems Atlas exhibit should **not** simply reproduce a network flowchart.

It should begin with an understandable customer/venue interaction, then let visitors investigate the meaningful engineering decisions: why a second venue cannot access another's records; how a suspended venue changes ordering behaviour; where customer payment stops and SaaS billing begins; and how safe demonstrations differ from real user authority.

Interactive scenarios should use clearly labelled synthetic state. They must not imply that the portfolio website is connected to a real customer database or that every animation reproduces actual runtime telemetry.

---

## Publication and evidence notes

**Status of this document:** Review draft, not an approved public statement or verified live demonstration.

**Primary private-repository source records:**
- [FTT README / current architecture](https://github.com/D4V1DW/OrderApp/blob/main/README.md)
- [Release Readiness Board, 29 September 2026](https://github.com/D4V1DW/OrderApp/blob/main/docs/pubflow/RELEASE_READINESS_BOARD.md)
- [Release Readiness Programme](https://github.com/D4V1DW/OrderApp/blob/main/docs/pubflow/RELEASE_READINESS.md)
- [Implementation Direction](https://github.com/D4V1DW/OrderApp/blob/main/docs/pubflow/IMPLEMENTATION_DIRECTION.md)
- [Lightweight Ordering Model](https://github.com/D4V1DW/OrderApp/blob/main/docs/pubflow/LIGHTWEIGHT_ORDERING_MODEL.md)
- [Minimum Viable Abuse Prevention](https://github.com/D4V1DW/OrderApp/blob/main/docs/pubflow/MINIMUM_VIABLE_ABUSE_PREVENTION.md)
- [Payment Boundary](https://github.com/D4V1DW/OrderApp/blob/main/docs/pubflow/PAYMENTS_MODEL.md)
- [Security and Abuse Closeout](https://github.com/D4V1DW/OrderApp/blob/main/docs/pubflow/ITEM11A_SECURITY_ABUSE_CLOSEOUT.md)
- [Resilience Closeout](https://github.com/D4V1DW/OrderApp/blob/main/docs/pubflow/ITEM10_PRODUCTION_RESILIENCE_CLOSEOUT.md)
- [Stripe Test-Mode Closeout](https://github.com/D4V1DW/OrderApp/blob/main/docs/pubflow/STRIPE_ITEM8_TEST_MODE_CLOSEOUT.md)
- [Public Read-Only Demo PR #144](https://github.com/D4V1DW/OrderApp/pull/144)
- [Item 13A Rehearsal Acceptance PR #146](https://github.com/D4V1DW/OrderApp/pull/146)

**Verification basis:** Documentary GitHub review on 10 November 2026. No fresh local build, remote application smoke, screenshot capture, CI run or production audit was executed as part of this case-study draft.

**Before publication:** Confirm personal role/attribution; choose approved product screenshots; check current public demo; decide whether the project is still pre-commercial-launch; remove this editorial appendix from the visitor-facing article; and make private-source evidence available in an appropriate public-safe form if desired.