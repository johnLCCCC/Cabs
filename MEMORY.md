# Twrite/VAL Website - Local Project Memory

*Created as workaround while claude-mem authentication is down*

---

## Project Overview

**Type**: Valorant-themed student website (BSIT 2nd Year)  
**Repo**: `WEBSITE_TWRITE` on branch `first`  
**Purpose**: All-in-one Valorant hub — guides, agent tierlists, weapons, shop, about

---

## Pages & Features

| Page | Key Features |
|------|--------------|
| `VAL/index.html` | Hero (Hush spotlight), agent tierlist (S→D), merch section, about section |
| `VAL/Meta.html` | Agent tiers by role (Duelist/Initiator/Controller/Sentinel), meta context cards, tier + role + search filter (sticky bar above tier list with data-tier/data-role attributes; fixes Sentinel detection bug; "All Roles" button added to reset role filters without page refresh) |
| `VAL/Guides.html` | Role guides, agent guides (filterable), featured guides (economy/crosshair/callouts/compositions), map guides, 4 modal types |
| `VAL/Weapons.html` | 19 weapons (incl. custom Bandit/Warden), category filter, detail modal with typewriter |
| `VAL/Shop.html` | Merch (sticker/plusie/keychain), VP bundles, multi-step purchase flow (GCash/PayMaya/Card/COD + Riot ID) |
| `VAL/About.html` | Team slider (6 BSIT members), disclaimer |

---

## Data Structures (JS)

- `window.agentsData` — 28 agents with skills, passive, role, image
- `window.weaponsData` — 19 weapons with stats, cost, damage, tips
- `agentGuidesData` — extended agent info (difficulty, combos, mistakes, maps)
- `roleGuidesData` — 4 roles with responsibilities, concepts, checklists
- `featuredGuidesData` — 4 guides (economy, crosshair, callouts, compositions)
- `mapGuidesData` — 13 maps with callouts, tips, tactical/minimap images, game modes

---

## Design System (CSS Variables)

```css
--primary:       #dc143c;   /* crimson */
--primary-text:  #ff6b6b;   /* lighter crimson for text */
--primary-dark:  #b3122b;
--matte-black:   #0f0f0f;
--bg:            var(--matte-black);
--text:          #eaeaea;
--card-bg:       #121212;
--muted:         #b8b8b8;
--nav-height:    64px;
--agents-gap:    16px;
--guides-gap:    16px;
```

**Role colors**: Duelist `#ff4444`, Initiator `#44aaff`, Controller `#8844ff`, Sentinel `#44ff88`

---

## Key Technical Patterns

- **Shared nav**: `nav.js` (hamburger, off-canvas slider, active link, scroll effect)
- **Scroll reveal**: `scroll-anim.js` (IntersectionObserver, `.scroll-reveal` → `.show`)
- **Typewriter animation**: With optional sound, respects `prefers-reduced-motion`
- **Modals**: Consistent pattern — open/close, focus trap, ESC key, click outside
- **Filter buttons**: Fill animation with `--fill-origin` direction
- **Cards**: Hover lift + shadow + border color transition

---

## Team Members

1. John Lourence Cabaluna
2. Eli Ochavo
3. Franck Adam Blanco
4. John Paul Cambaya
5. Peter Natad
6. Nino Katada

---

## Disclaimers

All pages include: "This is a student project for educational purposes only. VALORANT is a trademark of Riot Games, Inc. Not affiliated/endorsed/sponsored. Used under Riot Games' Legal Jibber Jabber policy."

---

