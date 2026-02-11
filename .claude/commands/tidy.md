---
description: Complete system maintenance - organize commits, check dependencies, audit structure, fix organizational issues
allowed-tools: Bash, Read, Glob, Grep, Edit, Write, Task
---

# Tidy

Complete system maintenance in one command:
1. Organize uncommitted changes into logical commits
2. Analyze downstream dependency impacts
3. Quick structural health check
4. Detect and fix organizational issues (misplaced files, broken references)

## Usage

- `/tidy` - Full maintenance (commits + dependencies + audit + reorganization)
- `/tidy --quick` - Just organize commits (skip audit/reorganization)
- `/tidy --audit-only` - Skip commits, just audit structure and suggest fixes

## Arguments

$ARGUMENTS - Optional: `--quick` (skip audit), `--audit-only` (skip commits)

---

## Philosophy

**One command to maintain system health.**

Instead of remembering multiple commands (`/tidy`, `/audit`, `/reorganize`), just run `/tidy` after every work session. It handles:
- Git commit organization (clean history)
- Dependency tracking (downstream impacts)
- Structural hygiene (files in right places)
- Reference integrity (no broken links)

**Good commits tell a story. Good systems stay organized.**

---

## Full Workflow Overview

```
/tidy execution flow:

┌─────────────────────────────────────┐
│ PHASE 1-4: GIT COMMITS              │
│ - Analyze uncommitted changes       │
│ - Group into logical commits        │
│ - Present plan to user              │
│ - Execute commits                   │
└─────────────────────────────────────┘
         ↓
┌─────────────────────────────────────┐
│ PHASE 5: DEPENDENCY ANALYSIS        │
│ - Launch agent to analyze commits   │
│ - Identify downstream docs affected │
│ - Suggest required updates          │
│ - Ask if user wants to update now   │
└─────────────────────────────────────┘
         ↓
┌─────────────────────────────────────┐
│ PHASE 6: QUICK STRUCTURAL AUDIT     │
│ - Scan for misplaced files          │
│ - Check for broken references       │
│ - Validate metadata completeness    │
│ - Check naming conventions          │
└─────────────────────────────────────┘
         ↓
┌─────────────────────────────────────┐
│ PHASE 7: REORGANIZATION (if needed) │
│ - Present reorganization plan       │
│ - Ask user approval                 │
│ - Execute safe file moves           │
│ - Update all references             │
│ - Commit reorganization             │
└─────────────────────────────────────┘
         ↓
         Done!
```

---

## Phase 1-4: Organize Git Commits

### Phase 1: Analyze Changes

Run these git commands to understand the current state:

```bash
git status
git diff --stat
git diff --name-only
```

For each changed file, understand WHAT changed:
- Read the diff (`git diff <file>`)
- Categorize the change type (new feature, bug fix, refactor, docs, config, etc.)
- Note which changes are related to each other

### Phase 2: Group Logically

Organize changes into logical commits based on:

| Grouping Signal | Example |
|-----------------|---------|
| Same document/area | All changes to sales department docs |
| Same type of change | All KPI updates together |
| Same business concern | Service catalog + pricing model updates |
| Logical dependency | Foundation doc + decision framework that uses it |

**Commit ordering matters:**
- Infrastructure/config changes first
- Foundation documents before intelligence/strategy docs
- Core business logic before decision frameworks
- Context additions before synthesized docs

**Commit types specific to business-builder:**
- `docs`: Documentation updates (most common)
- `feat`: New slash commands, new document types, new frameworks
- `refactor`: Restructuring existing docs, improving metadata
- `data`: Adding context files, raw business data
- `fix`: Correcting errors in docs, fixing metadata
- `chore`: Config, system maintenance

### Phase 3: Present Commit Plan

Show the user the proposed commit sequence:

Format each proposed commit as:
```
Commit 1: <type>: <description>
  - file1.md (what changed)
  - file2.md (what changed)

Commit 2: <type>: <description>
  - file3.md (what changed)
```

Ask user to confirm or adjust the grouping.

### Phase 4: Execute Commits

For each approved commit group:

1. Stage only the files for that commit:
   ```bash
   git add <file1> <file2>
   ```

