---
**Document:** Context_Map.md
**Version:** 1.0
**Last Updated:** 2026-02-10
**Owner:** Wei Zhuo
**Update Frequency:** As-needed (when new context sources are added)

**Synthesized From:**
- `context/01_eu-partnership-proposal.md` (coverage: ~90%)
- `context/02_customgpt-intro-email-generator.md` (coverage: ~85%)
- `context/03_eu-collateral-plan.md` (coverage: ~90%)
- `context/04_nexrizen-reseller-agreement.md` (coverage: ~95%)

**What Changed:**
- v1.0 (2026-02-10): Initial creation

**Downstream Dependencies:**
- `Current_State.md` - Uses this to understand what sources exist
- `Process_Flows.md` - References specific sections of context files

**Completeness:** ✅ Complete - All current partnership context sources cataloged
---

# Partnerships Department - Context Map

## Purpose

This document catalogs all context sources in the `partnerships/context/` directory, provides guidance on when to re-read each source, and tracks coverage percentages for downstream synthesized documents.

## Context Sources Catalog

### 01_eu-partnership-proposal.md

**Type:** Partnership proposal document
**Date:** February 2026
**Source:** Pre-meeting briefing document for Robertas V.P. / BIG GROUP
**Author:** Wei Zhuo

**Content Summary:**
- Complete partnership model overview (reseller/authorized representative)
- Commission structure (15% of collected revenue, 24-month attribution)
- Service catalog with pricing (3-Day MVP, Custom AI, Fractional CTO)
- 17+ case studies across verticals (fintech, healthcare, legal, etc.)
- Territory definition (EU/EEA countries + Switzerland)
- Getting started steps and timeline

**Key Data Points:**
- Commission rate: 15%
- Attribution period: 24 months
- 3-Day MVP pricing: $3K-$5K
- Custom software: $10K-$50K+
- Fractional CTO: $5K-$15K/month
- 50+ production apps shipped
- Team: 2 founders (Meta, IBM, Georgia Tech) + 2 PhDs + 3 engineers

**When to Re-Read:**
- 📊 ~90% coverage - Rarely needed after synthesis
- Re-read when: Updating pricing, revising case studies, changing commission structure
- Specific sections to reference: Case studies (lines 229-281), commission structure (lines 123-156)

**Used By:**
- `Current_State.md` - Partnership model, commission structure
- `Process_Flows.md` - Introduction and attribution flow
- Future: `Pricing_Model.md`, `Case_Study_Library.md`

---

### 02_customgpt-intro-email-generator.md

**Type:** Email generation instructions (CustomGPT configuration)
**Date:** February 2026
**Source:** Internal tool instructions for Robertas
**Author:** Unknown (Nexrizen team)

**Content Summary:**
- Email template generator instructions for warm introductions
- Robertas's background and positioning (58yo AI engineer, Luxembourg/Monaco, 30+ years finance/banking)
- Nexrizen messaging framework (prototype-first sales, AI-native operations)
- 5 example emails by industry (healthcare, insurance, e-commerce, aviation, private equity)
- Tone and style guidelines (European business style, 150-250 words)
- Email structure: personal greeting → context → 2-3 sentences on Nexrizen → relevance → soft CTA

**Key Messaging Points:**
- Tagline: "We don't sell AI. We make it work for your business."
- Unique differentiator: Working prototype after first discovery call (NOT slide deck)
- AI-native: Own business runs on proprietary AI systems
- Team credibility: ex-Meta, ex-IBM, Georgia Tech
- Proof points: 100x speed, 1,300 hours saved, 10x cost reduction

**When to Re-Read:**
- 📊 ~85% coverage - Re-read when writing new emails
- Re-read when: Crafting introduction emails, updating messaging, adapting for new verticals
- Specific sections to reference: Example emails (lines 96-271), messaging guidelines (lines 55-80)

**Used By:**
- Future: `Outreach_SOP.md`, `Messaging_Framework.md`
- Reference for any partner-facing communication

---

### 03_eu-collateral-plan.md

**Type:** Marketing collateral production plan
**Date:** February 2026
**Source:** Internal planning document
**Author:** Unknown (Nexrizen team)

**Content Summary:**
- Marketing materials roadmap for EU resellers
- Priority 1 (Week 1-2): One-pager, case study collection, capability sheets by vertical
- Priority 2 (Week 3-4): Presentation deck, email templates, FAQ document
- Priority 3 (As needed): Co-branded materials, video content, localized versions
- Production timeline with owner assignments
- Budget estimate: $1,200-2,200 for design work
- File organization structure
- Success metrics (usage, feedback, conversion, requests)

**Key Deliverables:**
1. **One-Pager** - A4 PDF, EU executive overview
2. **Case Study Collection** - 8-12 page booklet, 7 selected cases
3. **Capability Sheets** - 5 industry-specific one-pagers (fintech, healthcare, professional services, aviation, private equity)
4. **Presentation Deck** - 10-15 slides for group presentations
5. **Email Templates** - 5 versions by industry
6. **FAQ Document** - 2-3 pages covering common questions

