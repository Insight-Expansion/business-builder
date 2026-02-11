# Sync Case Studies from Proposal Builder

You are syncing new projects from the **remote proposal-builder GitHub repository** into the business-builder case studies library.

## Your Task

1. **Fetch remote proposal-builder projects:**
   - **GitHub Repo:** https://github.com/Insight-Expansion/proposal-builder
   - **Method:** Use GitHub API or `gh` CLI to list projects (preferred over git clone for speed)
   - **Path:** `projects/` directory
   - **Exclude:** `_template/` folder

   **Recommended approach:**
   ```bash
   # List all directories in projects/ from remote repo
   gh api repos/Insight-Expansion/proposal-builder/contents/projects \
     --jq '.[] | select(.type == "dir") | .name' \
     | grep -v "^_template$"
   ```

   Or if `gh` unavailable, fetch via git:
   ```bash
   cd /tmp
   git clone --depth 1 https://github.com/Insight-Expansion/proposal-builder.git
   ls proposal-builder/projects/ | grep -v "^_template$"
   ```

2. **Read existing case studies:**
   - Location: `business-core/case-studies/Case_Studies_Library.md`
   - Extract list of projects already documented
   - Build a map of: project folder name → case study number/section
   - Track coverage percentage and last sync date from metadata

3. **Compare and identify new projects:**
   - Find projects in remote repo NOT yet in case studies library
   - For each new project, fetch and extract basic info:
     - Use GitHub API to read `projects/[name]/PROJECT.md` (if exists and not just template)
     - Browse `projects/[name]/references/` directory for context files
     - Browse `projects/[name]/docs/` for proposals, estimates, architecture docs
     - Determine project status based on what exists:
       - Has `docs/Client_Facing/Gate3_Proposal.md` or `Project_Estimate.md` = High priority
       - Has `docs/Internal_Facing/Solution_Architecture.md` = Medium priority
       - Only has references/ = Low priority (discovery only)
     - Extract: client name, industry, project description, budget/timeline if available

4. **Generate report:**
   ```markdown
   # New Projects Found for Case Studies

   **Total new projects:** [count]
   **Last sync:** [date from Case_Studies_Library.md metadata]

   ## High Priority (Has proposal/estimate)
   1. **[project-folder-name]**
      - Client: [name]
      - Industry: [vertical]
      - Status: [Proposal ready / Estimate complete / etc.]
      - Budget: [if available]
      - Brief: [1-2 line description]

   ## Medium Priority (Has solution architecture)
   [same format]

   ## Low Priority (Discovery only)
   [same format]

   ## Recommendations
   - Start with high priority projects (revenue/validation proof)
   - [Any specific insights about which cases would be most valuable]
   ```

5. **Optional: Auto-add skeleton entries**
   If user confirms, add skeleton case study entries to Case_Studies_Library.md:
   - Use the existing template format
   - Mark fields as [TBD] where info is missing
   - Add to appropriate industry section
   - Update metadata (version increment, sources list)

## Key Rules

- **DO fetch from remote** GitHub repo (not local files) - ensures canonical source
- **DO NOT modify** remote proposal-builder repo (read-only access)
- **DO respect** the existing Case_Studies_Library.md structure and format
- **DO track** what percentage of projects are now documented
- **DO note** projects that have changed significantly since last documented (check GitHub commit timestamps)
- **DO prioritize** projects with completed proposals, budgets, or production systems
- **DO use GitHub API or `gh` CLI** when possible (faster than full clone)

## Success Criteria

- Clear report showing what's new
- Actionable priorities (which to document first)
- If adding entries: properly formatted, metadata updated, no duplicates

## Example Usage

**User:** `/sync-case-studies`
**Output:** Report of new projects found

**User:** `/sync-case-studies --add`
**Output:** Report + skeleton entries added to library + confirmation

## Implementation Notes

**GitHub API Endpoints to use:**
- List directory contents: `GET /repos/Insight-Expansion/proposal-builder/contents/projects`
- Read file contents: `GET /repos/Insight-Expansion/proposal-builder/contents/projects/{name}/PROJECT.md`
- Get commit info: `GET /repos/Insight-Expansion/proposal-builder/commits?path=projects/{name}`

**Fallback:** If API rate-limited, clone to `/tmp/proposal-builder-sync-[timestamp]` and clean up after.

**Performance:** GitHub API is paginated (30 items default). For 38+ projects, may need pagination handling.

---

Begin by:
1. Checking if `gh` CLI is available (run `gh --version`)
2. Fetching list of projects from remote GitHub repo
3. Reading the local Case_Studies_Library.md
4. Generating your comparison report
