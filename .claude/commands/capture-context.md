---
description: Synthesize raw business context into organized, structured documentation
allowed-tools: Read, Write, Edit, Glob, Grep
---

# Capture Context

Distill raw business inputs (interviews, meeting notes, exports, existing docs) into organized, readable documentation with metadata and coverage tracking.

## Usage

- `/capture-context` - Interactive: asks which area to capture
- `/capture-context <department>` - Capture context for specific department (sales, delivery, etc.)
- `/capture-context <doc-type>` - Capture specific doc type (unit-economics, service-catalog, etc.)

## Arguments

$ARGUMENTS - Optional: department name or doc type

---

## Philosophy

**Organize, don't analyze.** Extract and structure what's there. Save interpretation and decision-making for other commands.

**Preserve voices.** Verbatim quotes from interviews and meetings are more valuable than paraphrasing.

**Track coverage honestly.** Dense interviews might only be 40% captured. Short notes might be 95% captured. Be honest.

**Metadata matters.** Track sources, versions, and coverage so the team knows when to trust synthesis vs. consult originals.

**Living documentation.** Unlike proposal-builder (one-time), this is continuous. Update frequency matters.

---

## Phase 1: Discover Context

### 1.1 Determine Capture Target

**If no arguments provided**, ask user:
```
What would you like to capture context for?

Options:
1. Department (sales, delivery, marketing, operations, finance)
2. Business-core doc (service-catalog, unit-economics, pricing-model, etc.)
3. Agency-intelligence doc (estimation-accuracy, current-capacity, client-health, etc.)
4. Strategic doc (quarterly-okrs, revenue-plan, risk-register, etc.)

Enter number or name:
```

**If argument provided**:
- Check if it matches a department name → Department capture mode
- Check if it matches a known doc type → Doc-specific capture mode
- If unclear → Ask for clarification

### 1.2 Identify Existing Context Sources

**For departments**:
Look in `departments/[name]/context/` for:
- Numbered files (`01_*.md`, `02_*.md`)
- Interview transcripts
- Notion exports (CSV, markdown)
- Google Drive files
- Meeting notes
- Existing documentation

**For business-core/agency-intelligence/strategy docs**:
Look in project root or specified locations for:
- Existing Notion pages (if exported)
- Spreadsheets (financial data, project lists, hours tracking)
- Meeting transcripts relevant to this topic
- Email threads or Slack exports
- Previous attempts at documenting this

