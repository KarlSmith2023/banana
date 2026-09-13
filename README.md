# DESK://trade (static PWA)

Karl Smith’s private **paper-trading** blotter for an India NSE breakout / VCP playbook. Complements research around [BananaPatterns](https://bananapatterns.com).

This is the **phone-installable, no-Node** build: plain HTML / JS / CSS. The paper book lives in `localStorage` (not SQLite). Host it on GitHub Pages, open `index.html` as a file, or serve the folder as `/desk/`.

> **BananaPatterns has no official API.** Desk does not invent vendor endpoints. Paste JSON on Scanner to ingest your own setups.
>
> **Not financial advice.** Paper only until the live gate clears.

## What’s included

- SPA: Markets · Trade · API (ingest) · Brief · Journal · Playbook (+ Overview / Positions / Charts under More)
- **DESK://trade** phone UI: neon green on near-black, monospace headers, LIVE/PAPER pills, metric chips, HL-style paper ticket
- Bottom nav: MARKETS · TRADE · API · BRIEF · MORE · JOURNAL
- Big green **PLACE PAPER ORDER** CTA while live lock active · **Keep paper** · Short N/A for India cash
- Dual currency **INR + GBP** (default FX **129.26**)
- Start equity **£800** = **₹1,03,408**
- Seed setups as-of **Fri 11 Sep 2026**: KPL, BLUESTONE, CPPLUS, DIACABS, FILATEX, KABRAEXTRU, WHEELS
- Working paper ticket (Market / Limit / Stop / Stop-Limit), positions, attached 8% stop + 50-EMA trail
- Live button **hard-locked · 60 sessions left** (stub even when unlocked)
- PWA: `manifest.webmanifest`, `sw.js`, icons under `./icons/`

Playbook defaults (editable, persisted; changes snapshot a regime):

| Rule | Default |
|------|---------|
| Universe | Blue sky **or** VCP∩Blue sky |
| Risk | **1.5%** equity / idea; stop **8%**; size = risk / stop% |
| Caps | Max **5** open; max **2** new / session |
| Chase | No chase if **>5%** above pivot; prefer RS ≥ **85** |
| Trail | Daily close below **50-EMA** |
| Other | No averaging down |

Try: open `index.html` (defaults to **Trade · FILATEX**) → **Place paper order**. Position + 8% stop appear under **Positions** (More). KABRAEXTRU / WHEELS reject as do-not-chase. Use **Next move** for the playbook suggestion sheet.

## Paths (GitHub Pages + file://)

All assets are **relative** (`./app.js`, `./styles.css`, `./icons/...`). There are **no leading-slash** URLs, so the desk works at:

- `https://<user>.github.io/desk/`
- `https://<user>.github.io/Lona-Site/desk/`
- opening `index.html` directly (`file://`) — PWA install still needs HTTPS or localhost

Routing is hash-based (`index.html#/overview`, `#/ticket?symbol=FILATEX`).

## GitHub Pages

1. Copy this folder into your Pages repo as `desk/` (for example `Lona-Site/desk/`).
2. Keep `.nojekyll` so Pages does not rewrite files.
3. Push. Enable Pages on the branch (root or `/docs` as you already use).
4. Open `https://<user>.github.io/<repo>/desk/` (or `.../desk/index.html`).

`404.html` sends unknown paths such as `/desk/scanner` back to `index.html#/scanner`.

### Install as an app (Add to Home Screen)

**Phone target:** restyle matches the DESK://trade dark-terminal mockup. After install, launch from the home screen for the standalone blotter.

Needs HTTPS (GitHub Pages) or `localhost`. `file://` runs the blotter but cannot register a service worker.

**iPhone / iPad (Safari)**

1. Open Desk in **Safari**.
2. Share → **Add to Home Screen** → name it **Desk** → Add.
3. Launch from the home screen (standalone, `apple-mobile-web-app-capable`).

**Android (Chrome)**

1. Open Desk in Chrome.
2. Menu → **Install app** / **Add to Home screen**.

**Windows (Chrome or Edge)**

1. Open Desk.
2. Address-bar install icon, or menu → **Install Desk** / **Apps → Install this site as an app**.

## Reset

Playbook → **Reset paper book to seed** (or clear site data / `localStorage` key `desk-static-book-v1`).

## Honesty

- No official BananaPatterns API — do not expect Desk to scrape or call one.
- Paper fills are simulated (10 bps slippage model); not exchange-quality.
- Quotes are **seed marks** (static build has no quote server).
- Reference Rule C bake-off (68.8% CAGR / −12.5% DD / 52% WR) is **not a promise**.
