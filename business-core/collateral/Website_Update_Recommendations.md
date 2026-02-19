---
**Document:** Website_Update_Recommendations.md
**Version:** 1.0
**Last Updated:** 2026-02-18
**Owner:** Wei / Gabe
**Update Frequency:** As-needed

**Synthesized From:**
- `github.com/nexrizen/marketing` repo (coverage: ~90%)
- `Nexrizen_Market_Positioning.md` (coverage: ~60%)
- `Nexrizen_Business_Overview.md` (coverage: ~50%)
- `LinkedIn_Company_Page_Update.md` (coverage: ~30%)
- `Upwork_Profile_Update.md` (coverage: ~20%)

**Downstream Dependencies:**
- All outbound sales (LinkedIn DMs, Upwork proposals, partner intros land here)
- SEO / organic discovery
- Omnibot product sales
- Partnerships (Robertas sends EU prospects to website)

**Completeness:** ⚠️ Requires decisions on 5 items marked with 🔘 below
---

# Website (nexrizen.com) — Comprehensive Update Recommendations

## Executive Summary

The site is well-designed and well-built (Hugo + Tailwind v4, custom animations, solid layout). The homepage and service pages are strong — the "Free Prototype" positioning, founder credentials, and testimonials all land well. But there are significant gaps between what the site communicates and what the internal business docs say the strategy is. There are also several broken/placeholder pages that actively hurt credibility.

**Priority breakdown:**

| Priority | Category | Items |
|----------|----------|-------|
| 🔴 Critical | Broken/placeholder pages damaging credibility | 3 |
| 🔴 Critical | Analytics & tracking not working | 2 |
| ⚠️ High | Content misaligned with current strategy | 5 |
| ⚠️ High | Missing content that should exist | 4 |
| 💡 Medium | Optimization & polish | 6 |
| 💡 Low | Cleanup & tech debt | 5 |

---

## 🔴 Critical Issues (Fix ASAP)

### 1. Pricing Page Is Fake

`/pricing/` shows generic template tiers: $99 / $199 / $299 per month with features like "5GB Disk Space." This is clearly placeholder content from the Hugo theme and has nothing to do with Nexrizen.

**Risk:** Any prospect who clicks "Pricing" in the URL bar or finds this via search sees obviously fake content. Instant credibility killer.

**Meta description is literally:** `"this is meta description"`

**Fix options:**
- **Remove entirely** — delete the page and remove any internal links to it
- **Replace with engagement model page** — see Decision 2 below

### 2. FAQ Page Is Lorem Ipsum

`/faq/` is filled with placeholder text. Same credibility risk as pricing.

**Meta description:** `"this is meta description"`

**Fix:** Remove the page or populate with real FAQs. Suggested real FAQs below in "Content to Add" section.

### 3. Google Analytics Is Not Working

The GA4 measurement ID is literally `G-MEASUREMENT_ID` — a placeholder. You have zero analytics on your primary website. reCAPTCHA site key is also `xxx-xxxxxxxxxxxxxxxxxxxxxxxx`.

**This means:**
- No data on which pages convert
- No data on traffic sources
- No data on how prospects navigate the site
- Contact form has no spam protection
- The GA4, Facebook Pixel, and LinkedIn conversion tracking code in `contact-form.js` is firing against fake IDs

**Fix:** Set up real GA4 property, configure GTM, add real reCAPTCHA key. This is a 30-minute task that's been left undone.

---

## 🔘 Decision 1: Pricing Page Strategy

The `/pricing/` page currently has fake content. What should it become?

| Option | What It Shows | Pros | Cons |
|--------|---------------|------|------|
| **A: Remove entirely** | Nothing — page doesn't exist | Clean, no risk of wrong expectations, forces conversation | Prospects expect pricing info, may bounce |
| **B: "How We Work" page** | Engagement model (hourly at $120/hr), process, what's included, what's not | Transparent, filters bad-fit clients, aligns with hourly-only policy | Commits you publicly to $120/hr, less negotiation flexibility |
| **C: "Investment Guide"** | Ranges by project type ("AI chatbot: $5K-$15K typical", "Custom dashboard: $8K-$25K") without committing to hourly | Gives prospects budget context, reduces unqualified leads | Ranges might anchor too low, doesn't reflect hourly-only policy |
| **D: "Start Free" page** | Just the free prototype offer + "Book a call to discuss pricing" | Keeps pricing private, leads with free value | Doesn't answer the pricing question at all |

