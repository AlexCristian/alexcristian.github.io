# Goleta Trip Plan — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a single-file HTML travel plan for a Jun 28–Jul 5, 2026 trip to Goleta/Santa Barbara, CA, matching the design system of the Colorado reference plan and deployed to GitHub Pages.

**Architecture:** Single self-contained HTML file with inlined CSS and JS. No build step. Follows the Colorado trip plan component pattern exactly (stop-cards, drive-pills, buffer-blocks, alt-drawers, carousels, booking checklist). Adapted accent color: deep ocean blue `#1a4a6b`.

**Tech Stack:** HTML/CSS/JS, Unsplash CDN images (verified 200), Wikimedia Commons for landmark-specific shots, Google Maps drive embeds, Komoot trail embeds for hike stops, AllTrails links.

---

## Key File Paths

| Role | Path |
|------|------|
| **Output** | `/Users/acristian/Documents/website/goleta-trip/index.html` |
| **Colorado reference** | `/Users/acristian/Documents/Claude/Projects/Colorado travel plan/colorado-trip/index.html` |
| **Design spec** | `/Users/acristian/Documents/website/docs/superpowers/specs/2026-06-13-goleta-trip-design.md` |
| **Template rules** | `/Users/acristian/Documents/Claude/travel-plan-template.md` |
| **Repo root** | `/Users/acristian/Documents/website` (deploy branch: `master`) |

---

## Trip Summary (for reference while building)

| Field | Value |
|-------|-------|
| Arrive | LAX Sun Jun 28 ~8pm → rental car → Goleta ~10pm |
| Work | Mon Jun 29 – Fri Jul 3 (Google office, Goleta) |
| Friends | Arrive Fri Jul 3 afternoon, leave Sun Jul 5 early afternoon |
| Depart | LAX ~midnight going into Jul 6 (leave Goleta ~9:30pm Jul 5) |
| Airbnb | Residential Goleta, Hollister Ave corridor |
| Transport | Rental car at LAX, returned Jul 5 |

### Weekday Evening Map
| Day | Focus | Area |
|-----|-------|------|
| Mon Jun 29 | Neighborhood walk, commute recon, local dinner | Goleta |
| Tue Jun 30 | Jazz at SOhO Music Club + Funk Zone dinner | Santa Barbara |
| Wed Jul 1 | Shooting range | Goleta area |
| Thu Jul 2 | Woodworking shop/makerspace + Goleta Beach sunset | Goleta |
| Fri Jul 3 | Friends arrive → harbor dinner + State St walk | Santa Barbara |
| Sat Jul 4 | Inspiration Point hike → beach BBQ → fireworks | SB/Goleta |
| Sun Jul 5 | Rattlesnake Canyon → brunch → friends depart → LAX | SB → LAX |

### User Interests
- **Hockey:** Plays hockey — find ice rink (UCSB Ice Arena), adult leagues, sports bar for watching games
- **Shooting:** Pistol/rifle range near Goleta
- **Jazz:** SOhO Restaurant & Music Club (SB)
- **Country music:** Any country nights/venues in the area
- **Classical music:** Lobero Theatre, Granada Theatre (verify Jul programming)
- **Woodworking:** Makerspace or hobby shop (Rockler/Woodcraft/UCSB shop)
- **Hiking:** Weekend primary activity + alt drawers throughout

---

## Task 1: Research — Verify All Facts via Web Search

This task must be completed before writing any stop descriptions. Do NOT guess facts.

**Files:** none (produces notes used in Tasks 3–10)

- [ ] **Step 1: Santa Barbara 4th of July fireworks**
  Search: "Santa Barbara 4th of July fireworks 2026 location time"
  Find: exact venue (East Beach? Chase Palm Park?), start time, viewing tips, whether tickets needed, parking.

- [ ] **Step 2: Shooting ranges near Goleta**
  Search: "shooting range Goleta Santa Barbara pistol rifle"
  Find: name, address, walk-in vs reservation policy, calibers/disciplines allowed, hours, cost.

- [ ] **Step 3: Ice rink / hockey near Goleta**
  Search: "ice rink Goleta Santa Barbara UCSB ice arena hockey"
  Find: UCSB Ice Arena public skate hours, adult league info, drop-in hockey sessions, cost.

- [ ] **Step 4: SOhO Music Club**
  Search: "SOhO Restaurant Music Club Santa Barbara July 2026"
  Find: address, cover charges, reservation policy, whether tickets needed in advance.

- [ ] **Step 5: Woodworking shops / makerspaces**
  Search: "woodworking shop makerspace Santa Barbara Goleta Rockler Woodcraft"
  Find: specific name, address, whether public access or membership needed, hours.

- [ ] **Step 6: Inspiration Point trail — Santa Barbara**
  Search: "Inspiration Point Santa Barbara trail conditions parking 2026"
  Find: AllTrails URL, trailhead parking, permit requirements, distance/gain confirmation, Komoot tour ID.

- [ ] **Step 7: Rattlesnake Canyon trail**
  Search: "Rattlesnake Canyon Santa Barbara trail AllTrails"
  Find: AllTrails URL, distance/gain, trailhead parking, any permit requirements, Komoot tour ID.

- [ ] **Step 8: Country music venues in SB**
  Search: "country music bar venue Santa Barbara"
  Find: any specific venue that hosts country nights.

- [ ] **Step 9: Lobero Theatre / Granada Theatre July 2026**
  Search: "Lobero Theatre Santa Barbara July 2026 schedule" and "Granada Theatre Santa Barbara July 2026"
  Find: any classical/jazz performances in early July.

- [ ] **Step 10: Car rental at LAX**
  Search: "LAX car rental terminal shuttle how it works"
  Find: whether on-site or shuttle-based pickup, typical logistics.

- [ ] **Step 11: Gaviota State Park**
  Search: "Gaviota State Park day use fee 2026"
  Find: current entry fee, whether reservation needed, what trails/hot springs are accessible.

- [ ] **Step 12: Sports bar for hockey near Goleta/SB**
  Search: "sports bar Santa Barbara Goleta hockey"
  Find: one specific bar name for the alt drawer.

- [ ] **Commit notes** — no commit needed; keep findings in memory for Tasks 3–10.

---

## Task 2: Find and Verify Unsplash Image URLs

Every carousel needs 2–3 images. Use ONLY the long-hash Unsplash format:
`https://images.unsplash.com/photo-XXXXXXXXXX-XXXXXXXXXXXX?w=900&q=80&auto=format&fit=crop`

Never use short-hash Unsplash URLs (e.g. `images.unsplash.com/AbCdEf`) — they return 404.
Use Wikimedia Commons only for landmark-specific shots with no Unsplash equivalent.

**Files:** none (produces URLs used in Tasks 5–10)

- [ ] **Step 1: Find images for each location**

  Find 2–3 verified Unsplash (or Wikimedia) URLs for each:
  - LAX airport arrival / rental car
  - Goleta neighborhood / US-101 coastal drive
  - Santa Barbara State Street / Funk Zone
  - SOhO Music Club or SB live music scene (generic jazz bar OK)
  - Shooting range (generic pistol range OK if no SB-specific)
  - Goleta Beach / Goleta coastline
  - UCSB Ice Arena or hockey rink
  - Inspiration Point Santa Barbara (panoramic view)
  - Rattlesnake Canyon Santa Barbara (creek/gorge)
  - East Beach Santa Barbara / 4th of July beach
  - Santa Barbara fireworks or waterfront evening
  - Stearns Wharf / SB Harbor
  - Cold Spring Trail (alt hike)
  - Seven Falls (alt hike)
  - Lizard's Mouth rock formations
  - Gaviota State Park

- [ ] **Step 2: Verify every URL returns HTTP 200**

  ```bash
  curl -sIL "https://images.unsplash.com/photo-XXXXXXXXXX-XXXXXXXXXXXX?w=900&q=80&auto=format&fit=crop" | grep "HTTP"
  ```
  Expected: `HTTP/2 200`
  Remove any that return 404 and find replacements.

