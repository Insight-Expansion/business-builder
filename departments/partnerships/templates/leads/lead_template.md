---
**Document Type:** Lead Tracking Template
**Version:** 2.0 (Scalable table-based format)
**Last Updated:** 2026-02-10
**Purpose:** Track partner-sourced leads in scalable format
---

# Lead Tracking Template

## Overview

Leads are tracked in the partner's `LEADS.md` file using a **hybrid approach**:
- **All leads:** Single row in pipeline table (scalable to 100+ leads)
- **High-priority leads:** Expandable detail sections (only for top 10-20)

## Quick Add: Table Row Format

**For most leads, adding a single row to the pipeline table is sufficient:**

| ID | Company | Industry | Contact | Relationship | Status | Intro Date | Est. Value | Commission | Next Action | Notes |
|----|---------|----------|---------|--------------|--------|------------|------------|------------|-------------|-------|
| ### | [Company Name] | [Industry] | [Name, Title] | ⭐⭐⭐⭐⭐ [Type] | 🟡 Ready | - | $[X]K-$[Y]K | $[Z]K-$[W]K | [Next step] | [Brief note] |

### Field Guide

**ID:** Sequential number for this partner (e.g., ROBERTAS-006, ROBERTAS-007)

**Company:** Company name (bolded if high-priority)

**Industry:** Primary vertical (Healthcare, FinTech, E-commerce, Aviation, etc.)

**Contact:** Name and title if known, or "TBD" if not yet provided

**Relationship:** Star rating + type
- ⭐⭐⭐⭐⭐ = Family, very close friend (highest trust)
- ⭐⭐⭐⭐ = Long-term colleague, close professional relationship
- ⭐⭐⭐ = Professional acquaintance, warm intro
- ⭐⭐ = Loose connection, friend-of-friend
- ⭐ = Cold or weak relationship

**Status:** Use emoji for quick scanning
- 🟡 Ready to Introduce
- 🔵 Introduction Sent
- 🟢 Discovery Scheduled
- 🟠 Prototype Delivered
- 🟣 Proposal Presented
- ✅ Contract Signed
- ❌ Declined/Lost

**Intro Date:** Date trilateral email was sent (blank until introduced)

**Est. Value:** Estimated deal size range (e.g., "$20K-$80K")

**Commission:** 15% of est. value range (e.g., "$3K-$12K")

**Next Action:** What needs to happen next (e.g., "Send capability sheet", "Schedule discovery call")

**Notes:** Brief context (1 sentence - e.g., "Largest EU clinic network", "Cousin is VP ICT")

---

## When to Create Detailed Section

**Create expandable "High-Priority Lead Details" section for leads that meet ANY of these criteria:**

✅ **High value:** Estimated deal size >$50K
✅ **Strategic importance:** New vertical, case study potential, referral channel opportunity
✅ **Complex sale:** Multiple stakeholders, unique positioning required, regulatory considerations
✅ **Sensitive relationship:** Family member, very close friend (extra care needed)
✅ **Learning opportunity:** First lead in new industry, experimental approach

**Keep in table only for:**
- ❌ Standard deals (<$50K)
- ❌ Clear use case, straightforward sale
- ❌ Low complexity

---

## Detail Section Template (High-Priority Leads Only)

When a lead meets the criteria above, add this section under "High-Priority Lead Details":

```markdown
### 🔥 [PARTNER-ID]: [Company Name] ([Industry])

**Why high-priority:**
- [Reason 1 - e.g., "Largest company in vertical", "Family relationship", "Referral channel potential"]
- [Reason 2]
- [Reason 3]

**Company Profile:**
- **Website:** [URL]
- **Size:** [Company size/scale]
- **Geography:** [Markets served]
- **Contact:** [Name, Title, Background]
- **Special context:** [Unique details - e.g., "200-person internal tech team", "Conservative about AI"]

**Opportunity:**
- **Primary use cases:** [3-5 specific applications]
- **Entry point:** [3-Day MVP / Custom / Fractional CTO] ($X-$Y)
- **Expansion potential:** $[Z]-$[W]+ ([What follow-on looks like])
- **Relevant case studies:** [List 2-4 Nexrizen case studies that apply]

**Strategic positioning:**
- [How to position given company context - e.g., "Complement internal team, not replace"]
- [Key messaging points - e.g., "Emphasize GDPR compliance for healthcare"]

**Risk mitigation:**
- [Risk 1] → [How to address]
- [Risk 2] → [How to address]
- [Risk 3] → [How to address]

**Discovery agenda:**
- [Question 1 to ask]
- [Question 2 to ask]
- [Question 3 to ask]
- [What to assess - budget, timeline, decision process]

**Attribution:** [Date identified] → 24-month window expires [Date + 24 months]
```

---

## Example: Complete Lead Entry

**Table row (all leads):**

| ID | Company | Industry | Contact | Relationship | Status | Intro Date | Est. Value | Commission | Next Action | Notes |
|----|---------|----------|---------|--------------|--------|------------|------------|------------|-------------|-------|
| 006 | **MedTech Global** | Healthcare | Dr. Sarah Chen, CTO | ⭐⭐⭐⭐ 8-yr colleague | 🟡 Ready | - | $60K-$200K | $9K-$30K | Send healthcare capability sheet | Fortune 500, AI-powered diagnostics |

