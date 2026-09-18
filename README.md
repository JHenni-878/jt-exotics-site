# JT Exotics — Inventory Site

Static one-page catalog. No backend, no logins, no trackers. `noindex` is ON until the LF502 license is filed (remove the `<meta name="robots">` line in `index.html` to go public-search visible).

## How Jude updates inventory (phone, no code)
1. Open the **JT Exotics Inventory** Google Sheet (built from `inventory-seed.csv`).
2. Change the **Status** column: `AVAILABLE` / `PENDING` (shows "Deposit Pending") / `SOLD` (greys out, sinks to bottom).
3. Site refreshes itself on next load (published CSV caches ~5 min).
4. New car = new row. Delete a row to remove a car entirely.

## Sheet columns
`Status | Car | Down | Monthly | Term | Miles | City | Photos | Notes`
- **Down/Monthly**: plain numbers fine (8000) — site formats them.
- **Term**: leave blank → shows "Flexible — ask". ⚠️ Only put months if the OWNER's exact wording confirms it.
- **City**: drives the filter chips. Use metro form: "Houston, TX", "Phoenix, AZ".
- **Photos**: comma-separated filenames that exist in `/img/`, e.g. `urus-se-1.jpg, urus-se-2.jpg`. First one = card hero. Blank = classy placeholder.

## Wiring the Sheet (one-time)
1. In the Sheet: File → Share → **Publish to web** → select the tab → **CSV** → Publish. Copy URL.
2. Paste it into `SHEET_CSV_URL` at the top of the `<script>` in `index.html`.
3. Until then the site uses the baked-in inventory in `index.html`.

## Deploy
GitHub repo (JHenni-878) → Settings → Pages → deploy from main. Custom domain later (jtexotics.com/.co) — same flow as allsetsupply.co.

## Guardrails baked in
- No owner names/contacts anywhere. Only CTA = IG DM (@JT_Exotics via ig.me deep link). No phone number on site.
- McLaren listed at Jude's $49,000 quote (never owner net).
- No "licensed/authorized/guaranteed approval" language. Footer says vehicles listed on behalf of private owners.
