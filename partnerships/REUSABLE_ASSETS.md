---
**Document:** REUSABLE_ASSETS.md
**Version:** 1.1
**Last Updated:** 2026-02-12
**Owner:** Wei Zhuo
**Purpose:** Catalog of reusable partnership assets and where they're stored

**Update Frequency:** As-needed (when new assets are created)

**What Changed:**
- v1.0 (2026-02-10): Initial catalog of partnership assets
- v1.1 (2026-02-12): Updated directory structure to reflect business-core/ org-wide assets; noted Brand_Guidelines moved to business-core/brand/; updated EU one-pager status to v2.0 complete
---

# Partnerships Department - Reusable Assets

## Directory Structure

**Note:** As of Feb 2026, org-wide assets moved to `business-core/` for reuse across all departments.

```
business-core/                 # ORG-WIDE ASSETS (used by all departments)
├── collateral/               # Reusable sales materials
│   └── Executive_Overview.md # Market-neutral base template for all one-pagers
├── brand/                    # Brand identity
│   └── Brand_Guidelines.md   # Colors, typography, logo, design aesthetic
└── case-studies/             # 33 case studies across 10 verticals

partnerships/
├── templates/                # Reusable document templates
│   ├── partner/             # Partner management
│   ├── leads/               # Lead tracking
│   └── meetings/            # Meeting notes
├── assets/                  # PARTNERSHIP-SPECIFIC collateral
│   ├── one-pagers/         # Regional variants (EU, US, APAC) derived from business-core base
│   ├── capability-sheets/  # Industry-specific capabilities
│   ├── email-templates/    # Introduction emails
│   └── presentations/      # Slide decks
├── frameworks/              # Decision support tools
│   ├── partner-qualification.md
│   ├── lead-qualification.md
│   └── vertical-fit-matrix.md
└── docs/SOPs/               # Standard operating procedures
    ├── Partner_Onboarding_SOP.md
    ├── Lead_Attribution_SOP.md
    ├── Commission_Payment_SOP.md
    └── Monthly_Check_In_SOP.md
```

**Key principle:** Generic collateral lives in `business-core/` (single source of truth). Market-specific variants live in partnerships or other departments.

---

## 1. Templates (Internal Use)

**Location:** `templates/`

### Partner Management Templates

**File:** `templates/partner/PARTNER_template.md`
**Purpose:** Template for creating new partner profiles
**Use when:** Onboarding a new partner
**Contains:**
- Partner background section
- Agreement details
- Territory assignment
- Lead generation capacity
- Target verticals
- Communication cadence
- Status tracking

**File:** `templates/partner/partner_performance_report_template.md`
**Purpose:** Monthly/quarterly partner performance reports
**Use when:** Reviewing partner metrics
**Contains:**
- Activity metrics (leads, intros, calls)
- Conversion metrics (intro→close rates)
- Revenue metrics (deals, commission paid)
- Relationship health (qualitative)

**File:** `templates/partner/commission_statement_template.md`
**Purpose:** Monthly commission statements sent to partners
**Use when:** Paying commissions
**Contains:**
- Reporting period
- Client/project breakdown
- Payments received
- Commission calculation (15%)
- Total commission due
- Payment details

### Lead Tracking Templates

**File:** `templates/leads/lead_template.md` (v2.0 - Table-based)
**Purpose:** Scalable lead tracking using hybrid table + detail approach
**Use when:** Partner introduces new prospects (supports 100+ leads easily)
**Format:**
- **All leads:** Single row in pipeline table (quick add, scannable overview)
- **High-priority leads (>$50K or strategic):** Expandable detail sections

**Contains:**
- Table row template with field guide (ID, Company, Industry, Contact, Relationship, Status, Est. Value, Next Action)
- Detail section template (for high-value/complex leads only)
- Workflow guides (adding leads, updating status)
- When to create detailed section vs. keep in table only
- Scaling recommendations (Notion/Airtable at 100+ leads)

**Benefits:** Scales to 100+ leads without file clutter, searchable in one file, low overhead to add/update

**File:** `templates/leads/lead_qualification_checklist.md` (Optional - not yet created)
**Purpose:** Quick checklist to assess lead quality
**Use when:** Partner shares a new lead
**Contains:**
- ICP fit criteria
- Budget authority
- Pain point clarity
- Relationship warmth
- Timeline urgency
- Decision-maker access

### Meeting Templates