2. Create the commit with proper message format:
   ```bash
   git commit -m "$(cat <<'EOF'
   <type>: <concise description>

   <optional body explaining why, not what>

   🤖 Generated with [Claude Code](https://claude.com/claude-code)

   Co-Authored-By: Claude <noreply@anthropic.com>
   EOF
   )"
   ```

3. Verify with `git status` before proceeding to next commit

---

## Phase 5: Downstream Dependency Analysis

**After commits are created**, launch an agent to analyze impacts:

### Agent Task

Launch `general-purpose` agent with this prompt:

```
You are analyzing commits made to the business-builder system to identify which documents may need updates to maintain consistency.

COMMITS TO ANALYZE:
[Include git log --oneline -n <count> and git show for each commit]

YOUR TASK:
1. **Identify changed documents**: List each file that was modified/added
2. **Find downstream dependencies**: For each changed document:
   - Read the document metadata to see if "Downstream Dependencies" are listed
   - Search for any other documents that reference this file (grep across the repo)
   - Check the document type (foundation, intelligence, strategy, decision-framework)
3. **Assess impact**: Determine what needs updating:
   - If foundation docs changed → which decision frameworks use that data?
   - If KPIs changed → which strategy docs reference those metrics?
   - If process flows changed → which SOPs need updating?
   - If context was added → which synthesized docs should incorporate it?
4. **Suggest updates**: For each impacted document, describe:
   - What section likely needs updating
   - What information from the commit should be incorporated
   - Priority: 🔴 Critical / ⚠️ Should update / 💡 Consider updating

RETURN FORMAT:
```markdown
# Downstream Impact Analysis

## Changed Documents
- `path/to/file.md` - [Brief description of change]

## Impacted Documents

### 🔴 Critical Updates Required
- **`path/to/doc.md`**
  - **Why**: [Explanation of dependency]
  - **What to update**: [Specific section]
  - **Change needed**: [Description]

### ⚠️ Should Update Soon
- **`path/to/doc.md`**
  - **Why**: [Explanation]
  - **What to update**: [Section]

### 💡 Consider Updating
- **`path/to/doc.md`**
  - **Why**: [Explanation]

## No Downstream Impacts Detected
[If applicable: explain why no updates needed]
```

DO NOT make any changes yet. Only analyze and report.
```

### Present Impact Report

Display the agent's impact analysis to the user.

If critical or recommended updates were identified, ask:
```
Would you like me to:
1. Update impacted documents now
2. Create a tracking issue/todo list for these updates
3. Skip for now (you'll handle manually)
```

If user chooses (1), proceed to make the updates following standard metadata practices.

---

## Phase 6: Quick Structural Audit

**Run a lightweight audit** to catch common organizational issues:

### What to Check

**1. Misplaced Org-Wide Assets**

Scan department folders for content that should be org-wide:

```bash
# Find potential misplaced files
glob: departments/**/*case*study*
glob: departments/**/*ICP*
glob: departments/**/*value*prop*
glob: departments/**/*service*catalog*
glob: departments/**/*meeting*
```

**Signals a file is misplaced:**
- Generic name in specific folder (e.g., "case-studies" in partnerships/)
- Referenced by multiple departments (grep for cross-references)
- Content scope is org-wide, not dept-specific

**2. Broken References**

```bash
# Extract all markdown links
grep -r "\[.*\](.*\.md)" . --include="*.md"

# For each link, check if target file exists
# Flag broken links
```

**3. Missing Metadata**

```bash
# Check all docs have required metadata
glob: **/docs/**/*.md
glob: business-core/**/*.md

# For each doc, verify presence of:
# - Document, Version, Last Updated, Owner, Update Frequency
```

**4. Naming Violations**

```bash
# Check department names are lowercase-with-hyphens
glob: departments/*/

# Check context files have numeric prefixes
glob: **/context/*.md

# Check docs are Title_Case_With_Underscores
glob: **/docs/*.md
```

### Quick Audit Output

Present a concise report:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
STRUCTURAL AUDIT (Quick Scan)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

🔴 CRITICAL ISSUES: 2
  - Broken reference: departments/sales/docs/Playbook.md → nonexistent.md
  - Missing metadata: strategy/Q1_OKRs.md (no version number)

