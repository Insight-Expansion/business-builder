---
**Document:** Sales_Process_Framework.md
**Version:** 1.0
**Last Updated:** 2026-02-10
**Owner:** Sales (Wei/Gabe)
**Update Frequency:** Monthly or when process changes

**Synthesized From:**
- `../../meetings/sales-intros/*` (coverage: ~90%)
- `../../business-core/Nexrizen_Business_Overview.md` (coverage: ~80%)

**What Changed:**
- v1.0 (2026-02-10): Initial extraction from successful sales conversations
- v1.1 (2026-02-10): Added automated demo generation, greenfield/brownfield qualification, conference/Upwork metrics, 3-Day service performance data

**Downstream Dependencies:**
- `Sales_Playbook.md` - Tactical scripts and talk tracks
- `Sales_Onboarding.md` - Training new sales team members
- `CRM_Workflow.md` - System automation requirements

**Completeness:** ✅ Complete - Ready for team training
---

# Nexrizen Sales Process Framework

**Purpose:** Document Wei's battle-tested sales process that achieves ~50% close rate on warm Upwork leads. This process is designed to be taught to Gabe, Ruth, and future sales team members.

---

## Core Philosophy: "Show, Don't Tell"

**Traditional Agency Sales:**
1. Discovery call → 2. Requirements gathering → 3. Proposal → 4. Negotiation → 5. Contract → 6. Kickoff
**Problems:** Long cycle, high friction, trust issues