**When to Re-Read:**
- 📊 ~90% coverage - Re-read when producing collateral
- Re-read when: Creating marketing materials, updating collateral roadmap, prioritizing deliverables
- Specific sections to reference: Capability sheets structure (lines 80-110), production plan (lines 197-226)

**Used By:**
- Future: `Marketing_Collateral_Status.md`, `Brand_Guidelines.md`
- Reference when creating partner enablement materials

---

### 04_nexrizen-reseller-agreement.md

**Type:** Legal contract template
**Date:** 2026 (template)
**Source:** Authorized Reseller Agreement draft
**Author:** Nexrizen legal/Wei Zhuo

**Content Summary:**
- Complete reseller agreement template
- Definitions: Qualified Introduction, Referred Client, Collected Revenue, Territory, Services
- Appointment and scope (non-exclusive, limitations, authority)
- Commission and payment terms (15%, 24-month attribution, 30-day payment, USD/EUR)
- Client attribution protocols
- Reseller obligations (professional conduct, compliance, GDPR)
- Nexrizen obligations (service delivery, sales support, marketing materials)
- Confidentiality (3-year duration post-termination)
- Intellectual property (license to use Nexrizen materials)
- Term and termination (12-month initial, auto-renewal, 60-day termination notice)
- Independent contractor relationship
- Limitation of liability
- Governing law (Delaware, arbitration via AAA)

**Key Legal Terms:**
- **Commission:** 15% of collected revenue (not contract value)
- **Territory:** EU/EEA + Switzerland + UK
- **Attribution period:** 24 months from introduction
- **Payment timing:** 30 days after Nexrizen receives payment
- **Confidentiality:** 3 years post-termination
- **Initial term:** 12 months, auto-renewing
- **Termination notice:** 60 days for convenience, 30 days cure for cause

**When to Re-Read:**
- 📊 ~95% coverage - Complete legal document, selectively re-read
- Re-read when: Finalizing agreements, resolving disputes, updating terms, onboarding new resellers
- Specific sections to reference: Commission structure (§3), attribution (§4), termination (§9)

**Used By:**
- Actual partnership agreements (when signed)
- Future: `Partnership_Terms_Summary.md`, `Commission_Tracking.md`

---

## Coverage Assessment Summary

| Context File | Type | Density | Coverage | Re-read Frequency |
|--------------|------|---------|----------|-------------------|
| 01_eu-partnership-proposal.md | Structured proposal | Medium | ~90% | Rarely - synthesis sufficient |
| 02_customgpt-intro-email-generator.md | Instructional | Medium | ~85% | Often - when writing emails |
| 03_eu-collateral-plan.md | Project plan | Medium | ~90% | Occasionally - for deliverable details |
| 04_nexrizen-reseller-agreement.md | Legal document | High | ~95% | Rarely - complete extraction |

## Quick Reference Guide

**Need to...**
- Explain the partnership model → `01_eu-partnership-proposal.md` (lines 63-122)
- Calculate commission → `01_eu-partnership-proposal.md` (lines 123-156) or `04_nexrizen-reseller-agreement.md` (§3)
- Write an introduction email → `02_customgpt-intro-email-generator.md` (lines 96-271)
- Find case studies → `01_eu-partnership-proposal.md` (lines 229-281)
- Check legal terms → `04_nexrizen-reseller-agreement.md` (entire document)
- Plan collateral production → `03_eu-collateral-plan.md` (lines 19-111, 197-226)
- Understand attribution rules → `04_nexrizen-reseller-agreement.md` (§4, lines 103-117)

## Gaps and Missing Context

**Known gaps:**
- ⚠️ No historical data on actual partnership performance (no deals closed yet - pilot phase)
- ⚠️ No signed agreement yet (template only)
- ⚠️ No collateral produced yet (plan only)
- ⚠️ No competitor analysis for EU reseller models
- ⚠️ No pricing benchmarks for EU market

**Questions to answer:**
1. What are typical reseller commission rates in EU B2B software?
2. How do competitors structure their channel partnerships?
3. What legal/tax considerations exist for US-EU reseller arrangements?
4. What GDPR implications exist for client data sharing?
5. What payment methods work best for EU resellers (wire transfer, PayPal, Wise)?

**Next context sources to add:**
- Meeting notes from Friday call with Robertas (after it happens)
- Signed reseller agreement (after finalization)
- First introduction outcomes (after pilot leads)
- Collateral feedback (after materials are shared)
- Competitive intelligence on other agencies' EU channel programs

---

## Metadata Tracking

**Context files:** 4
**Total line count:** ~1,100 lines
**Last updated:** 2026-02-10
**Next review:** After first partnership deal closes or 2026-Q2, whichever comes first

**Synthesis status:**
- ✅ Context_Map.md - Complete
- 🕐 Current_State.md - In progress
- 🕐 Process_Flows.md - Pending
- 🕐 DEPARTMENT.md - Pending
