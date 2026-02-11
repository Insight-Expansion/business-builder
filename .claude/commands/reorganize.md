---
description: Safely move files and update all references automatically - maintains system integrity during restructuring
allowed-tools: Bash, Read, Write, Edit, Glob, Grep, Task
---

# Reorganize

Safely execute file and directory moves while automatically updating all cross-references, metadata, and maintaining system integrity.

## Usage

- `/reorganize --plan` - Show what would be moved (dry run)
- `/reorganize --execute` - Execute the planned reorganization
- `/reorganize --move "<source>" "<dest>"` - Move specific file/folder with reference updates
- `/reorganize --audit-based` - Execute moves recommended by last `/audit` report

## Arguments

$ARGUMENTS - Required: `--plan`, `--execute`, `--move "<source>" "<dest>"`, or `--audit-based`

---

## Philosophy

**Moving files breaks references. This command doesn't.**

When you move a file in a documentation system with cross-references:
- Markdown links break
- Inline file path references become invalid
- Metadata "Downstream Dependencies" entries go stale
- "Synthesized From" sources point to wrong locations

Manual find-and-replace misses edge cases. This command handles the full chain automatically.

---

## Safety First

### Pre-Flight Checks (Always Run Before Moving)

1. **File exists check** - Source path must exist
2. **Destination conflict check** - Don't overwrite existing files
3. **Reference scan** - Find ALL mentions of the file
4. **Git status check** - Warn if uncommitted changes
5. **Context directory protection** - Never move files FROM `context/` directories (read-only)

### Execution Safety

1. **Create destination directory** if needed
2. **Move file** to new location
3. **Update all references** in one atomic operation
4. **Update metadata** in moved file
5. **Verify** all references updated correctly
6. **Git commit** with detailed description

---

## What Gets Updated Automatically

### 1. Markdown Links

**Pattern:** `[Link Text](path/to/file.md)`

```markdown
Before: [Case Studies](departments/marketing/docs/Case_Studies_Library.md)
After:  [Case Studies](business-core/case-studies/Case_Studies_Library.md)
```

### 2. Inline File References

**Pattern:** `` `path/to/file.md` ``

```markdown
Before: See `departments/marketing/docs/Case_Studies_Library.md` for examples
After:  See `business-core/case-studies/Case_Studies_Library.md` for examples
```

### 3. Metadata "Synthesized From" Fields

```markdown
Before:
**Synthesized From:**
- `departments/marketing/context/meetings/intro.md`

After:
**Synthesized From:**
- `meetings/sales-intros/intro.md`
```

### 4. Metadata "Downstream Dependencies" Fields

```markdown
Before:
**Downstream Dependencies:**
- `departments/sales/docs/Playbook.md` - Uses case studies

After:
**Downstream Dependencies:**
- `departments/sales/docs/Playbook.md` - Uses case studies from business-core/
```

### 5. Moved File's Own Metadata

Updates "Last Updated", adds version note:

```markdown
**What Changed:**
- v1.0 (2026-02-10): Initial creation
- v1.1 (2026-02-10): Moved from departments/marketing/docs/ to business-core/case-studies/ (org-wide reorganization)
```

---

## Execution Modes

### Mode 1: Plan (Dry Run)

```bash
/reorganize --plan
```

Shows what would happen WITHOUT making changes:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
REORGANIZATION PLAN (DRY RUN)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Based on last /audit report, the following moves are recommended:

MOVE 1: Case Studies Library
  From: departments/marketing/docs/Case_Studies_Library.md
  To:   business-core/case-studies/Case_Studies_Library.md

  Reason: Org-wide asset referenced by 22 files across sales, marketing, partnerships

  References to update (22 files):
    - departments/sales/docs/Sales_Process_Framework.md (line 45)
    - departments/partnerships/REUSABLE_ASSETS.md (line 189)
    - departments/partnerships/docs/Current_State.md (line 78)
    - [... 19 more files ...]

  Metadata updates:
    - Increment version: 2.0 → 2.1
    - Update "Last Updated" to 2026-02-10
    - Add version note about move

MOVE 2: Target Verticals ICP
  From: departments/marketing/docs/Target_Verticals_ICP.md
  To:   business-core/Target_Verticals_ICP.md

  Reason: Foundation strategy document, not marketing-specific

  References to update (8 files):
    - departments/sales/docs/Pricing_Framework.md (line 23)
    - [... 7 more files ...]

MOVE 3: Relevant Meetings Directory
  From: departments/marketing/docs/Relevant Meetings/
  To:   meetings/sales-intros/

  Reason: Sales intro meetings, not marketing-specific

  Files to move (8):
    - Gary Intro Meeting.md
    - Israel-Gold Intro meeting.md
    - Nick_intro.md
    - [... 5 more files ...]

  References to update (3 files):
    - departments/marketing/docs/Case_Studies_Library.md

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
IMPACT SUMMARY
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Files to move: 3 files + 1 directory (8 files within)
Total references to update: 33 across 28 files
New directories to create: 2 (business-core/case-studies/, meetings/sales-intros/)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
NEXT STEPS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Review this plan. If acceptable, run:
  /reorganize --execute

