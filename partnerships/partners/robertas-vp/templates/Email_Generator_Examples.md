---
**Document:** Email_Generator_Examples.md
**Version:** 1.0
**Last Updated:** 2026-02-16
**Owner:** Wei / Robertas
**Update Frequency:** When new leads are introduced or email approach evolves

**Synthesized From:**
- `Email_Generator_Instructions.md` v3.0 (coverage: ~100% — follows the 4-phase workflow)
- `../context/02_customgpt-intro-email-generator.md` v1.0 (coverage: ~60% — original lead details)
- `../LEADS.md` (coverage: ~80% — lead context, relationship details, strategic notes)

**What Changed:**
- v1.0 (2026-02-16): Initial creation — split from Email_Generator_Instructions.md v2.0. Added research summaries, email strategies, and expanded follow-up recommendations for all 5 leads. Each example now follows the full 4-phase workflow (Research → Plan → Write → Review).

**Downstream Dependencies:**
- `Email_Generator_Instructions.md` — References this file for examples
- `../LEADS.md` — Email outreach for each lead
- CustomGPT instance — These examples train the model on expected output quality

**Completeness:** ✅ Complete — 5 examples covering healthcare, insurance, e-commerce, aviation, and private equity
---

# Email Generator Examples

**Purpose:** These examples demonstrate the full 4-phase workflow from `Email_Generator_Instructions.md`. Each example shows how website research, strategic planning, and outcome-based writing come together to produce emails that feel personal and specific — not templated.

**How to use these examples:**
- Study the research → strategy → email pipeline (not just the final email)
- Notice how each email references something specific about the company
- Notice how the angle changes based on industry, relationship strength, and pain points
- Use these as calibration for the CustomGPT — the output quality should match or exceed these

---

## EXAMPLE 1: Affidea (Healthcare)

### Lead Information

| Field | Detail |
|-------|--------|
| **Company** | Affidea |
| **Website** | affidea.com |
| **Contact** | Chief-level executive (name TBD) |
| **Relationship** | "One of Chiefs is our good colleague" — Family friend |
| **Industry** | Healthcare — pan-European diagnostic imaging network |
| **Context** | Largest EU diagnostic imaging network. Robertas knows the chief/owner personally. |

### Research Summary

**What they do:** Affidea is Europe's largest provider of advanced diagnostic imaging, outpatient, and cancer care services. They operate across 15+ countries with 300+ clinics.

**Size/Scale:** 11,000+ employees, 300+ clinics, 15+ European countries, ~30 million patient interactions annually.

**Business model:** B2B2C — contracts with national health systems and insurers, serves patients directly.

**Industry:** Healthcare — diagnostic imaging, outpatient services, oncology.

**Key observations from website:**
- Massive multi-country operation requiring coordination across different health systems, languages, and regulatory environments
- Focus on clinical quality and patient experience — mentions AI in radiology and clinical decision support
- Recent growth through acquisitions — integrating new clinics into existing infrastructure is a recurring challenge
- Patient-facing digital tools appear limited — opportunity for intake automation and patient communication

**Likely pain points (based on industry + size + website):**
1. **Cross-border data coordination** — 15+ countries means fragmented systems, inconsistent reporting, and manual data consolidation for pan-European dashboards
2. **Patient intake volume** — 30M+ patient interactions per year, much of it still paper or semi-manual forms across 300+ clinics
3. **Radiologist workload** — diagnostic imaging generates massive data volumes; AI-assisted reading could reduce turnaround and increase throughput

**Best-fit Nexrizen services:**
- **AI & Automation** — patient intake automation, AI-assisted document processing across clinics
- **Custom Software** — real-time operational dashboards consolidating data from 15+ country operations

**Relevant results:**
- Johns Hopkins research partnership (AI diagnostics) — directly relevant to their imaging work
- 1,300 hours saved annually (AI meeting summaries) — applicable to clinical documentation
- 99% time reduction (document generation) — applicable to patient intake forms

**Recommended email angle:** Pain-point specific — reference their 15-country, 300-clinic scale and the operational complexity of coordinating across that many locations.

### Email Strategy

