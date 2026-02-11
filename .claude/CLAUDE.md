# Business Builder System

Build comprehensive business intelligence and operating system for software agencies.

## Project Structure

```
/
├── business-core/          # Foundation layer (vision, financial model, delivery framework)
│   └── case-studies/       # Org-wide case studies library (synced from proposal-builder)
├── departments/            # Department-specific context and SOPs
├── agency-intelligence/    # Data-driven insights (historical, capacity, client portfolio)
├── strategy/               # Strategic planning (quarterly, annual, risks)
├── decision-frameworks/    # Structured decision support
├── rhythms/                # Operating cadence templates (daily, weekly, monthly, quarterly)
└── integrations/           # External system sync (Notion, Google Drive, Go High Level)
```

## Core Rules

1. **Never modify `context/` directories** - These are source of truth (like `references/` in proposal-builder)
2. **Always track metadata** - Every doc needs: version, last updated, sources, owner, completeness
3. **Coverage matters** - When synthesizing, track what % of source was captured
4. **Decision-first** - Every doc should answer a specific question
5. **Living documentation** - This is continuous, not one-time. Update frequency matters.
6. **Cross-reference awareness** - Flag dependencies between docs

## Document Standards

### Metadata Header (Required for all docs/)

```markdown
---
**Document:** [Filename]
**Version:** [X.Y]
**Last Updated:** [YYYY-MM-DD]
**Owner:** [Name/Team]
**Update Frequency:** [Weekly/Monthly/Quarterly/As-needed]

**Synthesized From:**
- `context/[file1]` (coverage: ~XX%)
- `context/[file2]` (coverage: ~XX%)

**What Changed:**
- v1.0 (YYYY-MM-DD): Initial creation
- v1.1 (YYYY-MM-DD): [Description of changes]

**Downstream Dependencies:**
- `[other-doc].md` - Uses this for [purpose]
- `[another-doc].md` - References [specific section]

**Completeness:** ✅ Complete / ⚠️ Missing [specific info] / 🔴 Conflicts detected
---

# [Document Title]

[Content starts here...]
```

### Coverage Assessment Rubric

When synthesizing from context sources:

| Coverage | % Extracted | Re-read Frequency |
|----------|-------------|-------------------|
| 📊 ~90-100% | Nearly complete | Rarely - synthesis sufficient |
| 📊 ~60-80% | Substantial | Occasionally - for details |
| 📊 ~40-60% | Selective | Often - during implementation |
| 📊 ~20-40% | Lossy by design | Constantly - synthesis is overview only |

**Dense interviews, long transcripts = lossy synthesis by design.**
**Short notes, simple data = can be fully synthesized.**

## Department Structure

Each department follows this pattern:

```
departments/[name]/
├── DEPARTMENT.md           # Overview: owner, update frequency, current state
├── context/                # Raw inputs (DO NOT MODIFY)
│   ├── 01_[source].md
│   ├── 02_[source].md
│   └── [exports/interviews/notes]
└── docs/
    ├── Context_Map.md              # Catalog of context sources
    ├── Current_State.md            # How things work now
    ├── Process_Flows.md            # Detailed workflows
    ├── SOPs/                       # Standard Operating Procedures
    │   ├── [Process_Name]_SOP.md
    │   └── ...
    ├── KPIs.md                     # Metrics, targets, current state
    ├── Tools_Stack.md              # Systems used
    └── Dependencies.md             # What this dept needs from others
```

## External System Integration

### Current Stack
- **Notion**: PM work, SOPs, hour tracking, CRM
- **Google Drive**: Client folders, meeting transcripts
- **Go High Level**: LinkedIn outreach CRM

### Integration Approach
- **Phase 1**: Manual exports/imports (CSV, Notion exports)
- **Phase 2**: MCP servers for real-time data
- **Phase 3**: Automated sync and alerts

### Data Flow
```
External Systems (Notion, Drive, GHL)
         ↓ (MCP/Exports)
business-builder (Context Layer)
         ↓ (Synthesis/Analysis)
Decision Outputs (Can we take this project? Who's at risk?)
```

## Key Document Types

### 1. Foundation Documents (business-core/)
**Purpose**: Establish how the business operates fundamentally