**Recommendation:** B — Your internal docs say "hourly only at $120/hr, no exceptions." Making this public filters out clients who can't afford it and positions you as a premium fractional team, not a commodity dev shop. The market positioning doc already uses "fractional AI/tech team" language.

---

## 🔘 Decision 2: ThreeDays.ai Link

The main nav has "Your Free Prototype" linking to `https://www.threedays.ai` (external site). This sends traffic away from nexrizen.com to a separate domain with minimal content.

| Option | Pros | Cons |
|--------|------|------|
| **A: Keep external link** | Separate brand, dedicated landing experience | Sends traffic away, confusing brand relationship, threedays.ai has minimal content |
| **B: Link to `/contact/`** (recommended) | Keeps traffic on-site, contact form already positioned as "Get Your Free Prototype" | Loses dedicated landing page |
| **C: Build ThreeDays section on nexrizen.com** | Best of both — dedicated page at `/free-prototype/` explaining the 3-day process | Requires new page build |
| **D: Remove from main nav, keep as secondary CTA** | Declutters nav, still accessible | Reduces visibility of key differentiator |

**Recommendation:** B or C — The header CTA button already links to `/contact/` with "Free Prototype" messaging. Having a separate nav item going to a different domain is confusing. Either make them consistent (both → `/contact/`) or build a proper `/free-prototype/` page on nexrizen.com explaining the 3-day process.

---

## ⚠️ High Priority: Content Misaligned with Strategy

### 4. No Pricing / Engagement Model Visible

Internal policy (Feb 2026): "All new work: hourly at $120/hr, no exceptions."

Website: Zero mention of hourly pricing, engagement model, or what it costs to work with Nexrizen. Contact form offers budget ranges from "Under $5K" to "$100K+" which implies fixed-price project scoping.

**Impact:** Prospects come in with wrong expectations. Sales calls wasted on budget misalignment.

**Fix:** See Decision 1 above. At minimum, add a line to the contact page or process section: "All engagements are billed hourly at $120/hr with weekly demos and full transparency."

### 5. Blog Is 2 Years Stale

Only 2 blog posts, both from March 2024. For a company positioning as cutting-edge AI-native thought leaders, this signals abandonment.

**Blog description says:** *"Discover how we're transforming service firms with AI automation"* — but there's no evidence of this on the blog.

**Fix options:**
- Add 3-5 posts covering recent work (case studies already written internally could be adapted)
- If no bandwidth for blog content, remove the blog link from nav until you have 5+ posts
- Repurpose LinkedIn content from Gabe's daily posts as blog articles

### 6. Case Studies Don't Mention Legal Tech Depth

18 case studies exist in the portfolio, which is strong. But the legal tech specialization — Nexrizen's deepest moat — is underrepresented. The immigration law page mentions AILA but the case studies don't prominently feature the Saenz-Garcia fractional CTO engagement or the 1,000 leads/day intake system as standalone showcases.

**Fix:** Ensure the top 2-3 portfolio items visible on the homepage grid include legal tech work with the strongest metrics.

### 7. "About" Team Section Shows Only 4 People

The About page lists Wei, Gabe, Zhimin, and Sol. Internal docs say 8 team members (2 founders, 2 PhDs, 3 engineers, 1 VA). The engineers and Ruth aren't shown.

**This could be intentional** (showing only senior/PhD-level talent) but it contradicts the "team of 8" and "100+ years combined experience" claims elsewhere.

**Fix:** Either show the full team or adjust the "100+ years" claim to specify "founding team" or "senior leadership."

### 8. Footer Industries Missing Personal Injury

Footer lists Industries as just "Immigration Law" and "Fintech" — but Personal Injury has its own page and is internally identified as the #1 legal vertical priority.

**Fix:** Add "Personal Injury" to footer industries list. Simple config change.

---