**If no context sources found**:
- Ask user: "No context files found in [location]. Would you like to:
  - (a) Point me to existing files to read
  - (b) Provide context interactively (I'll ask questions)
  - (c) Create template for you to fill in"

### 1.3 Check for Existing Derived Docs

Before synthesizing, check if derived docs already exist:
- `departments/[name]/docs/Current_State.md`
- `business-core/[category]/[DocName].md`
- `agency-intelligence/[category]/[DocName].md`

**If found**:
1. Read existing doc and check version/date
2. Compare to context sources dates
3. Determine: **Create new** vs **Update existing** vs **Ask user**

---

## Phase 2: Read All Context Sources

Read every file in the relevant `context/` directory or identified sources.

### What to Extract

**From interviews/meetings**:
- Key points and decisions
- Verbatim quotes (especially pain points, goals, constraints)
- Numbers (costs, hours, metrics, targets)
- Processes described
- Tools/systems mentioned
- Pain points and challenges
- Contradictions or ambiguities

**From data exports (Notion, spreadsheets)**:
- Current state (projects, hours, clients, pipeline)
- Historical patterns (trends, averages, variance)
- Structure (how data is organized currently)
- What's tracked vs not tracked

**From existing docs**:
- What's already documented well
- What's outdated or incorrect
- Gaps in documentation
- Conflicting information

### Track as You Read

Build mental index:
- For each key fact → Note source file and location
- For each process → Note who described it and when
- For contradictions → Flag both sources
- For gaps → Note what's missing or unclear

---

## Phase 3: Determine Output Structure

### For Department Capture

**Default output structure**:
1. `DEPARTMENT.md` - Overview (owner, update frequency, current challenges)
2. `docs/Context_Map.md` - Catalog of all context sources with coverage and re-read guidance
3. `docs/Current_State.md` - How things work now (processes, tools, team structure)
4. `docs/KPIs.md` - Current metrics, targets, how measured
5. `docs/Dependencies.md` - What this dept needs from others, what others need from this dept

**Optional (create if content warrants)**:
6. `docs/Process_Flows.md` - Detailed workflow descriptions
7. `docs/Tools_Stack.md` - Systems used and integrations
8. `docs/SOPs/[Process]_SOP.md` - Step-by-step procedures (one file per major process)

**Guideline**: Create 2-5 docs per department. Favor readability over consolidation.

### For Business-Core Docs

**Output location**: `business-core/[category]/[DocName].md`

**Structure depends on doc type**:

**Service_Catalog.md**:
- List of services offered
- Standard scope per service
- Typical timeline and team size
- Starting price ranges
- What's included/excluded by default

**Unit_Economics.md**:
- Fully-loaded cost per team member
- Target margin by service type
- Break-even utilization rates
- Monthly burn rate
- Revenue per employee targets

**Pricing_Model.md**:
- How we price (hourly, fixed, retainer, value-based)
- Markup/margin targets
- When to use which model
- Payment terms and cash flow impact

### For Agency-Intelligence Docs

**Output location**: `agency-intelligence/[category]/[DocName].md`

**Structure depends on doc type**:

**Estimation_Accuracy.md**:
- Table: Past projects with estimated vs actual hours
- Variance analysis by project type/service
- Patterns: what causes overruns
- Lessons learned
- Current estimation confidence by service type

**Current_Capacity.md**:
- Table: Team members with current allocation %
- Available hours next 12 weeks
- Projects in flight with end dates
- Who's overloaded vs underutilized
- Hiring implications

**Client_Health_Scores.md**:
- Table: Clients with health score (1-10)
- Scoring criteria
- Why each score (evidence)
- At-risk clients with mitigation plans
- Renewal dates and likelihood

---

## Phase 4: Write or Update Documents

### Core Synthesis Principles

| Principle | Why | Example |
|-----------|-----|---------|
| **Verbatim quotes** | Evidence and authenticity | "We're bleeding 20 hours a week on manual data entry" - CEO |
| **Tables for structured data** | Scannable, comparable | Use for: team structure, KPIs, costs, tools, decision criteria |
| **Specific numbers** | Precision builds trust | "$120/hr", "75% utilization", "15 team members" NOT "competitive", "high", "medium team" |
| **Source attribution** | Traceability for updates | "(Source: `context/01_sales_interview.md` lines 45-67)" |
| **Honest coverage** | Know when to re-read | "~40% coverage - dense interview, re-read for implementation details" |
| **Contradictions flagged** | Don't guess, document | "⚠️ CONFLICT: Interview says $120/hr, spreadsheet shows $100/hr" |

### Metadata Header Template

**Every document must start with**:

```markdown
---
**Document:** [Filename]
**Version:** 1.0
**Last Updated:** [YYYY-MM-DD]
**Owner:** [Name or "TBD"]
**Update Frequency:** [Weekly/Monthly/Quarterly/As-needed]

**Synthesized From:**
- `context/[file1]` (coverage: ~XX%, [brief description])
- `context/[file2]` (coverage: ~XX%, [brief description])
- [External system]: [Data source]

**What Changed:**
- v1.0 ([Date]): Initial creation from [sources]

**Downstream Dependencies:**
- `[path/to/doc].md` - Uses this for [purpose]
- `[another-doc].md` - References [specific data]

**Completeness:** ✅ / ⚠️ Missing [what] / 🔴 Conflicts: [where]
---

# [Document Title]

[Content starts here...]
```

### Context_Map.md Structure

**Always create or update Context_Map.md** to catalog sources:

```markdown
# Context Map - [Department/Area Name]

**Last Updated:** [YYYY-MM-DD]
**Total Context Sources:** [N] files

---

## context/01_[filename]

| Attribute | Value |
|-----------|-------|
| **Type** | [Interview/Meeting/Export/Document] |
| **Date** | [YYYY-MM-DD or "Unknown"] |
| **Participants** | [Names and roles] |
| **Length** | [Lines/pages/duration] |

**Key Topics:**
- [Topic 1 with brief description]
- [Topic 2 with brief description]
- [Numbers/metrics mentioned]

**Used In:**
- `docs/Current_State.md` (primary source for [section])
- `docs/KPIs.md` (metrics data)

**Re-read Full Source When:**
- 🔴 **[Specific scenario]** - Synthesis is overview only, ~40% coverage
- Implementing [specific process] → Lines X-Y have detailed steps
- Resolving ambiguities about [topic] → Full context may clarify
- Need exact quotes for [purpose]

**Synthesis Coverage:** 📊 ~XX%
- ✅ [What was captured well]
- ⚠️ [What was summarized/condensed]
- 🔴 [What was omitted]

---

## context/02_[filename]

[Same structure for each source...]
```

### Coverage Assessment

Be honest about extraction completeness:

| Coverage | When to Use | Re-read Frequency |
|----------|-------------|-------------------|
| 📊 ~90-100% | Short notes, simple data, structured exports | Rarely - synthesis is sufficient |
| 📊 ~60-80% | Standard meetings, interviews with clear structure | Occasionally - for exact quotes or details |
| 📊 ~40-60% | Dense interviews, long discussions, complex processes | Often - during implementation or decision-making |
| 📊 ~20-40% | Very dense content, technical deep-dives, existing long SOPs | Constantly - synthesis is high-level overview only |

**Dense interviews, complex processes = lossy by design. That's OK - that's what Context_Map is for.**

---

## Phase 5: Handle Special Cases

### Case 1: No Context Sources Available

**Create interview template** for user to fill in:

```markdown
# [Department/Area] Context Interview Template

**Instructions**: Answer these questions to build initial context. Use bullet points, be specific with numbers, include examples.

## Current State
1. What does this department/area do? (Core responsibilities)
2. Who's on the team? (Names, roles, FTE/contractor)
3. What tools/systems do you use?
4. What's the typical workflow? (Step by step)
5. What works well right now?
6. What's broken or frustrating?

## Metrics & Performance
7. What metrics do you track? (List with current values)
8. What are the targets for each metric?
9. How do you measure these? (Tools, frequency)
10. Where are you vs target? (Ahead, behind, on track)

## Dependencies & Integration
11. What do you need from other departments to do your job?
12. What do other departments need from you?
13. Where do handoffs break down?
14. What information is hard to get?

## Processes & SOPs
15. What are your major processes? (List top 3-5)
16. Which are documented? (Where?)
17. Which are undocumented? (Tribal knowledge)
18. What happens when someone new joins?

## Future State
19. What would "working better" look like?
20. What should we start/stop/continue doing?
21. What's blocking improvements?

**After completing**: Save as `context/01_initial_interview.md` and run `/capture-context [area]`
```

### Case 2: Conflicting Information

**Flag clearly and explicitly**:

```markdown
## ⚠️ CONFLICT DETECTED

**Topic:** [What the conflict is about]

**Source A** (`context/01_file.md` line 67):
"[Exact quote or data point]"

**Source B** (`context/03_other.md` line 23):
"[Conflicting quote or data point]"

**Impact:** [Why this matters - which decisions depend on resolving this]

**Resolution Needed:** [What needs to happen to resolve]
- Option 1: Ask [person] to clarify
- Option 2: Check [system/data source]
- Option 3: Accept that [explanation of both being valid]

**Status:** ❓ Unresolved - Added to open questions
```

### Case 3: Updating Existing Docs

**Use Edit tool, don't rewrite**:

1. **Read existing doc** - Understand current structure and version
2. **Identify what's new** - What changed in context sources?
3. **Edit specific sections** - Use Edit tool to update sections that changed
4. **Update metadata**:
   - Increment version (1.0 → 1.1 for additions, 1.0 → 2.0 for major changes)
   - Update "Last Updated" date
   - Add new source to "Synthesized From"
   - Add entry to "What Changed"
5. **Update Context_Map** - Add new source entry

**Don't**: Regenerate entire document from scratch (loses manual edits, version history)

### Case 4: Data from External Systems

**For Notion/spreadsheet exports**:

Include in metadata:
```markdown
**Synthesized From:**
- Notion Projects Database (exported [YYYY-MM-DD], [N] projects)
- Notion Hours Tracking (exported [YYYY-MM-DD], [N] entries)
- Go High Level Pipeline (exported [YYYY-MM-DD], [N] opportunities)

**Data Freshness:**
- Last export: [YYYY-MM-DD]
- Next export recommended: [YYYY-MM-DD]
- Sync method: Manual export / MCP / API
```

Note in doc when data is stale:
```markdown
⚠️ **Data as of [Date]**: This represents snapshot from [date]. For real-time data, check [system name].
```

---

## Phase 6: Create Open Questions Section

**At end of synthesis, document unknowns**:

```markdown
## Open Questions

*Ambiguities and gaps found during context capture that need resolution*

### 1. [Topic]

**Question:** [Specific question that needs answering]

**Why it matters:** [Impact on operations, decisions, or documentation]

**How to resolve:** [Action needed - ask who, check where, research what]

**Priority:** 🔴 Critical / 🟡 High / 🔵 Medium / ⚪ Low

**Source of ambiguity:** [What made this unclear - conflict, missing info, vague language]

---

### 2. [Another question]

[Same structure...]
```

---

## Phase 7: Completion Summary

**Present clear summary of what was created/updated**:

```
✅ Context Capture Complete - [Department/Area Name]

**Created:**

1. ✅ **DEPARTMENT.md** ([N] lines)
   - Overview, owner, update frequency, current challenges

2. ✅ **docs/Context_Map.md** ([N] lines)
   - Catalog of [N] context sources
   - Coverage assessment and re-read guidance

3. ✅ **docs/Current_State.md** ([N] lines)
   - Team structure, tools, processes, current metrics
   - [N] key insights extracted

4. ✅ **docs/KPIs.md** ([N] lines)
   - [N] metrics tracked with current values and targets
   - Measurement methods documented

5. ✅ **docs/Dependencies.md** ([N] lines)
   - [N] dependencies on other departments
   - [N] handoffs this department provides

**Updated:**
- [Existing doc] (v[X.X] → v[X.Y]): [What changed]

**Sources Synthesized:**
- [N] total sources ([types])
- Average coverage: ~XX%
- [N] sources with <50% coverage (expect frequent re-reads)

**Completeness Status:**
- ✅ All [N] context sources synthesized
- ⚠️ [N] open questions identified (see [doc name] Open Questions section)
- 🔴 [N] conflicts detected (see [doc name] Conflicts section)

**Next Steps:**
1. Review documents for accuracy
2. Resolve [N] open questions by [action]
3. Assign owner for [department/area] (currently "TBD")
4. Set update frequency review date: [suggested date]
5. [If low coverage sources] Flag that context sources with ~XX% coverage will need frequent re-reads during [when]

**Statistics:**
- Total lines synthesized: [N]
- Verbatim quotes preserved: [N]
- Tables created: [N]
- Sources requiring frequent re-read: [N]
```

**This gives user**:
- Clear inventory of what was created
- Understanding of coverage and completeness
- Specific actions to take next
- Visibility into quality (quotes, tables, conflicts)

---

## Update Mode: Adding New Context

**When new context sources are added**:

### Step 1: Detect New Sources

Compare context directory contents with Context_Map entries:
```
NEW sources found:
- context/04_followup_interview.md (not in Context_Map)
- context/05_q1_metrics_export.csv (not in Context_Map)

EXISTING docs:
- Current_State.md (v1.0, last updated [date])
- KPIs.md (v1.0, last updated [date])
```

### Step 2: Determine Update Strategy

| New Content Type | Likely Action |
|------------------|---------------|
| New interview/meeting | Add section to Current_State, update Dependencies if new info |
| New metrics export | Update KPIs.md with latest data |
| New process documentation | Add to Process_Flows or create new SOP |
| Conflicting information | Flag conflict, ask user how to proceed |

### Step 3: Use Edit Tool

**Don't rewrite entire docs - use targeted edits**:

```markdown
// Example: Adding new metrics to KPIs.md

OLD_STRING (end of section):
| Metric | Target | Current | Trend |
|--------|--------|---------|-------|
| Win Rate | 40% | 35% | 📉 |

NEW_STRING:
| Metric | Target | Current | Trend | Last Updated |
|--------|--------|---------|-------|--------------|
| Win Rate | 40% | 35% | 📉 | 2026-01-01 |
| Lead Response Time | <2 hrs | 4 hrs | ⚠️ | 2026-01-11 |

(Added Lead Response Time from `context/05_q1_metrics_export.csv` 2026-01-11)
```

### Step 4: Update Metadata

**Increment version and track changes**:

```markdown
**Version:** 1.1  ← (was 1.0)
**Last Updated:** 2026-01-11  ← (was 2026-01-03)

**Synthesized From:**
- `context/01_sales_interview.md` (coverage: ~60%)
- `context/02_crm_export.csv` (coverage: ~90%)
- `context/04_followup_interview.md` (coverage: ~70%)  ← NEW
- `context/05_q1_metrics_export.csv` (coverage: ~95%)  ← NEW

**What Changed:**
- v1.0 (2026-01-03): Initial creation
- v1.1 (2026-01-11): Added Lead Response Time metric, updated team structure from followup interview  ← NEW
```

### Step 5: Update Context_Map

**Add entries for new sources** with full template (type, date, topics, coverage, re-read guidance)

### Step 6: Report Update Summary

```
✅ Context Update Complete - [Area Name]

**New Sources Processed:**
- context/04_followup_interview.md (~70% coverage)
- context/05_q1_metrics_export.csv (~95% coverage)

**Documents Updated:**
1. ✏️ **Current_State.md** (v1.0 → v1.1)
   - Added team structure update (Sarah promoted to lead)
   - +30 lines

2. ✏️ **KPIs.md** (v1.0 → v1.1)
   - Added Lead Response Time metric
   - Updated Q1 actual values
   - +15 lines

3. 🆕 **Context_Map.md**
   - Added 2 new source entries

**Open Questions:**
- Previous: [N] questions
- Resolved: [N] questions (from new context)
- New: [N] questions (from new context)
- Total remaining: [N] questions

**Next Review Due:** [Date based on update frequency]
```

---

## Quality Checklist

**Before completing, verify**:

**Content Quality:**
- [ ] Verbatim quotes preserved with attribution
- [ ] Specific numbers included (not vague "significant", "many")
- [ ] Tables used for structured data (team, KPIs, tools, costs)
- [ ] Source attribution clear (file and location)
- [ ] Coverage honestly assessed

**Metadata Complete:**
- [ ] Document headers present on all docs
- [ ] Version numbers assigned
- [ ] Owner specified (or "TBD" with note to assign)
- [ ] Update frequency specified
- [ ] Sources listed with coverage %
- [ ] Downstream dependencies identified
- [ ] Completeness flag accurate

**Context_Map Quality:**
- [ ] All sources cataloged
- [ ] Coverage assessment honest and specific
- [ ] Re-read guidance actionable and specific
- [ ] Key topics extracted for each source
- [ ] Used-in cross-references accurate

**Completeness:**
- [ ] All context sources read and synthesized
- [ ] Contradictions flagged clearly (not hidden or guessed)
- [ ] Gaps and unknowns documented in Open Questions
- [ ] No information invented or assumed beyond sources

---

## What NOT to Do

- ❌ Don't analyze, evaluate, or make recommendations (that's for other commands)
- ❌ Don't paraphrase when you can quote directly
- ❌ Don't claim 90% coverage if you selectively extracted key points from dense content
- ❌ Don't hide contradictions - flag them explicitly
- ❌ Don't add information not in context sources
- ❌ Don't modify files in `context/` directories (source of truth, read-only)
- ❌ Don't silently overwrite existing docs without checking dates/versions
- ❌ Don't skip metadata - it's critical for maintenance
- ❌ Don't create 20-page monster docs - split into readable pieces