- [ ] **No commit needed** — URLs go directly into the HTML in later tasks.

---

## Task 3: Scaffold HTML — CSS, JS, Header

Copy the full CSS and JS from the Colorado reference. Update: accent color, header, title.

**Files:**
- Create: `/Users/acristian/Documents/website/goleta-trip/index.html`
- Read first: `/Users/acristian/Documents/Claude/Projects/Colorado travel plan/colorado-trip/index.html`

- [ ] **Step 1: Create the file with full Colorado CSS verbatim**

  Copy lines 1–564 of the Colorado reference (everything through `</style></head>`).
  Then make these targeted edits:

  ```html
  <!-- Title -->
  <title>Goleta · Jun 28–Jul 5</title>

  <!-- Color variables — replace these 2 lines in :root -->
  --accent: #1a4a6b;
  --accent-light: #e6eef5;
  ```

  Keep ALL other CSS variables and classes exactly as in the Colorado file.

- [ ] **Step 2: Add the header**

  Replace Colorado's mountain SVG header with a coastal wave version:

  ```html
  <header class="trip-header">
    <h1>🌊 Goleta · Santa Barbara</h1>
    <div class="meta">
      <span>📅 Jun 28–Jul 5, 2026</span>
      <span>🚗 Rental Car · LAX</span>
      <span>📍 Airbnb · Goleta</span>
      <span>🏢 Google Office · Goleta</span>
      <span>🎆 4th of July with friends</span>
    </div>
  </header>
  ```

  For the `trip-header::before` SVG background, replace the mountain path with a wave:
  ```
  M0 160 Q50 120 100 160 Q150 200 200 160 Q250 120 300 160 Q350 200 400 160 L400 200 L0 200Z
  ```

- [ ] **Step 3: Open the container div**

  ```html
  <div class="container">
  ```

- [ ] **Step 4: Copy the JS block verbatim** from the Colorado reference (lines 1507–end).
  It handles: booking checklist toggle, alt-drawer toggles, iframe titles, carousel autoplay.
  No changes needed.

- [ ] **Step 5: Verify file structure**

  File should have: `<!DOCTYPE html>` → `<head>` with CSS → `<body>` → `<header>` → `<div class="container">` (open, no content yet) → `</div>` → `<footer>` → `<script>` → `</html>`

- [ ] **Step 6: Commit**

  ```bash
  cd /Users/acristian/Documents/website
  git add goleta-trip/index.html
  git commit -m "Scaffold Goleta trip plan HTML (CSS + header)"
  ```

---

## Task 4: Booking Checklist

Insert immediately after `<div class="container">`, before Day 0.

**Files:** Modify `/Users/acristian/Documents/website/goleta-trip/index.html`

Use facts verified in Task 1. Count items and update the toggle hint summary accordingly.

- [ ] **Step 1: Insert the booking checklist block**

  ```html
  <!-- ═══════════════════════════════════
       BOOKING CHECKLIST
  ════════════════════════════════════ -->
  <div class="booking-checklist">
    <button class="bc-toggle" type="button" aria-expanded="false">
      <span class="bc-heading">📋 Book Before You Go</span>
      <span class="bc-toggle-hint">2 🔴 · 3 🟡 · 3 🟢 · 3 🔵 — 11 items</span>
      <span class="bc-arrow">▼</span>
    </button>
    <div class="bc-body">
    <div class="bc-subtitle">🔴 sells out — book immediately · 🟡 book 2–4 weeks out · 🟢 walk-in / pay at gate · 🔵 only needed if you choose that alt</div>

    <div class="bc-section">🔴 Sells out — book the moment dates are confirmed</div>

    <div class="bc-row">
      <span class="bc-urgency red"></span>
      <div>
        <div class="bc-name">Airbnb — residential Goleta (Hollister Ave / near Google office)</div>
        <div class="bc-meta">Book immediately — Jul 4th weekend is peak demand. Filter for 3 guests, full kitchen, private parking. Avoid Isla Vista (too college-town) and downtown SB (too tourist). Target: Goleta neighborhoods 93117.</div>
      </div>
      <span class="bc-day">Jun 28</span>
    </div>

    <div class="bc-row">
      <span class="bc-urgency red"></span>
      <div>
        <div class="bc-name">Rental Car — LAX pickup Jun 28, return Jul 5</div>
        <div class="bc-meta">Jul 4th weekend surge — book now. [INSERT VERIFIED PRICE RANGE AND CAR TYPE]. LAX rental cars use an off-site consolidated facility; shuttle from Terminal [INSERT TERMINAL] takes ~10 min.</div>
      </div>
      <span class="bc-day">Jun 28</span>
    </div>

    <div class="bc-section">🟡 Book 2–4 weeks out</div>

    <div class="bc-row">
      <span class="bc-urgency amber"></span>
      <div>
        <div class="bc-name"><a href="https://sohosb.com" target="_blank">SOhO Music Club — check July schedule ↗</a></div>
        <div class="bc-meta">[INSERT VERIFIED INFO: cover charge, reservation policy, Tue Jun 30 or any other evening]. Address: 1221 State St, Santa Barbara.</div>
      </div>
      <span class="bc-day">Tue Jun 30</span>
    </div>

    <div class="bc-row">
      <span class="bc-urgency amber"></span>
      <div>
        <div class="bc-name">4th of July Fireworks — [INSERT VERIFIED LOCATION]</div>
        <div class="bc-meta">[INSERT: start time, viewing spot logistics, whether tickets needed, parking advice]. Arrive by [INSERT TIME] for a good spot.</div>
      </div>
      <span class="bc-day">Sat Jul 4</span>
    </div>

    <div class="bc-row">
      <span class="bc-urgency amber"></span>
      <div>
        <div class="bc-name">[INSERT VERIFIED ICE RINK NAME] — check public skate / drop-in hockey hours</div>
        <div class="bc-meta">[INSERT: schedule, adult league info, cost]. Reserve if drop-in session requires it.</div>
      </div>
      <span class="bc-day">TBD evening</span>
    </div>

    <div class="bc-section">🟢 Walk-in / pay at gate</div>

    <div class="bc-row">
      <span class="bc-urgency green"></span>
      <div>
        <div class="bc-name">Inspiration Point — no permit required</div>
        <div class="bc-meta">Free trail, no reservation. Trailhead parking at [INSERT PARKING LOCATION]. Arrive early on Jul 4 to beat heat. [VERIFY: no seasonal closure].</div>
      </div>
      <span class="bc-day">Sat Jul 4</span>
    </div>

    <div class="bc-row">
      <span class="bc-urgency green"></span>
      <div>
        <div class="bc-name">Rattlesnake Canyon — no permit required</div>
        <div class="bc-meta">Free trail. Trailhead at [INSERT]. Street parking available. No reservation needed. [VERIFY: current trail conditions].</div>
      </div>
      <span class="bc-day">Sun Jul 5</span>
    </div>

    <div class="bc-row">
      <span class="bc-urgency green"></span>
      <div>
        <div class="bc-name">[INSERT SHOOTING RANGE NAME] — walk-in</div>
        <div class="bc-meta">[INSERT: address, hours, calibers allowed, cost per session]. [VERIFY: walk-in policy or reservation needed].</div>
      </div>
      <span class="bc-day">Wed Jul 1</span>
    </div>

    <div class="bc-section">🔵 Only if you choose this alt</div>

    <div class="bc-row">
      <span class="bc-urgency blue"></span>
      <div>
        <div class="bc-name">Lobero Theatre / Granada Theatre — check July programming</div>
        <div class="bc-meta">[INSERT: any classical/jazz performances in early Jul]. Tickets at [INSERT URL].</div>
      </div>
      <span class="bc-day">Any evening</span>
    </div>

    <div class="bc-row">
      <span class="bc-urgency blue"></span>
      <div>
        <div class="bc-name">Gaviota State Park — day use fee</div>
        <div class="bc-meta">[INSERT: current fee, reservation needed?, what's accessible — trails, hot springs, beach]. ~[INSERT DISTANCE] from Goleta.</div>
      </div>
      <span class="bc-day">Any evening</span>
    </div>

    <div class="bc-row">
      <span class="bc-urgency blue"></span>
      <div>
        <div class="bc-name">[INSERT WOODWORKING SHOP NAME]</div>
        <div class="bc-meta">[INSERT: address, hours, whether membership needed or drop-in allowed]. Great for scoping out whether the local maker scene fits your hobby.</div>
      </div>
      <span class="bc-day">Thu Jul 2</span>
    </div>

    </div><!-- bc-body -->
  </div><!-- booking-checklist -->
  ```

  **After inserting:** replace all `[INSERT ...]` placeholders with facts from Task 1. Zero placeholders allowed in the final file.
  Update the toggle-hint count to match actual items: `X 🔴 · Y 🟡 · Z 🟢 · W 🔵 — N items`.

