# OnePort365 CRM Mobile

Clickthrough prototype of the OnePort365 CRM for mobile, built on the OnePort 365 design system.

## Open it

- **Single file:** open `standalone.html` in any browser. Everything is inlined, so it can be emailed or shared as one file.
- **From source:** serve the folder and open `index.html`:

  ```bash
  python3 -m http.server 8000
  ```

  then visit http://localhost:8000/.

On a desktop browser it shows in a phone frame with shortcuts to each flow; on a phone it fills the screen. Data is sample data held in memory, so it resets on reload.

## What it covers

- **Deal IDs, RFQs and quotes:** every deal has an ID (`OP-YY-MM-NNN`, e.g. OP-26-11-017). Moving a deal to Qualified raises an RFQ (`RFQ-YY-MM-NNN`, e.g. RFQ-26-11-015) and moving it to Quote issued raises a quote (`Q-YY-MM-NNN`, e.g. Q-26-11-017). Both are linked on the deal card and deal detail, and searchable.
- **Login:** log in with an email and password (show/hide password, keep me logged in, field errors, loading state), forgot password and a "check your email" confirmation. Tap your initials in the top bar to see your account and log out. In the prototype any valid email with any password logs in.
- **Pipeline:** filter deals by stage, search by company, deal owner or contact, and move a deal forward through Prospect → Contacted → Qualified → Quote issued → Closed (Won or Lost), with an optional comment on each move. Deals can't move back.
- **New deal:** pick an existing company and contact, or add a new company and contact in the same form.
- **Deal detail:** deal information only, like the desktop deal page: stage, contact, deal amount, product, date created, sales owner, class and note.
- **Deal activities:** from the Activity tab, a deal's activities (paged at 10, scrollable) with Add activity, and the comments left when the deal was moved.
- **Companies:** company details (name, class, deal owner), contacts and a deal count. Add company also captures its main contact.
- **Activity:** every activity logged against a deal (meeting type, date, time, duration, comment), filterable by deal owner. Each activity has an Edit button to change its meeting type, date, time, duration or comment. Each activity is tied to the deal's stage when it was logged.
- Lists are paginated at 5 per page.

## Files

| File | Purpose |
|---|---|
| `index.html` | Page markup and bottom sheets |
| `mobile.css` | Styles, built only from the design tokens |
| `mobile.js` | Sample data and all interactions |
| `design/tokens.css` | OnePort 365 design tokens (colour, type, spacing, radius, elevation) |
| `design/DESIGN_SYSTEM.md` | Design system rules the prototype follows |
| `standalone.html` | Generated single-file copy of the three source files |
