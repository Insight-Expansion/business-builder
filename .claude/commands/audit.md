---
description: Comprehensive system health check - find misplaced files, broken references, metadata issues, and structural problems
allowed-tools: Task
---

# Audit

Perform comprehensive system health analysis to identify:
- Misplaced files (department-specific folders containing org-wide assets)
- Broken cross-references and outdated links
- Metadata completeness and staleness
- Naming convention violations
- Duplicate or fragmented content
- Downstream dependency drift

## Usage

- `/audit` - Full system audit
- `/audit --quick` - Quick scan (structural issues only)
- `/audit --path <directory>` - Audit specific directory

## Arguments

$ARGUMENTS - Optional: `--quick` or `--path <directory>`

---

## Philosophy

**Systems drift without maintenance.** Files get created in convenient locations instead of correct ones. References break. Metadata falls out of date. Dependencies drift.

This command acts as **architectural hygiene** - systematically identifying organizational debt before it compounds.

---

## Execution Strategy

Launch a general-purpose agent to analyze the entire repository structure and return a comprehensive health report.

### Agent Prompt Template

```
You are auditing the business-builder system to identify organizational and structural issues.

SYSTEM CONTEXT:
This is a living documentation system for a software agency with:
- business-core/ - Foundation documents (vision, services, unit economics, ICP)
- departments/ - Department-specific context and SOPs
- agency-intelligence/ - Data-driven insights (capacity, client health, estimation accuracy)
- strategy/ - Strategic planning (OKRs, revenue plans, risks)
- decision-frameworks/ - Decision support tools
- rhythms/ - Operating cadence templates
- integrations/ - External system sync

CORE RULES:
1. context/ directories are read-only (source of truth)
2. All docs/ need metadata headers (version, owner, update frequency, sources, dependencies)
3. Cross-references must be tracked
4. Department-specific folders should NOT contain org-wide assets

YOUR TASK:
Perform a comprehensive audit across 6 dimensions. Use Read, Glob, and Grep tools extensively.

---

## PHASE 1: STRUCTURAL ANALYSIS

**Goal:** Find files in the wrong place

### 1.1 Identify Misplaced Org-Wide Assets

Scan all department folders for content that should be org-wide:

**Signals a file is misplaced:**
- Generic name in specific folder (e.g., "case-studies" in partnerships/)
- Referenced by multiple departments (grep for cross-references)
- Metadata shows org-wide owner, not department-specific
- Content mentions multiple departments or company-wide scope

**Check these specifically:**
```bash
# Find case study files
glob: **/*case*study*.md
grep -i "case.studies" across all .md files

# Find ICP/strategy files in department folders
glob: departments/**/*ICP*.md
glob: departments/**/*value*prop*.md
glob: departments/**/*target*.md