## 🔘 Decision 3: Omnibot Pricing Visibility

Omnibot has explicit pricing on the website: $997 / $1,797 / $2,497 per month. This is the only product with public pricing.

| Option | Pros | Cons |
|--------|------|------|
| **A: Keep public pricing** | Transparent, filters unqualified leads, standard SaaS practice | Competitors can see and undercut, limits negotiation |
| **B: Remove pricing, add "Book a Demo"** | More flexibility, can price by value | Adds friction, loses self-serve leads |
| **C: Keep pricing but add "Custom" enterprise tier** | Best of both — transparent base, flexible upmarket | Slightly more complex page |

**Recommendation:** A (keep as-is) or C if you're getting enterprise inquiries. SaaS products benefit from visible pricing — it's expected. The current tiers are well-structured.

---

## 🔘 Decision 4: Contact Form Budget Ranges

The contact form asks for budget range with options: Under $5K, $5K-$15K, $15K-$50K, $50K-$100K, $100K+.

With the hourly-only policy at $120/hr, fixed budget ranges don't make sense anymore. A $15K budget = ~125 hours = ~3 weeks of full-time work. The framing should match.

| Option | Pros | Cons |
|--------|------|------|
| **A: Keep budget ranges** | Familiar to prospects, helps qualify leads | Implies fixed-price, misaligns with hourly policy |
| **B: Replace with "Estimated hours/week"** | Aligns with hourly model, honest | Prospects may not know how to estimate hours |
| **C: Replace with "Team size needed"** | Frames as fractional team, matches positioning | Unusual, may confuse |
| **D: Keep ranges but add "(at $120/hr)"** | Transparent, helps self-qualify | Very direct, some may bounce |

**Recommendation:** A with a note — keep the budget ranges (they help with lead scoring, which is already built into the form JS) but add a small note near the field: *"All engagements billed hourly at $120/hr. Budget helps us estimate scope."*

---

## 🔘 Decision 5: Unused Language Content

The repo has full content directories for French, German, and Italian with placeholder content (Rio Furniture projects, lorem ipsum). These are from the original Hugo theme template.

| Option | Pros | Cons |
|--------|------|------|
| **A: Delete all non-English content** (recommended) | Clean repo, no risk of accidental exposure, reduces build size | Loses multilingual scaffolding if ever needed |
| **B: Keep but ensure not accessible** | Preserves structure for EU expansion (Gabe → Spain, Robertas) | Clutter, risk of indexing |