**Examples**:
- `Vision_Mission_Values.md` - Why we exist
- `Service_Catalog.md` - What we sell, standard scope
- `Unit_Economics.md` - Cost to deliver, target margins
- `ICP_Profile.md` - Ideal client profile

**Update frequency**: Quarterly or when strategy shifts

### 2. Intelligence Documents (agency-intelligence/)
**Purpose**: Data-driven insights from actual business operations

**Examples**:
- `Estimation_Accuracy.md` - Estimated vs actual hours
- `Current_Capacity.md` - Team availability next 12 weeks
- `Client_Health_Scores.md` - Health by client, risk factors
- `Delivery_Velocity.md` - Actual hours per deliverable type

**Update frequency**: Weekly to monthly (data-driven)

### 3. Strategic Documents (strategy/)
**Purpose**: Planning and execution tracking

**Examples**:
- `Q1_2026_OKRs.md` - Quarterly objectives and key results
- `2026_Revenue_Plan.md` - How we hit the number
- `Risk_Register.md` - Top risks and mitigation plans
- `Win_Loss_Analysis.md` - Why we win/lose deals

**Update frequency**: Set quarterly, review monthly

### 4. Decision Frameworks (decision-frameworks/)
**Purpose**: Structured decision support with clear criteria

**Examples**:
- `Should_We_Take_This_Project.md` - ICP fit, margin, capacity check
- `Should_We_Hire_Now.md` - Utilization, pipeline, cash runway check
- `Pricing_This_Deal.md` - Cost-plus calculation, value multiplier

**Update frequency**: Review quarterly, use continuously

### 5. Operating Rhythms (rhythms/)
**Purpose**: Templates for recurring meetings and reviews

**Examples**:
- `Weekly_Sales_Review.md` - Pipeline, forecasts, next week focus
- `Weekly_Delivery_Review.md` - Project health, risks, resource needs
- `Quarterly_OKR_Review.md` - Score last quarter, set next quarter

**Update frequency**: Templates updated as-needed, used on schedule

## Slash Commands Philosophy

Commands should:
1. **Solve real pain points** - "Can we take this project?" not "Generate generic doc"
2. **Use existing context** - Read from business-builder, don't ask for redundant input
3. **Provide reasoning** - Don't just say "Yes", explain WHY with sources
4. **Track coverage** - When synthesizing, note what % was captured
5. **Update metadata** - Auto-increment versions, track sources

## Synthesis Guidelines (from proposal-builder)

### Core Principles

| Principle | Why | Example |
|-----------|-----|---------|
| **Verbatim quotes** | Evidence matters | "We're losing 20hrs/week on manual data entry" - CEO |
| **Tables for structured data** | Easier to scan | Use for: KPIs, costs, team structure, decision matrices |
| **Specific numbers** | Precision builds trust | "$120/hr", "15 team members" - NOT "competitive rate", "medium team" |
| **Source attribution** | Traceability | "Per `context/01_sales_interview.md` line 47" |
| **Coverage honesty** | Know when to re-read | "~40% coverage - re-read for implementation details" |

### When Synthesizing Context

1. **Read everything first** - Understand all sources before writing
2. **Identify contradictions** - Flag conflicts, don't guess
3. **Extract key quotes** - Preserve exact language for important points
4. **Assess coverage** - Be honest about what % was captured
5. **Create Context_Map** - Catalog sources with re-read guidance
6. **Flag gaps** - Note what's missing or unclear

### Document Length Guidelines

| Document Type | Target Length | Action if Exceeded |
|---------------|---------------|-------------------|
| Current State | 300-600 lines | Ok up to 800; split if >1000 |
| Process Flows | 200-400 lines | Split by process if >600 |
| Context Map | 200-300 lines | Ok to go longer with many sources |
| SOPs | 100-300 lines each | Keep focused on single process |
| KPIs | 100-200 lines | Split by category if >300 |

## Cross-Reference Tracking

### When Creating/Updating Documents

**Always consider downstream impact**:
- If updating `Unit_Economics.md` → affects `Pricing_Model.md`, `Should_We_Take_This_Project.md`
- If updating `Current_Capacity.md` → affects `Should_We_Hire_Now.md`, `Pipeline_Requirements.md`
- If updating `Service_Catalog.md` → affects `Estimation_Standards.md`, `ICP_Profile.md`

