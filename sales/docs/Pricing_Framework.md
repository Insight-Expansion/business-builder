---
**Document:** Pricing_Framework.md
**Version:** 1.0
**Last Updated:** 2026-02-10
**Owner:** Sales/Finance
**Update Frequency:** Quarterly or when cost structure changes

**Synthesized From:**
- `../meetings/sales-intros/*` (coverage: ~70%)
- `../business-core/Nexrizen_Business_Overview.md` (coverage: ~90%)

**What Changed:**
- v1.0 (2026-02-10): Initial extraction from sales conversations
- v1.1 (2026-02-10): Added 3-Day AI service pricing validation, price anchoring model, managed service packages

**Downstream Dependencies:**
- `Sales_Process_Framework.md` - Uses these rates in proposals
- `Unit_Economics.md` - Margin calculations
- `Should_We_Take_This_Project.md` - Decision framework

**Completeness:** ⚠️ In Progress - Needs margin validation
---

# Nexrizen Pricing Framework

**Purpose:** Document pricing strategy, rates, and decision frameworks for consistent, profitable quoting.

---

## Core Pricing Philosophy

> "First-world expertise at third-world rates because AI makes us 3-4x faster"

**Value-Based, Not Cost-Plus:**
- Price based on client value delivered, not just hours
- Faster delivery = more value per dollar
- Senior expertise commands premium

---

## Standard Hourly Rates

### For Client Work

| Role | Rate | When to Use |
|------|------|-------------|
| **CEO (Wei)** | $200/hr | Fractional CTO, Strategic consulting |
| **CTO (Gabe)** | $200/hr | Fractional CTO, Architecture design |
| **Senior Engineers** | $120/hr | Implementation, development work |
| **PhD Data Scientists** | $150/hr | ML/AI specialized work |
| **Project Rate (blended)** | $120-150/hr | Standard project quote |

**Market Comparison:**
- Offshore teams: $30-50/hr (junior, slower)
- US freelancers: $100-150/hr (mixed quality)
- US agencies: $200-400/hr (high overhead)
- **Nexrizen positioning:** Senior talent at mid-market rates

**From Wei's Sales Conversations:**
> "We're ex-Meta, ex-IBM, PhDs—you'd expect us to charge $300-500/hour. We charge $120-200 because AI makes us faster."

---

## Project Pricing Tiers (Menu-Based)

### Tier 1: Proof of Concept ($0 - FREE)
- **Purpose:** Build trust, prove capability
- **Deliverable:** 40-60% of full solution, working demo
- **Timeline:** 3-7 days
- **Investment:** 4-16 engineering hours
- **ROI:** ~50% conversion to paid project

### Tier 2: 3-Day AI Service ($3K / $6K / $10K)
**VALIDATED SERVICE - 10-12 clients Month 1**

**Price Anchoring Model:**
- **$3,000** - Entry/Basic
- **$6,000** - Standard ← **Most clients choose this (middle anchor)**
- **$10,000** - Premium

**Why Price Anchoring Works:**
- Middle option = sweet spot (most conversions)
- High option makes middle look reasonable
- Low option qualifies serious buyers (weeds out tire-kickers)

**Examples:**
- Simple chatbot (3-5 intents)
- Basic dashboard (single data source)
- Small automation workflow
- Voice agent (starter package)
- Rapid MVP/prototype

**Timeline:** 3-12 weeks (despite "3-day" branding)
**Typical Hours:** 20-50 hours (AI speeds up development)
**Target Clients:** Greenfield projects, SMBs without tech teams, startups

**Upsell Strategy:**
- Complete project
- Suggest additional features during delivery
- Offer managed service subscription (see below)

**Performance (Nov 2025):**
- 10-12 projects completed Month 1
- 10-12 in waitlist
- $60-72K revenue (Month 1)
- 90% Upwork response rate
- 75-80% conversion to contract

### Tier 3: Mid-Range ($5-15K)
**Examples:**
- Multi-agent orchestration system
- Advanced dashboard with multiple integrations
- Video analysis system (post-hoc)
- Complete automation workflow

**Timeline:** 3-6 weeks
**Typical Hours:** 40-100 hours
**Target Clients:** SMBs, established companies with clear ROI

**From Meetings:**
- Essay service automation: Quoted "2-3 weeks"
- Restoration video AI: "$3-6K for Phase 1"
- General custom projects: "$4-6K" range mentioned