---

## Examples

### Example 1: Department Capture (Sales)

**Input:**
```
/capture-context sales
```

**Context sources found:**
- `context/01_sales_team_interview.md` (600 lines, dense)
- `context/02_go_high_level_pipeline_export.csv` (200 lines)
- `context/03_current_sales_process_notes.md` (150 lines)

**Output created:**
1. `DEPARTMENT.md` - Overview, owner (VP Sales), update freq (monthly)
2. `docs/Context_Map.md` - 3 sources cataloged, coverage 60%/95%/80%
3. `docs/Current_State.md` - Team of 3, tools (GHL, LinkedIn, Notion), current metrics
4. `docs/KPIs.md` - 6 metrics tracked (pipeline value, win rate, lead response time, etc.)
5. `docs/Dependencies.md` - Needs from Marketing (qualified leads), provides to Delivery (closed deals)
6. `docs/Process_Flows.md` - Lead-to-close process, LinkedIn outreach workflow

**Coverage notes:**
- Interview: ~60% (dense, recommend re-read during process improvement)
- Export: ~95% (structured data, nearly complete)
- Notes: ~80% (concise, most extracted)

### Example 2: Business-Core Doc (Unit Economics)

**Input:**
```
/capture-context unit-economics
```

**Context sources found:**
- Financial spreadsheet (team costs)
- Notion hour tracking export (billable hours by project)
- Pricing document (current rates)

