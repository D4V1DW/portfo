# Systems Atlas: FTT exhibit interaction principles (design exploration 03)

**Date:** 10 November 2026  
**Status:** Design research only. Not a PAF build contract, deployment instruction, or owner acceptance of the final experience.  
**Companion probe:** `systems_atlas_ftt_exhibit_02.html`

## Owner feedback and direction

The restrained editorial visual direction was positively received, but the initial three-box FTT architecture flow was **rejected as underwhelming**. More boxes, glow or animation alone are not the answer. The exhibit must use the browser as an *interactive explanatory medium* rather than an animated slide deck.

## What the exhibit should accomplish

Visitors should be able to explore both the business-facing operation and the engineering machinery, with progressive depth:

1. **Human-scale opening:** A customer scans a venue entry QR, selects a table and places a synthetic order in a visually convincing hospitality scene.
2. **Continuous transition:** Zoom or spatially unfold the scene into the services and authority boundaries that made that action possible. Maintain continuity so the user can understand where each interaction went.
3. **Causality, not choreography:** Events advance meaningful state; status changes, failures and permissions affect what the viewer sees. A timeline should support step, replay, rewind and branch.
4. **Investigable architecture:** Selecting a node reveals what it owns, why it exists, its interfaces, design trade-offs and any documented test/evidence. Avoid disclosing secrets or private implementation.
5. **Negative cases and real boundaries:** Explore venue isolation, suspension and normal order-state convergence. Never present synthetic denials as penetration-test proof.
6. **Evidence layer:** Visually distinguish implemented and documented capabilities, newly verified live demonstrations, and simulation-only behaviours. Source revision and verification tier must be evident.

## Current interactive design probe

The second probe replaces the three-box flow with 11 selectable components, three diagram lenses (experience, architecture, trust), four step-by-step synthetic scenarios (place order, cross-tenant attempt, suspend venue, Same again), an inspector, payload snapshots, timeline, play/pause and reset. It preserves the cream/green editorial look and is dependency-free.

**Verification conducted:** Chromium in three viewports (1440, 768 and 390 CSS pixels) using in-memory HTML content; interaction checks passed for selecting a negative scenario, advancing to denial, changing lens and inspecting PostgreSQL. No JavaScript page errors or page-level horizontal overflow in those checks. This is not a WCAG audit, full keyboard audit or production performance audit. The small-screen graph uses an intentionally horizontally scrollable internal viewport.

**Honest evaluation:** This is a useful **interaction architecture prototype**, but the central scene is still a two-dimensional topology map. It is **not yet** the ambitious signature spatial experience promised by the creative brief. Treat it as a way of testing scenario and inspector semantics, not as final creative approval.

## Next art-direction spike

Prototype a **transition from the realistic customer surface into a spatial systems model**, then back out to operational consequence. The decisive test is whether the viewer experiences *why* the architecture behaves as it does, rather than observing dots move between boxes.

Suggested first authored arc: order placed → focus on the order object → expand into the API/venue context/data ownership → operational staff action → collapse back to customer status. The architecture can begin 2.5D/orthographic SVG or Canvas/WebGL where appropriate, but must have a usable 2D/semantic equivalent. Delay any technology commitment until proof of comprehension and art direction.

## Evidence boundaries

FTT repo documents a React/Vite platform, Node API, shared PostgreSQL architecture, venue-scoped customer and admin operations, anonymous guest entry, Same again and platform lifecycle controls. The 29 September 2026 readiness board recorded an accepted **hosted synthetic operational rehearsal**, not customer launch. Any illustrative order IDs, event timings, denial responses and data values are synthetic and must be labelled accordingly.

No existing application repository was modified to create these design probes.