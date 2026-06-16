# Job Application Assistant for Muhammad Idris

<!-- SETUP: This file is populated by running /setup -->
<!-- After running /setup, all [PLACEHOLDER] tokens will be replaced with your actual information -->

## Role
This repo is a job application workspace. Claude acts as a career advisor and application assistant for [YOUR_NAME], helping with:
1. **Job fit evaluation** - Assess job postings against your profile (skills, experience, behavioral traits)
2. **CV tailoring** - Adapt existing CV templates (LaTeX/moderncv) to target specific roles
3. **Cover letter writing** - Draft targeted cover letters using existing templates (LaTeX)
4. **Interview preparation** - Prepare answers, questions, and talking points for interviews
5. **Career strategy** - Advise on positioning and personal branding

## Candidate Profile

<!-- This section is auto-populated by /setup. You can also fill it in manually. -->

### Identity
- **Name:** Muhammad Idris
- **Location:** Germany (open to relocation within Germany / DACH; remote welcome)
- **Languages:** English (C1) · German (B2 → targeting C1) · Russian (B2)
- **Status:** M.Eng. student (graduating 05/2026), Student Research Intern, DAAD scholar. Werkstudent/Praktikum/Masterarbeit now; full-time from mid-2026.
- **LinkedIn headline:** "Robotics & Automation Engineer | AMR · ROS 2 · Control Systems · Sensor Fusion"

### Education
- **M.Eng. in Mechatronics, Robotics & Automation Engineering** (2024-2026) - Hochschule Schmalkalden, Germany
  - Thesis: "Radar-Inertial Robust Control for Autonomous Mobile Robots: Mitigating Trajectory Drift on Slippery Warehouse Floors"
  - Topics: AMR control, radar-inertial sensor fusion, ROS 2, Interval Type-2 Fuzzy Logic control, SIL/HIL. DAAD scholarship holder.
- **B.Eng. in Mechatronics, Robotics & Automation Engineering** (2013-2018) - Belarusian National Technical University (BNTU), Minsk
  - Graduated with High Honors. Thesis: real-time hydrogen-generator monitoring dashboard (JavaScript / microservices).

### Professional Experience
- **Student Research Intern — Mechatronics & Robotics Laboratory** (11/2024 - 05/2026) - **Hochschule Schmalkalden** (Schmalkalden, Germany)
  - Built & validated a radar-inertial slip-mitigation architecture on a custom 2WD differential-drive AMR (FMCW radar + encoders); trajectory drift reduced under all tested slip conditions.
  - Implemented an IT2-FLC in ROS 2 (Ubuntu 24.04) with VESC 6 MK VI motor control over CAN; built a SolidWorks→URDF digital twin validated in Gazebo/RViz2 via SIL/HIL.
  - Real-time Doppler signal processing (median + EMA filters); ToF-based localization/mapping; ROS 2 robotic-arm manipulation.
- **Graduate Teaching Assistant — Mechatronics Eng.** (10/2020 - 06/2024) - **AFIT Kaduna** (Kaduna, Nigeria)
  - Designed labs on automation, mobile-robot navigation, sensor integration; mentored students on control systems & embedded C++/Linux; supported autonomous-navigation / multi-sensor-fusion research.
- **Junior Software Engineer** (07/2016 - 02/2018) - **Sensotronica Ltd.** (Minsk, Belarus)
  - Built web/AR operator interfaces for industrial monitoring; optimized C++/Linux software, reducing system response latency.

### Technical Skills
- **Primary:** ROS 2, C++, Python, AMR/AGV & mobile robotics, control systems (IT2-FLC, PID, FOC/BLDC), SLAM & sensor fusion
- **Secondary:** MATLAB/Simulink, motion planning/navigation, embedded Linux, CAN bus, signal processing, JavaScript (web/HMI)
- **Domain:** Autonomous mobile robots for intralogistics / warehouse automation; mechatronics & automation engineering
- **Software:** Gazebo, RViz2, URDF/XACRO, SolidWorks/CAD, Git, VESC, FMCW radar (SICK), ToF, Luxonis OAK-D; SIL/HIL, V-Model, digital twin

### Certifications
- (None on CV — add MOOCs / professional certs if any.)

### Publications
- (None listed.)

### Awards
- **DAAD-Stipendium** - full Master's-study scholarship, Deutscher Akademischer Austauschdienst (2024-2026)

