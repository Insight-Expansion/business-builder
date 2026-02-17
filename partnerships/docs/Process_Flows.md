---
**Document:** Process_Flows.md
**Version:** 1.0
**Last Updated:** 2026-02-10
**Owner:** Wei Zhuo
**Update Frequency:** Quarterly (or when processes change)

**Synthesized From:**
- `context/01_eu-partnership-proposal.md` (coverage: ~85%)
- `context/04_nexrizen-reseller-agreement.md` (coverage: ~90%)
- `context/03_eu-collateral-plan.md` (coverage: ~75%)

**What Changed:**
- v1.0 (2026-02-10): Initial creation

**Downstream Dependencies:**
- Future: `Partner_Onboarding_SOP.md`, `Lead_Attribution_SOP.md`, `Commission_Payment_SOP.md`

**Completeness:** ✅ Complete - All key processes documented
---

# Partnerships Department - Process Flows

## Overview

This document details the step-by-step workflows for managing partner relationships, from initial onboarding through lead introduction, sales process, and commission payment.

---

## Process 1: Partner Onboarding

**Trigger:** New potential partner identified
**Owner:** Wei Zhuo (CEO)
**Duration:** 2-4 weeks from first contact to signed agreement

### Steps

**1.1 Initial Contact & Qualification**
- **Who:** Wei or Gabriel
- **Action:** Initial conversation to assess fit
- **Assess:**
  - Does partner have relevant network for target industries?
  - Does partner understand and value the AI/software space?
  - Is partner professional and values-aligned?
  - What is partner's motivation? (Revenue, value-add to network, learning)

**Output:** Decision to proceed or pass

---

**1.2 Partnership Proposal Preparation**
- **Who:** Wei
- **Action:** Customize partnership proposal template
- **Include:**
  - Partnership model overview
  - Commission structure
  - Services catalog
  - Relevant case studies for partner's network
  - Territory assignment
  - Getting started steps

**Output:** Customized proposal document (see `context/01_eu-partnership-proposal.md` as example)

**Time:** 2-3 hours

---

**1.3 Proposal Review Meeting**
- **Who:** Wei + Gabriel + Partner
- **Duration:** 60-90 minutes
- **Agenda:**
  - Present partnership model
  - Walk through commission structure with examples
  - Show case studies relevant to partner's network
  - Discuss territory and exclusivity
  - Answer questions
  - Identify 2-3 initial prospects for pilot
  - Align on positioning (how partner will describe Nexrizen)

**Output:** Agreement to proceed (or not), clarified terms

---

**1.4 Agreement Drafting & Review**
- **Who:** Wei (with legal review if needed)
- **Action:** Customize reseller agreement template
- **Clarify:**
  - Partner entity details (individual vs company)
  - Territory specifics
  - Payment method and currency preference
  - Any custom terms negotiated

**Template:** `context/04_nexrizen-reseller-agreement.md`

**Output:** Draft agreement sent to partner for review

**Time:** 1-2 days

---

**1.5 Agreement Execution**
- **Who:** Wei (CEO) signs for Nexrizen, Partner signs for their entity
- **Action:** Sign and countersign agreement
- **Method:** DocuSign, Adobe Sign, or wet signature + scan

**Output:** Fully executed agreement, partnership is official

---

**1.6 Partner Enablement**
- **Who:** Wei or designated operations person
- **Action:** Provide partner with collateral and access
- **Deliver:**
  - One-pager (EU executive overview)
  - Case study collection
  - Capability sheets for relevant industries
  - Presentation deck
  - Email templates (or CustomGPT access)
  - FAQ document
  - Logo and brand assets
  - Introduction email address for attribution (e.g., partnerships@nexrizen.com)

**Output:** Partner has all materials needed to begin introductions

**Time:** 1-2 hours (assuming collateral already exists)

---

**1.7 Kickoff / Orientation Call**
- **Who:** Wei + Partner
- **Duration:** 30-45 minutes
- **Cover:**
  - Review attribution process (how to notify of introduction)
  - Review sales process (discovery → prototype → close)
  - Discuss first 2-3 prospects to introduce
  - Set communication cadence (monthly check-ins)
  - Answer any remaining questions

**Output:** Partner ready to make first introductions

---

**Total timeline:** 2-4 weeks from initial contact to first introduction

**Current status:** Robertas/BIG GROUP in step 1.3-1.4 (proposal reviewed, agreement pending)

---

## Process 2: Lead Introduction & Attribution