To only execute specific moves:
  /reorganize --move "departments/marketing/docs/Case_Studies_Library.md" "business-core/case-studies/"
```

### Mode 2: Execute (Apply Changes)

```bash
/reorganize --execute
```

Executes all moves from the plan:

1. Creates destination directories
2. Moves files
3. Updates all references
4. Updates metadata
5. Creates git commit

Progress output:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
EXECUTING REORGANIZATION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[1/3] Moving Case Studies Library...
  ✅ Created directory: business-core/case-studies/
  ✅ Moved file to new location
  ✅ Updated 22 references across 22 files
  ✅ Updated metadata (v2.0 → v2.1)

[2/3] Moving Target Verticals ICP...
  ✅ Moved file to new location
  ✅ Updated 8 references across 8 files
  ✅ Updated metadata (v1.0 → v1.1)

[3/3] Moving Relevant Meetings directory...
  ✅ Created directory: meetings/sales-intros/
  ✅ Moved 8 files
  ✅ Updated 3 references

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
REORGANIZATION COMPLETE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Files moved: 11
References updated: 33 across 28 files
Directories created: 2

Git commit created:
  refactor: reorganize org-wide assets to correct locations

  - Move Case Studies Library to business-core/case-studies/
  - Move Target Verticals ICP to business-core/
  - Move sales intro meetings to meetings/sales-intros/

  Updated 33 references across 28 files to maintain integrity.

  Closes organizational debt identified in /audit report.

Next steps:
  1. Review changes: git diff HEAD~1
  2. Run /audit to verify integrity
  3. Push when ready: git push origin main
```

### Mode 3: Single File Move

```bash
/reorganize --move "departments/marketing/docs/Case_Studies_Library.md" "business-core/case-studies/Case_Studies_Library.md"
```

Moves one specific file with full reference updates.

### Mode 4: Audit-Based

```bash
/reorganize --audit-based
```

Automatically executes all moves recommended by the most recent `/audit` report.

**Workflow:**
1. User runs `/audit`
2. Reviews findings
3. Runs `/reorganize --audit-based` to apply structural fixes
4. System executes all recommended moves

---

## Implementation Strategy

### Step-by-Step Process

#### 1. Parse Input

Determine mode:
- `--plan`: Dry run only
- `--execute`: Apply changes
- `--move <src> <dest>`: Single file mode
- `--audit-based`: Use last audit recommendations

#### 2. Build Move List

**For `--audit-based`:**
- Read last audit report (stored in memory or temp file)
- Extract all "Misplaced Files" recommendations
- Build move list from recommendations

**For `--move`:**
- Single move: source → destination
- Validate paths

**For `--execute`:**
- Use previously generated plan

#### 3. Pre-Flight Validation

For each planned move:

```bash
# Check source exists
test -e "$SOURCE_PATH" || error "Source not found"

# Check destination doesn't exist
test ! -e "$DEST_PATH" || error "Destination already exists"

# Check not moving FROM context/
[[ "$SOURCE_PATH" =~ /context/ ]] && error "Cannot move from context/ (read-only)"

# Check git status
git status --porcelain | grep -q "^" && warn "Uncommitted changes detected"
```

#### 4. Find All References

Use `grep` to find every mention of the file:

```bash
# Find markdown links
grep -r "\]\(.*$(basename $SOURCE_PATH)" . --include="*.md"

# Find inline code references
grep -r "\`.*$(basename $SOURCE_PATH)" . --include="*.md"

# Find metadata references
grep -r "Synthesized From:.*$SOURCE_PATH" . --include="*.md"
grep -r "Downstream Dependencies:.*$SOURCE_PATH" . --include="*.md"

# Find relative path references
grep -r "$SOURCE_PATH" . --include="*.md"
```

Store all matches with:
- File path
- Line number
- Full line content
- Match type (link, inline, metadata, etc.)

#### 5. Calculate Replacement Paths

For each reference, calculate the correct new relative path:

```python
# Example logic:
referencing_file = "departments/sales/docs/Playbook.md"
old_target = "departments/marketing/docs/Case_Studies_Library.md"
new_target = "business-core/case-studies/Case_Studies_Library.md"

# Calculate relative path from referencing_file to new_target
new_relative_path = calculate_relative_path(referencing_file, new_target)
# Result: "../../business-core/case-studies/Case_Studies_Library.md"
```

#### 6. Execute (If Not Dry Run)

