---
**Document:** Emerging_Verticals.md
**Version:** 1.1
**Last Updated:** 2026-02-18
**Owner:** Business Development
**Update Frequency:** Monthly
**Parent:** Case_Studies_Library.md

**Synthesized From:**
- `Founder_Track_Record.md` v1.0 (coverage: ~100% for EdTech/AgriTech projects)

**What Changed:**
- v1.0 (2026-02-10): Initial creation — 7 Nexrizen case studies
- v1.1 (2026-02-18): Added 5 founder track record projects (F4, F12, F18, F21, F25)

**Downstream Dependencies:**
- README.md - Index file references this
- Case_Studies_Library.md - Master index references this
- Sales playbooks and proposals may reference specific cases
- Emerging opportunity tracking
---

# Emerging Verticals Case Studies

**Total Cases:** 12 (7 Nexrizen + 5 Founder Track Record)
**Status Mix:** 1 discovery delivered / 1 discovery complete / 1 consultation / 4 early stage + 5 completed (pre-Nexrizen)

Emerging verticals represent opportunities where Nexrizen is exploring new markets or early-stage engagements that haven't yet matured into full production systems. These case studies demonstrate breadth of capability and willingness to tackle novel problems across diverse industries.

---

## Quick Reference

| Case Study | Client | Status | Budget | Key Metric |
|------------|--------|--------|--------|------------|
| Voice Agent Turn-Taking | Nathan (Trice) | 📝 Discovery Delivered | Premium | 600-1000ms → 200ms |
| Heritage Football Scouting | Ross & Alistair | 📝 Discovery Complete | Long-term retainer | 23K → 300K players |
| Car Dealership AI Receptionist | Dan Bilthouse | 📝 Consultation | TBD | 24/7 coverage |
| Habit Tracking App | Gregory Zlevor | 📝 Early Discovery | TBD | TBD |
| Fashion Trend Analysis | Latifa | 📝 Folder Created | TBD | TBD |
| Lumetica Engineering | Lumetica | 📝 Folder Created | TBD | TBD |
| Maui Consulting | Kevin (Maui) | 📝 Transcript Exists | TBD | TBD |
| **Founder Track Record** | **Pre-Nexrizen** | | | |
| F4: Moxie — AI Writing Assistant | Wei (Fractional CTO) | ✅ Completed | — | $300K+ pre-seed raise |
| F12: Education Workforce Analytics | Wei (Consulting) | ✅ Completed | — | $1M potential savings |
| F18: EdTech Analytics Dashboard | Wei (Consulting) | ✅ Completed | — | 10K+ users, 70% faster |
| F21: Peer Feedback — EdTech | Gabe (Founded) | ✅ Completed | — | 7,000+ students, 10 years |
| F25: ABACROP — Precision Agriculture | Gabe (Fractional CTO) | ✅ Completed | — | MVP in 3 months |

---

## Case Study 25: Voice Agent Turn-Taking Optimization

**Client:** Nathan Stratton (Trice - Voice AI for Businesses)
**Client Type:** AI Voice Agents / Telecommunications
**Project:** Custom turn-taking/end-pointing model to reduce latency in voice agents
**Status:** 📝 Initial meeting held, discovery to be delivered

### Problem
- Current voice agent latency: 600-1000ms turn-around time
- Goal: Reduce to ~200ms (aggressive target)
- Biggest time consumer: Turn-taking/end-pointing detection
- Attempted to license Sparrow technology (declined)
- Own infrastructure (on-prem GPUs, no cloud dependencies)
- Stochastic nature creates validation challenges

### Solution
Custom turn-taking model (not Gemini-based). Training data: Switchboard corpus, YouTube interviews, client's own call recordings. Real-time inference optimized for on-device GPUs. Integration with existing ASR and TTS alternatives. Handles conversational overlap and natural pauses.

### Technologies
- Deep learning
- Speech processing
- Turn-taking detection
- End-pointing models
- Real-time inference
- On-premises GPU deployment
- Hugging Face models

### Team
Wei + speech ML specialists

### Sales Usage
Voice AI companies, call centers wanting low-latency agents, businesses requiring on-premises AI for data security. **Unique differentiator:** On-prem voice infrastructure (not cloud-dependent) - key competitive advantage.

