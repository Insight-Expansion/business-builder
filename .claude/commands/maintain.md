---
description: Audit system structure and automatically fix organizational issues - keeps files in right places and references intact
allowed-tools: Bash, Read, Write, Edit, Glob, Grep
---

# Maintain

Comprehensive structural health check and automatic fixing:
- Detect misplaced files (org-wide assets in department folders)
- Find broken references (links to moved/renamed files)
- Validate metadata completeness
- Check naming conventions
- Safely reorganize files with automatic reference updates

## Usage

- `/maintain` - Full structural audit + automatic fixes
- `/maintain --check-only` - Audit only, don't fix anything (dry run)

## Arguments

$ARGUMENTS - Optional: `--check-only` for dry run

---

## Philosophy

**Systems drift without maintenance. Files end up in wrong places.**

This command acts as your **structural hygiene system**:
1. Scans for common organizational anti-patterns
2. Identifies files in wrong locations
3. Detects broken links and stale metadata
4. Proposes fixes with clear reasoning
5. Executes safe moves with automatic reference updates

For git commit organization, use `/tidy` instead.

---

## Workflow Overview

```
/maintain execution flow:

┌────────────────────────────────────┐
│ PHASE 1: SCAN STRUCTURE            │
│ - Find misplaced files             │
│ - Detect broken references         │
│ - Check metadata completeness      │
│ - Validate naming conventions      │
└────────────────────────────────────┘
         ↓
┌────────────────────────────────────┐
│ PHASE 2: ANALYZE ISSUES            │
│ - Prioritize problems              │
│ - Build fix plan                   │
│ - Calculate impact                 │
└────────────────────────────────────┘
         ↓
┌────────────────────────────────────┐
│ PHASE 3: PRESENT REPORT            │
│ - Show all issues found            │
│ - Explain why they're problems     │
│ - Propose specific fixes           │
│ - Ask user approval                │
└────────────────────────────────────┘
         ↓
┌────────────────────────────────────┐
│ PHASE 4: EXECUTE FIXES (if approved)│
│ - Move files to correct locations  │
│ - Update all references            │
│ - Fix metadata                     │
│ - Create git commit                │
└────────────────────────────────────┘
         ↓
         Done!
```

---

## Phase 1: Scan Structure

### 1.1 Detect Misplaced Org-Wide Assets

Scan department folders for content that should be org-wide:

```bash
# Find potential misplaced files
glob: departments/**/*case*study*
glob: departments/**/*ICP*
glob: departments/**/*value*prop*
glob: departments/**/*service*catalog*
glob: departments/**/*meeting*
glob: departments/**/*vision*
glob: departments/**/*mission*
```

**Signals a file is misplaced:**
- Generic name in specific folder (e.g., "case-studies" in partnerships/)
- Referenced by multiple departments (grep for cross-references)
- Metadata shows org-wide owner, not department-specific
- Content mentions multiple departments or company-wide scope

**For each misplaced file, note:**
- Current location
- Recommended location
- Reason (referenced by X departments, owner is org-wide, etc.)
- Number of references that would need updating

### 1.2 Find Broken References

```bash
# Extract all markdown links
grep -r "\[.*\](.*\.md)" . --include="*.md"

# For each link:
# 1. Extract target file path
# 2. Check if file exists at that path
# 3. If not, search for filename elsewhere (was it moved?)
# 4. Flag broken references with suggested fix
```

### 1.3 Check Metadata Completeness

```bash
# Find all docs that should have metadata
glob: **/docs/**/*.md
glob: business-core/**/*.md
glob: strategy/**/*.md
glob: decision-frameworks/**/*.md

# For each doc, verify presence of:
# - Document
# - Version
# - Last Updated
# - Owner
# - Update Frequency
# - (Optional) Synthesized From, Downstream Dependencies
```

### 1.4 Validate Naming Conventions

Per CLAUDE.md standards:

```bash
# Check department names are lowercase-with-hyphens
glob: departments/*/  # should all match lowercase-with-hyphens

# Check context files have numeric prefixes
glob: **/context/*.md  # should start with 01_, 02_, etc.

# Check docs are Title_Case_With_Underscores
glob: **/docs/*.md  # should be Title_Case

# Check no spaces in critical file/folder names
find . -name "* *" -type f
```

---

## Phase 2: Analyze Issues

### Prioritize Problems

**🔴 Critical (must fix):**
- Broken references (links to nonexistent files)
- Missing critical metadata (no version, no owner)
- Context/ directory modifications (read-only violation)

**⚠️ Important (should fix):**
- Misplaced org-wide assets (in department folders)
- Stale metadata (past update frequency)
- Naming convention violations

**💡 Recommendations (consider):**
- Missing optional metadata fields
- Duplicate content opportunities
- Structure optimizations

