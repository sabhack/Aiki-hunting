# Interview Preparation Guide

<!-- SETUP: STAR examples are personalized by running /setup based on your actual experience -->

## STAR Format

Structure answers as: **Situation** (context), **Task** (your responsibility), **Action** (what you did), **Result** (outcome).

Keep answers to 1-2 minutes. Be specific. End with what you learned or would do differently.

## Ready-Made STAR Examples

<!-- Drafted from CV (Path A). ⚠️ Verify/insert concrete numbers where marked before using. -->

### 1. Radar-Inertial AMR Slip Mitigation (flagship — problem-solving, controls, sensor fusion)
**S:** Autonomous mobile robots in intralogistics lose tracking on slippery warehouse floors — wheel odometry reports motion the robot isn't actually making, causing trajectory drift.
**T:** As the research lead on the "Sabby Robby" AMR (M.Eng. thesis), design a control architecture that holds trajectory under variable floor friction.
**A:** Fused FMCW radar (SICK RMS2000) ground-velocity with magnetic-encoder odometry; built signal-conditioning (median filter N=5 + EMA β=0.85) for stable slip-ratio estimation independent of friction; implemented an Interval Type-2 Fuzzy Logic Controller in ROS 2 driving VESC 6 MK VI motor controllers over CAN for real-time torque correction; validated via a SolidWorks→URDF digital twin in Gazebo/RViz2 with SIL then HIL.
**R:** Trajectory drift reduced under all tested slip conditions; slip-ratio estimation stable regardless of floor friction. *[Add specific % / error figures if available.]*
**Use for:** "Walk me through a hard technical problem", "Describe a project end to end", "Tell me about sensor fusion / control work"

### 2. Digital Twin & SIL/HIL Validation (rigor, simulation, test engineering)
**S:** Testing new control code directly on real robot hardware risks damage and gives slow, noisy feedback.
**T:** Establish a validation pipeline so the control stack could be verified before touching hardware.
**A:** Built a high-fidelity digital twin in SolidWorks, exported to URDF, and stood up the full control stack in Gazebo + RViz2; ran Software-in-the-Loop first, then Hardware-in-the-Loop, following a V-Model methodology.
**R:** Caught issues in simulation before hardware runs and enabled confident, repeatable iteration on the controller. *[Add iteration-speed / defect-catch detail if available.]*
**Use for:** "How do you ensure quality?", "Tell me about your testing approach", "Simulation vs. real hardware"

### 3. Teaching & Mentoring Engineering Students (communication, collaboration)
**S:** Undergraduate mechatronics cohorts at AFIT needed practical instruction in automation, navigation, and embedded control.
**T:** As Graduate Teaching Assistant, design and deliver labs and mentor students on real implementation.
**A:** Built lab exercises on automation principles, mobile-robot navigation, and sensor integration; mentored students on control-systems implementation and embedded C++/Linux; supported research on autonomous navigation and multi-sensor fusion.
**R:** Delivered hands-on labs across multiple cohorts over ~3.5 years and strengthened students' practical control/embedded skills.
**Use for:** "Tell me about a time you explained something complex", "How do you work in a team / mentor others?"

<!-- Add a 4th (e.g. Sensotronica C++ latency-reduction / AR HMI) covering software-engineering depth. -->

## Common Tough Questions

<!-- Draft answers tailored to Muhammad's profile — refine in your own voice. -->

### "Why are you moving from research/academia into industry?" (or "why leave teaching?")
> I love the engineering itself — taking a robotics problem from idea to validated hardware. My thesis gave me deep research rigor; now I want to apply that on real products with a team and see robots deployed, not just demonstrated. That's why I'm targeting an industry robotics role.

### "You don't have full-time industry experience / [specific skill]."
> True — my robotics depth comes from research and a custom-built AMR rather than a product team yet. But I've owned a full stack end to end (sensing → ROS 2 control → digital twin → SIL/HIL), I work in C++/Linux daily, and I pick up new tools fast (I taught them for years). On [specific gap], I'd point to the closest thing I've done and how quickly I ramped on it.

### "Where do you see yourself in 5 years?"
> Established as a robotics/controls engineer specializing in autonomous mobile robots for intralogistics — owning real subsystems (perception, control, or motion), fluent in German, and ideally mentoring newer engineers the way I did as a TA.

### "What's your biggest weakness?"
> My German is B2 and improving toward C1 — I'm comfortable technically in English and in German-speaking teams, and I'm actively closing that gap. Also, most of my robotics work has been research-grade; I'm deliberately seeking an industry role to build production discipline (CI, code review at scale, deployment) on top of my engineering foundation.

### "Why this company specifically?"
> Customize per company. Must reference: specific projects, company values, market position, or team structure. Never give a generic answer.

## Questions You Should Ask Interviewers

### About the Role
- "What does a typical week look like in this role?"
- "What would success look like in the first 6 months?"
- "What's the biggest challenge the team is facing right now?"

### About the Team
- "How big is the team, and how do you divide work?"
- "What does the development/project lifecycle look like, from idea to production?"
- "How do you onboard new team members?"

### About Tech & Growth
- "What's your current tech stack for [relevant area]?"
- "Is there room to grow into more architectural or strategic decisions?"
- "How does the team stay current with new tools and methods?"

### About Culture (use these to prevent disappointment)
- "How would you describe the team culture?"
- "What does professional development look like here?"
- "Is there flexibility for remote/hybrid work?"
- "What's the balance between development/new projects and maintenance work?"
- "How would you describe the leadership style in this team?"
- "What do people who thrive here have in common?"

## Phone/Video Interview Tips
- Have STAR examples written out (use this file)
- Keep a glass of water nearby
- Smile when speaking (it changes your tone)
- Ask for clarification if a question is vague
- It's OK to take 5 seconds to think before answering
- End with: "Is there anything else you'd like to know about my background?"

## After the Application (Best Practice)

### Follow-Up Etiquette
- **Don't call to "stand out"** or to learn more about the role post-submission - this risks a negative impression
- If the employer specified a timeline, respect it and wait
- If no timeline was given and significant time has passed (2+ weeks), a brief call to ask about status is acceptable
- If you have genuinely new, relevant information to share, a short follow-up is fine

### Thank-You Notes
- When you receive any update (interview invitation, rejection, or status update), send a brief thank-you message
- Express appreciation for their time and the process
- Keep it short (2-3 sentences)

## Roleplay Guidelines
When the user asks for interview practice:
1. Ask which role/company to simulate
2. Start with easy warm-up questions ("Tell me about yourself")
3. Progress to role-specific technical questions
4. Include 1-2 behavioral questions using the competencies from the job posting
5. End with a tough question or curveball
6. After each answer, give brief feedback: what worked, what to sharpen
7. Suggest which STAR example would work best for each question