---

## Case Study 26: Heritage-Based Football Scouting Platform

**Client:** Ross & Alistair (International Football Consultancy, Scotland/New Zealand)
**Client Type:** Professional Sports / Football (Soccer) Scouting
**Project:** Automated heritage-based eligibility finder for international football opportunities
**Status:** 📝 Discovery complete, comprehensive documentation delivered

### Problem
- Current system: Too many bolt-ons and subscriptions (web scraping, findmypast.com, monthly retainer to Indian agency)
- First offshore attempt failed to meet expectations
- Suspects current system "quite basic in background - possibly could be done in Excel"
- Manual weighting and scoring by Ross
- Database needs to scale from 23K → 200-300K players
- Communication barriers with offshore team

### Solution
**Phase 1:** Automated web scraping (league player rosters, stats, contract info)

**Phase 2:** Heritage data integration (ancestry databases for player eligibility)

**Phase 3:** Weighted scoring algorithm (heritage strength, player performance, career stage, contract status)

**Phase 4:** Web application (searchable database, opportunity matching)

Full IP ownership, standalone system. Monthly maintenance retainer.

### Technologies
- Web scraping
- Ancestry database APIs
- PostgreSQL
- Weighted scoring algorithms
- Player profile aggregation
- Dashboard UI

### Budget
[Long-term build + monthly retainer model discussed]

### Team
Wei + full-stack team

### Sales Usage
Sports agencies, niche B2B platforms, businesses with complex weighted scoring needs, international compliance/eligibility checking. **Unique differentiator:** Niche intersection of sports scouting + genealogy - identifies hidden international eligibility opportunities.

---

## Case Study 27: Car Dealership AI Receptionist

**Client:** Dan Bilthouse
**Client Type:** Automotive / Car Dealerships
**Project:** AI phone receptionist for car dealership lead qualification
**Status:** 📝 Consultation held 01-14-2026

### Problem
- Dealerships need 24/7 phone coverage for inbound leads
- Manual qualification of tire-kickers vs serious buyers
- Need to route qualified leads to sales team efficiently
- Appointment scheduling automation

### Solution
AI voice agent answers dealership calls. Qualification questions (budget, timeline, trade-in, financing needs). CRM integration for lead handoff. Appointment booking. After-hours coverage.

### Technologies
- Voice AI
- Telephony integration
- CRM integration
- Appointment scheduling API

### Team
Wei + voice AI team

### Sales Usage
Automotive industry, high-volume phone-based businesses, lead qualification needs, after-hours coverage. **Unique differentiator:** Dealership-specific qualification logic (understands car buying journey).

---

## Case Study 28: Habit Tracking App

**Client:** Gregory Zlevor
**Client Type:** Wellness / Habit Formation
**Project:** [Early discovery, NOTES.md exists]
**Status:** 📝 Early discovery

### Problem
[Not documented yet]

### Solution
[TBD]

### Technologies
[TBD]

### Sales Usage
[Information pending]

---

## Case Study 29: Fashion Trend Analysis

**Client:** Latifa
**Status:** 📝 Project folder created, no content

### Sales Usage
[Pending documentation]

---

## Case Study 30: Lumetica Engineering Project

**Client:** Lumetica
**Status:** 📝 Project folder created, no content

### Sales Usage
[Pending documentation]

---

## Case Study 31: Maui Consulting Recording

**Client:** Kevin (Maui-based)
**Status:** 📝 Discovery, transcript exists

### Sales Usage
[Pending transcript analysis]

---

## Founder Track Record (Pre-Nexrizen)

> **Important:** These are NOT Nexrizen client projects. Frame them as "our founders' track record" or "what our team has built before," not as Nexrizen deliverables.

---

### F4: Moxie (Academic Insight Lab) — AI Writing Assistant

**Client Type:** EdTech / AI Research Tools
**Role:** Fractional CTO (October 2023 – April 2024) — Gabe also worked here as Senior Engineer
**Status:** ✅ Completed (contributed to $300K+ raise)

#### Problem
Moxie had an AI-powered writing assistant built as a no-code MVP. It lacked robustness, customizability, and IP independence needed for institutional partnerships and Series A readiness.