- **Primary angle:** Pain-point specific (multi-country operational complexity)
- **Supporting evidence:** Johns Hopkins AI diagnostics partnership + 99% time reduction on document generation
- **Outcome framing:** "Coordinating patient data across 300+ clinics in 15 countries — imagine one dashboard, one view, auto-updated in real time."
- **Company-specific detail used:** 15+ countries, 300+ clinics, 30M+ patient interactions

### Email Draft

**Subject Line:** Quick introduction — AI for healthcare operations

Dear [Name],

I hope this message finds you well. It's been too long since we last connected.

I wanted to make a brief introduction that I believe could be genuinely valuable for Affidea. I've recently partnered with a US-based AI-native firm called Nexrizen — a team of senior engineers (ex-Meta, ex-IBM, Georgia Tech PhDs) who serve as a fractional AI and technology team for organizations like yours.

What caught my attention for you: they've done significant work in healthcare, including a research partnership with Johns Hopkins on AI diagnostics. One of their clients went from spending 1,300 hours per year on manual documentation to having AI handle it in seconds — a 99% time reduction.

Their approach is unusual and, frankly, refreshing — after a single discovery conversation, they build a working prototype before any contract is signed. Not a slide deck. A functional application your team can interact with. And their ongoing rate is approximately €110 per hour — roughly one-third of what senior consultancies charge for comparable talent.

Given Affidea's scale across Europe — 300+ clinics in 15 countries — I thought there might be interesting applications, whether for patient intake automation, imaging workflow optimization, or operational dashboards across your network.

Would you be open to a brief call with their team? No pressure — just an exploratory conversation.

Warm regards,
Robertas

### Follow-Up Recommendations

- **Best send day/time:** Tuesday-Thursday, morning (9-11 AM CET). Healthcare executives often have clinical commitments Monday and Friday.
- **Follow-up timing:** If no response in 7 days, a brief one-line follow-up: "Just wanted to make sure this reached you — happy to discuss whenever convenient."
- **Personalization notes:** Robertas should insert the contact's first name and any personal reference (e.g., "since we last met at [event]"). If they've discussed healthcare technology before, reference that conversation.
- **Routing notes:** If the chief is a medical professional rather than operational executive, ask them to route to CIO/CTO or head of digital transformation.
- **LinkedIn action:** Ping on LinkedIn the same day the email is sent — brief message: "Just sent you a note about something I think could be interesting for Affidea."
- **GDPR note:** If they raise data concerns, emphasize Nexrizen builds GDPR-compliant systems and has experience with healthcare data requirements.

---

## EXAMPLE 2: Allianz (Insurance/Financial Services)

### Lead Information

| Field | Detail |
|-------|--------|
| **Company** | Allianz |
| **Website** | allianz.com |
| **Contact** | HR Department executive (name TBD) |
| **Relationship** | "My daughter is Senior Partner there" — Family (daughter) |
| **Industry** | Insurance, financial services |
| **Context** | Global insurance giant. Contact is in HR department. Allianz is "conservative about AI." Daughter has autonomy within HR to make decisions. Not yet discussed with daughter. |

### Research Summary

**What they do:** Allianz is one of the world's largest financial services companies — insurance, asset management, and financial services across 70+ countries.

**Size/Scale:** 150,000+ employees globally, €150B+ revenue, Fortune Global 500.

**Business model:** B2B2C — insurance products for individuals and businesses, asset management for institutional clients.

**Industry:** Insurance + financial services — highly regulated, data-intensive, compliance-heavy.

**Key observations from website:**
- Massive global operation with complex HR needs (150K+ employees, dozens of countries, multiple languages)
- Mentions digital transformation initiatives but primarily in customer-facing insurance products
- HR operations at this scale involve enormous volumes: onboarding, compliance training, employee inquiries, benefits administration
- Conservative culture — any introduction needs to feel low-risk and non-disruptive

**Likely pain points (based on industry + size + website):**
1. **HR inquiry volume** — 150K+ employees generating constant HR questions (benefits, policies, procedures) that consume team capacity
2. **Onboarding at scale** — Global hiring across dozens of countries requires localized, compliant onboarding that's currently manual
3. **Meeting documentation** — HR teams spend significant time documenting meetings, disciplinary proceedings, and compliance reviews

