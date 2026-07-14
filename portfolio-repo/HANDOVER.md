# Handover: Regulation Inspector — Portfolio Site

**From:** Claude · **Date:** 2026-07-14 · **Session focus:** Full build of the static portfolio case study, plus first exchange with a parallel Gemini-built functional prototype.

## 1. Since the Last Handover

First handover for this project.

## 2. Executive Summary

A two-page static portfolio site (`index.html` + `regulation-inspector.html`) presenting "Regulation Inspector" — a personal project concept demonstrating BI/data-structuring skills by turning regulatory text (starting with DORA) into a structured, human-reviewed compliance dashboard. Built for job applications, hosted on GitHub Pages. This is a **polished mockup, not a working product** — all data is realistic sample data, not live extraction.

A separate, genuinely functional prototype (React/Vite/Express, real Gemini API clause extraction) exists in a parallel repo, built by Gemini/AI Studio and being restructured for Vercel deployment. The two are intentionally independent (see `DESIGN_SYSTEM.md` for what must stay in sync between them).

## 3. Architecture & Tech Stack

- **Runtime/framework:** None — plain HTML/CSS/JS, single file per page, no build step
- **Styling approach:** Custom CSS using the tokens in `DESIGN_SYSTEM.md`, Google Fonts (Spectral/Inter/JetBrains Mono)
- **Data layer:** Hardcoded sample data inline in each page's `<script>` block — no backend, no persistence
- **Deployment target:** GitHub Pages (static hosting), not yet pushed

### Directory structure
```
index.html                  — Portfolio home (intro, skills, project card)
regulation-inspector.html   — Case study (hero, approach, dashboards, governance, stack, reflection)
DESIGN_SYSTEM.md            — Shared token reference (also lives in the Vercel prototype repo)
HANDOVER.md                 — This file
```

## 4. What's Real vs. Simulated

| Feature | Status | Notes |
|---|---|---|
| Consolidated requirement hero (DORA/BAIT/DNB) | Real citations, static | Paraphrased regulatory content, verified against search but not primary legal text — flagged for a second check before high-stakes use |
| Tracker coverage popovers | Simulated | Static sample data, no live document link-checking |
| Governance link-health/ticket flow | Simulated | Illustrates the concept; no real ticketing system connected |
| Heatmap market sidebar | Simulated | Static numbers per market, no live regulatory database |
| Everything on this site | Simulated | This entire site is a design mockup — the real functional build lives in the separate Vercel prototype repo |

## 5. Known Issues / Flags for the Receiving Tool

- [ ] Placeholder links still present: `mailto:you@example.com`, GitHub/LinkedIn `href="#"` on both pages — must be filled in before publishing
- [ ] Status-value naming diverges from the Vercel prototype (`Not Assessed`/`N/A` here vs. `In Progress` there) — tracked as an intentional-for-now divergence in `DESIGN_SYSTEM.md`, not yet reconciled
- [ ] No Open Graph meta tags yet (`og:title`, `og:description`, `og:image`) — needed before sharing the link on LinkedIn

## 6. Design System Reference

- [x] No design system changes this session (this session established `DESIGN_SYSTEM.md` for the first time, drawing from what was already built)

## 7. Recommended Next Steps

1. Push this repo to GitHub, enable Pages (see setup steps provided separately)
2. Fill in the placeholder contact/social links before sharing publicly
3. Add Open Graph meta tags to `index.html`
4. Once the Vercel prototype is live and the Barclays reference is fixed there, decide whether this site should link out to it as a "live functional prototype"

## 8. Open Questions for the Human

- Reconcile the status-naming divergence now, or leave it until both sides are being actively worked on together?
- Custom domain, or ship on the default `github.io` subdomain for now?
