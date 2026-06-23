# Multi-Shop Kids Portal

A partner investment tracker for kids' dress shops. Logs each partner's spends (their capital into the shop), withdrawals/repayments, per-partner ledgers, and profit-share splits — across multiple shops. Optional live sync to Google Sheets.

## Run it

- **Locally:** double-click `index.html` to open in any browser.
- **GitHub Pages:** put `index.html` in your repo, push, and open `https://<user>.github.io/<repo>/`.

No build step — it's a single self-contained file.

## Connect Google Sheets (optional)

1. Create a blank Google Sheet → **Extensions → Apps Script**.
2. Paste the Apps Script backend (see `apps-script.gs`) and save.
3. **Deploy → New deployment → Web app**
   - Execute as: **Me**
   - Who has access: **Anyone**
4. Copy the Web App URL (ends in `/exec`).
5. In the portal, open **Sheet Sync**, paste the URL, click **Test Connection**.

The script auto-creates three tabs: `Shops`, `Spends`, `Withdrawals`. Each row is tagged with its shop name, so one Sheet holds every outlet.

## Features

- Per-shop dashboard + **All Shops** overview
- Spends, Withdrawals/Repayments, Partner Ledger
- **Profit Share** — split by capital invested or custom %
- Date-range filter
- Live Google Sheets sync + CSV export

## Sync troubleshooting

| Message | Fix |
|---|---|
| `Failed to fetch` | Page is sandboxed — run on GitHub Pages or locally, not inside a preview. |
| HTML / login page | Set deployment access to **Anyone**; use the `/exec` URL (not `/dev`). |
| Changes not saving | Edited the script? **Deploy → Manage deployments → New version**. |

**Fallback:** `Export CSV` from the portal works anywhere — paste straight into the Sheet.

## Notes

- Each partner's investment = the total they've **spent By**.
- Last write wins on sync, so coordinate simultaneous edits.
- Set the Apps Script time zone (Project Settings → IST) to keep dates accurate.