### Tier 4: Premium ($15-30K+)
**Examples:**
- Enterprise-grade multi-agent systems
- Real-time AI coaching (complex)
- Complete business automation suite
- Large-scale integrations

**Timeline:** 6-12 weeks
**Typical Hours:** 100-250+ hours
**Target Clients:** Established businesses, strategic partners

### Tier 5: Fractional CTO ($5-20K/month)
**Models:**
- Hourly: $200/hr (10-20 hrs/week)
- Monthly Retainer: $8-15K/month
- Equity + Reduced Cash: Negotiable

**From Israel Meeting:**
> Wei: "$10K a month for 10 hours of my time + 5-10 hours of engineer time"

---

## Pricing by Vertical

### Legal Tech (Immigration Focus)
**Premium Pricing:** +20% over standard
**Why:** Deep expertise, compliance requirements, higher ROI
**Typical Range:** $10-25K projects
**Example:** Lead qualification system (1,000/day) - likely $15-20K

### Construction/Real Estate
**Standard Pricing:** Base rates
**Typical Range:** $5-15K projects
**Example:** Restoration video AI - $3-6K (Phase 1)

### Professional Services
**Standard to Premium:** Depends on complexity
**Typical Range:** $5-20K projects
**Example:** Essay service automation - likely $8-12K

### Fintech/Insurance
**Premium Pricing:** +30% over standard
**Why:** Regulatory requirements, higher stakes
**Typical Range:** $15-30K+ projects
**Example:** Live sales coaching system - likely $15-20K

---

## Pricing Modifiers

### Speed Premium (+20-30%)
**When:** Client needs faster delivery than standard
**Requires:** Pulling engineers from other projects
**Trade-off:** Higher cost OR reduced scope

### Complexity Premium (+20-50%)
**When:**
- Real-time systems (vs batch processing)
- Multi-channel integrations
- Regulatory compliance requirements
- Novel/research-heavy work

### Maintenance Discount Package
**Offer:** $300-600/month maintenance (20-40 hours annual support)
**Discount:** 10% off project if they commit to 12-month maintenance
**Goal:** Build recurring revenue base

### Partnership/Equity Arrangements
**Model:** Reduced cash + equity stake
**Typical:** 50% cash + 5-15% equity
**Used When:** Strategic opportunity, strong founding team

**From Zane Meeting:**
> Zane offering equity + partnership structure for AI venture
> Wei: "Dating phase" first, then discuss equity

---

## Pricing by Complexity (Internal Estimation)

### Simple (Tier 2: $2-5K)
- **Characteristics:**
  - Single-purpose tool
  - One integration
  - Standard UI/UX
  - Minimal custom logic
- **Hours:** 15-35
- **Examples:** Basic chatbot, simple dashboard, single automation

### Moderate (Tier 3: $5-15K)
- **Characteristics:**
  - Multi-component system
  - 2-3 integrations
  - Custom business logic
  - Moderate AI complexity
- **Hours:** 40-100
- **Examples:** Multi-agent orchestration, video analysis, advanced automation

### Complex (Tier 4: $15-30K+)
- **Characteristics:**
  - Enterprise-grade system
  - Real-time processing
  - Multiple integrations
  - Novel AI/ML work
  - Compliance requirements
- **Hours:** 100-250+
- **Examples:** Live coaching systems, enterprise platforms, complex AI

---

## Phased Pricing Strategy

**Problem:** Clients with budget constraints
**Solution:** Break into phases

### Example: Restoration Video AI

**Phase 1:** Post-hoc video analysis ($3-6K, 3-4 weeks)
- Upload video → get analysis
- No real-time guidance yet

**Phase 2:** Real-time guidance system (+$5-8K, 4-6 weeks)
- Live feedback during walkthrough
- More complex, higher value

**Total:** $8-14K vs $12-18K if quoted upfront
**Benefit:** Lower initial commitment, prove value before Phase 2

**From Sean Meeting:**
> Wei: "Phase 1 is $3-6K. Live guidance would ~2x the price."

---

## Discounting Policy

### When to Discount
✅ **Scope reduction** (less work = less cost)
✅ **Annual maintenance commitment** (recurring revenue)
✅ **Strategic case study** (valuable for portfolio)
✅ **Multiple projects bundled** (economy of scale)
✅ **Referral source** (reward network effects)

