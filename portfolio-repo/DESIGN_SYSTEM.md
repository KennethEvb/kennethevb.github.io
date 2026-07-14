# DESIGN_SYSTEM.md — Regulation Inspector

Shared reference for both the portfolio site (GitHub Pages, static HTML) and the functional
prototype (Vercel, React/Vite). **Both sides read this before making visual changes, and both
sides update it if a change is made.** If this file and the actual code disagree, the code is
wrong — fix the code, not this file, unless the change was intentional (in which case update
both in the same session).

Last confirmed in sync: 2026-07-14 (portfolio + Vercel-prototype restructure)

## Color tokens

```css
--ink: #14171F;
--ink-light: #262B36;
--paper: #F5F4EF;
--paper-dark: #EBE9E1;
--teal: #1F6F6B;
--teal-deep: #154F4C;
--mark: #F0B94D;      /* mustard highlight/accent — the signature "highlighter" color */
--mark-deep: #C9922A;
--line: #DBD8CC;
--soft: #5B6472;
--red: #B03A32;
--amber: #B5791E;
--green: #2F7A4D;
--low-green: #7FAE8E;  /* low-severity heatmap cells specifically */
```

## Typography

| Role | Font | Notes |
|---|---|---|
| Display / headings | Spectral (serif) | Editorial, legal-document feel — this is deliberate, ties to the "reading regulation" theme |
| Body / UI | Inter (sans) | |
| Mono / data / citations / reference codes | JetBrains Mono | Used for article references, status badges, technical labels |

Both loaded via Google Fonts. Do not substitute — the serif/sans/mono three-way split is a
structural part of the design language, not a stylistic default.

## Signature visual motif

A "highlighter" annotation style on regulation text — mimics a compliance reviewer marking up
a document by hand:
```css
background: linear-gradient(180deg, transparent 60%, var(--mark) 60%);
padding: 0 1px;
```
This appears on every "here's the actual clause text" moment across both sites. If a new
component shows regulation text, it should use this treatment, not a different highlight style.

## Naming conventions that must stay consistent

- Coverage states: `Covered` / `Gap` / `In Progress` (prototype) — note the portfolio's earlier
  static mockups used `Not Assessed` / `N/A` instead of `In Progress`; **the prototype's set is
  now the source of truth** if these ever need reconciling.
- Severity: `HIGH` / `MED` / `LOW` (uppercase, prototype convention)
- Domains: `ICT Risk`, `BCDR`, `Incident Rep.`, `Testing`, `3rd-Party`, `Info Sharing` — exact
  strings, used as object keys in both codebases' data layers. Do not rename without updating
  both sides in the same session, since these are used as lookup keys, not just display labels.

## Known intentional divergences (not bugs)

- The static portfolio's Tracker used simple domain names; the Vercel prototype's `data.ts`
  additionally groups clauses by `similarityGroup` across DORA/BAIT/COBIT. This is a real
  evolution, not drift — the portfolio's copy should eventually be updated to reflect this same
  grouping concept once the two are reconciled, but hasn't been yet as of this file's last sync.

## Content that must NOT diverge

- Regulatory citations (DORA Art. 11(3), BAIT Ch.10 §10.1, DNB guidance, etc.) — same paraphrase
  in both, since both are showing the same underlying research. If one side improves a
  citation's accuracy, port the fix to the other side too.