- [ ] **Step 2: Commit**

  ```bash
  git add goleta-trip/index.html
  git commit -m "Add booking checklist to Goleta trip plan"
  ```

---

## Task 5: Day 0 — Sunday Jun 28 (Arrival)

- [ ] **Step 1: Insert Day 0 block after the booking checklist**

  ```html
  <!-- ═══════════════════════════════════
       DAY 0 — Sun Jun 28 — Arrival
  ════════════════════════════════════ -->
  <div class="day-block" id="day0">
    <div class="day-header">
      <span class="day-label">Day 0</span>
      <span class="day-date">Sunday, June 28 · Arrival</span>
    </div>
    <div class="timeline">

      <!-- Land at LAX -->
      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">✈️ Land at LAX + Pick Up Rental Car</span>
          <span class="stop-time">~8:00pm</span>
        </div>
        <div class="carousel" data-autoplay>
          <div class="carousel-track">
            <img src="[VERIFIED UNSPLASH LAX URL]" alt="LAX terminal">
            <img src="[VERIFIED UNSPLASH US-101 COASTAL URL]" alt="US-101 Pacific Coast Highway">
          </div>
          <button class="carousel-btn carousel-prev">&#8249;</button>
          <button class="carousel-btn carousel-next">&#8250;</button>
          <div class="carousel-dots"><span class="dot active"></span><span class="dot"></span></div>
        </div>
        <div class="stop-desc">Land at LAX ~8pm. Rental car pickup: [INSERT LOGISTICS from Task 1 — shuttle or on-site, terminal, directions]. Head north on US-101 — it's a coastal drive even at night, city lights giving way to the Pacific. Budget ~1hr 45min with light Sunday evening traffic; can be longer if there's a jam around Malibu or Ventura.</div>
        <div class="stop-tags">
          <span class="tag tag-culture">Arrival</span>
        </div>
      </div>

      <!-- Drive to Goleta -->
      <div class="drive-segment">
        <div class="drive-dot"></div>
        <div class="drive-pill">
          🚗 Leave LAX ~8:30pm · ~1 hr 45 min · Goleta
          <a href="https://www.google.com/maps/dir/Los+Angeles+International+Airport,+CA/Goleta,+CA" target="_blank">Open in Maps ↗</a>
        </div>
        <div class="map-embed"><iframe src="https://maps.google.com/maps?saddr=33.9425,-118.4081&daddr=34.4358,-119.8276&output=embed" loading="lazy" title="Driving directions map"></iframe></div>
      </div>

      <div class="airbnb-note">
        <div class="airbnb-dot"></div>
        <div><strong>🏠 Check into Airbnb — Goleta</strong> — Residential neighborhood near the Hollister Ave corridor, 10–15 min from the Google office. Look for a place with a full kitchen and parking. Arrive ~10:15–10:30pm. Grab groceries at the Von's or Trader Joe's on Hollister if it's still open.</div>
      </div>

      <div class="buffer-block buffer-sleep">
        <div class="buffer-dot"></div>
        🌙 ~10:30pm — Sleep · Goleta Airbnb
      </div>

    </div>
  </div>
  ```

  Replace all `[VERIFIED UNSPLASH ... URL]` with URLs verified in Task 2.

- [ ] **Step 2: Commit**

  ```bash
  git add goleta-trip/index.html
  git commit -m "Add Day 0 arrival (LAX → Goleta)"
  ```

---

## Task 6: Workweek Days — Mon Jun 29 through Thu Jul 2

Each day follows the same structure: work all day (implicit, not shown), then evening activities.

**Files:** Modify `/Users/acristian/Documents/website/goleta-trip/index.html`

- [ ] **Step 1: Insert Day 1 — Mon Jun 29 (Goleta recon)**

  ```html
  <!-- ═══════════════════════════════════
       DAY 1 — Mon Jun 29
  ════════════════════════════════════ -->
  <div class="day-block" id="day1">
    <div class="day-header">
      <span class="day-label">Day 1</span>
      <span class="day-date">Monday, June 29 · Work + Evening: Goleta Neighborhood</span>
    </div>
    <div class="timeline">

      <div class="buffer-block buffer-rest">
        <div class="buffer-dot"></div>
        🏢 9:00am–6:00pm — Work · Google Office, Goleta
      </div>

      <!-- Evening: Neighborhood walk -->
      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">Goleta Neighborhood Walk + Commute Recon</span>
          <span class="stop-time">6:30pm – 8:00pm</span>
        </div>
        <div class="carousel" data-autoplay>
          <div class="carousel-track">
            <img src="[VERIFIED GOLETA NEIGHBORHOOD/COAST URL]" alt="Goleta coastline">
            <img src="[VERIFIED GOLETA BEACH URL]" alt="Goleta Beach">
          </div>
          <button class="carousel-btn carousel-prev">&#8249;</button>
          <button class="carousel-btn carousel-next">&#8250;</button>
          <div class="carousel-dots"><span class="dot active"></span><span class="dot"></span></div>
        </div>
        <div class="stop-desc">Drive or walk the neighborhood around the Airbnb — this is the area you'd actually live in. Scope out: the nearest grocery (Von's on Hollister, Trader Joe's nearby), coffee spots for morning runs, the actual commute route to the Google office. Note the feel: residential, quiet, suburban — not a college town strip. Goleta is UCSB-adjacent but the residential neighborhoods north of Hollister have a genuine local feel.</div>
        <div class="stop-tags">
          <span class="tag tag-culture">Relocation Recon</span>
        </div>
      </div>
      <div class="alt-drawer">
        <button class="alt-toggle" type="button" aria-expanded="false"><span class="alt-names">↕ Also: Goleta Beach evening walk · Lizard's Mouth sunset scramble · UCSB campus</span><span class="arrow">▼</span></button>
        <div class="alt-content"><div class="alt-list">
          <div class="alt-item"><strong>Goleta Beach Park</strong><span class="alt-tag">easy</span> — 5 min from most Goleta Airbnbs. Sandy beach with a fishing pier. Easy evening walk with ocean views and Channel Islands on the horizon. Free parking.</div>
          <div class="alt-item"><a href="https://www.alltrails.com/trail/us/california/lizards-mouth-rock" target="_blank"><strong>Lizard's Mouth</strong></a><span class="alt-tag">sunset</span> — 1.8mi RT into the Santa Ynez Mountains. Huge sandstone boulders with panoramic coastal views. Hit this at golden hour (around 7:30–8pm in late June). Trailhead off Hwy 154.</div>
          <div class="alt-item"><strong>UCSB Campus Walk</strong><span class="alt-tag">free</span> — Wander the campus lagoon and coastal bluffs. The bluffs trail along the ocean is one of the better surprises in the area. Gives you a sense of the university's footprint in the neighborhood.</div>
        </div></div>
      </div>

      <!-- Dinner -->
      <div class="buffer-block buffer-meal">
        <div class="buffer-dot"></div>
        🍽 8:00pm — Dinner · Local Goleta spot · ~1.5 hrs
      </div>

      <!-- Stop: local dinner -->
      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">Dinner in Goleta</span>
          <span class="stop-time">8:00pm – 9:30pm</span>
        </div>
        <div class="stop-desc">Skip downtown SB tonight — eat local. Try the Goleta strip on Hollister Ave or Calle Real. Good options to look up: Los Agaves (Mexican, Goleta location), Tupelo Junction (just into SB but neighborhood feel), or the brewery scene at Pure Order Brewing. The goal is to find your default Tuesday-night dinner spot.</div>
        <div class="stop-tags">
          <span class="tag tag-food">Dinner</span>
          <span class="tag tag-culture">Relocation Recon</span>
        </div>
      </div>

      <div class="buffer-block buffer-sleep">
        <div class="buffer-dot"></div>
        🌙 ~10:00pm — Sleep · Goleta Airbnb
      </div>

    </div>
  </div>
  ```

