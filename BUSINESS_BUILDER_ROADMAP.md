# Business Builder System - Roadmap & Architecture

**Purpose**: Build a comprehensive business context management system for software agencies that integrates with existing tools (Notion, Google Drive, Go High Level) to enable AI-powered decision making, process documentation, and strategic planning.

**Last Updated**: 2026-01-11
**Status**: Planning Phase

---

## Table of Contents

1. [System Overview](#system-overview)
2. [Core Philosophy](#core-philosophy)
3. [Architecture](#architecture)
4. [Existing Tech Stack Integration](#existing-tech-stack-integration)
5. [Implementation Phases](#implementation-phases)
6. [Slash Commands Roadmap](#slash-commands-roadmap)
7. [Skills & Automation](#skills--automation)
8. [Success Metrics](#success-metrics)

---

## System Overview

### What This System Does

**Problem**: Software agencies have scattered business context across Notion, Google Drive, Slack, email, and people's heads. Making strategic decisions (Can we take this project? Should we hire? Why did we lose that deal?) requires hours of hunting and synthesis.

**Solution**: A Claude Code-powered system that:
- Synthesizes messy inputs into structured business intelligence
- Maintains living documentation of how the business operates
- Enables AI-powered decision making with full business context
- Tracks what actually happened vs what we planned (learning loop)
- Integrates with existing tools (Notion, Google Drive, Go High Level)

### Inspiration: proposal-builder

This system adapts the proposal-builder workflow:
- `references/` → `context/` (raw inputs from meetings, Notion, Drive)
- `projects/` → `departments/` + `business-core/` + `agency-intelligence/`
- Synthesis commands → Context capture + intelligence building
- Client deliverables → Internal operating docs (SOPs, dashboards, frameworks)
- One-time proposals → Living business documentation

### Key Differences from proposal-builder

| Aspect | proposal-builder | business-builder |
|--------|-----------------|------------------|
| **Update frequency** | Once per project | Continuous (weekly/monthly) |
| **Audience** | External (clients) | Internal (team, leadership) |
| **Validation** | Client gates (3 checkpoints) | Internal reviews, data validation |
| **Dependencies** | Linear (requirements → solution → estimate) | Network (cross-department, historical data) |
| **Artifacts** | Proposals, contracts | SOPs, KPIs, decision frameworks |
| **Time horizon** | Project lifecycle (weeks-months) | Ongoing business operations (years) |

---

## Core Philosophy

### 1. **Single Source of Truth, Multiple Systems of Record**

- Notion = Active operational docs (SOPs, project management, hour tracking)
- Google Drive = Client-specific files and meeting transcripts
- Go High Level = Sales/outreach CRM
- **business-builder** = Synthesized intelligence layer that reads from all sources

### 2. **Context Completeness Tracking**

Every doc tracks:
- **Sources**: What inputs were synthesized (with coverage %)
- **Last Updated**: When was this validated as accurate
- **Owner**: Who maintains this
- **Downstream Impact**: What depends on this being accurate
- **Freshness**: How often should this be reviewed

### 3. **Learning Loop Architecture**

```
PLAN → EXECUTE → MEASURE → LEARN → IMPROVE PLAN
  ↓        ↓          ↓         ↓          ↓
Strategy → Projects → Actuals → Analysis → Next Quarter
```

Track:
- Estimates vs actuals
- Revenue plan vs revenue actuals
- Client health predictions vs churn
- Capacity forecasts vs utilization

### 4. **Decision-First Design**

Every framework answers a question:
- "Can we take this project?" → Capacity + Margin + ICP fit check
- "Should we hire now?" → Utilization + Pipeline + Cash check
- "Why did we lose this deal?" → Win/loss pattern analysis
- "What's at risk this quarter?" → Project health + Client health + Cash position

---

## Architecture

### Directory Structure

```
business-builder/
├── .claude/
│   ├── commands/                    # Slash commands (see section below)
│   ├── settings.local.json          # Hooks, MCP configs
│   └── CLAUDE.md                    # System instructions
│
├── business-core/                   # Foundation layer
│   ├── 01_foundation/
│   │   ├── Vision_Mission_Values.md
│   │   ├── Strategic_Positioning.md
│   │   ├── Service_Catalog.md
│   │   ├── Pricing_Philosophy.md
│   │   └── ICP_Profile.md
│   │
│   ├── 02_financial_model/
│   │   ├── Unit_Economics.md
│   │   ├── Margin_by_Service.md
│   │   ├── Team_Cost_Structure.md
│   │   ├── Pricing_Model.md
│   │   └── Cash_Flow_Requirements.md
│   │
│   ├── 03_delivery_framework/
│   │   ├── Project_Methodology.md
│   │   ├── Estimation_Standards.md
│   │   ├── Quality_Standards.md
│   │   ├── Tech_Stack_Decisions.md
│   │   └── Change_Control_Process.md
│   │
│   ├── 04_client_lifecycle/
│   │   ├── Lead_to_Close_Process.md
│   │   ├── Onboarding_Process.md
│   │   ├── Delivery_Cadence.md
│   │   ├── Success_Criteria.md
│   │   └── Offboarding_Process.md
│   │
│   └── 05_people_system/
│       ├── Hiring_Standards.md
│       ├── Onboarding_Journey.md
│       ├── Growth_Framework.md
│       ├── Compensation_Philosophy.md
│       └── Culture_Playbook.md
│
├── departments/                     # Department-specific context
│   ├── sales/
│   │   ├── DEPARTMENT.md           # Overview, owner, update frequency
│   │   ├── context/                # Raw inputs (DO NOT MODIFY)
│   │   │   ├── 01_sales_team_interviews.md
│   │   │   ├── 02_current_crm_process.md
│   │   │   └── 03_go_high_level_export.csv
│   │   └── docs/
│   │       ├── Context_Map.md
│   │       ├── Current_State.md
│   │       ├── Process_Flows.md
│   │       ├── SOPs/
│   │       ├── KPIs.md
│   │       ├── Tools_Stack.md
│   │       └── Dependencies.md
│   │
│   ├── delivery/
│   │   └── [same structure]
│   │
│   ├── marketing/
│   │   └── [same structure]
│   │
│   ├── operations/
│   │   └── [same structure]
│   │
│   └── finance/
│       └── [same structure]
│
├── agency-intelligence/             # Data-driven insights
│   ├── historical_data/
│   │   ├── Estimation_Accuracy.md
│   │   ├── Delivery_Velocity.md
│   │   ├── Project_Postmortems.md
│   │   └── Client_Churn_Analysis.md
│   │
│   ├── capacity_planning/
│   │   ├── Team_Utilization.md
│   │   ├── Current_Capacity.md
│   │   ├── Pipeline_Requirements.md
│   │   └── Hiring_Forecast.md
│   │
│   ├── client_portfolio/
│   │   ├── Client_Health_Scores.md
│   │   ├── Revenue_Concentration.md
│   │   ├── Upsell_Opportunities.md
│   │   └── Lifetime_Value_Analysis.md
│   │
│   └── technical_assets/
│       ├── Reusable_Components.md
│       ├── Integration_Patterns.md
│       ├── Architecture_Decisions.md
│       └── Tech_Debt_Register.md
│
├── strategy/                        # Strategic planning & execution
│   ├── quarterly_planning/
│   │   ├── Q1_2026_OKRs.md
│   │   ├── Q1_2026_Rocks.md
│   │   └── Q1_2026_Metrics_Dashboard.md
│   │
│   ├── annual_planning/
│   │   ├── 2026_Revenue_Plan.md
│   │   ├── 2026_Service_Roadmap.md
│   │   └── 2026_Team_Plan.md
│   │
│   ├── risk_register/
│   │   ├── Business_Risks.md
│   │   ├── Client_Risks.md
│   │   ├── Talent_Risks.md
│   │   └── Technical_Risks.md
│   │
│   └── competitive_intelligence/
│       ├── Market_Landscape.md
│       ├── Win_Loss_Analysis.md
│       └── Positioning_Strategy.md
│
├── decision-frameworks/             # Structured decision support
│   ├── Should_We_Take_This_Project.md
│   ├── Should_We_Hire_Now.md
│   ├── Should_We_Fire_This_Client.md
│   ├── Should_We_Build_vs_Partner.md
│   ├── Pricing_This_Deal.md
│   └── Resource_Allocation.md
│
├── rhythms/                         # Operating cadence templates
│   ├── daily/
│   │   └── Standup_Template.md
│   ├── weekly/
│   │   ├── Sales_Review.md
│   │   ├── Delivery_Review.md
│   │   ├── Team_1on1_Template.md
│   │   └── Leadership_Sync.md
│   ├── monthly/
│   │   ├── Financial_Review.md
│   │   ├── Client_QBR_Template.md
│   │   └── All_Hands_Template.md
│   └── quarterly/
│       ├── OKR_Review_Template.md
│       ├── Strategic_Offsite_Agenda.md
│       └── Board_Meeting_Template.md
│
└── integrations/                    # Cross-system intelligence
    ├── notion_sync/
    │   ├── Projects_Integration.md
    │   ├── SOPs_Integration.md
    │   └── Hours_Tracking_Integration.md
    ├── google_drive_sync/
    │   ├── Client_Folders_Map.md
    │   └── Meeting_Transcripts_Index.md
    └── go_high_level_sync/
        └── Pipeline_Integration.md
```

---

## Existing Tech Stack Integration

### Current State

| System | Current Use | Data We Need |
|--------|-------------|--------------|
| **Notion** | PM work, SOPs, hour tracking, CRM | Projects list, hours by project, SOPs content, client notes |
| **Google Drive** | Client data folders, meeting transcripts | Folder structure, transcript files, client documents |
| **Go High Level** | LinkedIn outreach CRM | Pipeline data, lead sources, win/loss, contact history |

### Integration Strategy

#### Option 1: MCP Servers (Recommended)

Build/use MCP servers to read directly from sources:
- **Notion MCP**: Read projects, hours, databases
- **Google Drive MCP**: Read transcripts, client folders
- **Go High Level API MCP**: Read pipeline, contacts

**Pros**: Real-time data, no manual sync, always current
**Cons**: Requires MCP setup, API keys, potential rate limits

#### Option 2: Export + Sync (Phase 1 Fallback)

Manual/scripted exports from each system:
- Notion → CSV exports of projects, hours
- Google Drive → Shared folder access for transcripts
- Go High Level → CSV export of pipeline

**Pros**: Simple to start, no API dependencies
**Cons**: Stale data, manual effort, error-prone

#### Option 3: Hybrid (Pragmatic)

- **Real-time critical data**: MCP for capacity, current projects, pipeline
- **Bulk historical data**: One-time imports for historical analysis
- **Documents**: Direct Google Drive MCP access for transcripts

### Data Flow Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    EXTERNAL SYSTEMS                          │
├─────────────────┬─────────────────┬─────────────────────────┤
│   Notion        │  Google Drive   │   Go High Level         │
│  (Projects,     │  (Transcripts,  │   (Pipeline,            │
│   Hours, SOPs)  │   Client Docs)  │    Contacts)            │
└────────┬────────┴────────┬────────┴─────────┬───────────────┘
         │                 │                  │
         │ MCP/API         │ MCP/API          │ API
         │                 │                  │
         ▼                 ▼                  ▼
┌─────────────────────────────────────────────────────────────┐
│              BUSINESS-BUILDER CONTEXT LAYER                  │
├─────────────────────────────────────────────────────────────┤
│  • Synthesizes data from all sources                         │
│  • Tracks coverage and freshness                             │
│  • Maintains derived intelligence                            │
│  • Enables AI-powered queries                                │
└─────────────────────────────────────────────────────────────┘
         │
         │ Claude Code Commands
         │
         ▼
┌─────────────────────────────────────────────────────────────┐
│                    DECISION OUTPUTS                          │
├─────────────────────────────────────────────────────────────┤
│  • Can we take this project?                                 │
│  • Who's at risk?                                            │
│  • Should we hire?                                           │
│  • What's our margin on X?                                   │
│  • Why did we lose that deal?                                │
└─────────────────────────────────────────────────────────────┘
```

### Specific Integrations to Build

#### 1. Notion Integration

**What to sync**:
- Projects table → `agency-intelligence/capacity_planning/Current_Capacity.md`
- Hours logged → `agency-intelligence/historical_data/Delivery_Velocity.md`
- SOPs database → `departments/*/docs/SOPs/`
- Client database → `agency-intelligence/client_portfolio/`

**Commands enabled**:
- `/capacity` - Real-time available hours
- `/margin <project>` - Hours logged vs budget
- `/utilization` - Team billable %

#### 2. Google Drive Integration

**What to sync**:
- Client folders list → `integrations/google_drive_sync/Client_Folders_Map.md`
- Meeting transcripts → Pull for synthesis when needed
- Project docs → Reference during decision making

**Commands enabled**:
- `/synthesize-transcript <meeting>` - Turn transcript into insights
- `/client-context <client>` - Pull all docs for a client

#### 3. Go High Level Integration

**What to sync**:
- Pipeline stages → `strategy/quarterly_planning/Q*_Pipeline.md`
- Win/loss data → `strategy/competitive_intelligence/Win_Loss_Analysis.md`
- Lead sources → `departments/sales/docs/Lead_Sources.md`

**Commands enabled**:
- `/pipeline-forecast` - Predicted close dates and values
- `/win-loss <timeframe>` - Why we're winning/losing deals
- `/lead-roi` - Which channels deliver best clients

---

## Implementation Phases

### Phase 0: Foundation (Week 1-2)

**Goal**: Set up repository structure and core system files

**Tasks**:
1. ✅ Create repository structure (directories above)
2. ⬜ Write `.claude/CLAUDE.md` (system instructions)
3. ⬜ Create `BUSINESS_BUILDER_ROADMAP.md` (this doc)
4. ⬜ Set up git repository with proper .gitignore
5. ⬜ Create first department template: `departments/_template/`

**Deliverables**:
- Empty folder structure
- CLAUDE.md with base instructions
- README.md explaining the system

**Success criteria**: Can run `ls` and see the full structure ready to populate

---

### Phase 1: Quick Wins - Core Intelligence (Week 3-4)

**Goal**: Build the 5 highest-value documents that unlock better decisions NOW

**Priority Documents**:

1. **Service_Catalog.md** (business-core/01_foundation/)
   - What we sell
   - Standard scope per service
   - Typical timeline per service
   - Starting price ranges

2. **Unit_Economics.md** (business-core/02_financial_model/)
   - Fully-loaded cost per team member
   - Target margin per service type
   - Break-even utilization rates
   - Monthly burn rate

3. **Estimation_Accuracy.md** (agency-intelligence/historical_data/)
   - Past 10-20 projects: estimated vs actual hours
   - Patterns: which project types go over estimate
   - Typical variance by service type
   - Lessons learned on estimation

4. **Current_Capacity.md** (agency-intelligence/capacity_planning/)
   - Team members and their current allocation
   - Available hours next 12 weeks
   - Projects in flight and end dates
   - Who's overloaded vs underutilized

5. **Client_Health_Scores.md** (agency-intelligence/client_portfolio/)
   - Current clients with health score (1-10)
   - Why each score (on-time, happy, paying, scope stable)
   - At-risk clients and mitigation plans
   - Renewal dates and likelihood

**Commands to build**:
- `/capture-context` (like `/synthesize` from proposal-builder)
- `/build-doc <type>` (generate a standard doc from context)

**Data sources**:
- Notion exports (projects, hours)
- Team interviews (capture tribal knowledge)
- Financial spreadsheets (costs, pricing)

**Success criteria**: Can answer these questions with data:
- "Can we take on a 12-week project starting Feb 1?"
- "What's our actual margin on retainer clients?"
- "Which clients are at risk this quarter?"

---

### Phase 2: Decision Frameworks (Week 5-6)

**Goal**: Build structured frameworks that turn intelligence into decisions

**Frameworks to build**:

1. **Should_We_Take_This_Project.md** (decision-frameworks/)
   - ICP fit scoring (1-10 scale with criteria)
   - Margin calculation (target vs actual)
   - Capacity check (do we have bandwidth?)
   - Strategic value assessment
   - Risk assessment
   - Go/no-go decision matrix

2. **Should_We_Hire_Now.md** (decision-frameworks/)
   - Utilization threshold (trigger: >85% for 4+ weeks)
   - Pipeline confidence (weighted by stage)
   - Cash runway requirement (3+ months of new salary)
   - Team load distribution check

3. **Pricing_This_Deal.md** (decision-frameworks/)
   - Cost-plus calculation (hours × loaded cost + margin)
   - Value-based pricing multiplier (if strategic)
   - Competitive pricing check
   - Payment terms impact on cash
   - Final price recommendation

**Commands to build**:
- `/should-we-bid <opportunity>` - Run project evaluation framework
- `/price-this <scope>` - Calculate recommended pricing
- `/hiring-check` - Should we hire now?

**Success criteria**: Leadership can make these decisions in 5 minutes instead of 2 hours:
- Take this project or pass?
- What should we charge?
- Time to hire?

---

### Phase 3: Department Context (Week 7-10)

**Goal**: Build complete context for each department

**Order of implementation**:
1. **Sales** (highest variance, most tribal knowledge)
2. **Delivery** (core process, biggest team)
3. **Operations** (support functions)
4. **Marketing** (usually documented already)
5. **Finance** (often already systematic)

**Per department**:
- Capture raw context (interviews, existing docs, Notion pages)
- Synthesize into Current_State.md
- Document process flows
- Extract/link to SOPs
- Define KPIs and current state
- Map dependencies on other departments

**Commands to build**:
- `/capture-department <name>` - Interactive context capture
- `/map-process <department>` - Generate process flow
- `/find-dependencies <department>` - Identify cross-dept needs

**Success criteria**: New hire in any department can read that department's folder and understand:
- How things work
- What the key processes are
- What success looks like
- Who to ask for what

---

### Phase 4: Strategic Planning Layer (Week 11-13)

**Goal**: Build quarterly and annual planning infrastructure

**Documents to build**:

1. **Q1 2026 Planning** (strategy/quarterly_planning/)
   - OKRs (3-5 objectives with key results)
   - Rocks (top priorities this quarter)
   - Metrics dashboard (KPIs to track)

2. **2026 Annual Plan** (strategy/annual_planning/)
   - Revenue plan (how we hit the number)
   - Service roadmap (new offerings, what we stop)
   - Team plan (hiring timeline, promotions)

3. **Risk Register** (strategy/risk_register/)
   - Business risks (top 10, mitigation plans)
   - Client risks (at-risk relationships)
   - Talent risks (flight risk, skill gaps)
   - Technical risks (tech debt, dependencies)

**Commands to build**:
- `/quarterly-review` - Score last quarter, plan next quarter
- `/risk-check` - Show top risks across all categories
- `/forecast <metric>` - Project forward based on trends

**Success criteria**:
- Quarterly planning takes 4 hours, not 2 days
- Everyone knows the top 3-5 priorities
- Risks are visible and tracked

---

### Phase 5: Learning Loop (Week 14-16)

**Goal**: Close the loop - track plan vs actual, learn, improve

**Infrastructure to build**:

1. **Postmortem System** (agency-intelligence/historical_data/)
   - Project Postmortems.md (structured learnings)
   - Win_Loss_Analysis.md (deal patterns)
   - Client_Churn_Analysis.md (why they leave)

2. **Actuals Tracking**
   - Estimation accuracy (ongoing)
   - Revenue plan vs actuals (monthly)
   - Utilization plan vs actuals (weekly)
   - Client health predictions vs churn (quarterly)

3. **Pattern Extraction**
   - What makes projects go well?
   - What causes estimates to blow up?
   - What predicts client churn?
   - What wins deals?

**Commands to build**:
- `/postmortem <project>` - Structured project retrospective
- `/analyze-pattern <topic>` - Extract insights from historical data
- `/compare-plan-actual <metric>` - Show variance and trends

**Success criteria**:
- Every project ends with documented learnings
- Estimation accuracy improves 10% per quarter
- Can predict which deals we'll win with 70%+ accuracy

---

### Phase 6: Advanced Intelligence (Week 17-20)

**Goal**: Build sophisticated cross-system intelligence

**Advanced capabilities**:

1. **The Context Engine** - `/ask` command
   - Answers questions across all business context
   - Examples:
     - `/ask "Why are our retainer clients more profitable?"`
     - `/ask "What technical debt affects multiple clients?"`
     - `/ask "Which team member should lead the React project?"`
   - Uses: Read, Glob, Grep across entire business-builder repo
   - Returns: Answer with sources and confidence level

2. **Reusable Asset Intelligence** (agency-intelligence/technical_assets/)
   - Integration_Patterns.md (how we've solved X integration before)
   - Reusable_Components.md (what we've built that we can reuse)
   - Architecture_Decisions.md (past technical choices and rationale)

3. **Proactive Alerts**
   - Client health drops → Alert in weekly review
   - Utilization hits threshold → Trigger hiring discussion
   - Margin on project drops below target → Flag for review
   - Cash runway drops below 6 months → Alert leadership

**Commands to build**:
- `/ask <question>` - Context engine query
- `/pattern-search <technology>` - Find similar past work
- `/alerts` - Show current alerts and triggers

**Success criteria**:
- Leadership asks AI before asking team members
- Decisions reference past patterns automatically
- Alerts catch problems before they're urgent

---

### Phase 7: Rhythms & Automation (Week 21-24)

**Goal**: Automate recurring processes and enforce operating rhythm

**Rhythm Implementation**:

1. **Daily Standup** (rhythms/daily/)
   - Template for async or sync standup
   - Auto-generate from project status
   - Track blockers across team

2. **Weekly Reviews** (rhythms/weekly/)
   - `/weekly-sales-review` - Generate sales review doc from Go High Level
   - `/weekly-delivery-review` - Generate delivery status from Notion
   - `/weekly-snapshot` - Leadership summary (5 min read)

3. **Monthly/Quarterly** (rhythms/monthly/, rhythms/quarterly/)
   - `/monthly-financial` - Actuals vs budget from accounting
   - `/quarterly-planning` - OKR review and next quarter setup

**Automation to build**:

1. **Slack/Email Integration**
   - Post weekly snapshot to leadership channel
   - Email quarterly review to board/advisors
   - Alert on critical client health drops

2. **Notion Sync**
   - Auto-update capacity doc from Notion projects
   - Sync hours logged to delivery velocity tracking

3. **Scheduled Commands** (via cron or similar)
   - Weekly: Generate snapshot
   - Monthly: Update financial actuals
   - Quarterly: Trigger planning process

**Success criteria**:
- Weekly snapshot generated automatically every Monday 9am
- No manual copy-paste between systems
- Operating rhythm is enforced by tooling, not memory

---

## Slash Commands Roadmap

### Priority 1: Foundation Commands (Phase 1)

| Command | Purpose | Inputs | Outputs |
|---------|---------|--------|---------|
| `/capture-context` | Synthesize messy inputs into structured context | Raw files, interviews, exports | Structured .md docs with metadata |
| `/build-doc <type>` | Generate standard doc from template + context | Doc type, existing context | Formatted doc following template |
| `/update-context` | Update existing doc with new information | New context files, existing doc | Updated doc with version tracking |

### Priority 2: Decision Support (Phase 2)

| Command | Purpose | Inputs | Outputs |
|---------|---------|--------|---------|
| `/should-we-bid <opportunity>` | Evaluate opportunity against frameworks | Opportunity details, ICP, capacity | Go/no-go recommendation with reasoning |
| `/price-this <scope>` | Calculate recommended pricing | Scope description, hours estimate | Price range with margin analysis |
| `/hiring-check` | Determine if it's time to hire | Current utilization, pipeline, cash | Hire now / wait / specific role |
| `/margin-check <project>` | Calculate actual vs target margin | Project name (pulls from Notion) | Margin analysis, variance explanation |

### Priority 3: Intelligence & Analysis (Phase 3-5)

| Command | Purpose | Inputs | Outputs |
|---------|---------|--------|---------|
| `/capacity` | Show current team capacity | None (reads from Notion/capacity docs) | Available hours next 12 weeks by person |
| `/client-health` | Generate client health scores | None (reads from projects, comms) | Health score by client with reasoning |
| `/postmortem <project>` | Structured project retrospective | Project name, optional inputs | Postmortem doc with learnings |
| `/win-loss <timeframe>` | Analyze why we win/lose deals | Timeframe (Q1 2026, 2025, etc.) | Pattern analysis with recommendations |
| `/estimate-accuracy` | Show estimation performance | None (reads historical data) | Accuracy by project type, trends |
| `/forecast <metric>` | Project metric forward | Metric name (revenue, utilization) | Forecast with confidence intervals |

### Priority 4: Strategic Planning (Phase 4)

| Command | Purpose | Inputs | Outputs |
|---------|---------|--------|---------|
| `/quarterly-review` | Score last quarter, plan next | Quarter (e.g., Q4 2025) | OKR scores, next quarter rocks |
| `/risk-check` | Show top risks across categories | None (reads risk register) | Top 10 risks, mitigation status |
| `/weekly-snapshot` | Generate leadership summary | None (reads all current state) | 1-page summary: delivery, sales, risks, cash |
| `/monthly-financial` | Financial review vs budget | Month (e.g., Dec 2025) | Actuals vs budget, variance analysis |

### Priority 5: Advanced Intelligence (Phase 6)

| Command | Purpose | Inputs | Outputs |
|---------|---------|--------|---------|
| `/ask <question>` | Query across all business context | Natural language question | Answer with sources and confidence |
| `/pattern-search <topic>` | Find similar past work | Technology, problem, or client type | Relevant past projects, decisions, patterns |
| `/alerts` | Show current alerts and triggers | None (checks thresholds) | Active alerts with recommended actions |
| `/compare-to <project>` | Compare current project to past one | Current + past project names | Similarities, differences, lessons learned |

### Supporting Commands (All Phases)

| Command | Purpose | Inputs | Outputs |
|---------|---------|--------|---------|
| `/status` | Show business-builder system status | None | Doc coverage, freshness, gaps |
| `/sync <system>` | Manual sync from external system | System name (notion, drive, ghl) | Updated docs with new data |
| `/verify-docs` | Consistency check across docs | Optional: specific doc or category | Conflicts, stale docs, missing dependencies |

---

## Skills & Automation

### Skills (Auto-Applied Standards)

**Priority 1**:
- `doc-metadata` - Auto-apply standard headers (version, sources, owner, last updated, completeness)
- `source-citation` - Consistent citation format when extracting from context

**Priority 2**:
- `coverage-tracking` - Track what % of source was synthesized, re-read guidance
- `decision-rationale` - When making recommendations, always explain WHY
- `kpi-standards` - Standard format for KPIs (metric, target, current, trend, owner)

**Priority 3**:
- `cross-reference-checker` - Flag when docs reference other docs that don't exist
- `freshness-reminder` - Warn when doc hasn't been updated per its update frequency

### Hooks (Guardrails & Automation)

**Priority 1**:
- `protect-context` - Block writes to `context/` directories (like `references/` in proposal-builder)
- `update-modified-date` - Auto-update "Last Updated" in doc headers on edit

**Priority 2**:
- `require-owner` - Warn if creating doc without owner specified
- `sync-trigger` - After updating certain docs, suggest related docs to update

**Priority 3**:
- `version-increment` - Auto-increment version number on significant edits
- `changelog-reminder` - Prompt to update changelog section when editing

### MCP Servers

**Priority 1**:
- **Notion MCP** - Read projects, hours, databases
- **Google Drive MCP** - Read client folders, transcripts

**Priority 2**:
- **Go High Level API MCP** - Read pipeline, contacts, deal history

**Priority 3**:
- **Slack MCP** - Post summaries, alerts to channels
- **Email MCP** - Send reports to stakeholders

---

## Success Metrics

### System Health Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| **Doc coverage** | 80% of critical business areas documented | Count of docs / total docs needed |
| **Doc freshness** | 90% of docs updated within frequency target | Docs updated on time / total docs |
| **Context completeness** | 70%+ coverage on synthesized docs | Avg coverage % across all docs |
| **Command usage** | 20+ command uses per week | Command invocation count |
| **Decision time reduction** | 50% faster strategic decisions | Time to decision (before vs after) |

### Business Impact Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| **Estimation accuracy** | ±15% variance | (Actual - Estimate) / Estimate |
| **Capacity utilization** | 75-85% billable | Billable hours / total hours |
| **Client retention** | 90%+ annual retention | Clients renewed / total clients |
| **Win rate** | 40%+ on qualified opps | Deals won / deals bid |
| **Margin achievement** | ±5% of target margin by service | Actual margin / target margin |

### Adoption Metrics (First 90 Days)

| Week | Milestone | Success Criteria |
|------|-----------|------------------|
| **Week 4** | Phase 1 complete | 5 core docs exist, can answer 3 key questions with data |
| **Week 8** | Phase 2 complete | Decision frameworks built, 3 decisions made using frameworks |
| **Week 12** | Phase 3 complete | 2+ departments fully documented, SOPs linked |
| **Week 16** | Phase 4 complete | Q2 2026 planning done using system, leadership adopts weekly snapshot |
| **Week 24** | Phase 7 complete | Automated weekly snapshot, 80%+ doc coverage |

---

## Next Steps

### Immediate Actions (Next 48 Hours)

1. ✅ **Save this roadmap** as `/business-builder/BUSINESS_BUILDER_ROADMAP.md`
2. ⬜ **Create directory structure** (run script or manually create folders)
3. ⬜ **Write CLAUDE.md** (base instructions for the system)
4. ⬜ **Choose pilot department** (recommend: Sales or Delivery)
5. ⬜ **Identify Phase 1 data sources**:
   - Export project list from Notion (last 12 months)
   - Export hours logged by project from Notion
   - Gather financial data (team costs, pricing)
   - List current clients with basic status

### Week 1 Decisions Needed

- [ ] **MCP vs Export?** - Will we set up MCP servers or use exports for Phase 1?
- [ ] **Pilot department?** - Which department to document first?
- [ ] **Owner assignment** - Who owns maintaining this system?
- [ ] **Update frequency** - How often will we update core docs? (Weekly? Monthly?)

### Risks & Mitigations

| Risk | Impact | Mitigation |
|------|--------|------------|
| **Team doesn't adopt system** | High - system becomes stale | Make commands solve real pain points, show value early |
| **Data sync overhead too high** | Medium - system falls behind reality | Invest in MCP early, automate as much as possible |
| **Too much documentation** | Medium - analysis paralysis | Focus on decision-enabling docs only, skip nice-to-haves |
| **Loss of context owner** | High - tribal knowledge lost again | Document as we go, multiple people involved in capture |
| **Integration breaks** | Medium - stale data | Build freshness checks, alert when data is >X days old |

---

## Appendix: Key Differences from proposal-builder

### What We Keep

✅ **Directory structure pattern** (context/ + docs/ separation)
✅ **Synthesis workflow** (messy inputs → structured docs)
✅ **Metadata tracking** (sources, version, completeness)
✅ **Slash command architecture** (explicit user actions)
✅ **Coverage assessment** (how much tribal knowledge is captured)
✅ **Git versioning** (track changes over time)

### What We Change

🔄 **Update frequency**: One-time → Continuous
🔄 **Audience**: External (clients) → Internal (team)
🔄 **Validation**: Client gates → Data validation + peer review
🔄 **Scope**: Per-project → Entire business
🔄 **Time horizon**: Weeks-months → Years
🔄 **Dependencies**: Linear → Network graph

### What We Add

✨ **Integration layer** (Notion, Drive, Go High Level)
✨ **Decision frameworks** (structured decision support)
✨ **Learning loop** (plan vs actual tracking)
✨ **Strategic planning** (OKRs, rocks, metrics)
✨ **Operating rhythms** (daily, weekly, monthly, quarterly)
✨ **Context engine** (`/ask` across all business context)
✨ **Proactive alerts** (threshold-based notifications)

---

**END OF ROADMAP**

*This document is a living roadmap. Update as we learn and evolve the system.*

*For questions or suggestions, see: [Your preferred contact method]*
