---
description: Organize uncommitted changes into logical commits and analyze downstream dependency impacts
allowed-tools: Bash, Read, Glob, Grep, Task
---

# Tidy

Organize uncommitted changes into clean git commits and identify which documents need updates to maintain consistency.

## Usage

- `/tidy` - Analyze changes, create commits, check downstream impacts

## Arguments

$ARGUMENTS - None required

---

## Philosophy

**Good commits tell a story. Dependencies must stay in sync.**

This command:
1. Transforms messy uncommitted changes into logical, well-organized commits
2. Analyzes which documents are affected by your changes
3. Identifies downstream dependencies that need updating

For structural maintenance (file organization, broken links), use `/maintain` instead.

---

## Workflow Overview

```
/tidy execution flow:

┌─────────────────────────────────────┐
│ PHASE 1: ANALYZE CHANGES            │
│ - Run git status, git diff          │
│ - Read each changed file            │
│ - Categorize changes                │
└─────────────────────────────────────┘
         ↓
┌─────────────────────────────────────┐
│ PHASE 2: GROUP LOGICALLY            │
│ - Same document/area together       │
│ - Related changes together          │
│ - Logical ordering                  │
└─────────────────────────────────────┘
         ↓
┌─────────────────────────────────────┐
│ PHASE 3: PRESENT PLAN               │
│ - Show proposed commits             │
│ - Ask user approval                 │
└─────────────────────────────────────┘
         ↓
┌─────────────────────────────────────┐
│ PHASE 4: EXECUTE COMMITS            │
│ - Stage files for each commit       │
│ - Create commits with messages      │
│ - Verify success                    │
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
         Done!
```

---

## Phase 1: Analyze Changes

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

---

## Phase 2: Group Logically

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

---

## Phase 3: Present Commit Plan

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

---

## Phase 4: Execute Commits

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

If user chooses (1), proceed to make the updates following standard metadata practices:
- Increment version numbers
- Update "Last Updated" timestamps
- Add to "What Changed" log
- Preserve coverage % tracking

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

[git log --oneline output]

✅ DEPENDENCY ANALYSIS
  - 2 downstream documents need updates
  - Updated both (incremented versions)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
NEXT STEPS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. **Review commits** - Use `git log -p` to inspect if needed

2. **Check file organization** - Run /maintain if you've moved files or added many new docs

3. **Push when ready:**
   git push origin main

Note: All changes are LOCAL only - not pushed yet
```

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
data: add Q1 2026 client meeting transcripts to context

8 sales intro meetings captured. Will synthesize into
case studies and sales process docs next.
```

---

## Safety Rules

- NEVER force push
- NEVER amend commits not created in this session
- NEVER commit files that look like secrets (.env, credentials, API keys)
- NEVER modify `context/` directories without user confirmation
- ALWAYS show the commit plan before executing
- ALWAYS verify each commit succeeded before proceeding
- ALWAYS run dependency analysis after commits

---

## Edge Cases

| Situation | Handling |
|-----------|----------|
| No uncommitted changes | Display "Working tree clean, nothing to tidy" |
| Mixed changes in one file | Group in single commit if related, or ask user to split |
| New context/ files added | Separate commit, note which docs should synthesize this |
| Metadata-only changes | Group all metadata updates together |
| CLAUDE.md changes | Separate commit, high-impact change |
| Only one logical change | Single commit is fine—don't force artificial splits |
| Merge conflicts present | Abort and ask user to resolve conflicts first |
| Staged + unstaged for same file | Show both, ask which version to commit |

---

## When to Run Tidy

**After every work session:**
```
Work on docs → /tidy → Push
```

**Signs you need to run tidy:**
- Uncommitted changes piling up
- Not sure what changed or why
- Want clean commit history before pushing
- Just added context files that affect other docs
- Updated foundation docs that decision frameworks depend on

---

## What Tidy Does NOT Do

**Tidy is focused on git + dependencies.**

For these tasks, use `/maintain` instead:
- ❌ Detect misplaced files (org-wide assets in dept folders)
- ❌ Find broken references (links to moved/renamed files)
- ❌ Validate metadata completeness
- ❌ Check naming conventions
- ❌ Reorganize file structure
- ❌ Fix organizational drift

**Run both regularly:**
- `/tidy` - After every work session (git hygiene)
- `/maintain` - Weekly (structural hygiene)

---

## Integration with /maintain

```
Typical Workflow:

1. Work on documents
2. /tidy - Clean commits + dependency check
3. (Weekly) /maintain - Check structure, fix organization
4. Push everything
```

Both commands are complementary:
- **Tidy** = Git commits + content dependencies
- **Maintain** = File structure + system integrity

---

*This command maintains git hygiene and content consistency.*