- [ ] **Step 2: Insert Day 2 — Tue Jun 30 (Jazz + Funk Zone)**

  ```html
  <!-- ═══════════════════════════════════
       DAY 2 — Tue Jun 30
  ════════════════════════════════════ -->
  <div class="day-block" id="day2">
    <div class="day-header">
      <span class="day-label">Day 2</span>
      <span class="day-date">Tuesday, June 30 · Work + Evening: Santa Barbara</span>
    </div>
    <div class="timeline">

      <div class="buffer-block buffer-rest">
        <div class="buffer-dot"></div>
        🏢 9:00am–6:00pm — Work · Google Office, Goleta
      </div>

      <!-- Drive to SB -->
      <div class="drive-segment">
        <div class="drive-dot"></div>
        <div class="drive-pill">
          🚗 Leave ~6:30pm · ~15 min · Santa Barbara State St
          <a href="https://www.google.com/maps/dir/Goleta,+CA/State+Street,+Santa+Barbara,+CA" target="_blank">Open in Maps ↗</a>
        </div>
      </div>

      <!-- SOhO Music Club -->
      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">SOhO Restaurant & Music Club</span>
          <span class="stop-time">7:00pm – 10:00pm</span>
        </div>
        <div class="carousel" data-autoplay>
          <div class="carousel-track">
            <img src="[VERIFIED SB LIVE MUSIC / STATE ST URL]" alt="Santa Barbara live music">
            <img src="[VERIFIED FUNK ZONE SB URL]" alt="Santa Barbara Funk Zone">
          </div>
          <button class="carousel-btn carousel-prev">&#8249;</button>
          <button class="carousel-btn carousel-next">&#8250;</button>
          <div class="carousel-dots"><span class="dot active"></span><span class="dot"></span></div>
        </div>
        <div class="stop-desc">SOhO is Santa Barbara's main live music venue — 1221 State St, upstairs. Check their schedule before going (sohosb.com). [INSERT VERIFIED INFO: cover charge, reservation policy]. This is the place you'd become a regular at if you lived here — not a tourist spot, but a real local music room. If no show tonight that fits, walk the Funk Zone a block south — the wine bar and arts district that's become SB's most interesting neighborhood. Check: Municipal Winemakers, Loquita, Lucky Penny.</div>
        <div class="stop-tags">
          <span class="tag tag-culture">Jazz</span>
          <span class="tag tag-culture">Live Music</span>
        </div>
      </div>
      <div class="alt-drawer">
        <button class="alt-toggle" type="button" aria-expanded="false"><span class="alt-names">↕ Also: Lobero Theatre · country night TBD · Stearns Wharf evening walk</span><span class="arrow">▼</span></button>
        <div class="alt-content"><div class="alt-list">
          <div class="alt-item"><strong>Lobero Theatre</strong><span class="alt-tag">classical</span> — One of California's oldest theatres (1873). [INSERT July programming if any]. 33 E. Canon Perdido St. If there's a classical or jazz show, this is worth prioritizing over SOhO.</div>
          <div class="alt-item"><strong>[INSERT COUNTRY NIGHT VENUE]</strong><span class="alt-tag">country</span> — [INSERT VERIFIED INFO or note that country music scene is limited in SB].</div>
          <div class="alt-item"><strong>Stearns Wharf Evening Walk</strong><span class="alt-tag">free</span> — California's oldest operating wooden pier. Walk out at sunset or after dark for Channel Islands views and harbor lights. Grab an ice cream at McConnell's (SB's best local creamery) on the way.</div>
        </div></div>
      </div>

      <div class="buffer-block buffer-sleep">
        <div class="buffer-dot"></div>
        🌙 ~10:30pm — Sleep · Goleta Airbnb (~15 min drive back)
      </div>

    </div>
  </div>
  ```

- [ ] **Step 3: Insert Day 3 — Wed Jul 1 (Shooting Range)**

  ```html
  <!-- ═══════════════════════════════════
       DAY 3 — Wed Jul 1
  ════════════════════════════════════ -->
  <div class="day-block" id="day3">
    <div class="day-header">
      <span class="day-label">Day 3</span>
      <span class="day-date">Wednesday, July 1 · Work + Evening: Shooting Range</span>
    </div>
    <div class="timeline">

      <div class="buffer-block buffer-rest">
        <div class="buffer-dot"></div>
        🏢 9:00am–6:00pm — Work · Google Office, Goleta
      </div>

      <!-- Shooting range -->
      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">[INSERT RANGE NAME] — Shooting Range</span>
          <span class="stop-time">6:30pm – 8:30pm</span>
        </div>
        <div class="carousel" data-autoplay>
          <div class="carousel-track">
            <img src="[VERIFIED SHOOTING RANGE URL]" alt="Pistol shooting range">
            <img src="[VERIFIED SANTA YNEZ MOUNTAINS URL]" alt="Santa Ynez Mountains">
          </div>
          <button class="carousel-btn carousel-prev">&#8249;</button>
          <button class="carousel-btn carousel-next">&#8250;</button>
          <div class="carousel-dots"><span class="dot active"></span><span class="dot"></span></div>
        </div>
        <div class="stop-desc">[INSERT VERIFIED: range name, address, what's available (pistol/rifle/outdoor), cost per session, walk-in policy, hours]. Good test for the area: if there's a well-run local range, that's a strong lifestyle point for moving here.</div>
        <div class="stop-tags">
          <span class="tag tag-culture">Shooting</span>
        </div>
      </div>
      <div class="alt-drawer">
        <button class="alt-toggle" type="button" aria-expanded="false"><span class="alt-names">↕ Also: Gaviota State Park · Cold Spring Trail · UCSB Ice Arena</span><span class="arrow">▼</span></button>
        <div class="alt-content"><div class="alt-list">
          <div class="alt-item"><strong>Gaviota State Park</strong><span class="alt-tag">evening</span> — [INSERT: distance from Goleta, trails, hot springs access, day-use fee]. North of Goleta on US-101. Good for a longer evening if the range doesn't fit.</div>
          <div class="alt-item"><a href="https://www.alltrails.com/trail/us/california/cold-spring-east-fork-trail" target="_blank"><strong>Cold Spring Trail (East Fork)</strong></a><span class="alt-tag">hike</span> — More challenging than Inspiration Point. [INSERT distance/gain]. Trailhead off Hwy 192. Good for a longer evening hike.</div>
          <div class="alt-item"><strong>[INSERT ICE RINK NAME]</strong><span class="alt-tag">hockey</span> — [INSERT: public skate / drop-in hours, cost]. If there's a drop-in hockey session on a weeknight, this is the better choice for scoping out the local hockey scene.</div>
        </div></div>
      </div>

      <div class="buffer-block buffer-meal">
        <div class="buffer-dot"></div>
        🍽 8:30pm — Dinner near range or back in Goleta · ~1 hr
      </div>

      <div class="buffer-block buffer-sleep">
        <div class="buffer-dot"></div>
        🌙 ~10:00pm — Sleep · Goleta Airbnb
      </div>

    </div>
  </div>
  ```