**Flag in metadata**:
```markdown
**Downstream Dependencies:**
- `decision-frameworks/Should_We_Take_This_Project.md` - Uses margin targets from this doc
- `agency-intelligence/capacity_planning/Hiring_Forecast.md` - Uses utilization thresholds
```

### Tidy: One Command for All Maintenance

**The `/tidy` command is your all-in-one system maintenance tool.**

Every time you run `/tidy`, it automatically:
1. **Organizes uncommitted changes** into logical git commits
2. **Analyzes downstream dependencies** to identify which docs need updates
3. **Runs quick structural audit** to catch misplaced files and broken references
4. **Fixes organizational issues** with safe file moves and automatic reference updates

**This replaces needing to remember multiple commands** - just run `/tidy` after every work session.

**Priority levels for dependency updates:**
- 🔴 **Critical**: Foundation doc changed, decision frameworks must update
- ⚠️ **Should update**: KPIs changed, strategy docs should reflect new data
- 💡 **Consider**: Context added, synthesis might benefit from inclusion

**Why this matters:**
Without automated maintenance, the system drifts:
- Commits become messy and unclear
- Decision frameworks use stale data
- Files end up in wrong locations
- Cross-references break
- New context doesn't get synthesized

**Run `/tidy` after every work session** (5-10 minutes total).

## Structural Health & System Integrity

**Systems drift without maintenance.** Files end up in wrong places, references break, metadata falls out of date. This section explains how to prevent and fix organizational debt.

### Common Anti-Patterns

| Anti-Pattern | Example | Why It Happens | How to Fix |
|--------------|---------|----------------|------------|
| **Org-wide assets in dept folders** | `departments/marketing/docs/Case_Studies_Library.md` | Convenient filing when created | Move to `business-core/` or top-level |
| **Generic folders in specific contexts** | `partnerships/assets/case-studies/` | Starts dept-specific, becomes org-wide | Move to org-wide location when usage broadens |
| **Meeting notes scattered** | Meetings in marketing/, sales/, partnerships/ | No clear convention established | Centralize to top-level `meetings/` directory |
| **Foundation docs in wrong location** | ICP, value props, service catalog in dept folders | Unclear ownership at creation | Move to `business-core/` (foundational strategy) |
| **Duplicate content** | Same case study in 3 places | Copy-paste without consolidation | Single source of truth, link to it |
| **Broken references** | Links to moved/renamed files | Files moved without updating references | Use `/reorganize` for safe moves |
| **Stale metadata** | "Last Updated" is 6 months old | No update frequency tracking | Set "Update Frequency" in metadata, honor it |
| **Missing cross-references** | Decision framework uses data but doesn't link | Implicit dependencies not documented | Add to "Downstream Dependencies" metadata |

### Signals Your System Needs Audit

Run `/audit` when you notice:

- ❌ **Can't find documents you know exist** - Poor organization
- ❌ **Multiple versions of "same" content** - Duplication or fragmentation
- ❌ **Broken links when clicking references** - References out of sync
- ❌ **New team member confused by structure** - Poor conventions
- ❌ **Searching by name instead of browsing** - No clear hierarchy
- ❌ **Unsure which file is "correct"** - Version drift
- ❌ **Documents reference outdated values** - Downstream drift

### When to Use Deep Audit (Optional)

**`/tidy` handles 95% of maintenance automatically.**

You only need the standalone `/audit` command for:

**Monthly Deep Clean:**
```
/tidy --audit-only
    → Comprehensive 6-phase analysis
    → Dependency graph validation
    → Content consistency checks
    → ~5 minutes
```

**After Major Changes:**
- New department created → `/tidy --audit-only` to verify structure
- Onboarding new team member → `/tidy --audit-only` to ensure clarity
- Before quarterly review → `/tidy --audit-only` to verify system health

**Most of the time:** Just run `/tidy` after work sessions and you're good!

### File Placement Decision Tree

**When creating a new document, ask:**