### When NOT to Discount
❌ **"Just because"** (devalues work)
❌ **First ask** (train them to negotiate)
❌ **Bad fit clients** (money isn't worth headache)
❌ **Unrealistic expectations** (will be unhappy regardless)

### Maximum Discount: 20%
- Protects team morale
- Maintains value perception
- Ensures profitability

**From Wei's Philosophy:**
> "We've turned down wealthy clients because they were jerks. Money isn't everything."

---

## Proposal Pricing Structure

### Format:
```markdown
## Investment

**Total Project Cost:** $12,000
**Payment Terms:** 50% upfront ($6K), 50% on completion ($6K)

### Breakdown:
- Discovery & Architecture: $2,000 (included)
- Development (80 hours @ $120/hr): $9,600
- Testing & Deployment: $1,200 (included)
- Training & Handoff: $1,200 (included)

**Timeline:** 4-6 weeks from contract signing
**Maintenance:** Optional $400/month (20 hours annual support)
```

### Alternative: Range Pricing
```markdown
## Investment Range

**Estimated Cost:** $8,000 - $12,000

Final cost depends on:
- Final scope after requirements phase
- Integration complexity
- Testing requirements

We'll provide exact quote after 2-week discovery phase.
```

**Range Pricing Benefits:**
- Flexibility during requirements gathering
- Protects against scope creep
- Sets expectations for variability

---

## Hourly vs Fixed Price

### Fixed Price (Preferred)
**Pros:**
- Client knows exact cost
- We absorb efficiency gains
- Incentivizes fast delivery

**Cons:**
- Risk of scope creep
- Need clear requirements
- May underestimate

**When to Use:** Clear, well-defined projects (most cases)

### Hourly (Select Cases)
**Pros:**
- Flexible for evolving requirements
- No risk of underestimating
- Works for "dating phase" partnerships

**Cons:**
- Client worried about cost overruns
- Incentive misalignment (slower = more money)

**When to Use:**
- Fractional CTO work
- Partnership evaluation periods
- Unclear/evolving scope
- Ongoing maintenance

**From Israel Meeting:**
> Wei: "We bill hourly... $120 an hour. I can submit a bill every two weeks."

---

## "Dating Phase" Pricing

**For Strategic Partnerships:**

### Structure:
- **Phase 1 (4-8 weeks):** Hourly at standard rates
- **Deliverables:** Prove capability, build relationship
- **Review:** Assess fit, value delivered, partnership potential
- **Phase 2:** Convert to equity, retainer, or rev share

### Example:
- 10 hours/week Wei ($200/hr) = $2K/week
- 5 hours/week Engineer ($120/hr) = $600/week
- **Total:** ~$10K/month
- **Outcome:** Partnership negotiation or continue hourly

**From Israel & Zane Meetings:**
> "Let's work together hourly, see if we're compatible, then talk equity"
- De-risks for both sides
- Generates cash during evaluation
- Builds trust before major commitment

---

## Managed Service Packages (Recurring Revenue)

**NEW MODEL - Launched with 3-Day AI Service (Nov 2025)**

### Standard Managed Service ($500-1,000/month)
**What's Included:**
- **Hosting costs covered** (AWS/GCP infrastructure)
- **On-call support** for bugs/issues
- **Priority feature development** - not in back of waitlist
- **Continuous improvements** as AI/tech evolves
- **Monitoring & maintenance** (uptime, performance)

**Value Proposition:**
> "Your system stays current with AI advancements without additional project fees"

**Why Clients Buy:**
- Don't want to manage hosting themselves
- Need ongoing support (not one-and-done)
- Want priority access when they need features
- Fear being left behind as tech evolves

**Pricing Factors:**
- $500/month - Simple systems, low usage
- $750/month - Standard complexity, moderate usage
- $1,000/month - Complex systems, high usage, priority SLA

### Legacy Maintenance Packages (Pre-3-Day Service)

**Tier 1: Basic ($300/month)**
- 10 hours annual support
- Bug fixes only
- Email support (48hr response)

**Tier 2: Standard ($400/month)**
- 20 hours annual support
- Bug fixes + minor feature updates
- Priority email support (24hr response)

**Tier 3: Premium ($600/month)**
- 40 hours annual support
- Bug fixes + feature development
- Slack support + quarterly strategy calls

---

**Target:** Every 3-Day AI project gets managed service upsell
**Current Status:** Just launched with service, building first cohort
**Attachment Rate Goal:** 50% of clients add managed service

---

## Upsell Strategies

### During Proposal
> "We recommend adding [feature] in Phase 2 once core system is proven"

### At Project Completion
> "Great! System is live. We offer maintenance packages to keep it running smoothly and add features over time. Most clients start with our $400/month standard package."

### Expansion Opportunities
- Additional features
- Scale to more users/volume
- Add integrations
- Training for their team
- White-label for resale

---

## Pricing Decision Framework

### Should We Quote This Project?

**YES if:**
- ✅ Budget range is $3K+ (worth our time)
- ✅ Clear problem statement (can deliver value)
- ✅ Client is reasonable (good communication, realistic expectations)
- ✅ Within our capability (can deliver with confidence)
- ✅ Profit margin >30% after costs

**MAYBE if:**
- ⚠️ Scope is unclear (requires discovery phase first)
- ⚠️ Budget is tight (can we phase it?)
- ⚠️ New technology for us (R&D required)

**NO if:**
- ❌ Budget <$2K (not profitable)
- ❌ Unrealistic timeline ("need it tomorrow")
- ❌ Bad fit personality ("asshole" filter)
- ❌ Outside core competency (will fail to deliver)
- ❌ Legal/ethical concerns

---

## Competitive Pricing Analysis

### Nexrizen vs Market

| Provider Type | Rate | Quality | Speed | Access |
|---------------|------|---------|-------|--------|
| **Nexrizen** | $120-200/hr | ⭐⭐⭐⭐⭐ | 3-12 weeks | Direct founders |
| **Offshore Teams** | $30-50/hr | ⭐⭐ | 3-6 months | Layers of PMs |
| **US Freelancers** | $100-150/hr | ⭐⭐⭐ | 2-4 months | Direct, varies |
| **US Agencies** | $200-400/hr | ⭐⭐⭐⭐ | 3-6 months | Account managers |
| **Big Consultancies** | $300-500/hr | ⭐⭐⭐⭐ | 6-12 months | Partners + teams |

**Nexrizen Sweet Spot:** Senior quality at mid-market rates with boutique speed

---

## Internal Cost Structure (For Margin Calculation)

### Fully-Loaded Cost per Hour
- Engineers: ~$40-60/hr (salary + benefits + overhead)
- PhDs: ~$60-80/hr
- Wei/Gabe: Opportunity cost varies

### Target Margins
- **Minimum:** 30% (covers overhead + profit)
- **Target:** 40-50% (healthy growth)
- **Premium:** 50-60% (strategic work)

### Current Reality
- Margins are thin due to internal R&D investment
- Proposal Builder, Business Builder = future sellable assets
- Short-term pain for long-term gain

---

## Pricing Communication Scripts

### Introducing Price (After POC Demo)
> "Based on what we've discussed and the POC you've seen, a project like this typically runs $8-12K. I'll send you a detailed proposal with exact pricing, timeline, and deliverables."

### Handling "That's expensive"
> "Let me break it down: We're looking at about 60 hours of senior engineer time at $120/hour. That's $7,200 in labor. Compare that to agencies charging $300/hour, or offshore teams taking 6 months. We're actually the most cost-effective option for this quality and speed."

### Offering Payment Plans
> "We typically do 50% upfront, 50% on completion. But if that's challenging, we can break it into milestones: 33% at signing, 33% at midpoint, 34% at completion."

---

## Pricing Experimentation

### A/B Tests to Run
1. **Range vs Exact:** Does range pricing ($8-12K) or exact ($10K) close better?
2. **Hourly breakdown:** Show hours × rate or just total?
3. **Maintenance bundled:** Include in project cost vs separate upsell?
4. **Payment terms:** 50/50 vs milestone-based?

### Track These Metrics
- Win rate by pricing tier
- Average deal size by vertical
- Discount frequency and impact on close rate
- Maintenance attachment rate

---

## Future Pricing Evolution

### Phase 1 (Current): Custom Projects
- Hourly/fixed price
- Manual quoting
- High touch sales

### Phase 2 (6-12 months): Productized Services
- Fixed pricing for "Voice AI Bot" ($5K standard package)
- Fixed pricing for "Dashboard" ($8K standard package)
- Self-service sizing calculator

### Phase 3 (12-24 months): Platform/SaaS
- Proposal Builder as product ($500-1000/month)
- Business Builder as product ($1000-2000/month)
- White-label offerings for agencies

---

*Last updated: 2026-02-10*
*Source: Sales conversations + business overview*
*Status: Draft - needs margin validation and ongoing testing*