# Find meeting notes in wrong places
find departments/*/docs/*meeting*

# Find templates/frameworks that might be org-wide
find departments/*/templates/
find departments/*/frameworks/
find departments/*/assets/
```

**For each misplaced file, report:**
- Current location
- Recommended location
- Reason (referenced by X departments, owner is org-wide, etc.)
- Number of references that would need updating

### 1.2 Identify Naming Convention Violations

**Per CLAUDE.md conventions:**
- Departments: lowercase-with-hyphens
- Context files: Numbered prefix (01_, 02_)
- Documents: Title_Case_With_Underscores
- SOPs: Process_Name_SOP.md

**Find violations:**
```bash
# Check department names
glob: departments/*/ (should all be lowercase-with-hyphens)

# Check context files
glob: **/context/*.md (should have numeric prefixes)

# Check document names in docs/
glob: **/docs/*.md (should be Title_Case)
```

### 1.3 Detect Duplicate or Fragmented Content

**Signals:**
- Multiple files with similar names (Case_Studies_Library.md in 2 places)
- Files with overlapping content (check via titles, headings)
- Same topic covered in multiple departments

**Check:**
```bash
# Find potential duplicates
glob: **/*case*study*.md
glob: **/*ICP*.md
glob: **/*pricing*.md
glob: **/*service*.md

# For each set of similar files, read them and assess:
# - Is this the same content?
# - Is this intentional (summary vs detail)?
# - Should these be consolidated?
```

---

## PHASE 2: CROSS-REFERENCE VALIDATION

**Goal:** Find broken links and outdated references

### 2.1 Extract All File References

Search for markdown link patterns and file path references:

```bash
# Find all markdown links
grep: \[.*\]\(.*\.md\) across all .md files

# Find all inline file references
grep: `[a-zA-Z_/-]+\.md` across all .md files

# Find references to directories
grep: departments/|business-core/|strategy/ across all .md files
```

### 2.2 Validate Each Reference

For each reference found:
1. Extract the target file path
2. Check if the file exists at that path
3. If broken, check if file was moved (search for filename elsewhere)
4. Report broken references with suggested fixes

### 2.3 Check Downstream Dependencies

For each document with **"Downstream Dependencies:"** metadata:
1. Read the listed downstream docs
2. Grep those docs to confirm they actually reference the source doc
3. Flag if metadata claims dependency but grep finds no reference
4. Flag if grep finds references NOT listed in metadata

---

## PHASE 3: METADATA COMPLETENESS

**Goal:** Ensure all documents have required metadata

### 3.1 Required Metadata Fields

Per CLAUDE.md, all docs/ files need:
```markdown
---
**Document:** [Filename]
**Version:** [X.Y]
**Last Updated:** [YYYY-MM-DD]
**Owner:** [Name/Team]
**Update Frequency:** [Weekly/Monthly/Quarterly/As-needed]
**Synthesized From:** (if applicable)
**What Changed:** (version history)
**Downstream Dependencies:** (if applicable)
**Completeness:** ✅/⚠️/🔴
---
```

### 3.2 Audit Metadata

```bash
# Find all docs
glob: **/docs/**/*.md
glob: business-core/**/*.md
glob: strategy/**/*.md
glob: decision-frameworks/**/*.md

# For each doc, check:
# - Does it have metadata header?
# - Are all required fields present?
# - Is the format correct?
# - Is "Last Updated" within its "Update Frequency"?
```

**Report:**
- Missing metadata entirely
- Missing specific fields
- Stale docs (past update frequency)

---

## PHASE 4: DOWNSTREAM DEPENDENCY DRIFT

**Goal:** Identify when upstream changes haven't propagated

### 4.1 Build Dependency Graph

1. Parse all metadata "Downstream Dependencies" sections
2. Build directed graph: Doc A → affects → [Doc B, Doc C]
3. Identify dependency chains: A → B → C

### 4.2 Check Version Consistency

For each dependency relationship:
- If Doc A was updated after Doc B, but Doc B depends on Doc A
- Flag Doc B as potentially stale (upstream changed, downstream didn't update)

### 4.3 Check Content Consistency

For critical dependencies:
- If `Unit_Economics.md` says "$120/hr"
- But `Pricing_Framework.md` says "$100/hr"
- Flag inconsistency

Use grep to find specific values referenced across docs.

---

## PHASE 5: CONVENTION COMPLIANCE

**Goal:** Ensure repo follows CLAUDE.md standards

### 5.1 Directory Structure Validation

Check expected directories exist:
```
business-core/
departments/
  [name]/
    context/
    docs/
      SOPs/