⚠️ ORGANIZATIONAL ISSUES: 3
  - Misplaced: departments/marketing/docs/Case_Studies_Library.md
    Should be: business-core/case-studies/
    Reason: Referenced by 22 files across 3 departments

  - Misplaced: departments/partnerships/assets/case-studies/
    Should be: Consolidate with business-core/case-studies/
    Reason: Duplicate content structure

  - Naming violation: departments/Marketing/ (should be lowercase)

💡 RECOMMENDATIONS: 1
  - Consider creating business-core/Service_Catalog.md (missing foundation doc)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Would you like to fix these issues now? [y/n]
```

---

## Phase 7: Safe Reorganization

**If structural issues detected**, offer to fix them automatically.

### Reorganization Workflow

**1. Build Move Plan**

For each misplaced file:
- Current location
- Recommended location
- Reason for move
- Number of references to update

**2. Present Plan**

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
REORGANIZATION PLAN
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

MOVE 1: Case Studies Library
  From: departments/marketing/docs/Case_Studies_Library.md
  To:   business-core/case-studies/Case_Studies_Library.md

  Reason: Org-wide asset referenced by 22 files
  References to update: 22 files

MOVE 2: Meeting Notes
  From: departments/marketing/docs/Relevant Meetings/
  To:   meetings/sales-intros/

  Reason: Sales meetings, not marketing-specific
  Files to move: 8
  References to update: 3 files

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
IMPACT SUMMARY
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Files to move: 9 total
References to update: 25 across 23 files
New directories to create: 2

Proceed with reorganization? [y/n]
```

**3. Execute Moves** (if approved)

For each move:

```bash
# Create destination directory
mkdir -p "$(dirname $DEST_PATH)"

# Move the file
mv "$SOURCE_PATH" "$DEST_PATH"

# Find all references
grep -r "$SOURCE_PATH" . --include="*.md" -n

# Update each reference (use Edit tool)
for ref in references:
    Edit(
        file_path=ref.file,
        old_string=ref.old_line,
        new_string=ref.new_line_with_updated_path
    )

# Update moved file's metadata
Edit(
    file_path=DEST_PATH,
    old_string=old_metadata,
    new_string=updated_metadata_with_version_bump
)
```

**4. Commit Reorganization**

```bash
git add -A
git commit -m "$(cat <<'EOF'
chore: reorganize files for better structure

Moves:
- Case_Studies_Library.md to business-core/case-studies/
- Meeting notes to meetings/sales-intros/

Updated 25 references across 23 files.

Reason: Org-wide assets were in department-specific folders.

🤖 Generated with [Claude Code](https://claude.com/claude-code)

Co-Authored-By: Claude <noreply@anthropic.com>
EOF
)"
```

---

## Final Output

After all phases complete:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
TIDY COMPLETE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

✅ COMMITS CREATED: 3
  - docs: update sales process framework
  - data: add Q1 client meeting notes to context
  - feat: add quarterly review SOP

✅ DEPENDENCY ANALYSIS
  - 2 downstream documents need updates
  - Updated both (incremented versions)

✅ STRUCTURAL AUDIT
  - Fixed 3 organizational issues
  - Moved 9 files to correct locations
  - Updated 25 references

✅ REORGANIZATION COMMIT
  - chore: reorganize files for better structure

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
NEXT STEPS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. **Review commits** - Use `git log --oneline -n 4` to inspect
2. **Push when ready:**
   git push origin main

Note: All changes are LOCAL only - not pushed yet