- [ ] **Step 4: Insert Day 4 — Thu Jul 2 (Woodworking + Beach)**

  ```html
  <!-- ═══════════════════════════════════
       DAY 4 — Thu Jul 2
  ════════════════════════════════════ -->
  <div class="day-block" id="day4">
    <div class="day-header">
      <span class="day-label">Day 4</span>
      <span class="day-date">Thursday, July 2 · Work + Evening: Woodworking + Beach</span>
    </div>
    <div class="timeline">

      <div class="buffer-block buffer-rest">
        <div class="buffer-dot"></div>
        🏢 9:00am–6:00pm — Work · Google Office, Goleta
      </div>

      <!-- Woodworking shop -->
      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">[INSERT SHOP NAME] — Woodworking / Makerspace</span>
          <span class="stop-time">6:30pm – 7:30pm</span>
        </div>
        <div class="carousel" data-autoplay>
          <div class="carousel-track">
            <img src="[VERIFIED WOODWORKING/MAKERSPACE URL]" alt="Woodworking shop">
            <img src="[VERIFIED GOLETA BEACH SUNSET URL]" alt="Goleta Beach sunset">
          </div>
          <button class="carousel-btn carousel-prev">&#8249;</button>
          <button class="carousel-btn carousel-next">&#8250;</button>
          <div class="carousel-dots"><span class="dot active"></span><span class="dot"></span></div>
        </div>
        <div class="stop-desc">[INSERT VERIFIED: shop name, address, hours, whether membership-only or drop-in browsing allowed, what tools/materials they carry]. If it's a makerspace, ask about membership tiers. If it's a retail shop (Rockler/Woodcraft-type), browse the local stock — a well-stocked shop is a lifestyle signal. Note what's available locally vs. what you'd have to order online.</div>
        <div class="stop-tags">
          <span class="tag tag-culture">Woodworking</span>
          <span class="tag tag-culture">Relocation Recon</span>
        </div>
      </div>
      <div class="alt-drawer">
        <button class="alt-toggle" type="button" aria-expanded="false"><span class="alt-names">↕ Also: UCSB Ice Arena · Granada Theatre · Rattlesnake Canyon preview</span><span class="arrow">▼</span></button>
        <div class="alt-content"><div class="alt-list">
          <div class="alt-item"><strong>[INSERT ICE RINK NAME]</strong><span class="alt-tag">hockey</span> — [INSERT: public skate hours, cost, adult league schedule]. Worth prioritizing if there's a drop-in evening session — you want to get on the ice to evaluate the local hockey scene before deciding to move here.</div>
          <div class="alt-item"><strong>Granada Theatre</strong><span class="alt-tag">classical</span> — [INSERT July programming if any]. 1214 State St. SB's main performing arts venue. If there's a classical show, swap this evening for it.</div>
          <div class="alt-item"><a href="https://www.alltrails.com/trail/us/california/rattlesnake-canyon-trail" target="_blank"><strong>Rattlesnake Canyon — preview hike</strong></a><span class="alt-tag">hike</span> — 3mi RT, creek crossings. Good evening hike if it stays light. You'll do this again Sunday with your friends, but a solo preview isn't wasted.</div>
        </div></div>
      </div>

      <!-- Goleta Beach sunset -->
      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">Goleta Beach Park — Sunset</span>
          <span class="stop-time">7:45pm – 9:00pm</span>
        </div>
        <div class="stop-desc">5 min from most Goleta Airbnbs. Sandy beach with a wooden fishing pier and direct Channel Islands views. Late June sunset is ~8:10pm. This is the beach you'd use on weekday evenings if you lived here — no tourist infrastructure, just the beach. Grab takeout and eat on the sand.</div>
        <div class="stop-tags">
          <span class="tag tag-scenic">Sunset</span>
          <span class="tag tag-water">Beach</span>
        </div>
      </div>

      <div class="buffer-block buffer-sleep">
        <div class="buffer-dot"></div>
        🌙 ~9:30pm — Sleep · Goleta Airbnb
      </div>

    </div>
  </div>
  ```

- [ ] **Step 5: Commit all four weekday days**

  ```bash
  git add goleta-trip/index.html
  git commit -m "Add workweek days 1–4 (Mon Jun 29 – Thu Jul 2)"
  ```

---

## Task 7: Day 5 — Fri Jul 3 (Friends Arrive)

- [ ] **Step 1: Insert Day 5 block**

  ```html
  <!-- ═══════════════════════════════════
       DAY 5 — Fri Jul 3
  ════════════════════════════════════ -->
  <div class="day-block" id="day5">
    <div class="day-header">
      <span class="day-label">Day 5</span>
      <span class="day-date">Friday, July 3 · Work + Friends Arrive</span>
    </div>
    <div class="timeline">

      <div class="buffer-block buffer-rest">
        <div class="buffer-dot"></div>
        🏢 9:00am–6:00pm — Work · Google Office, Goleta
      </div>

      <!-- Friends arrive -->
      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">Friends Arrive</span>
          <span class="stop-time">Afternoon / Evening</span>
        </div>
        <div class="stop-desc">2 friends joining for the long weekend. Coordinate pickup from SB Amtrak (Pacific Surfliner from LAX to SBA is a scenic option: ~2.5hr, ~$30–40/ticket) or pick up from SBA airport if flying. Either way, they're staying at the Airbnb with you through Sunday afternoon.</div>
        <div class="stop-tags">
          <span class="tag tag-culture">Friends Arrive</span>
        </div>
      </div>

      <!-- Drive to Harbor -->
      <div class="drive-segment">
        <div class="drive-dot"></div>
        <div class="drive-pill">
          🚗 Leave ~7:00pm · ~15 min · Santa Barbara Harbor
          <a href="https://www.google.com/maps/dir/Goleta,+CA/Santa+Barbara+Harbor,+CA" target="_blank">Open in Maps ↗</a>
        </div>
      </div>

      <!-- Harbor dinner -->
      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">Santa Barbara Harbor + Stearns Wharf</span>
          <span class="stop-time">7:30pm – 10:00pm</span>
        </div>
        <div class="carousel" data-autoplay>
          <div class="carousel-track">
            <img src="[VERIFIED STEARNS WHARF URL]" alt="Stearns Wharf Santa Barbara">
            <img src="[VERIFIED SB HARBOR URL]" alt="Santa Barbara Harbor">
            <img src="[VERIFIED SB STATE ST NIGHT URL]" alt="Santa Barbara State Street">
          </div>
          <button class="carousel-btn carousel-prev">&#8249;</button>
          <button class="carousel-btn carousel-next">&#8250;</button>
          <div class="carousel-dots"><span class="dot active"></span><span class="dot"></span></div>
        </div>
        <div class="stop-desc">Good first-impression spot for your friends. Walk Stearns Wharf for the harbor views, then dinner somewhere along State St or the Funk Zone. Loquita (Spanish, State St) or bouchon (French, upper State) are solid. After dinner: walk State Street south toward the Funk Zone — the area between Yanonali and the railroad tracks is SB's most interesting stretch right now.</div>
        <div class="stop-tags">
          <span class="tag tag-scenic">Harbor</span>
          <span class="tag tag-food">Dinner</span>
        </div>
      </div>
      <div class="alt-drawer">
        <button class="alt-toggle" type="button" aria-expanded="false"><span class="alt-names">↕ Also: Funk Zone wine bars · outdoor concert if anything's on · early night before Jul 4</span><span class="arrow">▼</span></button>
        <div class="alt-content"><div class="alt-list">
          <div class="alt-item"><strong>Funk Zone Wine Bars</strong><span class="alt-tag">evening</span> — Municipal Winemakers, Area 51 Wine, Cutler's Artisan Spirits. The Funk Zone is SB's arts-meets-wine neighborhood — walkable, local, not touristy. Good pre-dinner or after-dinner stretch.</div>
          <div class="alt-item"><strong>Early Night</strong><span class="alt-tag">practical</span> — If you're hitting Inspiration Point early on Jul 4 (recommended: 7am to beat the heat and crowds), an early Friday night is smart. The hike is more rewarding than one extra hour at a bar.</div>
        </div></div>
      </div>

      <div class="buffer-block buffer-sleep">
        <div class="buffer-dot"></div>
        🌙 ~10:30pm — Sleep · Goleta Airbnb (all three)
      </div>

    </div>
  </div>
  ```