**File:** `templates/meetings/partner_kickoff_template.md`
**Purpose:** Agenda and notes structure for first partner meeting
**Use when:** Onboarding new partner
**Contains:**
- Pre-meeting prep
- Agenda outline
- Key discussion points
- Action items section
- Follow-up template

**File:** `templates/meetings/partner_check_in_template.md`
**Purpose:** Recurring partner check-in meeting notes
**Use when:** Monthly/bi-weekly partner calls
**Contains:**
- Pipeline review
- Lead status updates
- Blockers/questions
- Next steps
- Scheduled next meeting

**File:** `templates/meetings/quarterly_review_template.md`
**Purpose:** Quarterly business review with partner
**Use when:** Every quarter
**Contains:**
- Performance metrics
- Wins and learnings
- Challenges and adjustments
- Next quarter goals
- Contract renewal discussion

---

## 2. Assets (Partner-Facing Collateral)

**Location:** `assets/`

### One-Pagers

**Base Template:** `business-core/collateral/Executive_Overview.md`
**Purpose:** Market-neutral executive overview (source of truth)
**Location:** business-core (org-wide, not partnership-specific)
**Contains:** Complete service catalog, 3 key differentiators, proven results, founder bios, tech stack
**Use:** Starting point for all regional/market-specific one-pagers

**File:** `partners/robertas-vp/assets/one-pagers/EU-Executive-Overview-CONTENT.md` (v2.0) ✅
**Purpose:** EU market one-pager content (ready for design)
**Audience:** C-suite executives in EU/EEA
**Format:** A4 PDF (design in progress)
**Language:** English (future: FR, DE, ES)
**Status:** Content complete Feb 11, 2026 - includes 6 AI systems, GitHub repos, "No Advance Payment" differentiator, banking-standard positioning
**Contains:**
- Tagline and value proposition
- "No Advance Payment" positioning (vs €25-50K EU competitors)
- Complete 6-system AI-native technology stack with GitHub credibility
- Banking-standard quality positioning for Big Four backgrounds
- Team credentials (ex-Meta, ex-IBM, Georgia Tech, meditation practice, successful exits)
- Key proof points (100x speed, 1,300 hours saved, etc.)
- Service tiers (3-Day MVP, Custom, Fractional CTO)
- Contact info + QR code
**Derived from:** business-core/collateral/Executive_Overview.md + EU-specific positioning

**File:** `assets/one-pagers/Nexrizen_US_Overview.pdf` (future)
**Purpose:** US market one-pager
**Differences:** US letter size, dollar pricing, US case studies emphasized, different competitive landscape
**Status:** Not yet created - will derive from business-core base template when needed

**File:** `assets/one-pagers/Nexrizen_3Day_MVP_Overview.pdf` (future)
**Purpose:** Focused on 3-Day MVP product (threedays.ai)
**Use when:** Partner wants low-risk entry point messaging

### Capability Sheets (by Vertical)

**Location:** `assets/capability-sheets/`

**Files:**
- `Financial_Services_FinTech.pdf` (Big-Data Renovation, Client Analytics, Chatbot)
- `Healthcare_Life_Sciences.pdf` (Johns Hopkins, Genomic Processing, Voice AI)
- `Professional_Services_Legal.pdf` (AI Meeting Summaries, Intake, Timeline Generator)
- `Aviation_Travel.pdf` (Operations dashboards, customer service AI, booking optimization)
- `Insurance.pdf` (Document processing, claims automation, compliance)
- `E_Commerce_Tech.pdf` (Customer service AI, seller management, analytics)
- `Private_Equity_Investment.pdf` (Portfolio analytics, due diligence, fractional CTO)

**Format:** 1-page PDF per vertical
**Contains:**
- Industry-specific pain points
- Relevant use cases
- 3-4 case studies for this vertical
- Key metrics/proof points
- Typical entry point and pricing
- CTA (discovery call)

### Case Studies

**File:** `assets/case-studies/Nexrizen_Case_Study_Collection.pdf`
**Purpose:** 8-12 page booklet with curated case studies
**Format:** Professional PDF layout
**Contains:**
- 7-10 selected case studies across verticals
- Consistent structure: Client context, Challenge, Solution, Results, Technologies
- Metrics highlighted visually
- 1-2 pages per case study

**Individual case study PDFs** (optional):
- `Big_Data_Fintech_Case_Study.pdf`
- `AI_Meeting_Summaries_Legal_Case_Study.pdf`
- `Johns_Hopkins_Vision_AI_Case_Study.pdf`
- etc.

### Email Templates