**Output created:**
1. `business-core/02_financial_model/Unit_Economics.md`
   - Fully-loaded cost per team member (15 people)
   - Target margin by service type (fixed: 45%, retainer: 35%)
   - Break-even utilization: 68%
   - Monthly burn rate: $87K
   - Revenue per employee targets

**Key insights extracted:**
- Senior devs: $90/hr loaded cost → charge $120/hr → 33% margin at 75% utilization
- Current average utilization: 72% (just above break-even)
- Top margin service: Custom development (48% actual)
- Lowest margin: Support retainers (22% actual - below target)

### Example 3: Update Mode

**Input:**
```
/capture-context sales
```

**Finds:**
- Existing docs from 2 weeks ago
- New source: `context/04_q1_review_meeting.md`

**Action:**
- Reads existing `Current_State.md`, `KPIs.md`
- Extracts Q1 actuals from new meeting notes
- Edits `KPIs.md` to update Q1 columns
- Edits `Current_State.md` to add new challenge mentioned (CRM limitations)
- Updates metadata (version 1.0 → 1.1)
- Updates Context_Map with new source entry

**Reports:**
"Updated 2 docs with Q1 review insights. 1 new challenge flagged. 2 open questions resolved, 1 new question added."

---

## Summary

**Context capture transforms scattered inputs into navigable business intelligence**:

1. **Discover** - Find context sources, check existing docs
2. **Read** - Extract key points, quotes, numbers, processes
3. **Structure** - Determine output docs (2-5 per department/area)
4. **Synthesize** - Write with metadata, track coverage, preserve quotes
5. **Catalog** - Create Context_Map with re-read guidance
6. **Flag** - Document contradictions, gaps, open questions
7. **Report** - Clear summary of outputs, completeness, next steps

**Remember**:
- This is lossy compression with pointers back to source
- Dense content = expect frequent re-reads (that's OK!)
- Update mode uses Edit, not rewrite
- Metadata enables maintenance and cross-referencing
- Living documentation - update frequency matters

---

**Next Steps After Capture**:

```
Once context is captured, you can:

1. Build decision frameworks using this context
   → /build-doc should-we-bid (uses ICP, capacity, margin data)

2. Generate SOPs from process flows
   → /build-sop [process-name] (uses Current_State, Process_Flows)

3. Analyze patterns and gaps
   → /find-gaps [department] (identifies process gaps, missing docs)

4. Track metrics over time
   → /update-context [department] (monthly/quarterly updates with new data)
```

---

**This command is the foundation. Everything else builds on captured context.**
