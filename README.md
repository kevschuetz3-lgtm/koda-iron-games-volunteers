# Koda Iron Games 2026 — Volunteer Signup

Volunteer signup site for the 6th Annual Koda Iron Games (October 3–4, 2026).

**Live:** https://kevschuetz3-lgtm.github.io/koda-iron-games-volunteers/

## How it works
- Static single-page site (GitHub Pages, `main` branch root). Branding matches the
  Iron Games sponsor site (`iron-games-sponsors`): Anton + Poppins, black / #c13b4a red.
- Form sections: Basic Info → Apparel (shirt size) → Availability (5 shifts +
  "All Weekend" with gift picker) → Experience → Job Preferences.
- Checking **All Weekend** auto-checks and locks all 5 shift slots and reveals the
  gift dropdown (Born Primitive kit / Box Basics kit / PWR Athlete backpack).
- Submit POSTs `{action:'ironGamesVolunteer'}` to the shared Koda Apps Script backend
  (`koda-coaching/apps-script/Code.js`, deploy @51+). The backend:
  - appends to the **"Koda Iron Games Volunteers"** Google Sheet
    (auto-created, script prop `IRON_VOLUNTEERS_SHEET_ID`;
    recover URL via `GET ?action=ironGamesVolunteersInfo`)
  - emails the volunteer a confirmation (reply-to kodaironview@gmail.com)
  - notifies kevschuetz3@gmail.com

## Editing
Edit `index.html`, commit, push — Pages redeploys automatically.
Shift times, roles, sizes, and gift options live in the `SHIFTS` / `ROLES` /
`SIZES` arrays and the `#giftSelect` markup near the bottom of `index.html`.