- [ ] **Step 2: Commit**

  ```bash
  git add goleta-trip/index.html
  git commit -m "Add Day 5 (Fri Jul 3 — friends arrive)"
  ```

---

## Task 8: Day 6 — Sat Jul 4 (Independence Day)

- [ ] **Step 1: Insert Day 6 block**

  ```html
  <!-- ═══════════════════════════════════
       DAY 6 — Sat Jul 4 — Independence Day
  ════════════════════════════════════ -->
  <div class="day-block" id="day6">
    <div class="day-header">
      <span class="day-label">Day 6</span>
      <span class="day-date">Saturday, July 4 · Independence Day 🎆</span>
    </div>
    <div class="timeline">

      <div class="buffer-block buffer-meal">
        <div class="buffer-dot"></div>
        ☕ 6:30am — Early breakfast + trail prep · ~30 min
      </div>

      <!-- Drive to Inspiration Point -->
      <div class="drive-segment">
        <div class="drive-dot"></div>
        <div class="drive-pill">
          🚗 Leave ~7:00am · ~20 min · Inspiration Point Trailhead
          <a href="https://www.google.com/maps/dir/Goleta,+CA/Inspiration+Point+Trailhead,+Santa+Barbara,+CA" target="_blank">Open in Maps ↗</a>
        </div>
      </div>

      <!-- Inspiration Point hike -->
      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">Inspiration Point</span>
          <span class="stop-time">7:30am – 10:30am</span>
        </div>
        <div class="carousel" data-autoplay>
          <div class="carousel-track">
            <img src="[VERIFIED INSPIRATION POINT SB URL]" alt="Inspiration Point Santa Barbara panoramic view">
            <img src="[VERIFIED SANTA YNEZ MOUNTAINS URL]" alt="Santa Ynez Mountains trail">
            <img src="[VERIFIED SB COASTLINE FROM ABOVE URL]" alt="Santa Barbara coastline from above">
          </div>
          <button class="carousel-btn carousel-prev">&#8249;</button>
          <button class="carousel-btn carousel-next">&#8250;</button>
          <div class="carousel-dots"><span class="dot active"></span><span class="dot"></span></div>
        </div>
        <div class="stop-desc">3.5mi round trip, ~900ft gain. Starts at Tunnel Trail trailhead on Tunnel Rd — the climb goes through oak woodland and chaparral to a saddle with panoramic views of Santa Barbara, the coast, the Channel Islands, and the Santa Ynez Valley behind. Best views in the area, and early July means wildflowers are still out. Start at 7:30am to finish before the heat and holiday crowds. No permit required. [INSERT VERIFIED trailhead parking details].</div>
        <div class="stop-tags">
          <span class="tag tag-hike">Hike</span>
          <span class="tag tag-scenic">Panoramic</span>
          <a class="alltrails-link" href="https://www.alltrails.com/trail/us/california/inspiration-point-trail-via-tunnel-trail" target="_blank">🥾 AllTrails ↗</a>
        </div>
        <div class="map-embed trail">
          <iframe src="https://www.komoot.com/tour/[INSERT KOMOOT TOUR ID]/embed?layout=classic&profile=1" loading="lazy" title="Trail map"></iframe>
        </div>
      </div>
      <div class="alt-drawer">
        <button class="alt-toggle" type="button" aria-expanded="false"><span class="alt-names">↕ Also: Cold Spring Trail East Fork · Seven Falls · Rattlesnake Canyon (save for Sun)</span><span class="arrow">▼</span></button>
        <div class="alt-content"><div class="alt-list">
          <div class="alt-item"><a href="https://www.alltrails.com/trail/us/california/cold-spring-east-fork-trail" target="_blank"><strong>Cold Spring Trail (East Fork)</strong></a><span class="alt-tag">harder</span> — [INSERT distance/gain]. More technical than Inspiration Point, longer. Good if the group wants a bigger challenge. Trailhead off Mountain Dr.</div>
          <div class="alt-item"><a href="https://www.alltrails.com/trail/us/california/seven-falls-trail" target="_blank"><strong>Seven Falls</strong></a><span class="alt-tag">scramble</span> — 3.6mi RT, fun gorge scrambling with waterfall payoffs. More adventurous than Inspiration Point but less panoramic. Shares the Tunnel Trail trailhead.</div>
          <div class="alt-item"><strong>Rattlesnake Canyon</strong><span class="alt-tag">save for Sun</span> — You're doing this with your friends Sunday morning. Don't overlap it here unless they specifically want two hikes.</div>
        </div></div>
      </div>

      <!-- Drive to beach -->
      <div class="drive-segment">
        <div class="drive-dot"></div>
        <div class="drive-pill">
          🚗 Leave ~10:30am · ~15 min · East Beach
          <a href="https://www.google.com/maps/dir/Tunnel+Trail,+Santa+Barbara,+CA/East+Beach,+Santa+Barbara,+CA" target="_blank">Open in Maps ↗</a>
        </div>
      </div>

      <!-- Beach BBQ -->
      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">East Beach BBQ — 4th of July</span>
          <span class="stop-time">11:00am – 6:00pm</span>
        </div>
        <div class="carousel" data-autoplay>
          <div class="carousel-track">
            <img src="[VERIFIED EAST BEACH SB URL]" alt="East Beach Santa Barbara">
            <img src="[VERIFIED SB BEACH BBQ / 4TH OF JULY URL]" alt="4th of July beach celebration">
          </div>
          <button class="carousel-btn carousel-prev">&#8249;</button>
          <button class="carousel-btn carousel-next">&#8250;</button>
          <div class="carousel-dots"><span class="dot active"></span><span class="dot"></span></div>
        </div>
        <div class="stop-desc">East Beach is Santa Barbara's best beach — wide, sandy, volleyball courts, and a dedicated BBQ picnic area. Claim a grill spot early (they fill up by noon on the 4th). Grab supplies from Von's or Trader Joe's the night before: burgers, hot dogs, chicken, corn, watermelon. The beach fills up through the afternoon as the fireworks crowd arrives. Bring a blanket or camp chairs — you'll be here all day. <strong>Note:</strong> alcohol is allowed in the picnic area with a permit; verify current policy at the beach entrance.</div>
        <div class="stop-tags">
          <span class="tag tag-water">Beach</span>
          <span class="tag tag-food">BBQ</span>
          <span class="tag tag-culture">4th of July</span>
        </div>
      </div>
      <div class="alt-drawer">
        <button class="alt-toggle" type="button" aria-expanded="false"><span class="alt-names">↕ Also: Goleta Beach (more local, less crowded) · Carpinteria State Beach · rooftop bar viewing</span><span class="arrow">▼</span></button>
        <div class="alt-content"><div class="alt-list">
          <div class="alt-item"><strong>Goleta Beach Park</strong><span class="alt-tag">quieter</span> — More local, less tourist-heavy than East Beach. Same channel views. Good option if you want a smaller crowd — though the fireworks view from here is further from the launch site.</div>
          <div class="alt-item"><strong>Carpinteria State Beach</strong><span class="alt-tag">mellow</span> — ~20min south on US-101. Known as one of the world's safest beaches (gentle waves, no rips). Smaller 4th of July crowd. More of a local family beach vibe.</div>
        </div></div>
      </div>

      <!-- Fireworks -->
      <div class="buffer-block buffer-rest">
        <div class="buffer-dot"></div>
        🎆 [INSERT VERIFIED TIME, e.g. 9:00pm] — 4th of July Fireworks · [INSERT VERIFIED LOCATION]
      </div>

      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">4th of July Fireworks — [INSERT LOCATION]</span>
          <span class="stop-time">[INSERT VERIFIED TIME]</span>
        </div>
        <div class="carousel" data-autoplay>
          <div class="carousel-track">
            <img src="[VERIFIED FIREWORKS / SB WATERFRONT NIGHT URL]" alt="Santa Barbara fireworks">
            <img src="[VERIFIED SB WATERFRONT EVENING URL]" alt="Santa Barbara waterfront evening">
          </div>
          <button class="carousel-btn carousel-prev">&#8249;</button>
          <button class="carousel-btn carousel-next">&#8250;</button>
          <div class="carousel-dots"><span class="dot active"></span><span class="dot"></span></div>
        </div>
        <div class="stop-desc">[INSERT VERIFIED: exact location, start time, best viewing spots, whether staying on the beach from the BBQ works, parking advice, whether crowd is big]. [INSERT VERIFIED TIPS: what time to arrive for a good spot if not staying on the beach all day].</div>
        <div class="stop-tags">
          <span class="tag tag-culture">Fireworks</span>
          <span class="tag tag-culture">4th of July</span>
        </div>
      </div>

      <div class="buffer-block buffer-sleep">
        <div class="buffer-dot"></div>
        🌙 ~11:00pm — Sleep · Goleta Airbnb
      </div>

    </div>
  </div>
  ```