```bash
# Create destination directory
mkdir -p "$(dirname $DEST_PATH)"

# Move the file
mv "$SOURCE_PATH" "$DEST_PATH"

# Update all references (use Edit tool for each file)
for ref in references:
    Edit(
        file_path=ref.file,
        old_string=ref.old_line,
        new_string=ref.new_line
    )

# Update moved file's metadata
Edit(
    file_path=DEST_PATH,
    old_string=old_metadata_header,
    new_string=updated_metadata_header
)

# Git commit
git add -A
git commit -m "refactor: move $SOURCE_FILE to $DEST_DIR

- Updated X references across Y files
- Incremented version and updated metadata

Reason: [from audit or user input]
"
```

#### 7. Verification

After moving:

```bash
# Verify file exists at new location
test -e "$DEST_PATH" || error "Move failed"

# Verify old location is gone
test ! -e "$SOURCE_PATH" || error "Source still exists"

# Grep for old path (should find 0 results)
grep -r "$SOURCE_PATH" . --include="*.md" | wc -l
# Expected: 0
```

---

## Reference Update Algorithm

### Challenge: Relative vs Absolute Paths

Markdown links can be:
- Relative: `../../../business-core/file.md`
- Absolute (from repo root): `/business-core/file.md`
- Mixed: Some files use relative, some use absolute

**Solution:** Normalize to relative paths from each referencing file.

### Python-Style Pseudocode

```python
import os
from pathlib import Path

def calculate_new_reference(ref_file, old_target, new_target):
    """
    Calculate what the reference should be updated to.

    ref_file: File containing the reference (e.g., "departments/sales/docs/Playbook.md")
    old_target: Current target path (e.g., "departments/marketing/docs/Case_Studies_Library.md")
    new_target: New target path (e.g., "business-core/case-studies/Case_Studies_Library.md")

    Returns: New relative path from ref_file to new_target
    """

    ref_dir = Path(ref_file).parent
    new_target_path = Path(new_target)

    # Calculate relative path
    relative = os.path.relpath(new_target_path, start=ref_dir)

    return relative

# Example:
ref = "departments/sales/docs/Playbook.md"
old = "departments/marketing/docs/Case_Studies_Library.md"
new = "business-core/case-studies/Case_Studies_Library.md"

result = calculate_new_reference(ref, old, new)
# Result: "../../../business-core/case-studies/Case_Studies_Library.md"
```

### Edge Cases

| Situation | Handling |
|-----------|----------|
| Reference uses absolute path | Convert to relative (more portable) |
| Reference uses `./` prefix | Preserve style |
| Reference in metadata block | Update path, preserve formatting |
| Multiple references in same line | Update all matches |
| Reference is a directory path | Update directory path |
| File moved within same directory | Update filename only |

---

## Integration with `/audit`

**Recommended workflow:**

```bash
# 1. Run audit to identify issues
/audit

# 2. Review audit report (especially "Misplaced Files" section)

# 3. Preview reorganization plan
/reorganize --plan

# 4. Execute if acceptable
/reorganize --execute

# OR execute automatically based on audit
/reorganize --audit-based

# 5. Verify integrity
/audit  # Should show improvements
```

---

## Git Commit Format

```
refactor: reorganize [brief description]

Moves:
- [file1] from [old location] to [new location]
- [file2] from [old location] to [new location]

References updated: X across Y files
New directories created: Z

Reason: [Audit recommendation / Organizational debt / User request]

Closes: [Related issue or audit finding]

🤖 Generated with [Claude Code](https://claude.com/claude-code)

Co-Authored-By: Claude <noreply@anthropic.com>
```

---

## Error Handling

| Error | Handling |
|-------|----------|
| Source file doesn't exist | Abort with clear error message |
| Destination already exists | Abort, suggest `--force` flag (future) |
| Trying to move from context/ | Block and explain read-only rule |
| Git uncommitted changes | Warn but allow (changes will be in same commit) |
| Reference update fails | Rollback move, report error |
| No references found | Warn (might be orphaned file), proceed with move |

---

## Success Metrics

After reorganization:

```
Before /reorganize:
- Audit health: 75/100 (8 misplaced files)
- Cross-reference integrity: 88% (12 broken links)

After /reorganize:
- Audit health: 92/100 (0 misplaced files)
- Cross-reference integrity: 100% (0 broken links)
```

Track:
- Files moved successfully
- References updated
- Broken links fixed
- Audit score improvement

---

## Future Enhancements

**Phase 2 (optional):**
- `--interactive` mode: Ask user to confirm each move
- `--rollback` flag: Undo last reorganization
- `--force` flag: Overwrite destination if exists
- Batch mode: Process CSV of moves

**Phase 3 (optional):**
- Integration with `/tidy`: Suggest reorganizations during commit
- Scheduled audits: Monthly reminder to run /audit + /reorganize
- Visual dependency graph: Show what references what

---

## Notes

- **Always run `/audit` first** to identify what needs moving
- **Review plan before executing** using `--plan`
- **Commit is automatic** - changes are committed immediately
- **No secrets protection** - Won't move .env, credentials.json
- **Respects .gitignore** - Won't move ignored files

---

*This command maintains system integrity during restructuring.*