**Nexrizen Sales (Wei's Innovation):**
1. Discovery call → 2. **FREE PROOF OF CONCEPT** → 3. Proposal → 4. Contract → 5. Kickoff
**Benefits:** Builds trust immediately, differentiates from ALL competitors, shortens cycle

---

## The "Proof Before Payment" Sales Process

### Phase 1: First Contact (15-30 min call)

**Goal:** Gather enough information to build a proof of concept

**What to Extract:**
1. **Problem Statement** - What are they trying to solve?
2. **Current State** - How do they do it today?
3. **Ideal Outcome** - What does success look like?
4. **Technical Context** - Existing systems, data sources, integrations
5. **Budget Signals** - Not asking directly, but listening for constraints
6. **Timeline Pressure** - How urgent is this?

**Key Questions Wei Asks:**
- "Do you mind just giving me a quick synopsis of what you're trying to do?"
- "What's the current state of [your system/process]?"
- "What's the biggest pain point right now?"
- "What systems are you currently using?" (Airtable, Make, CRM, etc.)
- "Have you worked with developers before? What was that experience like?"

**What Wei Does DURING the Call:**
- Records the entire meeting (with permission)
- Takes minimal notes (AI will transcribe later)
- Focuses on rapport and understanding, not selling
- Shares similar case studies: "We actually just built something like this for..."
- Plants the seed: "I can show you a proof of concept by [date]"

**What Wei Does NOT Do:**
- ❌ Give pricing on the call
- ❌ Promise specific timelines for full build
- ❌ Oversell capabilities
- ❌ Ask for commitment

**Call Ending:**
> "I have sufficient information from this meeting. Let me use the transcript to build a super early proof of concept for you. If you can send me [specific asset: video, data, etc.], I'll have something to show you by [1 week from now]. No cost, no commitment—just want to show you what we can do."

---

### Phase 2: POC Development (3-7 days)

**What Happens Internally:**
1. Meeting transcript auto-uploaded to Proposal Builder
2. AI synthesizes into Client Discovery Notes
3. Wei reviews and identifies highest-ROI proof of concept
4. Engineers build POC (usually 4-16 hours of work)
5. Wei prepares demo environment

**POC Selection Criteria:**
- **High Impact, Low Effort** - Show value fast
- **Visually Impressive** - Something they can see/interact with
- **Directly Addresses Pain** - Not a tangent feature
- **Uses Real Data** (if provided) - Makes it feel real

**Types of POCs by Project:**
| Project Type | POC To Build |
|--------------|--------------|
| **Chatbot/Voice AI** | Working conversational flow with 3-5 intents |
| **Dashboard** | Mock dashboard with sample data visualization |
| **Automation** | Single workflow automated end-to-end |
| **Document Processing** | Process one real document, show output |
| **Video Analysis** | Analyze one video, show structured output |

**Quality Bar:** POC should be 40-60% of full solution, not a toy demo

---

### Phase 3: POC Demo (30-45 min call)

**Goal:** Prove capability, establish trust, move to proposal

**Demo Script:**
1. **Recap Problem** (2 min)
   > "When we last spoke, you mentioned [problem]. Here's what I built..."

2. **Show POC** (10-15 min)
   - Share screen
   - Walk through functionality
   - Use their data/examples if possible
   - Highlight how it addresses their pain

3. **Gather Feedback** (5-10 min)
   - "What do you think?"
   - "Is this what you had in mind?"
   - "What would you change?"
   - Record this meeting too (refines requirements)

4. **Bridge to Full Solution** (5-10 min)
   - "This is about 40-50% of what the full system would do"
   - "Here's what else we'd add: [features]"
   - "Timeline would be [X weeks] for the complete build"

5. **Pricing Introduction** (5 min)
   - "For a project like this, based on what we've discussed, we're looking at [range]"
   - "I'll send you a detailed proposal with solution architecture, timeline, and exact pricing"
   - Use ranges first, exact numbers in proposal

6. **Next Steps** (2 min)
   - "I'll send over a proposal by [date]"
   - "If you like what you see, we can start as soon as you sign"
   - "Any questions I should address in the proposal?"

**Wei's Exact Language:**
> "We're so fucking good at building software. Like I can show you a proof of concept... We're completely changing the way sales is done, right? No one's doing this—we send a working prototype after the first meeting. Conversion goes through the roof."

**What This Achieves:**
- ✅ Establishes technical credibility (they SAW us build it)
- ✅ De-risks the engagement (they know we can deliver)
- ✅ Creates reciprocity (we gave them free work)
- ✅ Differentiates from every competitor (no one else does this)
- ✅ Shortens sales cycle (less "thinking about it" time)

---

### Phase 4: Proposal (Async, 24-48 hour turnaround)

**Proposal Builder System Auto-Generates:**
1. **Project Requirements** - Synthesized from both meetings
2. **Solution Architecture** - Technical approach with diagrams
3. **Timeline & Phases** - Breakdown of delivery schedule
4. **Pricing** - Itemized costs with justification
5. **Engagement Letter** - Contract ready to sign

**Wei's Review Process:**
- Review AI-generated documents (usually 80-90% accurate)
- Add personal touches, adjust pricing
- Send via interactive proposal tool (not static PDF)

**Proposal Contents:**
- Executive Summary (1 page)
- Problem Statement (client's own words)
- Proposed Solution (building on POC)
- Technical Architecture (how it works)
- Timeline (phases, milestones)
- Pricing (with options if applicable)
- Team Bios (Wei, Gabe, relevant engineers)
- Case Studies (2-3 relevant ones)
- Next Steps (sign, kickoff, payment)

**Delivery Method:**
- Interactive web-based proposal (not PDF)
- Includes clickable sections, embedded prototypes
- Tracks when client views it (via CRM)

---

### Phase 5: Negotiation (15-30 min call, if needed)

**Common Negotiation Scenarios:**

**Scenario 1: "This is more expensive than I expected"**
- Show cost breakdown (hourly rate × hours)
- Compare to market rates ($200-300/hr for senior devs)
- Offer phased approach (MVP first, add features later)
- Highlight POC quality as proof of value

**Scenario 2: "Can we reduce scope to reduce cost?"**
- Use Proposal Builder to immediately update scope
- AI back-propagates to requirements, estimates
- Send updated proposal within hours
- Document what's removed (can add later)

**Scenario 3: "I need more features than quoted"**
- "Great, let's add those in Phase 2"
- Or adjust quote if critical for MVP
- Forward-propagate changes through all docs

**Scenario 4: "Timeline is too long/short"**
- Explain resourcing constraints
- Offer to adjust team allocation (affects price)
- Suggest phased delivery if flexible

**Wei's Negotiation Principles:**
- 💰 Don't discount >20% (devalues work)
- ⏱️ Don't promise unrealistic timelines (sets up failure)
- 🤝 Always find win-win (not zero-sum)
- 🚪 Walk away from bad fits (protects team)

---

### Phase 6: Contract & Kickoff (Async + 1 hour call)

**Contract Signing:**
- Send engagement letter (auto-generated)
- Collect signature via DocuSign/HelloSign
- Collect first payment (usually 50% upfront)

**Kickoff Call:**
- Introduce full team (engineers, PMs if applicable)
- Review timeline and milestones
- Set communication cadence (daily standups, weekly check-ins)
- Give client access to project management system (Notion)
- Confirm next deliverable date

**Kickoff Deliverables:**
- Project plan in Notion
- Slack channel or communication method
- Calendar invites for recurring meetings
- Access to prototype/staging environment

---

## The "Dating Phase" Variation (For Strategic Partnerships)

**When to Use:** High-potential partnerships, fractional CTO work, equity discussions

**Modified Process:**
1. **Discovery Call** - Same as above
2. **Propose Hourly "Dating Phase"**
   > "Let's do 10-20 hours a week for the first month, see how we work together. Think of it as dating before marriage. If it works great, we can talk equity, partnership, whatever makes sense."
3. **Deliver Value on Hourly** (4-8 weeks)
   - Bill every 2 weeks
   - Provide detailed timesheets
   - Show tangible progress
4. **Renegotiate** (After proving value)
   - Convert to retainer
   - Discuss equity/rev share
   - Long-term partnership structure

**Used Successfully With:**
- Israel (GoldPro) - Went from "let's talk" to equity discussion
- Zane (AI venture partnership) - Positioned as CTO role
- Robertas (EU fintech partnerships) - Reseller agreement

**Wei's Exact Language:**
> "I see it as a dating phase. We work together and see how we're compatible, right? I don't want to just jump in. You don't want to give me X percent of equity immediately. We work together. I'll come visit. We'll hang out. We'll smoke some, right? Figure out how compatible we are."

---

## Sales Stage Definitions (For CRM Tracking)

| Stage | Definition | Typical Duration | Exit Criteria |
|-------|------------|------------------|---------------|
| **Lead** | Initial contact made | N/A | Discovery call scheduled |
| **Discovery** | First meeting completed | 1-2 days | POC agreed upon |
| **POC Development** | Building proof of concept | 3-7 days | POC demo scheduled |
| **Demo** | Showed POC, gathering feedback | 1-2 days | Proposal requested |
| **Proposal** | Proposal sent, awaiting response | 3-7 days | Negotiation or acceptance |
| **Negotiation** | Discussing terms, scope, pricing | 2-5 days | Contract sent or disqualified |
| **Contract** | Paperwork and payment | 2-5 days | Signed + paid = Won |
| **Won** | Project kicks off | N/A | Project delivered |
| **Lost** | Disqualified or chose competitor | N/A | Document reason |

**Total Sales Cycle:** 2-3 weeks for warm leads (Upwork), 4-6 weeks for cold leads (LinkedIn)

---

## Lead Source Specific Adjustments

### Upwork Leads (Wei's Primary - 50% of volume)
**Performance (3-Day AI Service Launch):**
- **90% response rate** on applications (vs typical 5-10%)
- **75-80% conversion** from response to contract
- **10-12 clients in first month** (Nov 2025)
- Competing against hundreds of applicants per project

**Secret Weapon: Automated Demo Generation**
- Read Upwork project description
- Auto-generate working front-end UI (using Lovable + AI)
- Host on demos.nexrizen.com subdomain
- Send demo link as part of application

**Client Reaction:**
> "Holy shit, you've already built this? How do you have time to do this?"

**Why It Works:**
- Proves capability immediately (not just claims)
- Creates massive reciprocity
- No competitor does this (100% unique differentiator)
- Demonstrates AI capabilities (meta-proof)

**Process:**
- Automated demo generation (before first contact)
- Full POC process as outlined above
- Close Rate: 75-80% (from response to contract)
- Wei's Time: 0 hours for demo + 30 min discovery + 30 min demo call = 1 hour to close

### Conferences (50% of volume - Higher Quality)
**Types:**
- Entrepreneurship conferences
- Immigration law conferences (AILA)
- Industry-specific events

**Performance:**
- Higher project value ($10K+ vs $6K average)
- Longer sales cycles (1-2 months vs 2-3 weeks)
- Enterprise/strategic opportunities
- Referral source relationships

**Process:**
- Face-to-face meeting at conference
- Follow-up call within 1 week
- POC if applicable (depends on project clarity)
- Proposal + close

**Key Success Factor (from Gianfranco):**
> "You need 50-100 face-to-face conversations to really understand a market"

**Current Mix:** 50% Upwork, 50% Conferences (as of Nov 2025)

### LinkedIn Leads (Future - NOT ACTIVE YET)
- **Status:** Not doing outbound marketing yet (too busy with delivery)
- **Qualification:** Will need to qualify harder (may not be in-market)
- **Warmth:** Cold to lukewarm
- **Process:** Add qualification step before POC
- **Close Rate:** TBD (will launch when capacity allows)
- **Adjustment:** Qualify budget + timeline + authority before investing in POC

### Referrals (Immigration Network)
- **Qualification:** Pre-qualified by referrer
- **Warmth:** Warm
- **Process:** Name-drop mutual contact, otherwise same process
- **Close Rate:** TBD
- **Advantage:** Higher trust, shorter cycle

---

## Sales Meeting Rhythms

### Weekly Sales Review (Wei + Gabe)
- Review all active deals (CRM pipeline review)
- Identify blockers (waiting on client, need more info, etc.)
- Assign POC builds (who's building what)
- Review win/loss reasons
- Update sales forecasts

### Monthly Sales Metrics Review
- Close rate by lead source
- Average deal size
- Sales cycle length
- POC conversion rate (POC demo → signed contract)
- Win/loss analysis

---

## Key Metrics to Track

| Metric | Current | Target | How to Improve |
|--------|---------|--------|----------------|
| **Close Rate** | 50% (Upwork) | 60% | Better qualification, stronger POCs |
| **Sales Cycle** | 2-3 weeks | 2 weeks | Faster POC turnaround |
| **Avg Deal Size** | ~$8K | ~$12K | Upsell maintenance, add-ons |
| **Calls/Week** | 15 | 10 qualified | Better lead filtering |
| **POC Conversion** | Unknown | 70% | Track this! |
| **Time to POC** | 5-7 days | 3-5 days | Improve internal systems |

---

## Sales Disqualification Criteria (Walk Away If...)

### Red Flags from Wei's Meetings:

❌ **"I need this done for free"**
- Not a fit for POC process (they expect everything free)

❌ **"Can you build this in 2 days?"**
- Unrealistic timeline expectations (will be unhappy customer)

❌ **"We want to own all your IP and systems"**
- Would require Proposal Builder, internal systems (not for sale)

❌ **Asshole behavior**
- Rude, dismissive, demanding
- Wei: "We don't work with assholes"

❌ **No budget / tire kicker**
- "What can you build for $500?"
- Not serious buyer

❌ **Overly complex / unclear requirements**
- Can't extract clear problem in 30 min call
- Suggests scope creep

❌ **Looking for staff augmentation**
- "We need a full-time developer for 6 months"
- Not Nexrizen's model (project-based)

❌ **Brownfield project with heavy integration** (NEW - from Nick meeting)
- Existing legacy systems requiring deep integration
- Months-long timeline due to existing tech debt
- Requires extensive existing codebase knowledge
- Not Nexrizen's sweet spot (prefer greenfield)

---

## Project Type Qualification: Greenfield vs Brownfield

### Greenfield Projects (NEXRIZEN'S SWEET SPOT)
**Definition:** Brand new systems, no legacy tech, clean slate

**Characteristics:**
- Starting from scratch
- No existing codebase to integrate with
- No technical debt
- Faster delivery (3-12 weeks)
- Clear requirements possible

**Target Clients:**
- SMBs without existing tech teams
- Startups building first product
- New initiatives within larger companies
- Rapid prototypes/MVPs

**Why We Excel:**
- AI-powered development shines on greenfield
- No legacy constraints
- Can use latest tech/frameworks
- 3-Day AI service optimized for this

**Examples:**
- Essay service automation (new system)
- Restoration video AI (new capability)
- Immigration intake (built from scratch)

### Brownfield Projects (REFER TO PARTNERS)
**Definition:** Existing systems requiring integration, legacy code, established architecture

**Characteristics:**
- Integrating with existing systems
- Technical debt to navigate
- Longer timelines (months+)
- Requires deep existing codebase knowledge

**Not Our Fit Because:**
- Slower delivery (can't use AI advantages)
- More debugging than building
- Requires existing team knowledge
- Higher risk of scope creep

**Partner Referral:**
- Nick's agency (focused on brownfield, months-long projects)
- Larger dev shops with dedicated teams

**Qualification Questions:**
1. "Is this a brand new system or integrating with existing?"
2. "Do you have an existing tech stack we need to work within?"
3. "How much of this is greenfield vs integrating with legacy?"

**Decision Matrix:**
- 80%+ greenfield → Take it
- 50-80% greenfield → Evaluate (may take with caveats)
- <50% greenfield → Refer to partner

---

## Objection Handling Scripts

See `Objection_Handling_Library.md` for full scripts. Quick reference:

| Objection | Response |
|-----------|----------|
| **"Too expensive"** | "We're ex-Meta PhDs at offshore prices. Here's the hourly breakdown..." |
| **"Too risky"** | "That's why we build a POC first. See it before you pay." |
| **"Takes too long"** | "3-12 weeks vs industry 6+ months. Speed is our differentiator." |
| **"Already have a dev team"** | "Great! We can work alongside them or hand off the code." |
| **"Need to think about it"** | "Totally understand. What specifically do you need to think about?" |

---

## Sales Tools & Systems

### Current Stack
- **Upwork** - Primary lead source
- **Dripify** - LinkedIn automation
- **Notion** - CRM + project management
- **Proposal Builder** - Custom AI system
- **Google Meet** - Calls (recorded)
- **Loom** - Async demos (sometimes)

### Future Needs
- **GoHighLevel** - Full CRM implementation
- **DocuSign** - Contract signing
- **Stripe/Payment** - Invoicing automation
- **Email Sequences** - Drip campaigns for nurture

---

## Sales Training: Wei → Gabe Handoff

**Goal:** Gabe can run full sales process independently before Wei's retreat

**Training Plan:**
1. **Week 1-2:** Shadow Wei on 5 calls (observe only)
2. **Week 3-4:** Wei shadows Gabe on 5 calls (Gabe leads, Wei supports)
3. **Week 5-6:** Gabe solo on 5 calls (Wei reviews recordings)
4. **Week 7+:** Gabe autonomous, Wei QA weekly

**Skills to Transfer:**
- ✅ Discovery call facilitation
- ✅ POC scoping (what to build)
- ✅ Demo delivery
- ✅ Objection handling
- ✅ Proposal review & customization
- ✅ Negotiation tactics
- ✅ Contract closing

**Gabe's Current Strengths:**
- Technical depth (can go deeper than Wei)
- Demo delivery (great at showing prototypes)
- Daily LinkedIn content (building personal brand)

**Gabe's Development Areas:**
- Volume management (overworked, need to delegate)
- Qualification (may go too deep too fast)
- Saying no (may take on tough projects Wei would decline)

---

## Success Metrics for Retreat Period (Wei Away)

**Minimum Viable:**
- 10 qualified calls/week to Gabe
- $15K/month revenue maintained
- 2-3 deals closed per month
- Ruth executing LinkedIn outreach autonomously

**Stretch Goals:**
- 15 qualified calls/week
- $20K/month revenue
- 4+ deals closed per month
- First maintenance clients upsold

---

## Continuous Improvement

**Monthly Review Questions:**
1. What close rate did we achieve this month? By source?
2. What was average sales cycle? Getting faster?
3. What deals did we lose? Why?
4. What objections came up repeatedly? How can we address earlier?
5. Which POCs converted best? Which flopped?
6. What feedback are we getting from POC demos?
7. How can we reduce sales cycle by 20%?
8. How can we increase deal size by 20%?

**Quarterly Process Audit:**
- Review this document vs actual practice
- Update based on what's working
- A/B test variations (e.g., POC timing, proposal format)
- Train team on updates

---

*Last updated: 2026-02-10*
*Sources: 6 successful sales conversations + Nexrizen business context*
*Owner: Wei (CEO), Gabe (CTO) to execute*