**Location:** `assets/email-templates/`

**File:** `Introduction_Email_Templates_by_Vertical.md`
**Purpose:** Partner-specific email templates for warm introductions
**Format:** Markdown with fill-in-the-blank sections
**Contains:**
- Healthcare intro template
- FinTech/Banking intro template
- Aviation intro template
- E-commerce intro template
- Private equity intro template
- Professional services intro template

**Structure per template:**
- Subject line
- Personal greeting (relationship-based)
- 2-3 sentences on Nexrizen (vertical-tailored)
- Specific relevance to prospect
- Soft CTA
- Warm sign-off

**File:** `Follow_Up_Email_Templates.md`
**Purpose:** Follow-up if no response
**Variants:**
- 7-day follow-up (gentle reminder)
- 14-day follow-up (offer alternative)
- Post-meeting thank you

### Presentations

**File:** `assets/presentations/Nexrizen_Partnership_Overview.pptx`
**Purpose:** Slide deck for partner-facing presentations
**Slides (10-15):**
1. Title slide
2. The problem we solve
3. Who we are (founders, team)
4. What we build (three pillars: 3-Day MVP, Custom, Fractional CTO)
5. How we work (prototype-first process)
6. Case study highlight #1 (high-impact)
7. Case study highlight #2 (relevant to audience)
8. Results metrics (visual)
9. Industries we serve
10. Why clients choose us (testimonials)
11. Pricing overview (ranges)
12. Next steps / Contact

**File:** `assets/presentations/Nexrizen_Partner_Onboarding_Deck.pptx`
**Purpose:** Internal deck for onboarding new partners
**Slides:**
- Partnership model overview
- Commission structure with examples
- How attribution works
- Sales process walkthrough
- Collateral available
- How to introduce leads
- Best practices
- Success stories from other partners

### Brand Assets

**Location:** `business-core/brand/` ← **ORG-WIDE** (moved from partnerships Feb 2026)

**Files:**
- `Brand_Guidelines.md` ✅ (colors, typography, logo, design aesthetic)
  - Primary colors: `#502cff` (purple/blue), `#fbffff` (theme background)
  - Typography: Inter font
  - Logo locations on website
  - Design aesthetic (minimal, clean, European-friendly)
  - Recommended color palettes for collateral
- `Nexrizen_Logo_Color.png` (standard logo) - Available at nexrizen.com/images/logo.png
- `Nexrizen_Logo_White.png` (for dark backgrounds) - To be created
- `Partner_Co_Branding_Guidelines.pdf` (future - how to use Nexrizen branding with partner materials)

**Note:** Brand guidelines moved to business-core/ as they're used across all departments (sales, partnerships, marketing), not just partnerships. Single source of truth for visual identity.

---

## 3. Frameworks (Decision Support)

**Location:** `frameworks/`

### Partner Qualification Framework

**File:** `frameworks/Partner_Qualification_Rubric.md`
**Purpose:** Assess whether to enter partnership with someone
**Use when:** New partner inquiry or referral

**Criteria:**
- **Network quality:** Do they have access to decision-makers in target industries?
- **Geographic fit:** Do they cover our target territories?
- **Relationship strength:** Warm intros or cold outreach?
- **Volume potential:** How many leads can they generate?
- **Values alignment:** Professional, ethical, quality-focused?
- **Capacity:** Do they have time/resources to execute?
- **Motivation:** Why do they want to partner? (Money, value-add to network, learning)

**Scoring:**
- 5-7 ✅ criteria met: Strong partner, proceed
- 3-4 ⚠️ criteria met: Conditional, test with pilot
- 0-2 ❌ criteria met: Pass

### Lead Qualification Framework

**File:** `frameworks/Lead_Qualification_Matrix.md`
**Purpose:** Assess whether a partner-introduced lead is worth pursuing
**Use when:** Partner shares new lead

**Criteria:**
- **ICP fit:** Does company match our ideal client profile?
- **Budget authority:** Does contact have budget or access to decision-maker?
- **Pain point:** Is there a clear, urgent problem we can solve?
- **Relationship warmth:** How strong is partner's relationship?
- **Timeline:** Do they need solution soon, or just exploring?
- **Company stage:** Are they funded/stable enough to pay?

**Scoring:**
- All ✅: Priority lead, respond within 24 hours
- 1-2 ⚠️: Qualified but lower priority
- Any ❌ on budget/authority: Politely decline or ask partner to route to right person

### Vertical Fit Matrix