```
Is this document used by multiple departments?
├─ YES → Consider org-wide location (business-core/, strategy/, decision-frameworks/)
│   └─ Is it foundational (vision, ICP, services, economics)?
│       ├─ YES → business-core/
│       └─ NO → Is it strategic planning (OKRs, revenue plans, risks)?
│           ├─ YES → strategy/
│           └─ NO → Is it a decision framework (should we X)?
│               ├─ YES → decision-frameworks/
│               └─ NO → Consider agency-intelligence/ or rhythms/
└─ NO → Is it department-specific process/knowledge?
    ├─ YES → departments/[name]/docs/
    │   └─ Is it raw input (transcript, export, notes)?
    │       ├─ YES → departments/[name]/context/
    │       └─ NO → Is it a synthesized doc or SOP?
    │           └─ YES → departments/[name]/docs/ or docs/SOPs/
    └─ NO → Might be org-wide after all, reconsider top branch
```

### Reference Update Best Practices

**When moving files manually** (not using `/reorganize`):

1. **Before moving:**
   ```bash
   # Find all references to the file
   grep -r "path/to/file.md" . --include="*.md"
   ```

2. **Move the file**
   ```bash
   git mv old/path/file.md new/path/file.md
   ```

3. **Update all references** (use Edit tool for each match)

4. **Update file's own metadata:**
   - Increment version (1.0 → 1.1)
   - Update "Last Updated"
   - Add to "What Changed" log

5. **Verify:**
   ```bash
   # Should find 0 results
   grep -r "old/path/file.md" . --include="*.md"
   ```

**Better:** Just use `/reorganize --move "old/path" "new/path"` to automate this.

### Metadata Hygiene Checklist

Run through this checklist for any document in `docs/`:

- [ ] **Document** field matches filename
- [ ] **Version** number present (start at 1.0)
- [ ] **Last Updated** is current (YYYY-MM-DD format)
- [ ] **Owner** assigned (person or team)
- [ ] **Update Frequency** specified (Weekly/Monthly/Quarterly/As-needed)
- [ ] **Synthesized From** listed (if applicable, with coverage %)
- [ ] **What Changed** has version history
- [ ] **Downstream Dependencies** documented (if other docs use this)
- [ ] **Completeness** flag appropriate (✅/⚠️/🔴)

### Health Score Targets

Track these metrics monthly via `/audit`:

| Metric | Target | What It Means |
|--------|--------|---------------|
| **Structural Organization** | >85/100 | Files in correct locations |
| **Cross-Reference Integrity** | >95/100 | No broken links |
| **Metadata Completeness** | >90/100 | All docs have required fields |
| **Freshness** | >80/100 | Docs updated within frequency target |
| **Convention Compliance** | >95/100 | Naming, structure follows standards |
| **Dependency Tracking** | >85/100 | Downstream deps documented & accurate |
| **Overall Health** | >85/100 | System is maintainable |

**If overall health drops below 75/100:** Schedule dedicated cleanup sprint.

### Primary Workflow: Just Use `/tidy`

```
Daily Workflow (Simple):

Work on docs → /tidy → Done!
                 ↓
    ┌────────────┴────────────┐
    │ 1. Commits organized    │
    │ 2. Dependencies checked │
    │ 3. Structure audited    │
    │ 4. Issues fixed         │
    └─────────────────────────┘

That's it! One command handles everything.
```

**Monthly deep audit (optional):**
```
Monthly Review:

/tidy --audit-only
    ↓
Deep structural analysis
    ↓
Fix any complex issues
    ↓
/tidy (commits the fixes)
```

### How `/tidy` Handles Reorganization

**Automatic detection and fixing:**

When you run `/tidy`, it automatically:
1. **Detects** misplaced files (quick structural audit)
2. **Proposes** moves with clear reasoning
3. **Asks approval** before making changes
4. **Executes** safe moves with reference updates
5. **Commits** reorganization automatically

**User approval flow:**
```
/tidy finds 3 misplaced files

Would you like to fix these issues now? [y/n]
  → You review the proposed moves
  → You approve or decline
  → If approved, /tidy handles everything
```

**No need for separate commands** - `/tidy` does it all!

### System Integrity Principles

1. **Single Source of Truth**: Each piece of information exists in ONE canonical location
2. **Explicit References**: If Doc A uses info from Doc B, Doc A links to Doc B
3. **Bidirectional Awareness**: If A links to B, B's metadata lists A as dependent
4. **Consistent Naming**: Follow conventions (Title_Case, numbered context files)
5. **Metadata Completeness**: Every doc has version, owner, update frequency
6. **Context Immutability**: Never modify `context/` directories (read-only source)
7. **Version History**: Track what changed and when in metadata
8. **Fresh Data**: Honor "Update Frequency" commitments