**Trigger:** Partner identifies potential client
**Owner:** Partner (introduction), Wei/Gabriel (attribution tracking)
**Duration:** Minutes to hours

### Steps

**2.1 Partner Identifies Prospect**
- **Who:** Partner
- **Action:** Evaluate prospect against ideal client profile
- **Consider:**
  - Does prospect fit target industries? (Fintech, healthcare, professional services, etc.)
  - Does prospect have budget authority?
  - What's the specific pain point or opportunity?
  - What's the relationship strength? (Close colleague, family, distant connection)
  - What's the best entry point? (3-Day MVP, custom project, fractional CTO)

**Output:** Decision to introduce or not

---

**2.2 Attribution Notice (BEFORE Introduction)**
- **Who:** Partner
- **Action:** Send email to partnerships@nexrizen.com (or designated contact)
- **Include:**
  - Prospect company name
  - Contact person name and title
  - Brief context on opportunity (1-3 sentences)
  - Industry/vertical
  - Estimated timing

**Example:**
```
Subject: Introduction - Affidea (Healthcare)

Wei,

I'm introducing you to [Name], Chief of Operations at Affidea (affidea.com),
a pan-European diagnostic imaging network. They're exploring AI for patient
intake automation and imaging workflow optimization. Strong relationship -
we've worked together for 10+ years. Planning to make intro this week.

Best,
Robertas
```

**Timeline:** BEFORE or within 48 hours of making introduction (per §1.1 of agreement)

---

**2.3 Nexrizen Reviews & Confirms Attribution**
- **Who:** Wei or Gabriel
- **Action:** Check if prospect is already in CRM or has prior contact with Nexrizen
- **If new:**
  - Reply confirming attribution
  - Add to CRM with partner attribution tag
  - Brief Wei/Gabriel on context from partner email
- **If pre-existing relationship:**
  - Reply notifying partner within 5 business days
  - No commission will apply (per §4.3 of agreement)

**Output:** Attribution confirmed or declined

**Timeline:** Within 5 business days (per `context/04_nexrizen-reseller-agreement.md` §4.2)

---

