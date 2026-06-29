# The L0 Guy — Portfolio Site

Production static implementation of the Claude Design project *Portfolio page design*
(`497fb3f1-c399-48ca-8665-316cae04bbe5`). The two `.dc.html` design files (desktop +
mobile) are the **same site** — this build folds them into one responsive `index.html`.

## Files

- `index.html` — the whole site. Desktop layout collapses to the mobile design at ≤860px.
- `llms.txt` — the agent-readable read of the page (linked from the footer). This is the
  site demonstrating its own pitch: docs correct for the agents reading them.
- `uploads/lz.jpg` — avatar / OG image.

## What was converted from the design source

The Claude Design `.dc.html` format (`<x-dc>`, `<helmet>`, `style-hover`, the `DCLogic`
runtime, the iOS-frame mobile wrapper) is preview-only. For a hostable site it was
converted to standard HTML:

- `<helmet>` → real `<head>` (title, meta, OpenGraph/Twitter, fonts, JSON-LD `ProfilePage`).
- `style-hover="…"` attributes → CSS `:hover` rules (`.nav-link`, `.btn-primary`,
  `.proof-card`, `.contact-card`).
- The mobile design's iOS-phone frame was dropped; its layout is reproduced via
  `@media (max-width: 860px)` so one page serves desktop and mobile.
- The `DCLogic` reveal script → a vanilla `IntersectionObserver`.

## Before going live — fill these placeholders

1. **Proof links** — three cards + the `llms.txt` proof block currently point at `#contact`
   and say "link soon". Add real URLs (OFT Sentinel, fee-switch piece, DVN piece).
2. **Contact channels** — `hello@thel0guy.xyz`, `https://x.com/`, `https://t.me/` are
   placeholders in both `index.html` and `llms.txt`. Set the real email + handles, and the
   `sameAs` array in the JSON-LD.

## Hosting

Fully static. Drop the folder on GitHub Pages / Vercel / Netlify. No build step.
`uploads/lz.jpg` and `llms.txt` must ship alongside `index.html` at the site root.