When these principles are violated, system integrity degrades. `/audit` detects violations, `/reorganize` fixes them.

## Learning Loop

**Critical difference from proposal-builder**: We track plan vs actual and learn.

### Always Track
1. **Estimates vs Actuals** - Every project: estimated hours vs logged hours
2. **Revenue Plan vs Revenue Actuals** - Monthly variance analysis
3. **Capacity Forecast vs Utilization** - Did we predict availability correctly?
4. **Client Health vs Churn** - Did health scores predict who left?
5. **Win/Loss Predictions vs Outcomes** - Are we learning why we win/lose?

### Postmortem Template

After every project, capture:
- What went well (replicate this)
- What went wrong (avoid this)
- Estimation accuracy (why variance?)
- Client satisfaction (NPS, would they return?)
- Technical learnings (reusable patterns, tech debt created)
- Process improvements (what should we change?)

### Pattern Extraction

Periodically analyze:
- Which project types consistently go over estimate? Why?
- What predicts client churn? (Scope creep? Team changes? Communication gaps?)
- What wins deals? (Pricing? Speed? Expertise? Relationship?)
- What technical patterns are we reusing? (Should we build a library?)

## Decision-Making Framework Structure

Every decision framework should include:

```markdown
# Should We [Decision]?

## Question
[Clear statement of decision to be made]

## Framework

### Criteria
1. **[Criterion 1]**: [Description]
   - ✅ Pass if: [Specific threshold]
   - ❌ Fail if: [Specific threshold]
   - ⚠️ Caution if: [Edge case]

2. **[Criterion 2]**: [Description]
   - [Specific scoring or threshold]

### Scoring
- All ✅: Strong yes
- 1-2 ⚠️: Proceed with caution
- Any ❌: Needs mitigation or pass

## Data Sources
- [Document or system that provides this data]
- [Another data source]

## Example Evaluation

**Opportunity**: [Example scenario]

**Analysis**:
- Criterion 1: ✅ Pass - [Reasoning with numbers]
- Criterion 2: ⚠️ Caution - [Reasoning with numbers]

**Recommendation**: [Yes/No/Conditional with clear reasoning]

## Historical Context
- Last 5 times we said yes to similar: [Outcomes]
- Last 3 times we said no: [What happened]
```

## Agency-Specific Defaults

Unless client requirements override:

- **Cloud Provider**: GCP (Cloud SQL, Cloud Storage, Cloud Run)
- **Hourly Rate**: $120/hour
- **Target Margin**: 40-50% on fixed-price, 30-40% on retainer
- **Utilization Target**: 75-85% billable
- **Estimation Contingency**: 20% for unknowns
- **Development Approach**: Agile, 2-week sprints
- **Quality Standards**: Code review required, automated tests

## Integration Metadata

When syncing from external systems, track:

```markdown
---
**Last Sync:** [YYYY-MM-DD HH:MM]
**Sync Source:** [Notion/Google Drive/Go High Level]
**Sync Method:** [Manual export/MCP/API]
**Records Synced:** [Count]
**Next Sync Due:** [YYYY-MM-DD]
**Sync Owner:** [Name]
---
```

## Commands to Build (Priority Order)

### Phase 1: Foundation (Week 3-4)
- `/capture-context` - Synthesize messy inputs into structured docs
- `/build-doc <type>` - Generate standard doc from template
- `/update-context` - Update existing doc with new information
- **`/tidy`** - **Complete system maintenance** (commits + dependencies + audit + reorganization)
- `/sync-case-studies` - Sync new projects from proposal-builder GitHub repo to case studies