Your system is now clean and organized ✨
```

---

## Command Modes

### Default Mode: `/tidy`

Full maintenance workflow:
1. Organize commits
2. Analyze dependencies
3. Quick structural audit
4. Fix organizational issues

**Use when:** After every work session (recommended)

### Quick Mode: `/tidy --quick`

Only organize commits, skip audit/reorganization:
1. Organize commits
2. Analyze dependencies
3. Skip audit
4. Skip reorganization

**Use when:** In a hurry, just want clean commits

### Audit-Only Mode: `/tidy --audit-only`

Skip commits, just check structure:
1. Skip commit organization (assumes working tree is clean)
2. Full structural audit
3. Fix organizational issues if found

**Use when:** Monthly deep clean, or after major changes

---

## Integration with Specialized Commands

While `/tidy` handles most maintenance, specialized commands still exist for specific needs:

### `/tidy` vs Deep Audit

**`/tidy` (quick audit):**
- Fast scan for common issues
- Runs automatically during normal workflow
- ~30 seconds

**Deep audit (if you create standalone `/audit` later):**
- Comprehensive 6-phase analysis
- Dependency graph validation
- Content consistency checks
- ~2-5 minutes
- Run monthly or when onboarding

### Manual Reorganization

**`/tidy` (automatic):**
- Detects and fixes common misplacements
- Part of regular workflow

**Manual file moves (when needed):**
- Moving specific files intentionally
- Custom reorganization not detected by audit
- Use Edit tool to update references manually

---

## Commit Message Guidelines

**Title (first line):**
- Start with type: `docs:`, `feat:`, `refactor:`, `data:`, `fix:`, `chore:`
- Use imperative mood: "Add KPI metrics" not "Added KPI metrics"
- Keep under 50 characters if possible
- No period at the end

**Body (optional):**
- Explain WHY, not WHAT (the diff shows what)
- Reference related documents if helpful
- Wrap at 72 characters
- Leave blank line between title and body

**Examples:**
```
docs: add sales department current state

Synthesized from interviews with sales team lead.
Coverage ~60% - detailed call scripts in context files.
```

```
feat: add should-we-hire decision framework

Based on current utilization targets and cash runway model
from Unit_Economics.md.
```

```
chore: reorganize org-wide assets to business-core

Case studies, ICP, and value props were in marketing/
but used by all departments. Moved to business-core/.
Updated 22 references.
```

---

## Safety Rules

- NEVER force push
- NEVER amend commits not created in this session
- NEVER commit files that look like secrets (.env, credentials, API keys)
- NEVER modify `context/` directories without user confirmation
- ALWAYS show plans before executing (commits, reorganizations)
- ALWAYS verify each commit succeeded before proceeding
- ALWAYS update metadata when moving files (version bump, update date)

---

## Edge Cases

| Situation | Handling |
|-----------|----------|
| No uncommitted changes | Skip Phase 1-4, proceed to audit |
| No structural issues | Skip Phase 6-7, just do commits + dependencies |
| User declines reorganization | Skip Phase 7, commit as-is |
| Mixed changes in one file | Group in single commit if related |
| New context/ files added | Separate commit, note which docs should synthesize |
| Metadata-only changes | Group all metadata updates together |
| CLAUDE.md changes | Separate commit, high-impact change |
| Merge conflicts present | Abort and ask user to resolve first |

---

## Performance Optimization

**Quick audit focuses on:**
- ✅ Files in wrong locations (glob patterns)
- ✅ Broken markdown links (regex + file checks)
- ✅ Missing critical metadata fields
- ✅ Naming convention violations

**Full audit would add** (for monthly deep clean):
- Dependency graph validation
- Content consistency checks (e.g., matching $120/hr across docs)
- Coverage % accuracy
- Update frequency compliance
- Cross-reference bidirectional validation

This keeps `/tidy` fast (~1-2 min total) for daily use.

---

## When to Run Tidy

**Recommended frequency:**

```
Daily/After Each Work Session:
  /tidy
  → Keeps commits clean
  → Catches organizational drift early
  → Maintains dependency consistency

Monthly Deep Clean (optional):
  /tidy --audit-only
  → Run with extended checks
  → Full dependency graph validation
  → Thorough structure review

Before Important Milestones:
  /tidy
  → Clean system before quarterly reviews
  → Before onboarding new team members
  → Before major presentations
```

**Signs you need to run tidy:**
- ❌ Uncommitted changes piling up
- ❌ Not sure what changed or why
- ❌ Can't find documents you created
- ❌ Links feel broken or stale
- ❌ System feels "messy"

---

## Success Metrics

**Track improvement over time:**

| Week | Commits Created | Deps Fixed | Files Reorganized | Health Score |
|------|----------------|------------|-------------------|--------------|
| 1 | 5 | 3 | 8 | 75/100 |
| 2 | 3 | 1 | 2 | 82/100 |
| 3 | 4 | 2 | 0 | 88/100 |
| 4 | 3 | 0 | 0 | 92/100 |

**Goal:** After 2-3 weeks of regular `/tidy` usage:
- Fewer files need reorganizing each time (system stays organized)
- Fewer dependency issues (proactive updates)
- Higher health scores (>85/100)

---

## Example Session

```
User: /tidy