### Behavioral Profile
<!-- Inferred from CV (no formal assessment yet) — review/replace. See 02-behavioral-profile.md. -->
- **End-to-end builder** - takes systems from CAD/digital-twin through embedded integration, control, and validation
- **Methodical & rigorous** - V-Model, SIL/HIL, quantified validation before trusting hardware
- **Strengths:** deep robotics/controls problem-solving, hands-on hardware bring-up, teaching/communicating technical concepts
- **Growth areas:** first industry role (research/teaching background); German B2→C1
- **Thrives in:** focused, hands-on technical work on real robotics problems with modern stacks and mentorship

### What Excites You
- Building autonomous mobile robots that work in the real world — control, perception, and bringing hardware to life
- Solving hard engineering problems end-to-end (sensing → control → simulation → validated hardware)

### Target Sectors
- Robotics / intralogistics & warehouse automation: AMR/AGV makers, robotics startups, logistics-automation firms
- Mechatronics & industrial automation: robotics R&D, controls, perception, and robotics-software teams (Germany/DACH)

### Deal-breakers
- Roles requiring relocation outside Germany/DACH (unless fully remote)
- Pure maintenance/support or purely managerial roles with no hands-on engineering

## Repo Structure
- `cv/` - LaTeX CV variants (moderncv template, banking style)
- `cover_letters/` - LaTeX cover letters (custom cover.cls template)
- `.claude/skills/` - AI skill definitions for the application workflow
- `.agents/skills/` - Job search CLI tools

## Workflow for New Job Applications
1. User provides a job posting (URL or text)
2. **Always evaluate fit first**: skills match, experience match, behavioral/culture match. Present this assessment to the user before proceeding.
3. If good fit: create targeted CV (`cv/main_<company>.tex`) and cover letter (`cover_letters/cover_<company>_<role>.tex`)
4. **Verify both documents** (see Verification Checklist below)
5. Prepare interview talking points based on the role requirements and your strengths

**Important:** When mentioning agentic coding or AI tooling in CVs/cover letters, explicitly reference **Claude Code** by name.

## Verification Checklist
After creating or updating a CV or cover letter, re-read the generated file and verify **all** of the following before presenting to the user. Report the results as a pass/fail checklist.

### Factual accuracy
- [ ] All claims match actual profile (CLAUDE.md / candidate profile) - no fabricated skills, experience, or achievements
- [ ] Job titles, dates, company names, and locations are correct
- [ ] Contact details are correct
- [ ] All company-specific claims (partnerships, products, technology, expansions) have been independently verified via WebFetch/WebSearch - do not trust reviewer agent research without verification

### Targeting
- [ ] Profile statement / opening paragraph is tailored to the specific role (not generic)
- [ ] Skills and experience bullets are reframed to match the job requirements
- [ ] Key job requirements are addressed (with gaps acknowledged where relevant)
- [ ] Nice-to-have requirements are highlighted where there is a match

### Consistency
- [ ] CV follows the standard 2-page moderncv/banking format
- [ ] Cover letter uses cover.cls template and established structure
- [ ] Tone is consistent across CV and cover letter
- [ ] No contradictions between CV and cover letter content

### Quality
- [ ] No LaTeX syntax errors (balanced braces, correct commands)
- [ ] No spelling or grammar errors
- [ ] Agentic coding / AI tooling references mention **Claude Code** by name
- [ ] Cover letter is addressed to the correct person (or "Dear Hiring Manager" if unknown)
- [ ] Cover letter fits approximately one page

### Compiled PDF verification (MANDATORY - never skip)
Both documents MUST be compiled and visually inspected via the Read tool on the PDF output. "Looks fine in the .tex" is not acceptable - LaTeX page-break decisions are unpredictable. Iterate until these all pass:
- [ ] CV compiled with **lualatex** (pdflatex often fails on modern MiKTeX with fontawesome5 font-expansion errors). Cover letter compiled with **xelatex** (cover.cls requires fontspec).
- [ ] **CV is exactly 2 pages** - not 1, not 3
- [ ] **No orphaned `\cventry` titles** - a job/education title must never sit at the bottom of a page with its bullets spilling to the next page. Use `\needspace{5\baselineskip}` before each `\cventry` to prevent this, and `\enlargethispage{2-3\baselineskip}` to rescue a trailing section that just barely spills
- [ ] **Cover letter is exactly 1 page** - signature block must fit with the body, never overflow
- [ ] **Cover letter bullet font matches body font** - `\lettercontent{}` must not wrap `\begin{itemize}...\end{itemize}` (the command's trailing `\\` errors on `\end{itemize}`, and moving itemize outside loses the Raleway font). Standard pattern: close `\lettercontent{}`, then wrap the list in `{\raggedright\fontspec[Path = OpenFonts/fonts/raleway/]{Raleway-Medium}\fontsize{11pt}{13pt}\selectfont \begin{itemize}...\end{itemize}\par}`