### Build Fix Plan

For each issue, prepare:
- What's wrong
- Why it's a problem
- Specific fix action
- Impact (files to move, references to update)
- Estimated effort

---

## Phase 3: Present Report

Show comprehensive audit results:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
STRUCTURAL HEALTH REPORT
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📊 SCAN SUMMARY
- Files scanned: 156
- Issues found: 8
- Critical: 1
- Important: 5
- Recommendations: 2

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🔴 CRITICAL ISSUES (1)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. BROKEN REFERENCE
   File: departments/sales/docs/Playbook.md (line 45)
   References: departments/marketing/docs/Case_Studies_Library.md
   Problem: Target file doesn't exist (was it moved?)
   Found at: business-core/case-studies/Case_Studies_Library.md
   Fix: Update reference to new location

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
⚠️ IMPORTANT ISSUES (5)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

2. MISPLACED ORG-WIDE ASSET
   File: departments/marketing/docs/Value_Propositions_Library.md
   Problem: Org-wide asset in department-specific folder
   Evidence: Referenced by sales/ (3 times), partnerships/ (5 times)
   Recommended location: business-core/Value_Propositions_Library.md
   Impact: 8 references need updating

3. MISPLACED ORG-WIDE ASSET
   File: departments/partnerships/assets/case-studies/
   Problem: Duplicate structure for case studies
   Recommended: Consolidate with business-core/case-studies/
   Impact: 2 files to move, 4 references to update

4. MISSING METADATA
   File: strategy/Q1_2026_OKRs.md
   Problem: No "Version" field in metadata
   Fix: Add version number (suggest starting at 1.0)

5. NAMING VIOLATION
   File: departments/marketing/docs/Relevant Meetings/
   Problem: Folder name has spaces
   Recommended: meetings/sales-intros/ or Relevant_Meetings/
   Impact: 8 files, 3 references

6. STALE METADATA
   File: agency-intelligence/Client_Health.md
   Last Updated: 2025-11-15
   Update Frequency: Monthly
   Problem: 3 months overdue
   Fix: Update document or change frequency

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
💡 RECOMMENDATIONS (2)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

7. MISSING FOUNDATION DOC
   Expected: business-core/Service_Catalog.md
   Referenced by: 3 documents
   Status: Not found
   Recommendation: Create this foundation document

