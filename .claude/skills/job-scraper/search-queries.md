# Search Queries for Job Scraper

<!-- Configured for: Muhammad Idris — M.Eng. Robotics/Mechatronics (Hochschule Schmalkalden, -->
<!-- graduating 05/2026). Stack: ROS 2, C++, Python, AMR/AGV, control (FLC/PID/FOC), SLAM/   -->
<!-- sensor fusion, radar/ToF, digital twin/Gazebo, SIL/HIL. Niche: intralogistics/warehouse  -->
<!-- robotics. Stage: Werkstudent / Praktikum / Masterarbeit now → Junior/Graduate from 2026. -->
<!-- Scope: ALL Germany + remote, extend to DACH (Austria, Switzerland). No fixed city.       -->

## Location config

> **Scope = all of Germany + remote, with DACH (AT/CH) as an extension.** No single city.
- **Stepstone:** `--location deutschland` (nationwide). For DACH, the actor also covers `.at`.
- **LinkedIn:** `--location "Germany"` (add `"Austria"` / `"Switzerland"` for DACH).
- **Indeed:** `--country de` by default; for DACH also run `--country at` and `--country ch`.
- **Arbeitnow & Xing:** run **without** a location flag — both are already DACH/EU-wide.
- **Remote:** always include. Use `--remote` (Arbeitnow/Indeed) or `--worktype remote`
  (LinkedIn) for remote-only passes; otherwise remote roles still surface nationwide.
- **DACH on demand:** Germany is the default; only fan out to AT/CH on `/scrape broad` or
  when the user asks, to avoid 3× Apify cost per run.

## Search Boards (German / DACH market)

Run via the board CLIs in `.agents/skills/` (same JSON shape). **Arbeitnow** always (free);
**Stepstone + Indeed** for broad German coverage; **LinkedIn + Xing** for engineer/professional
roles; **Glassdoor** when pay/reputation matters. Robotics employers cluster on Stepstone,
LinkedIn, and Indeed, so prioritize those three for this profile.

## Languages

Search **both German and English** terms — German robotics postings often use English titles
("Robotics Engineer") but German student terms ("Werkstudent", "Praktikum"). Each category
below lists both.

## Query Categories

### Priority 1: Core robotics & mechatronics (engineer / entry-level)

```
robotics engineer            | Robotik Ingenieur | Roboticist
mechatronics engineer        | Mechatronik Ingenieur | Mechatroniker
autonomous mobile robots     | AMR engineer | autonome mobile Roboter | mobile robotics
AGV | intralogistics robotics | warehouse robotics | Intralogistik Robotik   <!-- thesis niche -->
```

Per-board examples (nationwide):
```
arbeitnow:  --query "robotics" --limit 30          # single strong term: Arbeitnow AND-matches all words
arbeitnow:  --query "mobile robot" --limit 30
stepstone:  --query "robotics engineer" --location deutschland --posted 14
stepstone:  --query "mechatronik" --location deutschland --posted 14
stepstone:  --query "autonome mobile roboter" --location deutschland --posted 14
indeed:     --query "robotics engineer" --country de --posted 14
indeed:     --query "AMR intralogistik" --country de --posted 14
linkedin:   --query "mechatronics engineer" --location "Germany" --posted 7
linkedin:   --query "autonomous mobile robots" --location "Germany" --posted 7
glassdoor:  --query "robotics engineer" --location "Germany" --posted 14
glassdoor:  --query "mechatronics engineer" --location "Germany" --posted 14
xing:       --query "Robotik" --discipline "Engineering"
```

DACH fan-out (Austria + Switzerland — run on `/scrape broad` and on the scheduled runs):
```
indeed:     --query "robotics engineer" --country at --posted 14
indeed:     --query "robotics engineer" --country ch --posted 14
linkedin:   --query "mechatronics engineer" --location "Austria" --posted 7
linkedin:   --query "mechatronics engineer" --location "Switzerland" --posted 7
glassdoor:  --query "robotics engineer" --location "Austria" --posted 14
glassdoor:  --query "robotics engineer" --location "Switzerland" --posted 14
# Xing & Arbeitnow are already DACH/EU-wide — no extra location pass needed.
```

### Priority 2: Working-student & internship (Werkstudent / Praktikum)

```
Werkstudent Robotik     | Werkstudent Mechatronik | Werkstudent Automatisierung
Praktikum Robotik       | Praktikum Mechatronik   | Praktikant Robotik
internship robotics     | working student robotics | Abschlussarbeit Robotik (thesis)
```

Per-board examples:
```
arbeitnow:  --query "werkstudent robotik" --limit 25
arbeitnow:  --query "praktikum mechatronik" --limit 25
stepstone:  --query "werkstudent robotik" --location deutschland --posted 14
stepstone:  --query "praktikum robotik"   --location deutschland --posted 14
indeed:     --query "werkstudent mechatronik" --country de --jobtype parttime
indeed:     --query "praktikum robotik" --country de --jobtype internship
linkedin:   --query "werkstudent robotik" --location "Germany" --posted 7
```

### Priority 3: Related / adjacent roles (domain expansion)

<!-- Tuned to Muhammad's actual stack (from CV). These are the adjacencies where his thesis
     and lab work map directly — prioritize ROS/C++, controls, perception, simulation. -->