- [ ] **Step 2: Commit**

  ```bash
  git add goleta-trip/index.html
  git commit -m "Add Day 6 (Sat Jul 4 — Independence Day)"
  ```

---

## Task 9: Day 7 — Sun Jul 5 (Last Day + Departure)

- [ ] **Step 1: Insert Day 7 block**

  ```html
  <!-- ═══════════════════════════════════
       DAY 7 — Sun Jul 5 — Last Day
  ════════════════════════════════════ -->
  <div class="day-block" id="day7">
    <div class="day-header">
      <span class="day-label">Day 7</span>
      <span class="day-date">Sunday, July 5 · Last Day → LAX</span>
    </div>
    <div class="timeline">

      <div class="buffer-block buffer-meal">
        <div class="buffer-dot"></div>
        ☕ 7:30am — Early breakfast + pack · ~30 min
      </div>

      <!-- Drive to Rattlesnake -->
      <div class="drive-segment">
        <div class="drive-dot"></div>
        <div class="drive-pill">
          🚗 Leave ~8:00am · ~15 min · Rattlesnake Canyon Trailhead
          <a href="https://www.google.com/maps/dir/Goleta,+CA/Rattlesnake+Canyon+Trail,+Santa+Barbara,+CA" target="_blank">Open in Maps ↗</a>
        </div>
      </div>

      <!-- Rattlesnake Canyon -->
      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">Rattlesnake Canyon Trail</span>
          <span class="stop-time">8:15am – 10:30am</span>
        </div>
        <div class="carousel" data-autoplay>
          <div class="carousel-track">
            <img src="[VERIFIED RATTLESNAKE CANYON URL]" alt="Rattlesnake Canyon Santa Barbara creek">
            <img src="[VERIFIED SANTA BARBARA MOUNTAINS TRAIL URL]" alt="Santa Barbara mountain trail">
          </div>
          <button class="carousel-btn carousel-prev">&#8249;</button>
          <button class="carousel-btn carousel-next">&#8250;</button>
          <div class="carousel-dots"><span class="dot active"></span><span class="dot"></span></div>
        </div>
        <div class="stop-desc">~3mi RT, [INSERT VERIFIED GAIN]. Creek crossings, rock scrambling, and chaparral. More adventurous feel than Inspiration Point — good send-off hike. Trailhead at [INSERT VERIFIED LOCATION AND PARKING]. No permit required. [VERIFY: trail status as of July 2026].</div>
        <div class="stop-tags">
          <span class="tag tag-hike">Hike</span>
          <span class="tag tag-water">Creek</span>
          <a class="alltrails-link" href="https://www.alltrails.com/trail/us/california/rattlesnake-canyon-trail" target="_blank">🥾 AllTrails ↗</a>
        </div>
        <div class="map-embed trail">
          <iframe src="https://www.komoot.com/tour/[INSERT KOMOOT TOUR ID]/embed?layout=classic&profile=1" loading="lazy" title="Trail map"></iframe>
        </div>
      </div>
      <div class="alt-drawer">
        <button class="alt-toggle" type="button" aria-expanded="false"><span class="alt-names">↕ Also: Seven Falls · Lizard's Mouth · easy beach walk instead</span><span class="arrow">▼</span></button>
        <div class="alt-content"><div class="alt-list">
          <div class="alt-item"><a href="https://www.alltrails.com/trail/us/california/seven-falls-trail" target="_blank"><strong>Seven Falls</strong></a><span class="alt-tag">scramble</span> — 3.6mi RT, fun gorge scrambling with waterfall payoffs. Same general area as Rattlesnake, slightly more adventurous. Good if your group liked the technical bits of Inspiration Point.</div>
          <div class="alt-item"><a href="https://www.alltrails.com/trail/us/california/lizards-mouth-rock" target="_blank"><strong>Lizard's Mouth</strong></a><span class="alt-tag">easy</span> — 1.8mi RT, huge sandstone boulders with coastal panoramas. Lower effort but high reward. Better as a sunset hike than a morning one, but works either way.</div>
          <div class="alt-item"><strong>Easy Beach Walk</strong><span class="alt-tag">low-key</span> — If people are wiped from the 4th, skip the hike and do a slow morning at Goleta Beach or East Beach. Coffee, breakfast burritos, last look at the Channel Islands. No shame in this.</div>
        </div></div>
      </div>

      <!-- Brunch -->
      <div class="buffer-block buffer-meal">
        <div class="buffer-dot"></div>
        🥞 11:00am — Brunch · Santa Barbara or Goleta · ~1.5 hrs
      </div>

      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">Last Brunch + Coffee</span>
          <span class="stop-time">11:00am – 12:30pm</span>
        </div>
        <div class="stop-desc">Final meal with your friends. Good options: Scarlett Begonia (State St, SB — proper brunch), Renaud's Patisserie (State St, French pastries + eggs), or a simpler Goleta coffee shop if you want to keep it local. This is also your last chance to take a mental note: does SB feel like somewhere you'd want to do this every Sunday?</div>
        <div class="stop-tags">
          <span class="tag tag-food">Brunch</span>
        </div>
      </div>

      <!-- Friends depart -->
      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">Friends Depart</span>
          <span class="stop-time">Early afternoon</span>
        </div>
        <div class="stop-desc">Drop friends at SBA airport or SB Amtrak (Pacific Surfliner back to LAX: 2.5hr, scenic coastal route). Then a few hours to yourself: pack up the Airbnb, drive around any neighborhoods you haven't seen, grab a last coffee.</div>
        <div class="stop-tags">
          <span class="tag tag-culture">Friends Depart</span>
        </div>
      </div>

      <!-- Sports bar / ice rink opt -->
      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">Solo Afternoon — [INSERT SPORTS BAR NAME] or Last Wander</span>
          <span class="stop-time">2:00pm – 6:00pm</span>
        </div>
        <div class="stop-desc">Use this window to hit anything you didn't get to during the week. [INSERT SPORTS BAR NAME] is a good option — find the bar you'd watch hockey games at come October. Ask the bartender what the hockey crowd is like; if they know what you're talking about, that's a good sign. Or: one more wander through a neighborhood you haven't evaluated yet (Montecito is 10 min south — different vibe, much more expensive, worth seeing as a comparison).</div>
        <div class="stop-tags">
          <span class="tag tag-culture">Hockey Bar</span>
          <span class="tag tag-culture">Relocation Recon</span>
        </div>
      </div>
      <div class="alt-drawer">
        <button class="alt-toggle" type="button" aria-expanded="false"><span class="alt-names">↕ Also: UCSB Ice Arena drop-in · Montecito neighborhood drive · Summerland / Carpinteria</span><span class="arrow">▼</span></button>
        <div class="alt-content"><div class="alt-list">
          <div class="alt-item"><strong>[INSERT ICE RINK NAME]</strong><span class="alt-tag">hockey</span> — [INSERT Sunday afternoon public skate / drop-in hours]. If you haven't been on the ice yet this trip, this is the slot.</div>
          <div class="alt-item"><strong>Montecito</strong><span class="alt-tag">comparison</span> — 10 min south on US-101. Wealthier, quieter, more suburban than SB. Worth a drive through as a reference point — helps calibrate what "Goleta residential" means by comparison.</div>
          <div class="alt-item"><strong>Summerland / Carpinteria</strong><span class="alt-tag">coastal</span> — Continue south another 10–15 min. Small beach towns between SB and Ventura. Different community feel from Goleta — slower, more surfer. Useful for the relocation comparison if you have the time.</div>
        </div></div>
      </div>

      <!-- Drive to LAX -->
      <div class="drive-segment">
        <div class="drive-dot"></div>
        <div class="drive-pill">
          🚗 Leave Goleta ~9:30pm · ~1 hr 45 min · LAX
          <a href="https://www.google.com/maps/dir/Goleta,+CA/Los+Angeles+International+Airport,+CA" target="_blank">Open in Maps ↗</a>
        </div>
        <div class="map-embed"><iframe src="https://maps.google.com/maps?saddr=34.4358,-119.8276&daddr=33.9425,-118.4081&output=embed" loading="lazy" title="Driving directions map"></iframe></div>
      </div>

      <div class="stop-card">
        <div class="stop-dot"></div>
        <div class="stop-top">
          <span class="stop-name">Return Car + Check In at LAX</span>
          <span class="stop-time">Arrive ~11:15pm · Flight ~midnight</span>
        </div>
        <div class="stop-desc">Return rental car at LAX consolidated rental facility (shuttle ~10 min to terminal). Check in and clear security — leave ~45 min for this. Midnight departure → home to NYC. <strong>Note:</strong> Sunday night US-101 south can have traffic through Malibu — leave by 9:30pm to be safe.</div>
        <div class="stop-tags">
          <span class="tag tag-culture">Departs → NYC</span>
        </div>
      </div>

    </div>
  </div>
  ```

