# BANANA://trade (static PWA)

Karl Smith’s private **Banana paper desk** for [BananaPatterns](https://bananapatterns.com) research — India NSE breakout / VCP playbook. Complements BananaPatterns (text credit only; not affiliated; no logo copy).

This is the **phone-installable, no-Node** build: plain HTML / JS / CSS. The paper book lives in `localStorage` (not SQLite). Host it on GitHub Pages (`KarlSmith2023/banana`), open `index.html` as a file, or serve the folder as `/` or `/banana/`.

> **BananaPatterns has no official API.** Banana does not invent vendor endpoints. Paste JSON on Scanner / API to ingest your own setups.
>
> **Not financial advice.** Paper only until the live gate clears.

## What’s included

- SPA: Markets · Trade · API (ingest) · Brief · Journal · Playbook (+ Overview / Positions / Charts under More)
- **BANANA://trade** phone UI: BananaPatterns **yellow** (#F5C518) on near-black (not DESK/LONA neon green), monospace headers, LIVE/PAPER pills, metric chips, banana chip, host badge `banana · complements BananaPatterns.com`, paper ticket
- Bottom nav: MARKETS · TRADE · API · BRIEF · MORE · JOURNAL
- Big green **PLACE PAPER ORDER** CTA while live lock active · **Keep paper** · Short N/A for India cash
- Dual currency **INR + GBP** (default FX **129.26**)
- Start equity **£800** = **₹1,03,408**
- Seed setups as-of **Fri 11 Sep 2026**: KPL, BLUESTONE, CPPLUS, DIACABS, FILATEX, KABRAEXTRU, WHEELS
- Working paper ticket (Market / Limit / Stop / Stop-Limit), positions, attached 8% stop + 50-EMA trail
- Live button **hard-locked · 60 sessions left** (stub even when unlocked)
- PWA: `manifest.webmanifest` (name/short_name **Banana**), `sw.js`, icons under `./icons/`

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

All assets are **relative** (`./app.js`, `./styles.css`, `./icons/...`). There are **no leading-slash** URLs, so Banana works at:

- `https://KarlSmith2023.github.io/banana/`
- `https://<user>.github.io/banana/`
- opening `index.html` directly (`file://`) — PWA install still needs HTTPS or localhost

Routing is hash-based (`index.html#/overview`, `#/ticket?symbol=FILATEX`).

## GitHub Pages (`KarlSmith2023/banana`)

1. Push this folder to the `banana` repo root (or `/docs` if that is your Pages source).
2. Keep `.nojekyll` so Pages does not rewrite files.
3. Enable Pages on the branch.
4. Open `https://KarlSmith2023.github.io/banana/` (or `.../index.html`).

`404.html` sends unknown paths such as `/scanner` back to `index.html#/scanner`.

### Install as an app (Add to Home Screen)

**Phone target:** BANANA://trade dark-terminal blotter. After install, launch from the home screen for the standalone paper desk.

Needs HTTPS (GitHub Pages) or `localhost`. `file://` runs the blotter but cannot register a service worker.

**iPhone / iPad (Safari)**

1. Open Banana in **Safari**.
2. Share → **Add to Home Screen** → name it **Banana** → Add.
3. Launch from the home screen (standalone, `apple-mobile-web-app-capable`).

**Android (Chrome)**

1. Open Banana in Chrome.
2. Menu → **Install app** / **Add to Home screen**.

**Windows (Chrome or Edge)**

1. Open Banana.
2. Address-bar install icon, or menu → **Install Banana** / **Apps → Install this site as an app**.

## Reset

Playbook → **Reset paper book to seed** (or clear site data / `localStorage` key `desk-static-book-v1`).

## Honesty

- No official BananaPatterns API — do not expect Banana to scrape or call one.
- Complements BananaPatterns (text-only credit; not their logo or brand assets).
- Paper fills are simulated (10 bps slippage model); not exchange-quality.
- Quotes are **seed marks** (static build has no quote server).
- Reference Rule C bake-off (68.8% CAGR / −12.5% DD / 52% WR) is **not a promise**.
