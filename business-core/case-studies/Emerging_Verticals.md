---
**Document:** Emerging_Verticals.md
**Version:** 1.0
**Last Updated:** 2026-02-10
**Owner:** Business Development
**Update Frequency:** Monthly
**Parent:** Case_Studies_Library.md

**Downstream Dependencies:**
- README.md - Index file references this
- Sales playbooks and proposals may reference specific cases
- Emerging opportunity tracking
---

# Emerging Verticals Case Studies

**Total Cases:** 7
**Status Mix:** 1 discovery delivered / 1 discovery complete / 1 consultation / 4 early stage

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