**Advanced (optional):**
- `/audit` - Deep system health audit (monthly, comprehensive 6-phase analysis)
- `/reorganize` - Manual file reorganization (use when `/tidy` auto-detection isn't enough)

### Phase 2: Decision Support (Week 5-6)
- `/should-we-bid <opportunity>` - Evaluate against frameworks
- `/price-this <scope>` - Calculate recommended pricing
- `/margin-check <project>` - Actual vs target margin

### Phase 3: Intelligence (Week 7-10)
- `/capacity` - Current team availability
- `/client-health` - Health scores with reasoning
- `/estimate-accuracy` - Historical performance

### Phase 4: Strategic (Week 11-13)
- `/quarterly-review` - Score last quarter, plan next
- `/risk-check` - Top risks across categories
- `/weekly-snapshot` - Leadership summary

### Phase 5: Advanced (Week 14-20)
- `/ask <question>` - Query across all business context
- `/postmortem <project>` - Structured retrospective
- `/pattern-search <topic>` - Find similar past work

## Quality Checklist

Before marking any document complete:

**Content Quality**:
- [ ] Verbatim quotes preserved with attribution
- [ ] Specific numbers included (not vague descriptions)
- [ ] Tables used for structured data
- [ ] Source attribution clear
- [ ] Coverage honestly assessed

**Metadata Complete**:
- [ ] Version number present
- [ ] Last updated date accurate
- [ ] Owner assigned
- [ ] Update frequency specified
- [ ] Sources listed with coverage %
- [ ] Downstream dependencies identified
- [ ] Completeness flag appropriate

**Completeness**:
- [ ] All relevant context sources synthesized
- [ ] Contradictions flagged clearly
- [ ] Gaps and unknowns documented
- [ ] Cross-references validated
- [ ] Related docs updated if needed

## Conventions

### Naming
- **Departments**: lowercase with hyphens (`sales`, `delivery`, `marketing`)
- **Context files**: Numbered prefix (`01_`, `02_`, `03_`)
- **Documents**: Title_Case_With_Underscores (`Current_State.md`, `Process_Flows.md`)
- **SOPs**: Process_Name_SOP.md (`Lead_Qualification_SOP.md`)

### Versioning
- **Major version** (1.0 → 2.0): Significant restructure, major content change
- **Minor version** (1.0 → 1.1): New section added, existing content updated
- **Patch** (1.1 → 1.1.1): Typo fixes, small clarifications (optional)

### Status Indicators
- ✅ **Complete**: All sections filled, reviewed, current
- ⚠️ **In Progress**: Partial content, needs completion
- 🔴 **Blocked**: Waiting on data, client input, or resolution
- 📊 **Data-Driven**: Auto-updated from external systems
- 🕐 **Stale**: Past update frequency, needs refresh

## What NOT to Do

- ❌ Don't modify files in `context/` directories (source of truth)
- ❌ Don't create docs without metadata headers
- ❌ Don't claim 100% coverage when you selectively extracted
- ❌ Don't hide contradictions or gaps - flag them
- ❌ Don't create decision frameworks without clear criteria
- ❌ Don't synthesize without tracking sources
- ❌ Don't skip the learning loop (track actuals, extract patterns)
- ❌ Don't build analysis paralysis - focus on decision-enabling docs
- ❌ **Don't skip `/tidy` after work sessions** - it handles everything automatically
- ❌ Don't move files manually without updating references (use `/tidy` to fix)

## Success Metrics

Track these to measure system health:

**System Metrics**:
- Doc coverage: % of critical business areas documented
- Doc freshness: % of docs updated within frequency target
- Context completeness: Avg coverage % across synthesized docs
- Command usage: Uses per week
- Decision time: Time to make strategic decisions (before vs after)

**Business Metrics**:
- Estimation accuracy: ±% variance
- Capacity utilization: % billable
- Client retention: % annual retention
- Win rate: % on qualified opportunities
- Margin achievement: Actual vs target by service

## Current Phase: Phase 0 - Foundation

**Status**: Setting up repository structure and core system

**Next Steps**:
1. ✅ Create directory structure
2. ✅ Write CLAUDE.md (this file)
3. Create first slash command: `/capture-context`
4. Build Phase 1 priority docs: Service Catalog, Unit Economics, Estimation Accuracy, Current Capacity, Client Health

**Questions to Answer**:
- Which department to pilot first? (Recommend: Sales or Delivery)
- MCP vs exports for Phase 1? (Recommend: Exports for speed, MCP later)
- Update frequency for core docs? (Recommend: Weekly for intelligence, Monthly for strategy)

---

**Remember**: This is a living system. Update this file as we learn and evolve the approach.