**Recommendation:** A — Delete them. If you need EU-language pages later (for Robertas's network), you'd want real translated content, not template placeholders. The scaffolding is trivial to recreate.

---

## ⚠️ High Priority: Missing Content

### 9. No "Why Nexrizen" or Differentiator Page

The homepage has a "Why Nexrizen" section but it's brief. There's no dedicated page explaining:
- The 6 proprietary AI systems in detail
- The "Proof Before Payment" model with stats
- How you're different from offshore teams, traditional agencies, and freelancers
- The AI-native operations thesis

This is the content that closes deals. It exists in `Nexrizen_Market_Positioning.md` but not on the website.

**Fix:** Create a `/why-nexrizen/` page or significantly expand the About page to include this content.

### 10. No Client Logos Page or Trust Page

You have testimonials from Meta, Techstars, CITYROW (WaterRower acquired), Johns Hopkins, Georgia Tech, Saenz-Garcia Law. These are strong names. But there's no dedicated social proof page or "Clients" section beyond the small logo bar.

**Fix:** Add a `/clients/` page or expand the logo bar with brief case study links.

### 11. No GitHub / Open Source Visibility

Three public repos (threedays-dev-toolkit, browser-automation-generator, webinar-generator) are mentioned in internal docs as proof of technical credibility. Zero mention on the website.

**Fix:** Add GitHub links to the About page or create a "Tools" section showing public repos. Technical buyers (CTOs, engineering leads) check GitHub.

### 12. No Gabe-in-Spain / EU Presence Mention

Gabe is relocating to Spain Q2 2026 for EU timezone coverage. Robertas is developing the EU partnership. The website has zero mention of European availability or EU market readiness.

**Fix:** Once Gabe relocates, add "US + EU timezone coverage" to the About page and consider an EU-focused landing page.

---

## 💡 Medium Priority: Optimization & Polish

### 13. Legacy Theme Artifacts

- Disqus shortname is `themefisher-template` (theme default)
- Author pages exist for "John Doe" and "Mark Dinn" (template defaults)
- Hugo theme credits still in footer (Themefisher)
- Legacy SCSS from Bootstrap still in theme directory

**Fix:** Remove template defaults. These are minor but look unprofessional if discovered.

### 14. Hugo Version Mismatch

GitHub Actions uses Hugo v0.115.1, Netlify uses v0.145.0. This could cause build differences between the two deployment targets.

**Fix:** Align both to v0.145.0 (or latest stable).

### 15. SEO Meta Descriptions

Several pages have weak or placeholder meta descriptions:
- `/pricing/`: `"this is meta description"`
- `/faq/`: `"this is meta description"`
- Some service pages may have generic descriptions

**Fix:** Write unique, keyword-rich meta descriptions for every page. 150-160 characters each, including primary keyword and value prop.

### 16. Careers Page — No Open Roles Listed

The careers page says "we're always hiring" with role categories but no actual open positions with apply buttons. It reads more like a culture page.

**Fix:** Either list specific open roles with application method, or rename to "Culture" and remove from nav until you're actively hiring.

### 17. Call Intelligence Page — Standalone Product?

`/call-intelligence/` exists as a separate product page but it's not clear if this is a standalone product like Omnibot or a feature of the AI & Automation service. It's not in the main navigation.

**Fix:** Clarify the relationship. If it's a product, add to nav under a "Products" dropdown alongside Omnibot. If it's a feature, fold it into the AI & Automation service page.

### 18. Contact Form — No Spam Protection

reCAPTCHA key is a placeholder. The Supabase table allows anonymous inserts. No rate limiting visible. This form will eventually get spammed.

**Fix:** Add real reCAPTCHA v3 or switch to Cloudflare Turnstile (lighter weight, better UX).

---

## 💡 Low Priority: Cleanup & Tech Debt

### 19. `.env` File May Be in Repo

The agent noted `.env` and `.env.example` files. If `.env` contains real Supabase keys, this is a security issue (even if the anon key is designed to be public, it's bad practice).

**Fix:** Verify `.env` is in `.gitignore`. If real keys are committed, rotate them.

### 20. OG Image Generation

A script exists at `scripts/generate-og.mjs` for generating Open Graph images. Verify these are being generated and deployed for all pages (especially case studies and blog posts).

### 21. Dual Deployment (Netlify + GitHub Pages)

The site deploys to both Netlify and GitHub Pages. This is unusual and could cause confusion about which is the canonical deployment.

**Fix:** Pick one. Netlify is more capable (redirects, forms, functions). Remove the GitHub Actions workflow if Netlify is primary.

### 22. Supabase Migration

Only one migration file: `20250130_create_leads_table.sql`. The leads table structure looks good (UUID keys, RLS, indexes). No issues here, just noting for completeness.

### 23. Font Loading

Multiple font sources: Google Fonts (Inter, Roboto), theme assets (Space Grotesk), Font Awesome. Consider self-hosting fonts for performance and privacy (no Google Fonts requests).

---

## Content to Add: Suggested FAQ Content

If you decide to populate the FAQ page instead of removing it:

**General:**
- "How does the free prototype work?" → 3-day process explanation
- "What happens after the prototype?" → Hourly engagement, weekly demos, 3-12 week delivery
- "How much does it cost?" → $120/hr, all engagements hourly, typical projects $5K-$30K
- "Who will work on my project?" → Senior engineers only, direct founder involvement
- "What technologies do you use?" → Stack overview (Python, React, Next.js, GCP, Claude, etc.)

**AI-Specific:**
- "Can you integrate AI into my existing systems?" → Yes, with caveats on brownfield vs greenfield
- "Is my data secure?" → Data handling, compliance, no training on client data
- "What kind of AI systems do you build?" → Chatbots, automation, voice AI, multi-agent systems

**Process:**
- "How long does a typical project take?" → 3-12 weeks depending on scope
- "Do you offer ongoing maintenance?" → Yes, $300-600/month packages
- "Can I start with a small project?" → Yes, hourly model makes this easy

---

## Content Alignment: Website vs Internal Docs

| Topic | Internal Docs Say | Website Says | Gap |
|-------|-------------------|--------------|-----|
| **Pricing** | $120/hr, hourly only, no fixed-price | No pricing shown (except Omnibot) | 🔴 Major — prospects have no pricing context |
| **Team size** | 8 (2 founders, 2 PhDs, 3 engineers, 1 VA) | Shows 4 people (About page) | ⚠️ Moderate — "100+ years" claim unsubstantiated |
| **AI-native stack** | 6 named proprietary systems with detailed capabilities | Brief mention in "Why Nexrizen" section | ⚠️ Could be much stronger |
| **Legal tech depth** | AILA winner, fractional CTO at largest Dallas immigration firm, 1,000 leads/day | Immigration law page exists but undersells | ⚠️ Moderate |
| **Conversion metrics** | 90% response rate, 75-80% demo-to-client, ~50% Upwork close | "75%+ Demo-to-Client" chip on homepage | ✅ Mostly aligned |
| **Partnership model** | "Dating phase" → hourly → equity | Not mentioned | 💡 Could add for partnership prospects |
| **Values** | "Don't work with assholes", bootstrap mindset | About page mentions values briefly | ⚠️ Could be stronger (it's a differentiator) |
| **EU expansion** | Gabe → Spain Q2 2026, Robertas partnership, banking-standard quality | Zero EU mention | ⚠️ Premature until Gabe relocates |
| **Serial builders vision** | Services → products → exits | Not mentioned (probably shouldn't be) | ✅ Correct to omit |
| **Blog/thought leadership** | Daily LinkedIn content, webinars planned | 2 posts from 2 years ago | 🔴 Major — signals abandonment |
| **GitHub repos** | 3 public repos as credibility proof | Zero mention | ⚠️ Missing for technical buyers |
| **Engagement model** | Fractional AI/tech team, ongoing hourly | "Book a call" — no model explained | ⚠️ Moderate |

---

## Implementation Priority

### Phase 1: Damage Control (This Week)
- [ ] Remove or fix `/pricing/` page (fake tiers)
- [ ] Remove or fix `/faq/` page (lorem ipsum)
- [ ] Set up real GA4 property and add measurement ID
- [ ] Add real reCAPTCHA key
- [ ] Fix footer — add Personal Injury to industries
- [ ] Remove legacy template artifacts (Disqus, fake authors)
- [ ] Delete unused language directories (French, German, Italian)
- [ ] Align Hugo version in GitHub Actions to match Netlify (v0.145.0)
- [ ] Fix SEO meta descriptions on all pages

### Phase 2: Strategic Content (Next 2 Weeks)
- [ ] Make 5 decisions above
- [ ] Build pricing / engagement model page (per Decision 1)
- [ ] Fix ThreeDays.ai nav link (per Decision 2)
- [ ] Add 3-5 blog posts (repurpose internal case studies or LinkedIn content)
- [ ] Add GitHub repos to About page
- [ ] Expand "Why Nexrizen" content (6 AI systems detail, AI-native thesis)
- [ ] Add contact form note about hourly billing
- [ ] Populate FAQ or remove page

### Phase 3: Enhancement (Next Month)
- [ ] Add `/why-nexrizen/` or `/how-we-work/` dedicated page
- [ ] Record and embed a 60-second video on About page
- [ ] Create 2-3 Upwork-style "project catalog" offerings on the site
- [ ] Add EU timezone mention when Gabe relocates
- [ ] Self-host fonts (remove Google Fonts dependency)
- [ ] Resolve Netlify vs GitHub Pages dual deployment
- [ ] Verify OG images generating for all pages

---

*The website is Nexrizen's front door — every LinkedIn DM, Upwork proposal, and partner referral eventually lands here. The design and structure are solid, but the placeholder pages, missing analytics, stale blog, and absent pricing info are leaving value on the table. Phase 1 fixes are mostly config changes and deletions — high impact, low effort.*