```
robotics software engineer | ROS developer | ROS 2 | ROS2 engineer
C++ robotics | Python robotics | software engineer robotics
controls engineer | control systems engineer | Regelungstechnik | Regelungstechniker
perception engineer | SLAM engineer | sensor fusion | Lokalisierung | localization
robotics simulation engineer | digital twin | Gazebo | simulation engineer mechatronics
embedded systems engineer | embedded software robotics | Embedded Softwareentwickler
motion planning | navigation engineer | path planning
automation engineer | Automatisierungstechnik | Automatisierungsingenieur
HIL / SIL test engineer | test engineer robotics | Inbetriebnahmeingenieur
motor control | FOC | BLDC | Antriebstechnik
```

Per-board examples:
```
arbeitnow:  --query "ROS" --limit 25
arbeitnow:  --query "perception" --limit 25
stepstone:  --query "automatisierungstechnik" --location deutschland --posted 14
stepstone:  --query "regelungstechnik" --location deutschland --posted 14
indeed:     --query "ROS C++" --country de --posted 14
indeed:     --query "SLAM" --country de --posted 14
linkedin:   --query "controls engineer robotics" --location "Germany" --posted 7
linkedin:   --query "perception engineer" --location "Germany" --posted 7
```

> **Skip / down-rank** (not in profile): pure web/frontend, pure data-science/ML-only,
> non-robotics PLC-only factory roles, senior/lead-only postings.

## Location Filter (when evaluating results)

Scope is nationwide + remote, so relocation within Germany is acceptable. Tiers:
- Anywhere in **Germany** (any Bundesland) — acceptable
- **Remote / hybrid** — acceptable
- **Austria / Switzerland** — acceptable on DACH runs; otherwise flag, don't auto-drop
- Outside DACH — drop unless fully remote and explicitly open to applicants in Germany

## Date Filter

Prefer jobs posted within the last 14 days (use `--posted 7/14`). For niche Priority-3
terms, widen to 30 days. Skip postings with expired deadlines.

## Role-level Filter

Include early-career German terms: **Werkstudent**, **Praktikum / Praktikant**,
**Masterarbeit / Abschlussarbeit** (thesis roles — relevant until 05/2026), **Junior**,
**Absolvent / Berufseinsteiger / Einstieg**, **Trainee**, **Graduate**. De-prioritize
Senior/Lead/Principal unless the posting explicitly welcomes early-career applicants.

**Availability:** currently completing thesis (until ~05/2026) → favour Werkstudent /
Praktikum / Masterarbeit and thesis-compatible roles **now**; full-time Junior/Graduate
roles with a **start date from mid-2026** are also in scope (flag the start date).

## Adapting Queries

- "/scrape" → Priority 1 + 2, Germany-wide, all boards (Arbeitnow free + Apify if token set).
- "/scrape werkstudent" or "/scrape praktikum" → Priority 2 focus.
- "/scrape broad" → all three priorities, **all six boards** (Arbeitnow, Stepstone, Indeed,
  LinkedIn, Xing, Glassdoor) + fan out to DACH (Indeed/LinkedIn/Glassdoor AT + CH).
- "/scrape <keyword>" → that keyword + the 2–3 most related lines above.

### Scheduled runs (Monday + Thursday)

The twice-weekly scheduled run is the **broad** run: all six boards (Arbeitnow, Stepstone,
Indeed, LinkedIn, Xing, Glassdoor) across Priorities 1–3, including the Austria + Switzerland
fan-out above. This is the same as invoking `/scrape broad`. Cost note: LinkedIn bills a
minimum of ~150 results/run and Glassdoor ~$0.40/1k, so each scheduled run spends a few
cents of Apify credit — expected and intentional for the wider coverage.

### Watched company career boards (ATS) — fetch directly every scheduled run

These target robotics/aerospace employers don't index well on the job boards, but expose a
public ATS JSON/XML feed. On every scheduled run (and on `/scrape broad`), fetch each URL
directly (WebFetch/curl), then apply the SAME relevance filter (robotics / ROS / C++ /
controls / perception / embedded / mechatronics / avionics / Werkstudent / Praktikum /
Masterarbeit), the SAME 14-day date filter, and the SAME dedup against seen_jobs.json +
job_search_tracker.csv as the boards. Each posting's apply URL is in the feed.

| Company | Domain | ATS feed |
|---------|--------|----------|
| Isar Aerospace | aerospace · avionics/controls/embedded | https://boards-api.greenhouse.io/v1/boards/isaraerospace/jobs?content=true |
| Brainlab | surgical robotics / navigation · C++ | https://api.smartrecruiters.com/v1/companies/brainlab/postings?limit=100 |
| MOIA | autonomous driving (VW) | https://boards-api.greenhouse.io/v1/boards/moia/jobs?content=true |
| Wandelbots | industrial robotics (Dresden) | https://wandelbots.jobs.personio.de/xml |

Add new ATS feeds here as they're discovered. Companies whose ATS has no public feed
(Bosch, Siemens, BMW, Magna, Ottobock, Agile Robots) are covered by the keyword board
searches above using `<company> + robotics/embedded/mechatronik` queries.