**Best-fit Nexrizen services:**
- **AI & Automation** — HR chatbot for employee inquiries (24/7, multilingual), automated onboarding workflows
- **Custom Software** — Meeting summarization for HR proceedings, document processing for compliance

**Relevant results:**
- 1,300 hours saved annually (AI meeting summaries) — directly applicable to HR documentation
- 1,000+ daily AI conversations (chatbots) — applicable to employee inquiry handling
- 99% time reduction (document generation) — applicable to HR paperwork

**Recommended email angle:** Personal connection — the daughter relationship makes this warm and low-risk. Focus on HR-specific pain points, not company-wide AI transformation.

### Email Strategy

- **Primary angle:** Personal connection + HR-specific pain points
- **Supporting evidence:** 1,300 hours saved (meeting summaries) + 1,000+ daily AI conversations (chatbots)
- **Outcome framing:** "Your HR team handles thousands of employee inquiries manually. After Nexrizen, AI handles routine questions 24/7 — freeing your team for strategic work."
- **Company-specific detail used:** 150K+ employee scale, HR-specific focus, conservative culture requiring low-risk approach

### Email Draft

**Subject Line:** Introduction to share — AI for HR workflows

Dear [Name],

[Daughter's name] mentioned you might be interested in what's happening with AI in HR operations, so I wanted to make a quick introduction.

I've partnered with an American AI-native firm called Nexrizen. They're a small team of senior engineers — founders from Meta and IBM, both Georgia Tech graduates — who work as a fractional technology team for organizations looking to automate and modernize. No junior developers, no outsourcing — direct access to the people doing the work.

For HR specifically, one of their legal clients was spending 1,300 hours per year on meeting documentation alone. After Nexrizen built them an AI system, that same work takes seconds. They've also built intelligent chatbots that handle routine inquiries 24/7, freeing up teams for strategic work.

What makes them different: after a single discovery call, they build a working prototype before any contract is signed. Your team interacts with something real — not a slide deck. And they work hourly at approximately €110 per hour, with no minimums or long-term commitments. Quite different from the typical €50,000 advance payment most consultancies require.

I thought this might be relevant as Allianz continues to modernize HR operations. If you'd be interested, I'd be happy to arrange a brief introductory call with their CEO, Weipeng.

Best regards,
Robertas

P.S. — Please give my regards to [Daughter's name].

### Follow-Up Recommendations

- **Best send day/time:** Mid-week (Tuesday-Wednesday), morning. Insurance executives tend to have structured schedules.
- **Follow-up timing:** Given the family connection, keep follow-up light. If no response in 10 days, Robertas can ask his daughter to mention it casually.
- **Personalization notes:** MUST personalize with daughter's actual name (appears twice). Add any personal detail about the daughter's recent achievements or role if appropriate.
- **Routing notes:** HR is a good entry point — lower procurement friction than company-wide technology initiatives. The daughter's autonomy within HR means she may be able to greenlight a prototype without corporate IT approval.
- **LinkedIn action:** Optional — the family channel is stronger. If Robertas wants to reinforce, a LinkedIn message to the HR contact after the daughter confirms interest.
- **Conservative culture note:** Allianz is conservative about AI. Frame everything as "low-risk exploration" not "AI transformation." The free prototype is the perfect antidote to their caution.

---

## EXAMPLE 3: Vintage Cash Cow (E-commerce/Tech)

### Lead Information

| Field | Detail |
|-------|--------|
| **Company** | Vintage Cash Cow |
| **Website** | vintagecashcow.co.uk |
| **Contact** | VP ICT (cousin) |
| **Relationship** | "My cousin" — Family |
| **Industry** | E-commerce, vintage goods marketplace |
| **Context** | Valued at ~€5 billion, 200-person tech team, rapid growth. Cousin joined 3 months ago via acquisition. Origin: Lithuania → now UK-managed. |

### Research Summary

**What they do:** Vintage Cash Cow is a UK-based online marketplace for buying and selling vintage, antique, and pre-owned items. They handle the entire process — sellers ship items in, the platform photographs, lists, and sells them.

**Size/Scale:** ~€5B valuation (per Robertas), 200 ICT professionals, rapid expansion, originally Lithuanian-founded.

**Business model:** Marketplace/consignment — sellers send items, VCC handles photography, listing, pricing, selling, and shipping. Revenue from commission on sales.

**Industry:** E-commerce — vintage/secondhand goods marketplace, high-growth segment.

**Key observations from website:**
- High-volume operation: processing thousands of items daily (intake, photography, listing, selling, shipping)
- Customer-facing: both sellers (sending items in) and buyers (purchasing on platform)
- Heavy logistics component — warehousing, photography, quality assessment, pricing
- Rapid scaling means operational bottlenecks are likely multiplying
- 200-person tech team suggests significant in-house capability, but specialized AI projects may not be their core competency

**Likely pain points (based on industry + size + website):**
1. **Customer service volume** — Both buyer and seller inquiries at marketplace scale (where's my item? pricing questions? return requests?)
2. **Item processing pipeline** — Manual steps in intake, assessment, photography, pricing, listing could benefit from AI (automated pricing, image recognition, category tagging)
3. **Seller management** — Communicating with thousands of sellers about item status, payments, rejections is labor-intensive
4. **Operational dashboards** — At €5B scale, leadership needs real-time visibility across all operations

**Best-fit Nexrizen services:**
- **AI & Automation** — Customer service chatbot (buyer + seller inquiries), automated item categorization/pricing
- **Custom Software** — Operational dashboards, seller management portal
- **Fractional team positioning** — Complementary to 200-person team for specialized AI projects

**Relevant results:**
- 1,000+ daily AI conversations (chatbots) — directly relevant to their customer service volume
- AI-native operations with 6 proprietary systems (GitHub-verifiable) — appeals to a VP ICT who can evaluate technical claims
- ~$50,000 annual savings (workflow automation) — applicable to operational efficiency

**Recommended email angle:** Growth-stage — they're scaling rapidly and need to scale operations faster than headcount. Position as complementary to their 200-person team.

### Email Strategy

- **Primary angle:** Growth-stage + complementary positioning (not replacing their team)
- **Supporting evidence:** 1,000+ daily AI conversations + AI-native operations (GitHub-verifiable)
- **Outcome framing:** "Instead of scaling your support team proportionally with growth, AI handles 1,000+ customer conversations daily — instant, 24/7."
- **Company-specific detail used:** 200-person tech team (position as complementary), rapid growth/scaling, marketplace model with both buyer and seller operations

### Email Draft

**Subject Line:** Catching up + a technology partner introduction

Dear [Cousin's name],

Hope all is well with you and the family. I wanted to share something that might be useful as Vintage Cash Cow continues scaling.

I've partnered with a US-based AI-native firm called Nexrizen. They're quite different from typical agencies — senior engineers only, founders from Meta and IBM (both Georgia Tech), and they serve as a fractional AI and technology team. Their own business runs entirely on 6 proprietary AI systems they built internally — three of them are public on GitHub, so you can verify their claims.

What made me think of you: they've built AI customer service systems handling over 1,000 conversations per day — instant response, 24/7 — eliminating the need for large support teams. They've also built operational dashboards and analytics platforms for fast-growing companies at scale similar to yours.

I know you have a strong 200-person team in-house, so I'm not suggesting a replacement — they work alongside internal teams for specialized AI projects and rapid prototyping. Their approach: after one discovery call, they build a working prototype before any contract. And they work hourly at approximately €110 per hour — no minimums, no lock-in. It's a low-risk way to see if there's a complementary fit.

Would you have 20 minutes for an introductory call? Happy to join if helpful.

Warm regards,
Robertas

### Follow-Up Recommendations

- **Best send day/time:** Any weekday works — tech/e-commerce operates on flexible schedules. Tuesday-Thursday morning CET is safe.
- **Follow-up timing:** Family = can follow up by phone or WhatsApp if preferred. If email, 5-7 days.
- **Personalization notes:** Use cousin's first name. Reference any family news or recent visit. The casual tone is appropriate for family.
- **Routing notes:** The cousin IS the decision-maker (VP ICT) — no routing needed. But he's new (3 months, joined via acquisition), so help him look good internally. Position Nexrizen as something that makes HIM look innovative.
- **LinkedIn action:** Optional — family channel is stronger. But if the cousin is active on LinkedIn, connecting professionally adds credibility.
- **Strategic note:** This is the highest-value lead (€5B company). CRITICAL to position as complementary to their 200-person team, NEVER competitive. The cousin's success = Robertas's family relationship preserved AND commission earned.

---

## EXAMPLE 4: VistaJet (Aviation)

### Lead Information

| Field | Detail |
|-------|--------|
| **Company** | VistaJet |
| **Website** | vistajet.com |
| **Contact** | Captain/Pilot, Swiss Department |
| **Relationship** | "Family gentleman" — Family friend, pilot with ICT degree |
| **Industry** | Private aviation, luxury travel |
| **Context** | Major private jet company. Contact has ICT degree from London university but is a pilot, not a technology decision-maker. |

### Research Summary

**What they do:** VistaJet is one of the world's largest private aviation companies, offering on-demand charter flights globally. They operate a fleet of 360+ aircraft with a "Program" membership model.

**Size/Scale:** 360+ aircraft, global operations across 187 countries, thousands of employees, headquartered in Malta with offices in key financial centers.

**Business model:** B2B/B2C luxury service — membership programs + on-demand charter for UHNWIs, corporations, and governments.

**Industry:** Private aviation — luxury travel, high-touch customer service, complex logistics.

**Key observations from website:**
- Premium brand positioning — every touchpoint emphasizes luxury, personalization, and service excellence
- Complex global logistics: fleet management across 187 countries, crew scheduling, maintenance coordination, regulatory compliance per jurisdiction
- High-touch customer service: clients expect instant responses, personalized itineraries, 24/7 availability
- Membership model means recurring relationships — CRM and client management are critical
- Website is sleek and modern — suggests reasonable tech maturity

**Likely pain points (based on industry + size + website):**
1. **Booking and inquiry response time** — UHNWI clients expect instant responses; manual booking processes at scale create delays
2. **Fleet/crew coordination** — 360+ aircraft across 187 countries requires real-time operational visibility
3. **Client relationship management** — Personalized service for repeat members requires detailed tracking of preferences, history, and special requests
4. **Multilingual operations** — Global client base needs support in multiple languages

**Best-fit Nexrizen services:**
- **AI & Automation** — AI-powered booking inquiries (instant, 24/7, multilingual), client preference tracking
- **Custom Software** — Real-time fleet operations dashboards, client management systems

**Relevant results:**
- 1,000+ daily AI conversations (chatbots — 24/7, multilingual) — directly relevant to booking inquiries
- Real-time dashboards (Fortune 100 financial institution) — applicable to fleet operations visibility
- ~$50,000 annual savings (workflow automation) — applicable to operational efficiency

**Recommended email angle:** Pain-point specific — reference their 360+ aircraft fleet and 187-country operations, and the operational complexity of managing that scale while maintaining luxury-level service.

### Email Strategy

- **Primary angle:** Pain-point specific (operational complexity at luxury-service scale)
- **Supporting evidence:** 1,000+ daily AI conversations (multilingual) + real-time dashboards
- **Outcome framing:** "Instead of your team manually handling booking inquiries over several hours, an AI system responds instantly to 1,000+ inquiries per day — 24/7, in multiple languages."
- **Company-specific detail used:** 360+ aircraft fleet, 187-country operations, luxury service expectations

### Email Draft

**Subject Line:** Quick intro — AI for aviation operations

Dear [Name],

I hope you're keeping well and the skies are treating you kindly.

I wanted to pass along an introduction that might interest VistaJet's operations team. I've partnered with an AI-native firm from the US called Nexrizen — a team of senior engineers (ex-Meta, ex-IBM, Georgia Tech PhDs) who serve as a fractional technology team for companies modernizing with AI.

Given my background in aviation finance, I immediately saw applications for this kind of technology in your world. Imagine: instead of your team manually handling booking inquiries over several hours, an AI system responds instantly to 1,000+ inquiries per day — 24/7, in multiple languages. Or real-time operational dashboards that replace manual fleet tracking across your 360+ aircraft in 187 countries.

What sets them apart: after a discovery conversation, they build a working prototype before any contract is signed — a functional application, not a proposal deck. They work on an hourly basis at roughly €110 per hour, which is approximately a third of what traditional European consultancies charge for senior engineering talent.

If there's someone in operations or IT who might benefit from an introduction, I'd be happy to facilitate. Or if you'd like to hear more yourself, I can arrange a brief call.

With warm regards,
Robertas

### Follow-Up Recommendations

- **Best send day/time:** Mid-week. Pilots have irregular schedules — email may work better than trying to schedule calls immediately.
- **Follow-up timing:** 7-10 days. If no response, a brief WhatsApp or text if the relationship supports it.
- **Personalization notes:** Robertas should add any personal touch — reference to last meeting, family connection details, or shared aviation interests.
- **Routing notes:** CRITICAL — the contact is a pilot with an ICT degree, technically savvy but likely NOT the technology decision-maker. The email explicitly offers to help identify the right person in operations/IT. Robertas may need to ask: "Who handles technology decisions for operations? I'd love to connect them with Nexrizen."
- **LinkedIn action:** Connect with the pilot on LinkedIn if not already connected. After sending, brief message: "Sent you a note about something relevant to VistaJet operations — let me know if you'd like to discuss."
- **Credibility lever:** Robertas's aviation finance background gives him unique credibility in this vertical. Lean into it.

---

## EXAMPLE 5: Aalto Capital (Private Equity/Investment)

### Lead Information

| Field | Detail |
|-------|--------|
| **Company** | Aalto Capital |
| **Website** | aaltocapital.com |
| **Contact** | Partner (name TBD) |
| **Relationship** | "Our good colleague" — 12-year professional relationship |
| **Industry** | Private equity, venture capital, investment |
| **Context** | Finland/Scandinavia-based, 5 main partners. Robertas's core domain (FinTech). |

### Research Summary

**What they do:** Aalto Capital is a Nordic private equity and advisory firm focused on mid-market transactions, capital raising, and strategic advisory across Northern Europe.

**Size/Scale:** Boutique firm, 5 main partners, Finland/Scandinavia-based with cross-border deal flow.

**Business model:** B2B financial services — advisory fees, success fees on transactions, management fees on capital under management.

**Industry:** Private equity + investment banking — relationship-driven, deal-oriented, high-value transactions.

**Key observations from website:**
- Focus on mid-market transactions — typically €10M-€100M deal sizes
- Cross-border expertise (Nordic + European markets)
- Small team structure means each partner handles multiple deals simultaneously — operational efficiency matters
- Deal flow management, client relationships, and market research are core workflows
- Website is professional but not technology-forward — typical for PE firms

**Likely pain points (based on industry + size + website):**
1. **Deal flow management** — Tracking multiple active deals, potential targets, and investor relationships across partners manually
2. **Research and due diligence** — Market analysis, competitor research, and financial modeling are time-intensive manual processes
3. **Portfolio company support** — Limited bandwidth to provide hands-on operational support to portfolio companies (this is where Nexrizen adds value)
4. **Client communication** — Maintaining regular updates with investors and portfolio companies is manual and time-consuming

**Best-fit Nexrizen services:**
- **Fractional CTO** — For portfolio companies needing technology leadership (CITYROW precedent)
- **AI & Automation** — Deal flow tracking, research automation, investor reporting
- **Custom Software** — Portfolio management dashboards, client relationship tools

**Relevant results:**
- CITYROW → WaterRower acquisition (Fractional CTO) — directly demonstrates value creation in PE portfolio companies
- 100x processing speed improvement (Fortune 100 financial institution) — applicable to financial data processing
- ~$50,000 annual savings (workflow automation) — applicable to operational efficiency

**Recommended email angle:** Dual-value proposition — direct services for Aalto AND portfolio company value creation. The PE referral channel is the strategic prize.

### Email Strategy

- **Primary angle:** Portfolio company value creation (dual opportunity)
- **Supporting evidence:** CITYROW → WaterRower acquisition + 100x processing speed (Fortune 100) + €45,000 annual savings
- **Outcome framing:** "One introduction could unlock value across your entire portfolio — a fractional CTO who's already led a portfolio company through a successful acquisition."
- **Company-specific detail used:** 5-partner structure (bandwidth constraints), mid-market focus, portfolio company value creation as differentiator

### Email Draft

**Subject Line:** AI capabilities for portfolio companies — worth a look

Dear [Name],

Good to connect. I have an introduction I think could be valuable — both for Aalto Capital directly and potentially for your portfolio companies.

I've partnered with an American AI-native firm called Nexrizen. They work as a fractional AI and technology team — senior engineers only (ex-Meta, ex-IBM, Georgia Tech), direct founder involvement on every project, hourly engagement at approximately €110 per hour with no minimums or long-term commitments.

For investment firms, I see two angles worth exploring:

First, portfolio company value creation. They've helped companies achieve transformative results — a Fortune 100 institution saw 100x processing speed improvement, a professional services firm saves €45,000 annually from a single workflow automation. Their fractional CTO led CITYROW through a successful acquisition by WaterRower last year.

Second, their approach eliminates evaluation risk. After one discovery call, they build a working prototype before any contract is signed. For early-stage portfolio companies evaluating technology investments, this lets founders see exactly what they'd be getting — zero financial commitment.

As an ongoing fractional technology team, they can serve multiple portfolio companies at once. One introduction could unlock value across your entire portfolio.

Would you be interested in an introductory conversation? I'm happy to join the call.

Best regards,
Robertas

### Follow-Up Recommendations

- **Best send day/time:** Tuesday-Thursday morning. PE professionals are deal-focused — avoid Monday (deal pipeline reviews) and Friday (travel).
- **Follow-up timing:** 7 days. The 12-year relationship is strong enough to be more direct in follow-up: "Did you get a chance to look at my note about Nexrizen?"
- **Personalization notes:** Robertas should reference a recent deal, market trend, or personal catch-up. The 12-year relationship allows more directness than other leads.
- **Routing notes:** Partner is the decision-maker for both direct engagement AND portfolio introductions. No routing needed.
- **LinkedIn action:** Given the long-standing professional relationship, a LinkedIn message after sending is natural: "Sent you something I think could be interesting for your portfolio companies — let me know your thoughts."
- **Strategic note:** This lead's real value is as a referral channel. Even if Aalto doesn't engage directly, getting Nexrizen introduced to 3-5 portfolio companies could generate $50K-$200K in revenue over time. Frame for portfolio value, not just direct services. PE firms think in terms of leverage — one relationship that creates value across multiple investments.

---

## How These Examples Follow the 4-Phase Workflow

| Phase | What Happens | Why It Matters |
|-------|-------------|----------------|
| **Phase 1: Research** | Browse company website, extract profile, tech signals, pain points | Prevents generic emails. Every email references something real about the company. |
| **Phase 2: Plan** | Choose angle, select evidence, craft outcome framing | Strategic thinking before writing produces sharper, more compelling emails. |
| **Phase 3: Write** | Draft 150-250 word email using 7-part structure | Consistency in structure with specificity in content. |
| **Phase 4: Review** | Delivery recommendations, personalization notes, routing guidance | Ensures the email gets to the right person at the right time with the right follow-up. |

### Pattern Observations Across Examples

| Pattern | Observation |
|---------|-------------|
| **Family leads** (Allianz, VCC) | More casual tone, personal P.S., family channel for follow-up |
| **Family friend leads** (Affidea, VistaJet) | Warm but professional, reference shared history |
| **Colleague leads** (Aalto) | Most businesslike, can be more direct about value |
| **Decision-maker contacts** (VCC, Aalto) | Direct pitch to the person who can say yes |
| **Non-decision-maker contacts** (VistaJet) | Explicitly offer to help route to the right person |
| **Large enterprises** (Affidea, Allianz) | Focus on specific department/use case, not company-wide transformation |
| **Growth-stage** (VCC) | Position as complementary to existing team, help contact look good |
| **PE/Investment** (Aalto) | Dual value proposition (direct + portfolio), leverage framing |