8. OPTIMIZATION OPPORTUNITY
   Files: departments/*/docs/Meeting_Notes_*.md (12 files)
   Recommendation: Consider consolidating to meetings/ directory
   Benefit: Easier to find, clearer separation

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
FIX PLAN
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

If you approve, I will:

MOVE 1: Fix broken reference
  - Update departments/sales/docs/Playbook.md line 45
  - No files moved, just reference corrected

MOVE 2: Reorganize Value Propositions
  From: departments/marketing/docs/Value_Propositions_Library.md
  To: business-core/Value_Propositions_Library.md
  Update: 8 references across 6 files

MOVE 3: Consolidate case studies
  From: departments/partnerships/assets/case-studies/
  To: business-core/case-studies/
  Update: 4 references across 3 files

METADATA FIX 1: Add version to Q1_2026_OKRs.md
  Add: Version: 1.0

METADATA FIX 2: Flag stale doc
  Add warning to Client_Health.md metadata

Total impact:
- Files to move: 3
- References to update: 13
- Metadata fixes: 2

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Would you like me to execute these fixes? [y/n]
If yes, all changes will be committed automatically.
```

---

## Phase 4: Execute Fixes (if approved)

### 4.1 Fix Broken References

```bash
# For each broken reference:
Read(file_with_broken_reference)
Edit(
    file_path=file,
    old_string=line_with_old_reference,
    new_string=line_with_corrected_reference
)
```

### 4.2 Move Misplaced Files

For each file to move:

```bash
# 1. Create destination directory
mkdir -p "$(dirname $DEST_PATH)"

# 2. Move the file
mv "$SOURCE_PATH" "$DEST_PATH"

# 3. Find all references to this file
grep -r "$(basename $SOURCE_PATH)" . --include="*.md" -n
grep -r "$SOURCE_PATH" . --include="*.md" -n

# 4. Update each reference (calculate correct relative path)
for each reference:
    Read(referencing_file)
    Edit(
        file_path=referencing_file,
        old_string=old_line_with_old_path,
        new_string=new_line_with_new_relative_path
    )

# 5. Update moved file's metadata
Read(DEST_PATH)
Edit(
    file_path=DEST_PATH,
    old_string=old_metadata,
    new_string=updated_metadata  # increment version, update date, add move note
)
```

### 4.3 Fix Metadata

```bash
# For missing fields:
Read(file)
Edit(
    file_path=file,
    old_string=existing_metadata_block,
    new_string=metadata_with_missing_fields_added
)

# For stale docs, add warning:
**Completeness:** 🕐 Stale - Past update frequency, needs refresh
```

### 4.4 Create Commit

```bash
git add -A
git commit -m "$(cat <<'EOF'
chore: maintain system structure - fix organizational issues

Fixed:
- 1 broken reference (sales/Playbook.md)
- Moved 3 misplaced files to correct locations
- Updated 13 references across files
- Added missing metadata fields (2 files)
- Flagged 1 stale document

Moves:
- Value_Propositions_Library.md → business-core/
- partnerships/assets/case-studies/* → business-core/case-studies/

Reason: Weekly maintenance identified organizational drift.
All references updated to maintain system integrity.

🤖 Generated with [Claude Code](https://claude.com/claude-code)

Co-Authored-By: Claude <noreply@anthropic.com>
EOF
)"
```

---

## Final Output

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
MAINTAIN COMPLETE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

✅ FIXES APPLIED
  - Fixed 1 broken reference
  - Moved 3 files to correct locations
  - Updated 13 references
  - Fixed 2 metadata issues

✅ COMMIT CREATED
  chore: maintain system structure - fix organizational issues

📊 SYSTEM HEALTH
  Before: 82/100
  After: 94/100
  Improvement: +12 points

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
NEXT STEPS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. **Review changes** - Use `git log -p -n 1` to inspect

2. **Push when ready:**
   git push origin main

3. **Continue working** - Run /tidy before next push

Your system structure is now clean ✨
```

---

## Safety Rules

- NEVER delete files without asking
- NEVER modify `context/` directories (read-only)
- NEVER move files without updating references
- ALWAYS show full fix plan before executing
- ALWAYS create git commit after fixes
- ALWAYS verify file exists at new location after move

---

## Edge Cases

| Situation | Handling |
|-----------|----------|
| No issues found | Display "System is healthy, no fixes needed" |
| User declines fixes | Display report only, no changes made |
| File reference ambiguous | Ask user which path is correct |
| Circular references | Flag for manual review |
| Context/ files modified | Block and explain read-only rule |
| Too many issues (>20) | Batch into multiple fix sessions |

---

## What Maintain Does NOT Do

**Maintain is focused on structure + references.**

For these tasks, use `/tidy` instead:
- ❌ Organize git commits
- ❌ Analyze downstream content dependencies
- ❌ Update doc content based on changes
- ❌ Commit your work in progress

**Run both regularly:**
- `/tidy` - After every work session (git + content)
- `/maintain` - Weekly (structure + references)

---

## When to Run Maintain

**Weekly maintenance:**
```
(Every Friday) → /maintain → Review report → Fix issues
```

**After major changes:**
- Created new department
- Moved multiple files manually
- Added many new documents
- Onboarding new team member (clean house first)
- Before quarterly reviews

**Signs you need to run maintain:**
- Can't find documents you created
- Links feel broken
- Multiple versions of "same" content
- System feels disorganized

---

## Integration with /tidy

```
Recommended Workflow:

Daily:
  Work → /tidy → Push
  (Keeps git clean, dependencies in sync)

Weekly:
  /maintain → Review → Fix → /tidy → Push
  (Keeps structure organized)

Monthly:
  /maintain --check-only → Review deep health
  (Comprehensive system audit)
```

**Why both?**
- **Tidy** = Content-level maintenance (what you wrote)
- **Maintain** = Structure-level maintenance (where it lives)

---

## Common Issues Detected

### Misplaced Files
- Org-wide assets in department folders
- Meeting notes scattered across departments
- Generic resources (case studies, ICPs) not in business-core/
- Shared assets duplicated across departments

### Broken References
- Links to moved files
- References using old paths
- Missing target files
- Relative path errors

### Metadata Problems
- Missing required fields (version, owner, update frequency)
- Stale "Last Updated" dates
- No downstream dependencies listed
- Version history gaps

### Naming Issues
- Spaces in file/folder names
- Inconsistent casing (Title_Case vs lower-case)
- Context files without numeric prefixes
- Department names not lowercase-with-hyphens

---

## Health Score Calculation

After each `/maintain` run, calculate system health:

```
Health Score Components:

Structural Organization (30 points)
  - All org-wide assets in correct locations
  - No duplicate structures
  - Naming conventions followed

Reference Integrity (30 points)
  - No broken links
  - All paths valid
  - Relative paths correct

Metadata Completeness (25 points)
  - All required fields present
  - Dates are current
  - Dependencies documented

Freshness (15 points)
  - Docs updated within frequency
  - No stale content
  - Versions incremented properly

Total: /100
```

**Target: >85/100 for healthy system**

---

*This command maintains structural integrity and keeps your system organized.*