#### Solution
- Recruited and led a high-caliber technical team (data scientists + engineers)
- Transformed no-code MVP into robust, customizable platform
- Developed technical strategic vision for optimal utilization of seed funding toward Series A
- Designed KPIs and analytics frameworks to measure AI tool impact on research quality
- Led IP and technology licensing discussions with partner companies

#### Results
- Contributed to successful **$300K+ pre-seed funding round**
- Platform readied for institutional deployment
- KPI framework enabled data-driven product decisions

#### Technologies
Django, AI/ML, NLP, HECVAT/FERPA compliance, research analytics

#### Team
Wei (Fractional CTO) + Gabe (Senior Engineer) + technical team

#### Sales Usage
**Use when:**
- Selling Fractional CTO services (demonstrates the role in action)
- EdTech prospects
- Proving ability to transform MVPs into production-ready platforms
- **Verticals:** EdTech, research institutions, AI startups

**Note:** Both founders worked at Moxie — demonstrates pre-Nexrizen collaboration.

---

### F12: Predictive Analytics for Education Workforce

**Client Type:** EdTech Company
**Role:** Consultant via Insight Expansion
**Status:** ✅ Completed (discovery + model)

#### Problem
An EdTech company needed to optimize substitute teacher placement across a large school district. Fill rates were suboptimal, costing the system significantly.

#### Solution
- Analyzed historical data covering 500,000+ teacher absences
- Identified key factors influencing fill rates through comprehensive analysis
- Built ML model improving substitute matching accuracy
- Created phased implementation roadmap for executing data science use cases

#### Results
- **25% improvement** in substitute matching accuracy
- **$1M potential annual savings** identified
- Data-driven insights from 500,000+ historical records

#### Technologies
Python, ML classification/regression, historical data analysis, workforce optimization

#### Team
Wei (lead data scientist)

#### Sales Usage
**Use when:**
- Selling predictive analytics for workforce optimization
- Demonstrating data science discovery process
- **Verticals:** EdTech, HR/staffing, workforce management

---

### F18: Scalable EdTech Analytics Dashboard

**Client Type:** EdTech Platform
**Role:** Consultant via Insight Expansion
**Status:** ✅ Completed

#### Problem
An EdTech platform serving 10,000+ users needed a high-performance analytics dashboard. Existing dashboards were slow and deployments took days.

#### Solution
- Developed high-performance analytics dashboard
- Engineered efficient data models with materialized views
- Built responsive frontend using React and D3.js
- Set up CI/CD pipeline using Docker and GitHub Actions

#### Results
- **70% improvement** in dashboard load time
- **10,000+ users** served
- New feature deployment reduced from **days to hours**

#### Technologies
React, D3.js, Django ORM, materialized views, Docker, GitHub Actions, CI/CD

#### Team
Wei (full-stack developer)

#### Sales Usage
**Use when:**
- Selling dashboard development or analytics platforms
- Demonstrating full-stack capability (backend + frontend + DevOps)
- **Verticals:** EdTech, SaaS, analytics platforms

---

### F21: Peer Feedback — EdTech Platform

**Client Type:** EdTech / Higher Education
**Role:** Founder (December 2015 – December 2025, 10 years)
**Status:** ✅ Completed (10-year run)

#### Problem
Large online courses at Georgia Tech lacked effective peer feedback mechanisms. Students needed structured, research-based collaborative learning with AI-powered evaluation.

#### Solution
- Built full-stack EdTech SaaS platform from scratch
- Implemented AI-powered feedback evaluation system
- Integrated with Canvas LMS for seamless data import
- Implemented research-based collaborative learning features
- Maintained and evolved the platform for a full decade

#### Results
- **7,000+ students** served at Georgia Tech
- **10-year operation** — longest sustained entrepreneurial commitment
- Canvas LMS integration adopted across courses
- Research-based approach validated in academic environment

#### Technologies
Django, full-stack web development, AI/ML evaluation, Canvas LMS API, PostgreSQL

#### Team
Gabe (sole founder/developer for most of lifecycle)

#### Sales Usage
**Use when:**
- Demonstrating long-term commitment and sustainability (10 years!)
- Selling to EdTech or higher education prospects
- Proving ability to build and maintain systems at scale
- **Verticals:** EdTech, higher education, LMS integrations