- [ ] **Step 2: Add footer**

  ```html
  <footer>
    Goleta · Santa Barbara · Jun 28–Jul 5, 2026 · Rental Car · Last updated Jun 2026
  </footer>
  ```

- [ ] **Step 3: Commit**

  ```bash
  git add goleta-trip/index.html
  git commit -m "Add Day 7 (Sun Jul 5 — last day + LAX departure)"
  ```

---

## Task 10: Fill In All Verified Facts + Image URLs

Replace every `[INSERT ...]` placeholder with facts from Task 1. Replace every `[VERIFIED ... URL]` with URLs from Task 2. Replace every `[INSERT KOMOOT TOUR ID]` with the actual Komoot tour ID from searching komoot.com for each trail.

**Files:** Modify `/Users/acristian/Documents/website/goleta-trip/index.html`

- [ ] **Step 1: Fact substitution sweep**

  Search for `[INSERT` in the file and replace every instance with verified content.
  ```bash
  grep -n "\[INSERT" /Users/acristian/Documents/website/goleta-trip/index.html
  ```
  Expected: zero results when done.

- [ ] **Step 2: Image URL substitution sweep**

  Search for `[VERIFIED` in the file and replace every instance.
  ```bash
  grep -n "\[VERIFIED" /Users/acristian/Documents/website/goleta-trip/index.html
  ```
  Expected: zero results when done.

- [ ] **Step 3: Verify all image URLs return 200**

  Extract and test every Unsplash URL:
  ```bash
  grep -o 'https://images\.unsplash\.com/photo-[^"]*' /Users/acristian/Documents/website/goleta-trip/index.html | while read url; do
    status=$(curl -sIL "$url" | grep "^HTTP" | tail -1)
    echo "$status | $url"
  done
  ```
  Expected: all lines show `HTTP/2 200`. For any 404: find a replacement URL, substitute, and re-verify.

- [ ] **Step 4: Verify carousel dot counts match image counts**

  For each carousel, count `<img>` tags and count `<span class="dot">` tags — must match.

- [ ] **Step 5: Update booking checklist item count**

  Count actual items (🔴 + 🟡 + 🟢 + 🔵) and update the toggle-hint:
  ```html
  <span class="bc-toggle-hint">X 🔴 · Y 🟡 · Z 🟢 · W 🔵 — N items</span>
  ```

- [ ] **Step 6: Commit**

  ```bash
  git add goleta-trip/index.html
  git commit -m "Fill in verified facts and image URLs"
  ```

---

## Task 11: Quality Check + Final Commit + Push

Run through every item in the template quality checklist before pushing.

**Files:** Read `/Users/acristian/Documents/Claude/travel-plan-template.md` for the full checklist.

- [ ] **Step 1: Run the quality checklist**

  Check each item:
  - [ ] All image URLs return HTTP 200 (verified in Task 10)
  - [ ] Carousel dot counts match image counts
  - [ ] Every drive pill has: departure time, duration, destination
  - [ ] No buffer blocks that describe drives
  - [ ] Timeline arithmetic is correct (depart time + drive duration = next stop start time)
  - [ ] Overnight locations match next-day start (Day 0 ends Goleta → Day 1 starts Goleta ✓, etc.)
  - [ ] Booking checklist is present, collapsible, and fully filled (zero `[INSERT]` placeholders)
  - [ ] Page `<title>` is `Goleta · Jun 28–Jul 5`
  - [ ] Komoot embeds on both hike stops (Inspiration Point, Rattlesnake Canyon)
  - [ ] AllTrails links on both hike stops
  - [ ] Zero `[INSERT ...]` or `[VERIFIED ...]` placeholders remain in file
  - [ ] No facts stated confidently without verification (prices say "~$X as of 2026", hours say "verify before visiting")
  - [ ] JS block is verbatim from Colorado reference (carousel, alt-drawer, booking checklist toggles all work)

- [ ] **Step 2: Open in browser and visual check**

  ```bash
  open /Users/acristian/Documents/website/goleta-trip/index.html
  ```
  Check: header renders, all days visible, alt drawers expand/collapse, booking checklist expands, carousels advance, Komoot iframes load.

- [ ] **Step 3: Final commit**

  ```bash
  cd /Users/acristian/Documents/website
  git add goleta-trip/index.html
  git commit -m "Goleta trip plan — complete and verified"
  ```

- [ ] **Step 4: Push to master**

  ```bash
  git push origin master
  ```

---

## Self-Review Notes

- Spec coverage: all requirements mapped to tasks — Arrival ✓, weekday evenings ✓, Jul 3 friends ✓, Jul 4 holiday ✓, Jul 5 departure ✓, hockey (rink + bar) ✓, shooting ✓, jazz ✓, country ✓, classical ✓, woodworking ✓, hiking primary + alts ✓, booking checklist ✓
- No placeholders in plan structure — `[INSERT ...]` are explicit instructions to the builder to fill from Task 1 research, not final content
- Timeline arithmetic: Day 0 — LAX 8pm → depart 8:30pm → arrive Goleta ~10:15pm ✓; Day 7 — leave Goleta 9:30pm → arrive LAX ~11:15pm → midnight flight ✓
- Komoot tour IDs must be found via web search in Task 1 — they are not guessable
- Booking checklist item count set to placeholder "11 items" — update after Task 1 fills in actual items