**File:** `frameworks/Vertical_Fit_Matrix.md`
**Purpose:** Map which industries are best fit for Nexrizen capabilities
**Use when:** Partner asks "What industries should I focus on?"

**Matrix:**

| Vertical | Fit Score | Best Entry Point | Typical Use Cases | Relevant Case Studies |
|----------|-----------|------------------|-------------------|----------------------|
| FinTech/Banking | ⭐⭐⭐⭐⭐ | 3-Day MVP or Custom | Analytics, compliance, chatbots | Big-Data, Client Analytics |
| Healthcare | ⭐⭐⭐⭐ | Custom | AI diagnostics, workflow automation | Johns Hopkins, Genomic |
| Legal/Professional Services | ⭐⭐⭐⭐⭐ | 3-Day MVP | Meeting summaries, intake, automation | AI Meeting, Intake, Timeline |
| E-commerce/Tech | ⭐⭐⭐⭐ | 3-Day MVP | Customer service, analytics, seller mgmt | AI Outreach, Intake |
| Aviation/Travel | ⭐⭐⭐⭐ | Custom | Booking, ops dashboards, CRM | Listen Network |
| Insurance | ⭐⭐⭐⭐ | Custom | Document processing, claims automation | (Build case study) |
| Private Equity | ⭐⭐⭐⭐ | 3-Day MVP + Referrals | Portfolio analytics, fractional CTO | CITYROW |

**Use:** Share with partners to help them prioritize where to focus networking efforts.

---

## 4. Standard Operating Procedures (SOPs)

**Location:** `docs/SOPs/`

### Partner_Onboarding_SOP.md

**Purpose:** Step-by-step process for onboarding new partners
**Owner:** Wei Zhuo
**Update frequency:** Quarterly

**Sections:**
1. Initial qualification (use framework)
2. Partnership proposal preparation
3. Kickoff meeting agenda
4. Agreement customization and execution
5. Partner enablement (collateral delivery)
6. First check-in scheduling
7. Success criteria and timelines

**References:** `Process_Flows.md` section on Partner Onboarding

### Lead_Attribution_SOP.md

**Purpose:** How to track and confirm lead attribution
**Owner:** Wei Zhuo / Operations
**Update frequency:** As-needed

**Sections:**
1. Partner sends attribution notice (before or within 48 hours)
2. Nexrizen checks CRM for existing relationship
3. Confirmation or decline sent within 5 business days
4. Lead tagged in CRM with partner attribution
5. 12-month attribution window tracking
6. Dispute resolution process

**References:** `Process_Flows.md` section on Lead Introduction & Attribution

### Commission_Payment_SOP.md

**Purpose:** How to calculate and pay partner commissions
**Owner:** Finance / Operations
**Update frequency:** As-needed

**Sections:**
1. Client payment received and recorded
2. Commission calculation (15% of collected revenue)
3. Monthly commission statement generation (by 5th of month)
4. Payment execution (within 30 days of collection)
5. Payment confirmation to partner
6. Annual tax documentation (1099, etc.)

**References:** `Process_Flows.md` section on Commission Payment

### Monthly_Check_In_SOP.md

**Purpose:** Standard agenda and process for partner check-ins
**Owner:** Wei Zhuo / Partner Manager
**Update frequency:** As-needed

**Sections:**
1. Pre-meeting prep (review lead pipeline, check partner metrics)
2. Meeting agenda:
   - Pipeline review
   - Lead status updates
   - New opportunities identified
   - Nexrizen updates (services, case studies, pricing)
   - Partner questions/concerns
3. Post-meeting follow-up (send notes, action items)
4. Schedule next check-in

**References:** `Process_Flows.md` section on Ongoing Partner Management

---

## 5. Creation Priority

### Phase 1: Immediate (Needed for Robertas - Week of 2026-02-10)

**Critical for first partner:**
- [ ] `assets/one-pagers/Nexrizen_EU_Executive_Overview.pdf`
- [ ] `assets/capability-sheets/Healthcare.pdf` (Affidea)
- [ ] `assets/capability-sheets/Insurance_HR.pdf` (Allianz)
- [ ] `assets/capability-sheets/Aviation.pdf` (VistaJet)
- [ ] `assets/capability-sheets/E_Commerce.pdf` (Vintage Cash Cow)
- [ ] `assets/capability-sheets/Private_Equity.pdf` (Aalto Capital)
- [ ] `assets/email-templates/Introduction_Email_Templates_by_Vertical.md`
- [ ] `assets/brand/Nexrizen_Logo_Color.png`
- [ ] `assets/brand/Nexrizen_Logo_White.png`