agency-intelligence/
strategy/
decision-frameworks/
rhythms/
integrations/
```

### 5.2 Template Compliance

For departments:
- Each should have DEPARTMENT.md
- Each should have context/ and docs/ folders
- docs/ should have Context_Map.md (optional but recommended)

### 5.3 Context Directory Protection

**Critical rule:** context/ directories should NEVER be modified (read-only source of truth)

Check git history (if accessible) or at least flag if context/ files lack metadata indicating they're raw source.

---

## PHASE 6: QUALITY INDICATORS

**Goal:** Assess overall system health

### 6.1 Coverage Metrics

Calculate:
- **Doc coverage:** % of expected doc types present
  - Example: Do we have Unit_Economics.md, Service_Catalog.md, ICP_Profile.md?
- **Metadata completeness:** % of docs with complete metadata
- **Freshness:** % of docs updated within their frequency target
- **Cross-reference health:** % of references that are valid

### 6.2 Identify Gaps

**Missing critical documents:**
Check for CLAUDE.md recommended docs:
- business-core/: Vision_Mission_Values.md, Service_Catalog.md, Unit_Economics.md, ICP_Profile.md
- decision-frameworks/: Should_We_Take_This_Project.md, Should_We_Hire_Now.md, Pricing_This_Deal.md
- strategy/: Q1_2026_OKRs.md, Risk_Register.md

Flag which are missing.

---

## OUTPUT FORMAT

Return a comprehensive report in this format:

```markdown
# Business Builder System Audit Report
**Audit Date:** [YYYY-MM-DD]
**Audited By:** General-Purpose Agent
**Scope:** [Full system / Quick scan / Specific path]

---

## Executive Summary

**Overall Health:** 🟢 Healthy / 🟡 Needs Attention / 🔴 Critical Issues

**Key Metrics:**
- Docs with complete metadata: X/Y (Z%)
- Docs up-to-date: X/Y (Z%)
- Valid cross-references: X/Y (Z%)
- Misplaced files detected: X
- Broken references: X
- Naming violations: X

**Top 3 Priorities:**
1. [Most critical issue]
2. [Second priority]
3. [Third priority]

---

## 🔴 CRITICAL ISSUES (Fix Immediately)

### Broken Cross-References
- **File:** `path/to/doc.md` line 42
  - **References:** `old/path/missing.md`
  - **Status:** File not found
  - **Suggested fix:** Update to `new/path/found.md` or remove reference

### Missing Critical Documents
- **`business-core/Unit_Economics.md`**
  - **Why critical:** Required for pricing decisions
  - **Referenced by:** 5 other docs
  - **Action:** Create this document

### Inconsistent Data
- **Inconsistency:** Hourly rate mismatch
  - **`business-core/Unit_Economics.md`** says $120/hr
  - **`decision-frameworks/Pricing_Framework.md`** says $100/hr
  - **Action:** Resolve conflict, update downstream docs

---

## ⚠️ IMPORTANT ISSUES (Address Soon)

### Misplaced Files

#### Case Studies Fragmented
- **Current:** `departments/marketing/docs/Case_Studies_Library.md`
- **Should be:** `business-core/case-studies/Case_Studies_Library.md`
- **Reason:** Referenced by 22 files across sales, marketing, partnerships
- **Impact:** Org-wide asset in department-specific folder
- **References to update:** 22 files
- **Command to fix:** `/reorganize --move "departments/marketing/docs/Case_Studies_Library.md" "business-core/case-studies/"`

#### ICP Document Misplaced
- **Current:** `departments/marketing/docs/Target_Verticals_ICP.md`
- **Should be:** `business-core/Target_Verticals_ICP.md`
- **Reason:** ICP is foundational strategy, not marketing-specific
- **References to update:** 8 files

#### Meeting Notes in Wrong Location
- **Current:** `departments/marketing/docs/Relevant Meetings/`
- **Should be:** `meetings/sales-intros/` or in `context/`
- **Reason:** These are sales intro meetings, not marketing-specific
- **Files:** 8 meeting transcripts

### Stale Documents

- **`strategy/Q4_2025_OKRs.md`**
  - **Last updated:** 2025-10-15
  - **Update frequency:** Quarterly
  - **Status:** 🕐 Overdue by 3 months
  - **Action:** Review and update or archive

### Incomplete Metadata

- **`departments/sales/docs/Objection_Handling_Library.md`**
  - **Missing:** "Downstream Dependencies" field
  - **Missing:** "Update Frequency" field
  - **Action:** Add missing metadata

