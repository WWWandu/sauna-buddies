# Sauna Buddies

The official digital home and meeting archive for the Sauna Buddies group — built as a static site for GitHub Pages.

**Guiding philosophy:** *"Unity does not mean sameness; it means oneness of purpose. Oneness is the secret of all things."*

## What this is

A lightweight, dependency-free HTML/CSS/JS website with six sections:

- **Home** — introduction, philosophy, and quick links
- **About** — the group's story and how it operates
- **Meetings** — an archive of meeting minutes, starting with 14 August 2026
- **Members** — a member directory (currently placeholders)
- **Leadership** — confirmed and open leadership roles
- **Constitution** — placeholder page, marked "Coming Soon"

All content is sourced directly from the group's actual meeting minutes. Anything not yet confirmed (member profiles, most leadership roles, the constitution itself) is clearly marked as a placeholder — nothing has been invented.

## Structure

```
/
├── index.html
├── about.html
├── meetings.html          ← archive / index of all meetings
├── members.html
├── leadership.html
├── constitution.html
├── meetings/
│   └── 2026-08-14.html    ← one file per meeting
├── css/
│   └── style.css          ← single shared stylesheet (design tokens at the top)
├── js/
│   └── main.js            ← mobile nav toggle
└── assets/
    └── favicon.svg
```

## Adding a new meeting

1. Copy `meetings/2026-08-14.html` to a new file named after the date, e.g. `meetings/2026-09-11.html`.
2. Update the meta grid (date, venue, chairperson, secretary, attendance) and each `<details>` section with the new content.
3. Open `meetings.html` and add one new `.meeting-row` entry near the top, linking to the new file. Move the previous "latest meeting" row down if you like, or leave the archive in chronological order.
4. Optionally update the "Latest meeting" card on `index.html` to point to the new meeting.

No build step, template engine, or JavaScript changes are required — every page is plain HTML sharing the one stylesheet.

## Adding members or leadership

Edit `members.html` / `leadership.html` directly. Each entry is a `.card` — copy an existing placeholder card, fill in real details, and remove the `.placeholder-card` wrapper and label once information is confirmed.

## Publishing the constitution

Replace the contents of `constitution.html` with the finalised constitution once it's adopted. The planned section list (Name & Identity, Purpose & Objectives, Membership, Leadership & Governance, Meetings, Welfare, Financial Contributions, Financial Management, Decision-Making, Code of Conduct, Amendments, Dissolution) is already laid out as cards you can convert into full sections.

## Local preview

No build tools needed — just open `index.html` in a browser, or serve the folder locally:

```bash
python3 -m http.server 8000
```

## Deploying to GitHub Pages

1. Push this repository to GitHub as a **public** repo.
2. In the repo, go to **Settings → Pages**.
3. Under "Build and deployment", set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Save. The site will be published at `https://<username>.github.io/<repo-name>/`.

## Design notes

- **Palette:** deep earthy brown, charcoal, warm gold/ochre, terracotta, muted green, warm cream.
- **Type:** Fraunces (display/serif) for headings, Karla (sans-serif) for body text — loaded from Google Fonts.
- **Motif:** a simple circle-and-diamond mark (unity / oneness) used as the site's icon and a subtle geometric texture in the homepage hero.
