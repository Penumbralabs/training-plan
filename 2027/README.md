# Backcountry Archery Training Plan — September 2027

Annual periodized training plan for a 9-day backcountry archery mule deer hunt.

Built on principles from:
- *Training for the New Alpinism* — Steve House & Scott Johnston
- *Training for the Uphill Athlete* — Steve House, Scott Johnston & Kilian Jornet

## Objective

9-day self-supported backcountry archery hunt at 6000-8000ft elevation. ~60lb pack-in (long approach), 90-110lb pack-out loads. Longer and harder than 2026 hunt.

## How It Works

`index.html` is a single-page training tracker hosted via GitHub Pages. Checkbox state syncs across devices using the GitHub API + a Personal Access Token stored in `localStorage`.

### Setup

1. Push this repo to GitHub
2. Enable GitHub Pages (Settings → Pages → Deploy from branch: `main`)
3. Generate a fine-grained PAT with read/write access to Contents for this repo
4. Open the Pages URL, enter your PAT when prompted
5. Checkboxes sync to `state/checkboxes.json` in the repo

### Files

```
├── README.md              # This file
├── index.html             # Training plan tracker (single-page app)
└── state/
    └── checkboxes.json    # Checkbox progress state (synced via GitHub API)
```

## Periodization Overview

| Phase | Dates | Weeks | Focus |
|-------|-------|-------|-------|
| Hunt + Transition | Sep 15 – Oct 12, 2026 | 4 | Recovery, general movement, address knee |
| Base 1 (Aerobic + General Strength) | Oct 13 – Dec 21, 2026 | 10 | Aerobic volume, strength patterns |
| Base 2 (Aerobic + Max Strength) | Dec 22, 2026 – Feb 9, 2027 | 7 | Peak strength, continued aerobic |
| GS Race Mini-Peak | Feb 10 – Feb 16, 2027 | 1 | Short taper, race, recover |
| Base 3 (Aerobic + Strength Maintenance) | Feb 17 – Apr 13, 2027 | 8 | Volume peak, maintain strength |
| Specific 1 (Muscular Endurance) | Apr 14 – Jun 8, 2027 | 8 | Weighted carries, ME protocol, eccentric progression |
| Specific 2 (Hunt Simulation) | Jun 9 – Aug 17, 2027 | 10 | Full-load simulations, dress rehearsals |
| Taper | Aug 18 – Aug 31, 2027 | 2 | Volume drops 50%, intensity maintained |
| Hunt Week | Sep 1+, 2027 | — | Final prep, pack-in, hunt |
