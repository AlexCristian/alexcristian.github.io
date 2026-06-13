# Goleta Trip Plan — Design Spec
_Created: 2026-06-13_

## Overview

Single-file HTML travel plan for a Jun 28–Jul 5 trip to Goleta, CA. Primary purpose: evaluate Goleta/Santa Barbara as a potential relocation destination while working remotely from the Google office in Goleta. Friends join for the 4th of July long weekend.

Output: `/Users/acristian/Documents/website/goleta-trip/index.html`
Deploy: `master` branch → GitHub Pages (same repo as Colorado plan)

---

## Trip Facts

| Field | Value |
|-------|-------|
| Dates | Jun 28 – Jul 5, 2026 |
| Arrive | LAX, Jun 28 ~8pm |
| Depart | LAX, Jul 5 ~midnight (going into Jul 6) → leave Goleta ~9:30pm Jul 5 |
| Transport | Rental car, picked up at LAX on arrival, returned Jul 5 |
| Accommodation | Airbnb, residential Goleta (Hollister Ave corridor or between UCSB and Google office) |
| Friends | 2 friends join Jul 3 (Friday) afternoon/evening, leave Jul 5 early afternoon |
| Work | Mon Jun 29 – Fri Jul 3, Google office in Goleta (full days) |

---

## Evaluation Priorities

The plan is structured as a relocation evaluation. Every evening activity should implicitly answer: *would I do this again if I lived here?*

Priorities (in order of user weight):
1. Outdoor access (beaches, hiking, trails)
2. Community/vibe (residential feel vs. tourist/college town)
3. Proximity/commute (how the Google office fits daily life)
4. Nightlife & culture (live music, bars, things to do after work)

---

## Day-by-Day Structure

### Day 0 — Sun Jun 28: Arrival
- Land LAX ~8pm
- Pick up rental car
- Drive to Goleta (~1.5–2hr on US-101)
- Check into Airbnb (~10–10:30pm)
- Late grocery run or takeout

### Days 1–5 — Mon Jun 29–Fri Jul 3: Work Week
Each day: work at Google Goleta office. Evenings structured as deliberate probes of local life.

| Day | Evening Focus | Area |
|-----|--------------|------|
| Mon Jun 29 | Neighborhood walk, commute recon, local dinner | Goleta |
| Tue Jun 30 | Jazz at SOhO Music Club, Funk Zone / State St dinner | Santa Barbara |
| Wed Jul 1 | Shooting range (pistol/rifle) | Goleta area |
| Thu Jul 2 | Woodworking shop or makerspace scout; Goleta Beach sunset | Goleta |
| Fri Jul 3 | Friends arrive → harbor dinner + State St walk | Santa Barbara |

### Day 6 — Sat Jul 4: Independence Day (with friends)
- Morning: Inspiration Point hike (early, before heat) — 3.5mi RT, ~900ft gain
- Midday: East Beach or Goleta Beach BBQ setup
- Afternoon: Beach, swimming, chill
- Evening: Santa Barbara waterfront fireworks (East Beach / Chase Palm Park)
- Alt fireworks: Carpinteria (~20min south, more local feel)

### Day 7 — Sun Jul 5: Last Day
- Morning: Rattlesnake Canyon hike with friends (~3mi RT, creek crossings)
- Brunch / coffee crawl in Goleta or SB
- Friends depart early afternoon
- Late afternoon: solo wrap-up, last spot
- ~9:30pm: depart for LAX
- ~midnight: flight to NYC

---

## User Interests to Weave In

| Interest | How it appears in plan |
|----------|----------------------|
| Hockey | Visit a local ice rink; check adult league schedules (UCSB Ice Arena or similar); see if a local/college drop-in game is available — user plays hockey, not just watches |
| Shooting | Wed evening: local pistol/rifle range (verify: Santa Barbara Rifle & Pistol Club or similar) |
| Jazz | Tue evening: SOhO Restaurant & Music Club, SB's main jazz/live music venue |
| Country music | Alt drawer or evening option: find a country night or venue in the SB area (verify — may be limited, but worth scouting for relocation fit) |
| Classical music | Alt drawer: Lobero Theatre, Granada Theatre (verify Jul programming) |
| Woodworking | Thu evening: makerspace or hobby shop (verify: Rockler/Woodcraft presence in SB area, or UCSB makerspace) |
| Hiking | Weekend primary + alt drawers on multiple days |

---

## Alt Drawers

Every stop should have an alt drawer. Hiking trails appear as alts on at least:
- Mon/Thu evenings (lighter evening hikes)
- Sat Jul 4 (Cold Spring Trail as alt to Inspiration Point)
- Sun Jul 5 (Seven Falls as alt to Rattlesnake Canyon)

Named hiking alts to include (all need AllTrails + Komoot):
- **Inspiration Point** (3.5mi RT, ~900ft, primary Sat)
- **Rattlesnake Canyon** (3mi RT, creek crossings, primary Sun)
- **Cold Spring Trail East Fork** (longer, half-day option)
- **Seven Falls** (scrambling, waterfall payoff)
- **Lizard's Mouth** (boulder scramble, sunset spot)
- **Gaviota State Park** (beach + trail + hot springs, north of Goleta)

---

## Design System

Follow Colorado plan exactly:
- CSS variables, component classes, JS verbatim from reference
- Accent color: deep ocean blue `#1a4a6b` (replaces Colorado's forest green `#2d5a3d`); accent-light `#e6eef5`
- Header: mountain silhouette SVG → coastline/wave SVG inline
- Carousels: Unsplash CDN only, verify all URLs 200 before committing
- Drive pills: departure time + duration + destination, every segment
- Buffer blocks: meals, sleep, rest only — never drives
- Booking checklist: collapsible, 4 urgency tiers (🔴🟡🟢🔵), web-search verified

---

## Booking Checklist Items (to verify via web search)

- 🔴 Airbnb in residential Goleta (book ASAP — Jul 4 weekend will be tight)
- 🔴 Car rental at LAX (Jul 4 weekend surge pricing)
- 🟡 SOhO Music Club — check Jul 1 schedule, reserve if ticketed show
- 🟡 Fireworks viewing spot (East Beach fills early — arrive by 7pm)
- 🟢 Inspiration Point / Rattlesnake Canyon — no permit required (verify)
- 🟢 Shooting range — walk-in or reservation (verify)
- 🔵 Lobero Theatre / Granada Theatre — check Jul programming
- 🔵 Gaviota State Park — day-use fee (verify current amount)

---

## Facts to Verify via Web Search

- SOhO Music Club: current schedule, cover charges, reservation policy
- Santa Barbara 4th of July fireworks: exact location, start time, viewing logistics
- Shooting ranges near Goleta: name, walk-in policy, what calibers/types
- Woodworking shops/makerspaces: Rockler SB? UCSB makerspace public access?
- Inspiration Point: current trail conditions, parking
- Rattlesnake Canyon: permit requirements (none expected but verify)
- Lobero / Granada: July 2026 programming
- Ice rinks near Goleta: UCSB Ice Arena public skate/drop-in hours, adult league schedules
- Country music venues in SB: any regular country nights or dedicated venues
- Car rental LAX: pickup logistics (on-site vs. shuttle)

---

## File Location & Deployment

- Output: `/Users/acristian/Documents/website/goleta-trip/index.html`
- Repo: `/Users/acristian/Documents/website` (master branch)
- Deploy: `git push origin master` when done
- No amendments to published commits