**Detail section (if high-priority - this one qualifies due to >$50K value):**

```markdown
### 🔥 ROBERTAS-006: MedTech Global (Healthcare)

**Why high-priority:**
- Fortune 500 company (large deal potential)
- AI-powered diagnostics aligns perfectly with Johns Hopkins case study
- 8-year professional relationship (strong foundation)
- Healthcare vertical strategic expansion

**Company Profile:**
- **Website:** medtechglobal.com
- **Size:** Fortune 500, global operations
- **Geography:** US + EU + Asia
- **Contact:** Dr. Sarah Chen, CTO - PhD in biomedical engineering, worked together at previous company

**Opportunity:**
- **Primary use cases:** AI diagnostics integration, medical data processing, clinical workflow automation
- **Entry point:** Custom ($20K-$40K) - diagnostic AI proof of concept
- **Expansion potential:** $100K-$200K+ (multi-country rollout, ongoing R&D partnership)
- **Relevant case studies:** Johns Hopkins Vision AI, Genomic Processing, Real-Time Voice AI for Medical

**Strategic positioning:**
- Lead with Johns Hopkins partnership (research credibility)
- Emphasize regulatory compliance expertise (FDA, GDPR)
- Position as R&D partner, not vendor

**Risk mitigation:**
- Fortune 500 = slow procurement → Start with pilot project to prove value
- Regulatory environment → Engage early on compliance requirements
- Multiple stakeholders → Use CTO relationship to navigate

**Discovery agenda:**
- Current AI initiatives and challenges
- Regulatory requirements for diagnostic AI
- Timeline and budget for pilot vs. full deployment
- Who else needs to be involved in decision

**Attribution:** 2026-02-15 (identified) → Window expires 2028-02-15
```

---

## Workflow: Adding a New Lead

### Step 1: Partner shares lead

Receive via email, meeting, or conversation

### Step 2: Add to pipeline table

Add row to partner's `LEADS.md` under "Active Pipeline" section:
- Assign next sequential ID
- Fill in all table columns
- Default status: 🟡 Ready to Introduce

### Step 3: Decide if high-priority

Does it meet criteria for detailed section?
- **Yes:** Create detail section under "High-Priority Lead Details"
- **No:** Table row is sufficient

### Step 4: Take next action

Based on "Next Action" column:
- Send capability sheet
- Schedule intro call with partner
- Research company
- etc.

---

## Workflow: Updating Lead Status

As lead progresses, update the table row:

1. **Introduction sent** 🔵
   - Update status emoji
   - Add intro date
   - Confirm attribution

2. **Discovery scheduled** 🟢
   - Update status
   - Add discovery date in notes

3. **Prototype delivered** 🟠
   - Update status
   - Note what was built

4. **Proposal presented** 🟣
   - Update status
   - Update est. value if needed

5. **Contract signed** ✅
   - Update status
   - Move row to "Closed Deals" table
   - Record actual value & commission

6. **Declined/lost** ❌
   - Update status
   - Move row to "Declined/Lost" table
   - Record reason for learning

---

## Document Maintenance

**Update frequency:**
- Add new leads: As partner shares them
- Update status: Within 24 hours of status change
- Review pipeline: Weekly (during partner check-ins)

**Archive approach:**
- Keep "Active Pipeline" table lean (only active opportunities)
- Move closed deals to "Closed Deals" table
- Move declined/lost to "Declined/Lost" table
- After 6 months, consider archiving old declined leads to separate file if table gets too long

**Search & reporting:**
- Use grep to search across all leads: `grep "Healthcare" LEADS.md`
- Export table to CSV for analysis (copy/paste into spreadsheet)
- Track metrics: Total leads, conversion rate, average deal size, commission earned

---

## Benefits of This Approach

✅ **Scalable:** Table grows linearly, not exponentially (1 row per lead vs. 1 file per lead)
✅ **Scannable:** See entire pipeline at a glance
✅ **Flexible:** Add detail where needed, keep simple where not
✅ **Searchable:** Grep across all leads in one file
✅ **Version controlled:** All in repo, changes tracked
✅ **Easy updates:** Change one table cell vs. edit entire file
✅ **Low overhead:** Quick to add new leads (30 seconds vs. 5 minutes)

---

## When Volume Gets Very High (100+ leads)

**Consider additional tooling:**

**Option 1: Notion or Airtable database** (recommended)
- Better filtering, sorting, views
- Easier status updates
- Can link to contacts, tasks
- Export to CSV periodically and save to repo as backup

**Option 2: Separate LEADS.md files by status**
- `leads-active.md` (currently being worked)
- `leads-backlog.md` (not yet ready to introduce)
- `leads-closed.md` (won deals)
- `leads-declined.md` (lost opportunities)

**Option 3: Quarterly archives**
- `LEADS_2026_Q1.md`
- `LEADS_2026_Q2.md`
- Keep current quarter active, archive older

**Current recommendation:** Stick with single `LEADS.md` until 50+ leads, then evaluate

---

**Template version:** 2.0
**Last updated:** 2026-02-10
**Template owner:** Wei Zhuo / Partnerships