---

### F25: ABACROP — Precision Agriculture

**Client Type:** AgriTech / Precision Farming
**Role:** Fractional CTO (May 2023 – May 2024)
**Status:** ✅ Completed

#### Problem
An agricultural technology company needed a crop monitoring MVP built rapidly and with the right technical architecture for scaling.

#### Solution
- Led development team to build crop monitoring MVP in 3 months
- Architected precision agriculture technology stack
- Provided strategic technology direction for the product roadmap

#### Results
- **MVP delivered in 3 months**
- Precision agriculture tech stack architected for scale
- Foundation established for continued product development

#### Technologies
AgriTech, crop monitoring, sensor integration, web application, data visualization

#### Team
Gabe (Fractional CTO) + development team

#### Client Testimonial
> "Improved efficiency." — Josue Roman, ABACROP

#### Sales Usage
**Use when:**
- Demonstrating rapid MVP delivery
- Selling to AgriTech or IoT companies
- Proving cross-vertical adaptability
- **Verticals:** Agriculture, IoT, environmental monitoring

---

## Emerging Verticals Portfolio Summary

### Common Themes

**Voice AI:**
- Turn-taking optimization (low-latency)
- On-premises deployment (data security)
- Real-time inference (GPU optimization)
- Automotive use cases (dealership receptionists)

**Niche B2B Platforms:**
- Sports scouting (heritage-based eligibility)
- Complex scoring algorithms (weighted criteria)
- Web scraping + data aggregation
- Industry-specific workflows

**Wellness/Consumer:**
- Habit tracking
- Behavior change
- Mobile-first
- Gamification

### Sales Strategy

**Emerging Verticals Approach:**
1. **Explore breadth** - Don't say no to interesting problems
2. **Discovery phase** - Low-commitment, high-learning
3. **Pattern recognition** - Find common themes across one-offs
4. **Productize when ready** - Turn repeated patterns into offerings

**When to Invest:**
- Strong technical challenge (learn new capabilities)
- High-value client (worth custom build)
- Repeatable pattern (could serve multiple clients)
- Strategic positioning (enter new market)

**When to Pass:**
- Too far from core competencies
- Low budget, high complexity
- One-off with no repeatability
- Client not decision-ready

### Potential Vertical Clusters

**Voice AI Market:**
- Car dealerships (Case Study 27)
- Insurance agencies (Case Study 4)
- Professional services (consultation scheduling)
- Healthcare (patient intake)

**Sports Tech:**
- Heritage scouting (Case Study 26)
- Baseball analytics (Case Studies 8-9)
- Performance analysis
- Coaching tools

**Wellness/Consumer Apps:**
- Habit tracking (Case Study 28)
- Fitness (adjacent to sports tech)
- Mental health tracking
- Behavior change

### Next Steps for Emerging Verticals

**Voice AI:**
- [ ] Complete Trice discovery (turn-taking optimization)
- [ ] Build dealership AI receptionist MVP
- [ ] Package "Voice AI for [Industry]" offering
- [ ] Target call center / contact center market

**Sports Tech:**
- [ ] Deliver heritage scouting Phase 1
- [ ] Bundle baseball + scouting as "Sports Data Platform"
- [ ] Target youth sports market (parents/coaches)
- [ ] Explore esports analytics

**Niche B2B:**
- [ ] Look for more "scraping + scoring + dashboard" opportunities
- [ ] Build reusable components (web scraping, weighted scoring)
- [ ] Target industries with complex eligibility/compliance

**Consumer/Wellness:**
- [ ] Evaluate habit tracking app potential
- [ ] Consider white-label wellness platform
- [ ] Explore fitness coaching market

### Risk Management

**Early-Stage Projects:**
- ✅ Discovery phase = low financial commitment
- ✅ Learn before building (avoid waste)
- ✅ Client pays for discovery (not free consulting)
- ⚠️ Don't over-invest in one-offs
- ⚠️ Look for repeatability before full build

**Market Validation:**
- Does this problem exist for multiple clients?
- Is the client representative of a market?
- Can we package this as a product later?
- Does this build on our existing strengths?

---

**Last Updated:** 2026-02-10