**Budget:** $1,200-$2,200 for design work

### Phase 2: Near-Term (After Robertas partnership is active - Weeks 3-4)

**Operationalize processes:**
- [ ] `docs/SOPs/Partner_Onboarding_SOP.md`
- [ ] `docs/SOPs/Lead_Attribution_SOP.md`
- [ ] `docs/SOPs/Commission_Payment_SOP.md`
- [ ] `frameworks/Partner_Qualification_Rubric.md`
- [ ] `frameworks/Lead_Qualification_Matrix.md`
- [ ] `templates/partner/commission_statement_template.md`
- [ ] `templates/leads/lead_template.md`

### Phase 3: As-Needed (When scaling to multiple partners)

**Scale with reusable templates:**
- [ ] `assets/presentations/Nexrizen_Partnership_Overview.pptx`
- [ ] `assets/presentations/Nexrizen_Partner_Onboarding_Deck.pptx`
- [ ] `assets/case-studies/Nexrizen_Case_Study_Collection.pdf`
- [ ] `templates/partner/PARTNER_template.md`
- [ ] `templates/partner/partner_performance_report_template.md`
- [ ] `templates/meetings/partner_kickoff_template.md`
- [ ] `templates/meetings/partner_check_in_template.md`
- [ ] `templates/meetings/quarterly_review_template.md`
- [ ] `frameworks/Vertical_Fit_Matrix.md`
- [ ] `docs/SOPs/Monthly_Check_In_SOP.md`
- [ ] `assets/brand/Brand_Guidelines.pdf`
- [ ] `assets/brand/Partner_Co_Branding_Guidelines.pdf`

---

## 6. Asset Maintenance

### Ownership

| Asset Type | Owner | Update Trigger |
|------------|-------|----------------|
| **One-pagers** | Wei / Marketing | New services, pricing changes, major case studies |
| **Capability sheets** | Wei / Marketing | New vertical case studies, service changes |
| **Case studies** | Wei | New successful projects |
| **Email templates** | Wei / Partners | Partner feedback, conversion rate analysis |
| **Presentations** | Wei / Marketing | Quarterly refresh |
| **Brand assets** | Marketing | Rebrand or design updates |
| **Templates** | Operations | Process improvements |
| **Frameworks** | Wei | Quarterly review based on learnings |
| **SOPs** | Process owner | When process changes |

### Version Control

**All partner-facing assets (PDFs, presentations) should include:**
- Version number (v1.0, v1.1, etc.)
- Date created/updated
- Footer: "For partnership use only - Do not distribute"

**Update process:**
1. Identify need for update (new case study, pricing change, partner feedback)
2. Draft updated version
3. Review with relevant stakeholders
4. Increment version number
5. Send updated assets to all active partners
6. Archive old version (keep for reference)

### Asset Tracking

**Create:** `assets/ASSET_VERSION_LOG.md`

Track what assets exist, current version, last update, next planned update.

**Example:**

| Asset | Current Version | Last Updated | Next Update Due | Status |
|-------|----------------|--------------|-----------------|--------|
| EU One-Pager | v1.0 | 2026-02-12 | 2026-Q2 | ✅ Current |
| Healthcare Capability Sheet | v1.0 | 2026-02-12 | After next healthcare case study | ✅ Current |
| Email Templates | v1.0 | 2026-02-12 | After 10 partner intros (analyze conversion) | ✅ Current |

---

## 7. Partner Access & Distribution

### How Partners Receive Assets

**Option 1: Email delivery (Current - Robertas)**
- Send ZIP file with all relevant PDFs, templates, logos
- Include README with asset descriptions
- Update as new assets are created

**Option 2: Shared folder (Future - Multiple partners)**
- Google Drive or Dropbox folder
- Organized by asset type
- Partners have view-only access
- Update in place, notify partners of changes

**Option 3: Partner portal (Future - Scale)**
- Dedicated portal (Notion, Airtable, custom)
- Self-service asset download
- Lead submission form
- Commission statement access
- Automated notifications when assets update

**Current approach:** Option 1 (email to Robertas)
**Next milestone:** Transition to Option 2 when we have 3+ active partners

---

## Document Length

**Current length:** ~650 lines
**Status:** Comprehensive asset catalog and creation roadmap

**Last updated:** 2026-02-10
**Next update:** After Phase 1 assets are created (mid-February 2026)
**Owner:** Wei Zhuo