**2.4 Partner Makes Introduction**
- **Who:** Partner
- **Method:** Email, call, or in-person meeting
- **Content:**
  - Personal greeting (leverage existing relationship)
  - Brief context on why reaching out
  - 2-3 sentences on what Nexrizen does (tailored to prospect's industry)
  - Specific reason this is relevant to them
  - Soft call to action (would you be open to a brief call?)

**Tools available:**
- CustomGPT email generator (see `context/02_customgpt-intro-email-generator.md`)
- Static email templates by industry
- One-pager to attach

**Example structure (from `context/02_customgpt-intro-email-generator.md` lines 64-70):**
1. Personal greeting referencing the relationship
2. Brief context on why reaching out
3. 2-3 sentences on what Nexrizen does (tailored to industry)
4. Specific reason this is relevant to them
5. Soft call to action
6. Warm sign-off

**Output:** Prospect receives introduction

---

**2.5 Nexrizen Follows Up**
- **Who:** Wei or Gabriel
- **Action:** Reach out to prospect within 24-48 hours
- **Method:** Email or phone (depending on introduction method)
- **Content:**
  - Thank partner for introduction
  - Briefly restate value proposition
  - Propose discovery call (30-60 min)

**Output:** Discovery call scheduled (or prospect declines)

---

**2.6 Update Partner on Status**
- **Who:** Wei or designated operations person
- **Action:** Brief email update to partner
- **Timeline:** Within 1 week of introduction
- **Content:**
  - Discovery call scheduled [date/time]
  - OR: Prospect declined (no interest at this time)
  - OR: Prospect hasn't responded yet, will follow up again in X days

**Output:** Partner stays informed

---

**Attribution confirmed for 12 months from date of introduction.**

---

## Process 3: Sales Process (Partner-Sourced Lead)

**Trigger:** Discovery call scheduled with attributed prospect
**Owner:** Wei or Gabriel (primary), Partner (supporting)
**Duration:** 1-4 weeks from discovery to signed contract

### Steps

**3.1 Pre-Discovery Research**
- **Who:** Wei or Gabriel
- **Action:** Research prospect company, industry, potential pain points
- **Review:**
  - Partner's introduction context
  - Company website, LinkedIn, recent news
  - Similar projects we've done
  - Potential entry point (3-Day MVP vs custom)

**Output:** Prepared for discovery call

**Time:** 30-60 minutes

---

**3.2 Discovery Call**
- **Who:** Wei or Gabriel + Prospect + Partner (optional)
- **Duration:** 30-60 minutes
- **Goal:** Understand problem space, current state, desired outcomes
- **Cover:**
  - What's the pain point or opportunity?
  - What have they tried before?
  - What does success look like?
  - Who are the stakeholders?
  - What's the timeline?
  - What's the budget range?
  - Are there any technical constraints?

**Nexrizen's AI-native advantage:**
> "Our internal operations run on the same AI systems we build for clients. We use proprietary tools that ingest every meeting, document, and communication to maintain perfect continuity across projects." — `context/01_eu-partnership-proposal.md` lines 374-377

This means: no details are lost, no need to re-explain context in follow-ups.

**Output:** Clear understanding of project requirements

---

**3.3 Prototype Development (BEFORE Contract)**
- **Who:** Wei, Gabriel, and/or engineering team
- **Action:** Build working prototype of proposed solution
- **Timeline:** 1-3 days (depending on complexity)
- **Deliverable:** Functional application, not slide deck

**Key differentiator:**
> "After a single discovery meeting, we generate a working prototype of the proposed solution — a functional application, not a slide deck — before the prospect pays a cent." — `context/01_eu-partnership-proposal.md` lines 110-112

**Why this matters:**
- Eliminates visualization gap (prospect sees real solution)
- Builds immediate confidence in capabilities
- Accelerates internal decision-making (no debating abstractions)
- Reflects well on partner's recommendation (tangible value from day 1)

**Output:** Working prototype deployed (usually to staging URL)

---

**3.4 Prototype Review Meeting**
- **Who:** Wei or Gabriel + Prospect + Partner (optional)
- **Duration:** 30-45 minutes
- **Action:** Walkthrough prototype, gather feedback
- **Cover:**
  - Demo functionality
  - Explain technical approach
  - Discuss what full version would include
  - Answer questions
  - Gauge interest level

**Output:** Feedback for proposal refinement, clear signal on interest level

---

**3.5 Proposal Preparation**
- **Who:** Wei (with support from AI proposal system)
- **Action:** Create detailed proposal based on discovery + prototype feedback
- **Include:**
  - Problem statement (from discovery)
  - Proposed solution (informed by prototype)
  - Scope of work (features, deliverables)
  - Timeline and milestones
  - Pricing (per `Current_State.md` service tiers)
  - Team composition
  - Terms and conditions

**Output:** Proposal document ready to present

**Time:** 2-4 hours (accelerated by AI systems)

---

**3.6 Proposal Presentation**
- **Who:** Wei or Gabriel + Prospect + Partner (if client requests or relationship warrants)
- **Duration:** 30-45 minutes
- **Action:** Walk through proposal, answer questions, address concerns
- **Close:** Ask for decision timeline or next steps

**Output:** Prospect has clear proposal to evaluate

---

**3.7 Negotiation (if needed)**
- **Who:** Wei + Prospect
- **Common negotiation points:**
  - Price (budget constraints)
  - Scope (add/remove features)
  - Timeline (accelerate or extend)
  - Payment terms (upfront % vs milestone-based)

**Output:** Agreed terms, ready to contract

---

**3.8 Contract Execution**
- **Who:** Wei (signs for Nexrizen), Prospect (signs for their company)
- **Documents:** Master Services Agreement + Statement of Work
- **Method:** DocuSign, Adobe Sign, or wet signature

**Output:** Signed contract, project official

---

**3.9 Notify Partner of Close**
- **Who:** Wei or designated operations person
- **Action:** Email partner with good news
- **Include:**
  - Contract signed
  - Project value
  - Estimated commission (15% of contract value, paid as collected)
  - Expected project start date
  - Thank partner for introduction

**Output:** Partner informed and excited

---

**3.10 Project Kickoff**
- **Who:** Wei or Gabriel + engineering team + Client
- **Action:** Kick off delivery
- **Partner involvement:** Typically none (Nexrizen handles delivery)

**Output:** Project underway

---

**Typical timeline:** 1-4 weeks from discovery to signed contract (faster than traditional agencies due to prototype-first approach)

---

## Process 4: Commission Payment

**Trigger:** Nexrizen receives payment from client
**Owner:** Wei or finance/operations person
**Frequency:** Monthly (statements), 30 days after receipt (payment)

### Steps

**4.1 Client Payment Received**
- **Who:** Nexrizen finance/operations
- **Action:** Record payment in accounting system
- **Note:** Commission is based on **collected revenue** (cash received), not contract value

**Example:**
- Contract value: $30,000
- Payment schedule: $15,000 upfront, $15,000 on completion
- Commission accrues as payments are collected:
  - Payment 1: $15,000 collected → $2,250 commission due
  - Payment 2: $15,000 collected → $2,250 commission due
  - **Total: $4,500 commission** (15% of $30,000)

**Source:** `context/01_eu-partnership-proposal.md` lines 128-136

---

**4.2 Commission Calculation**
- **Who:** Finance/operations person
- **Action:** Calculate 15% of collected revenue
- **Verify:**
  - Confirm client attribution (check original attribution email)
  - Confirm payment received (not just invoiced)
  - Exclude: taxes, refunds, chargebacks, disputed amounts

**Output:** Commission amount calculated

---

**4.3 Monthly Commission Statement**
- **Who:** Finance/operations person
- **Action:** Prepare and send statement to partner
- **Frequency:** Monthly (by 5th of following month)
- **Include:**
  - Referred clients with active engagements
  - Payments received during the period (by client, by project)
  - Commissions earned
  - Commissions paid
  - Outstanding balance (if any)

**Output:** Partner has transparent view of earnings

**Source:** `context/01_eu-partnership-proposal.md` lines 91-94 and `context/04_nexrizen-reseller-agreement.md` §3.5

---

**4.4 Commission Payment**
- **Who:** Finance/operations person
- **Action:** Wire transfer to partner's designated account
- **Timeline:** Within 30 days of Nexrizen receiving client payment (per §3.3 of agreement)
- **Currency:** USD or EUR (partner's election)
- **Exchange rate:** Rate in effect on date of payment (per §3.4 of agreement)

**Output:** Commission paid, partner receives funds

---

**4.5 Payment Confirmation**
- **Who:** Finance/operations person
- **Action:** Send confirmation email to partner
- **Include:**
  - Amount paid
  - Currency
  - Date
  - Associated client/project
  - Reference number for partner's records

**Output:** Partner confirms receipt

---

**4.6 Tax Documentation (Annual)**
- **Who:** Finance/operations + accountant
- **Action:** Issue appropriate tax forms
- **US partner:** 1099-NEC
- **International partner:** May require different documentation (consult accountant)
- **Timeline:** By January 31 following calendar year

**Output:** Partner has documentation for tax filing

---

**Dispute resolution:**
> "Any dispute regarding commission calculation must be raised in writing within sixty (60) days of the relevant commission statement." — `context/04_nexrizen-reseller-agreement.md` §3.6

Partners agree to resolve disputes in good faith.

---

## Process 5: Ongoing Partner Management

**Trigger:** Active partnership agreement in place
**Owner:** Wei or designated partner manager
**Frequency:** Monthly check-ins, quarterly reviews

### Steps

**5.1 Monthly Check-In Call**
- **Who:** Wei (or partner manager) + Partner
- **Duration:** 15-30 minutes
- **Frequency:** Monthly (or as agreed)
- **Agenda:**
  - Review pipeline of introductions
  - Status update on active leads
  - Discuss new opportunities partner has identified
  - Provide updates on Nexrizen (new services, case studies, pricing changes)
  - Address any partner questions or concerns
  - Confirm next steps

**Output:** Aligned on priorities, partner feels supported

---

**5.2 Collateral Updates**
- **Who:** Wei or marketing person
- **Action:** Provide partner with updated materials as created
- **Trigger:** New case studies, updated pricing, new services, industry-specific materials
- **Method:** Email with link to updated files

**Output:** Partner always has current materials

---

**5.3 Quarterly Performance Review**
- **Who:** Wei + Partner
- **Duration:** 45-60 minutes
- **Frequency:** Quarterly
- **Review:**
  - Number of introductions made
  - Conversion rates (intro → discovery → close)
  - Revenue generated
  - Commission paid
  - What's working well?
  - What could be improved?
  - Adjust commission or territory terms if appropriate

**Output:** Alignment on performance, adjustments if needed

---

**5.4 Annual Agreement Renewal**
- **Who:** Wei + Partner
- **Action:** Review and renew agreement (auto-renews unless non-renewal notice given)
- **Timeline:** 30 days before end of term (per §9.2 of agreement)
- **Discuss:**
  - Keep terms the same or negotiate changes?
  - Expand territory?
  - Move to exclusive arrangement?
  - Adjust commission structure?

**Output:** Agreement renewed (or terminated)

---

## Process 6: Partner-Requested Materials or Support

**Trigger:** Partner needs custom collateral, co-branded materials, or specific support
**Owner:** Wei or marketing/operations person
**Duration:** Varies (1 day to 2 weeks depending on request)

### Steps

**6.1 Partner Makes Request**
- **Who:** Partner
- **Method:** Email or during monthly check-in
- **Examples:**
  - "Can we create a co-branded one-pager for this specific prospect?"
  - "Can you join this sales call? Client is technical and has questions."
  - "Do we have a case study in [specific industry]?"

**Output:** Request logged

---

**6.2 Nexrizen Evaluates Feasibility**
- **Who:** Wei or relevant team member
- **Action:** Assess request
- **Consider:**
  - Is this reasonable given partnership terms?
  - How much effort is required?
  - Will this benefit the partnership and increase close probability?
  - What's the timeline?

**Output:** Decision to fulfill, decline, or propose alternative

---

**6.3 Fulfill Request**
- **Who:** Relevant team member (Wei for sales calls, marketing for collateral, etc.)
- **Action:** Create deliverable or provide support
- **Timeline:** As agreed with partner

**Output:** Partner has what they need

---

**6.4 Follow Up**
- **Who:** Wei or operations person
- **Action:** Check if deliverable met partner's needs
- **Learn:** Was this useful? Should we create similar materials proactively for all partners?

**Output:** Continuous improvement of partner enablement

---

## Process 7: Collateral Production (Internal)

**Trigger:** Partnership program launch or material updates needed
**Owner:** Wei (content), Designer/contractor (design)
**Duration:** Varies by deliverable (see timeline below)

### Workflow (from `context/03_eu-collateral-plan.md`)

**7.1 Content Creation**
- **Who:** Wei
- **Action:** Draft content for each deliverable
- **Deliverables:**
  - One-pager (content: 2-3 hours)
  - Case study collection (content: 4-6 hours)
  - Capability sheets (5 verticals, content: 3-5 hours)
  - Presentation deck (content: 4-6 hours)
  - Email templates (content: 2-3 hours)
  - FAQ document (content: 2-3 hours)

**Output:** Draft content ready for design

---

**7.2 Design & Layout**
- **Who:** Designer (freelance or contractor)
- **Action:** Apply professional design to content
- **Budget:** $1,200 - $2,200 total (per `context/03_eu-collateral-plan.md` lines 262-272)
- **Design notes:**
  - Clean, minimal European aesthetic (not loud American marketing)
  - Subtle color palette (navy, white, light accent)
  - No stock photos (use data visualization or clean iconography)
  - GDPR-compliant (no tracking pixels in PDFs)

**Output:** Designed materials ready for review

---

**7.3 Review & Refinement**
- **Who:** Wei + Gabriel
- **Action:** Review materials for accuracy, tone, completeness
- **Revisions:** 1-2 rounds as needed

**Output:** Final materials approved

---

**7.4 Packaging & Distribution**
- **Who:** Operations person
- **Action:** Organize files and share with partner(s)
- **File structure:** Per `context/03_eu-collateral-plan.md` lines 228-260

**Output:** Partner has access to all materials

---

**Timeline (from `context/03_eu-collateral-plan.md` lines 197-226):**

| Timeframe | Deliverables |
|-----------|--------------|
| **Week 1** | One-pager (content draft), Case study collection (content) |
| **Week 2** | One-pager (final), Case study collection (design), Capability sheets (content for 2 verticals) |
| **Week 3** | Remaining capability sheets, Presentation deck (draft), FAQ document |
| **Week 4** | Presentation deck (final), Email templates, Package and send to partner |

**Current status (as of 2026-02-10):** Not yet started (pending partnership agreement finalization)

---

## Key Metrics to Track

**For each process:**

**Lead introduction & attribution:**
- Time from attribution notice to confirmation: Target <1 business day
- % of introductions that result in discovery calls: Track baseline, aim for 50%+

**Sales process:**
- Time from discovery to prototype delivery: Target 1-3 days
- Time from prototype to signed contract: Target 1-2 weeks
- Conversion rate (discovery → close): Track baseline

**Commission payment:**
- Time from payment received to commission paid: Target <30 days (per agreement)
- Accuracy of commission calculations: Target 100% (zero disputes)

**Partner management:**
- Monthly check-in completion rate: Target 100%
- Quarterly review completion rate: Target 100%
- Partner satisfaction (qualitative): Assess quarterly

**Current baseline:** No data yet (pre-pilot phase)

---

## Document Length

**Current length:** ~450 lines
**Status:** Within recommended 200-400 line range for Process_Flows docs

**Last updated:** 2026-02-10
**Next update due:** After first partnership closes OR when processes are revised, whichever comes first