### Naming Convention Violations

- **`departments/marketing/docs/Relevant Meetings/`**
  - **Issue:** Spaces in folder name (should use underscores or hyphens)
  - **Should be:** `Relevant_Meetings/` or `relevant-meetings/`

---

## 💡 OPTIMIZATION OPPORTUNITIES

### Consolidation Candidates

- **Value Propositions:**
  - `departments/marketing/docs/Value_Propositions_Library.md`
  - `departments/sales/docs/Sales_Messaging.md` (if exists)
  - **Opportunity:** Might have overlapping content, consider single source

### Better Organization

- **Create `meetings/` top-level directory**
  - Move all meeting notes here
  - Organize by: sales-intros/, partner-meetings/, internal/, client-calls/
  - Benefits: Easier to find, clear separation from department-specific work

### Missing Documents (Non-Critical)

- **`rhythms/Weekly_Sales_Review.md`** - Mentioned in CLAUDE.md but doesn't exist
- **`business-core/Service_Catalog.md`** - Recommended foundation doc
- **`decision-frameworks/Should_We_Hire_Now.md`** - Mentioned in CLAUDE.md

---

## DETAILED FINDINGS

### Structural Analysis

**Scanned:** X directories, Y files

**Misplaced files by category:**
| File | Current Location | Recommended Location | Reason | References to Update |
|------|-----------------|---------------------|--------|---------------------|
| Case_Studies_Library.md | marketing/docs/ | business-core/case-studies/ | Org-wide, 22 references | 22 |
| Target_Verticals_ICP.md | marketing/docs/ | business-core/ | Foundation strategy | 8 |

### Cross-Reference Health

**Total references checked:** X
**Valid references:** Y (Z%)
**Broken references:** A (B%)
**Outdated references:** C (D%)

**Broken references by file:**
[Detailed table]

### Metadata Completeness

**Documents scanned:** X
**Complete metadata:** Y (Z%)
**Missing metadata entirely:** A
**Incomplete metadata:** B

**Missing fields breakdown:**
- Missing "Owner": X files
- Missing "Update Frequency": Y files
- Missing "Downstream Dependencies": Z files

### Dependency Graph

**Total documented dependencies:** X relationships
**Validated dependencies:** Y (Z%)
**Potential stale dependencies:** A (upstream changed more recently)

**Dependency chains:**
```
Unit_Economics.md → Pricing_Framework.md → Should_We_Take_This_Project.md
  Last updated:      2026-01-15            2025-12-01 ⚠️                    2025-11-15 ⚠️
  Status:            Fresh                Potentially stale                Likely stale
```

### Convention Compliance

**Directory structure:** ✅ Matches CLAUDE.md standards
**Naming conventions:** ⚠️ 5 violations found
**Template compliance:** ✅ All departments have required structure

---

## RECOMMENDATIONS

### Immediate Actions (This Week)

1. **Fix broken references** (3 found)
2. **Move misplaced org-wide files** (Case Studies, ICP, Value Props)
3. **Update stale documents** (2 past update frequency)

### Short-Term Actions (This Month)

1. **Complete missing metadata** (12 docs)
2. **Create missing critical docs** (Unit_Economics.md, Service_Catalog.md)
3. **Reorganize meetings/** (create top-level directory)

### Long-Term Improvements (This Quarter)

1. **Run `/audit` monthly** to catch drift early
2. **Use `/tidy` after every work session** to maintain dependencies
3. **Build missing decision frameworks** per CLAUDE.md roadmap

---

## HEALTH SCORE CARD

| Category | Score | Status |
|----------|-------|--------|
| **Structural Organization** | 75/100 | 🟡 Needs improvement |
| **Cross-Reference Integrity** | 92/100 | 🟢 Good |
| **Metadata Completeness** | 68/100 | 🟡 Needs improvement |
| **Freshness** | 85/100 | 🟢 Good |
| **Convention Compliance** | 90/100 | 🟢 Good |
| **Dependency Tracking** | 70/100 | 🟡 Needs improvement |

**Overall Health:** 🟡 **80/100** - System is functional but has organizational debt

---

## NEXT STEPS

1. Review this report with system owner
2. Prioritize fixes (critical → important → optimizations)
3. Run `/reorganize` for misplaced files
4. Update metadata for incomplete docs
5. Schedule next audit (recommended: 30 days)

---

*Audit completed in X seconds*
*Files analyzed: Y*
*Issues found: Z*
```

END OF AUDIT REPORT FORMAT
---

## IMPORTANT INSTRUCTIONS

1. **Be thorough:** Use Glob and Grep extensively, don't just skim
2. **Be specific:** Include file paths, line numbers, exact issues
3. **Prioritize:** Critical issues first, then important, then optimizations
4. **Actionable:** Every issue should have a clear recommended action
5. **Evidence-based:** Don't guess - use grep to verify cross-references
6. **Honest:** If coverage is low, say so. Don't claim 100% if selective.

Run this audit now. Return ONLY the formatted report above.
```

---

## What Happens After Audit

1. **Review Report:** User reviews findings
2. **Prioritize Fixes:** User decides what to tackle first
3. **Execute Fixes:**
   - Use `/reorganize` for file moves
   - Manual fixes for metadata/content
   - `/tidy` to commit changes systematically
4. **Re-Audit:** Run `/audit` again after fixes to verify

---

## When to Run Audit

**Recommended frequency:**
- **Monthly:** Routine health check
- **After major changes:** New departments, big refactors
- **Before important milestones:** Quarterly reviews, client deliverables
- **When system feels messy:** Trust your instincts

**Signs you need an audit:**
- Can't find documents you know exist
- Multiple versions of "same" content
- Broken links when clicking references
- Metadata feels out of date
- New team member confused by structure

---

## Audit Scope Options

### Full Audit (default)
All 6 phases across entire repository
**Runtime:** 2-5 minutes
**Use when:** Monthly check, after major changes

### Quick Scan (`--quick`)
Phases 1-2 only (structural + cross-references)
**Runtime:** 30-60 seconds
**Use when:** Quick health check, pre-commit validation

### Path-Specific (`--path <dir>`)
All 6 phases, but only for specified directory
**Runtime:** 30-90 seconds
**Use when:** Auditing specific department or area

---

## Integration with Other Commands

**`/audit` + `/tidy`:**
- Run `/audit` monthly to find organizational debt
- Run `/tidy` after every work session to prevent new debt

**`/audit` + `/reorganize`:**
- `/audit` identifies misplaced files
- `/reorganize` executes the moves safely

**`/audit` + `/capture-context`:**
- `/audit` flags missing context maps
- `/capture-context` creates them

---

## Success Metrics

Track audit scores over time:

| Audit Date | Overall Health | Critical Issues | Important Issues |
|------------|----------------|-----------------|------------------|
| 2026-02-10 | 80/100 🟡 | 3 | 8 |
| 2026-03-10 | 88/100 🟢 | 0 | 4 |
| 2026-04-10 | 92/100 🟢 | 0 | 2 |

**Goal:** Maintain >85/100 overall health

---

## Edge Cases

| Situation | Handling |
|-----------|----------|
| Audit finds 100+ issues | Prioritize top 10, batch the rest |
| Agent times out (large repo) | Use `--path` to audit incrementally |
| Conflicting recommendations | Agent should flag and ask user to resolve |
| False positives | User can mark as "accepted deviation" |

---

## Notes

- **Read-only:** Audit never modifies files, only reports
- **No secrets:** Agent won't read .env, credentials.json, or similar
- **Respects .gitignore:** Won't audit ignored files
- **Context-aware:** Understands business-builder structure per CLAUDE.md

---

*This command maintains system integrity. Run it often.*
