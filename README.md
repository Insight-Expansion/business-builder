# Business Builder

**AI-powered business intelligence and operating system for software agencies.**

## What This Is

A Claude Code-powered system that transforms scattered business context (Notion docs, meeting transcripts, interviews, data exports) into structured intelligence that enables fast, data-driven decision making.

**Think of it as**: Your business's second brain - captures tribal knowledge, tracks what actually happens vs what you planned, and helps you make better decisions faster.

---

## The Problem

Software agencies struggle with:
- **Scattered context** across Notion, Google Drive, Slack, email, and people's heads
- **Slow strategic decisions** - "Can we take this project?" takes hours of hunting for data
- **Lost tribal knowledge** - Key insights locked in one person's memory
- **No learning loop** - We estimate, deliver, but don't track accuracy or extract patterns
- **Weak business intelligence** - Hard to answer: "Why did we lose that deal?" or "Which clients are at risk?"

---

## The Solution

**business-builder** provides:

1. **Structured context capture** - Synthesize messy inputs into organized docs with metadata
2. **Decision frameworks** - Answer key questions fast: Can we take this project? Should we hire? How to price this?
3. **Intelligence layer** - Track estimation accuracy, capacity, client health, win/loss patterns
4. **Learning loop** - Compare plan vs actual, extract patterns, improve over time
5. **Integration with existing tools** - Reads from Notion (projects, hours), Google Drive (transcripts), Go High Level (pipeline)
6. **AI-powered queries** - Ask questions across all business context, get answers with sources

---

## How It Works

### 1. Capture Context

Dump raw inputs (interviews, exports, meeting notes) into `context/` directories:

```bash
departments/sales/context/
├── 01_sales_team_interview.md
├── 02_go_high_level_pipeline_export.csv
└── 03_current_process_notes.md
```

Run `/capture-context sales` → Get organized documentation:

```
departments/sales/docs/
├── Context_Map.md          # Catalog of sources with coverage tracking
├── Current_State.md        # How things work now
├── KPIs.md                 # Metrics with targets and actuals
├── Process_Flows.md        # Detailed workflows
└── Dependencies.md         # Cross-department needs
```

### 2. Build Intelligence

Core business intelligence documents answer specific questions:

- **Can we take this project?** → `Unit_Economics.md`, `Current_Capacity.md`, `ICP_Profile.md`
- **Should we hire now?** → `Team_Utilization.md`, `Pipeline_Requirements.md`, `Cash_Flow.md`
- **Why are estimates wrong?** → `Estimation_Accuracy.md` (tracks estimated vs actual)
- **Which clients are at risk?** → `Client_Health_Scores.md` (health by client with evidence)

### 3. Make Decisions Fast

Use decision frameworks:

```bash
/should-we-bid <opportunity>
```

→ Evaluates against:
- ICP fit (scoring criteria)
- Margin calculation (target vs projected)
- Capacity check (do we have bandwidth?)
- Strategic value assessment
- Risk scoring

→ Output: **Go/No-go recommendation with reasoning and data sources**

### 4. Track & Learn

Learning loop closes the gap between plan and reality:

- Every project: Estimated hours vs actual hours logged
- Every quarter: Revenue plan vs actuals, OKR scoring
- Every deal: Why we won/lost (pattern analysis)
- Every client: Health score predictions vs actual churn

→ **System gets smarter over time**

---

## Structure

```
business-builder/
├── business-core/              # Foundation (vision, financial model, delivery framework)
│   ├── 01_foundation/          # Vision, ICP, service catalog, pricing
│   ├── 02_financial_model/     # Unit economics, margins, cash flow
│   ├── 03_delivery_framework/  # How we estimate, build, and deliver
│   ├── 04_client_lifecycle/    # Sales to delivery to offboarding
│   └── 05_people_system/       # Hiring, growth, compensation
│
├── departments/                # Department-specific context and SOPs
│   ├── sales/
│   ├── delivery/
│   ├── marketing/
│   ├── operations/
│   └── finance/
│
├── agency-intelligence/        # Data-driven insights
│   ├── historical_data/        # Estimation accuracy, postmortems, churn analysis
│   ├── capacity_planning/      # Team utilization, available hours, hiring forecast
│   ├── client_portfolio/       # Health scores, LTV analysis, upsell opportunities
│   └── technical_assets/       # Reusable components, integration patterns
│
├── strategy/                   # Strategic planning and execution
│   ├── quarterly_planning/     # OKRs, rocks, metrics dashboards
│   ├── annual_planning/        # Revenue plan, service roadmap, team plan
│   ├── risk_register/          # Business, client, talent, technical risks
│   └── competitive_intelligence/ # Win/loss analysis, positioning
│
├── decision-frameworks/        # Structured decision support
│   ├── Should_We_Take_This_Project.md
│   ├── Should_We_Hire_Now.md
│   ├── Pricing_This_Deal.md
│   └── ...
│
├── rhythms/                    # Operating cadence templates
│   ├── daily/                  # Standup templates
│   ├── weekly/                 # Sales review, delivery review, 1-on-1s
│   ├── monthly/                # Financial review, client QBRs, all-hands
│   └── quarterly/              # OKR review, strategic offsite
│
└── integrations/               # External system sync
    ├── notion_sync/            # Projects, hours, SOPs
    ├── google_drive_sync/      # Client folders, transcripts
    └── go_high_level_sync/     # Pipeline, contacts, deal history
```

---

## Key Commands

### Context Capture
- `/capture-context [area]` - Synthesize raw inputs into structured docs
- `/update-context [area]` - Update docs with new information

### Decision Support
- `/should-we-bid <opportunity>` - Evaluate opportunity against frameworks
- `/price-this <scope>` - Calculate recommended pricing
- `/hiring-check` - Determine if it's time to hire
- `/margin-check <project>` - Actual vs target margin

### Intelligence & Analysis
- `/capacity` - Show current team availability
- `/client-health` - Generate health scores by client
- `/estimate-accuracy` - Historical estimation performance
- `/postmortem <project>` - Structured retrospective
- `/win-loss <timeframe>` - Pattern analysis of deals

### Strategic Planning
- `/quarterly-review` - Score last quarter, plan next
- `/risk-check` - Show top risks across categories
- `/weekly-snapshot` - Generate leadership summary

### Advanced
- `/ask <question>` - Query across all business context
- `/pattern-search <topic>` - Find similar past work
- `/compare-to <project>` - Compare to past projects

---

## Quick Start

### Phase 0: Setup (You are here ✅)

```bash
# Repository structure created ✅
# CLAUDE.md written ✅
# /capture-context command built ✅
```

### Phase 1: Build 5 Core Intelligence Docs (Next 2 weeks)

The 5 highest-value documents that unlock better decisions NOW:

1. **Service_Catalog.md** - What you sell, standard scope, pricing
2. **Unit_Economics.md** - Cost per team member, target margins, break-even
3. **Estimation_Accuracy.md** - Past projects: estimated vs actual hours
4. **Current_Capacity.md** - Team availability next 12 weeks
5. **Client_Health_Scores.md** - Current clients with risk assessment

**How to build**:
```bash
# 1. Gather context sources
# - Export projects list from Notion (last 12 months)
# - Export hours logged by project
# - Gather financial data (team costs, pricing)
# - List current clients with status

# 2. Create context files
mkdir -p business-core/context
# Add your exports and notes to this directory

# 3. Capture context
/capture-context unit-economics
/capture-context service-catalog
# ... etc

# 4. Use the intelligence
/should-we-bid "New client: $80K project, 12 weeks, React + Node.js"
/margin-check "ProjectXYZ"
/capacity
```

### Phase 2: Decision Frameworks (Week 5-6)

Build frameworks for recurring decisions:
- Should we take this project?
- How should we price this?
- Is it time to hire?

### Phase 3: Department Documentation (Week 7-10)

Pick one department to pilot (recommend: Sales or Delivery):
```bash
# Add context sources
departments/sales/context/
├── 01_team_interview.md
├── 02_crm_export.csv
└── 03_process_notes.md

# Capture context
/capture-context sales

# Result: Complete department documentation
# - Current state, process flows, KPIs, dependencies
```

---

## Integration with Existing Tools

### Current Stack
- **Notion**: PM work, SOPs, hour tracking, CRM
- **Google Drive**: Client folders, meeting transcripts
- **Go High Level**: LinkedIn outreach CRM

### Integration Strategy

**Phase 1: Manual Exports** (Start here)
- Export projects, hours from Notion → CSV
- Access transcripts from Google Drive
- Export pipeline from Go High Level → CSV
- Run `/capture-context` to synthesize

**Phase 2: MCP Servers** (After Phase 1 works)
- Set up Notion MCP → Real-time project/hours data
- Set up Google Drive MCP → Direct transcript access
- Set up Go High Level API → Live pipeline data
- Auto-sync on schedule

**Phase 3: Automated Alerts** (Advanced)
- Client health drops → Alert in Slack
- Utilization hits threshold → Trigger hiring discussion
- Margin below target → Flag for review
- Generate weekly snapshot automatically

---

## Design Philosophy

### 1. Decision-First
Every doc answers a specific question. No "nice to know" docs that don't enable decisions.

### 2. Living Documentation
This isn't write-once. Update frequencies matter:
- Intelligence docs: Weekly to monthly (data-driven)
- Strategic docs: Set quarterly, review monthly
- Foundation docs: Review quarterly, update as needed

### 3. Coverage Tracking
Synthesis is lossy compression. Track what % was captured, when to re-read originals.

### 4. Learning Loop
Track plan vs actual. Extract patterns. Improve estimates, forecasts, and decisions over time.

### 5. Metadata Matters
Every doc tracks: version, sources, owner, update frequency, downstream dependencies, completeness.

---

## What Makes This Different

### vs Notion/Wiki
- **Synthesizes** messy inputs, not just storage
- **Tracks coverage** - know when docs are sufficient vs when to consult source
- **AI-powered queries** - ask questions across all context
- **Decision frameworks** - structured evaluation, not just documentation

### vs Dashboards/BI Tools
- **Qualitative + quantitative** - captures interviews, meetings, tribal knowledge (not just metrics)
- **Learning loop** - tracks accuracy of predictions, improves over time
- **Strategic context** - connects data to decisions and strategy

### vs Consultants
- **Always available** - no waiting for meetings or reports
- **Learns your business** - gets smarter as you add context
- **Transparent reasoning** - shows sources and logic
- **Continuous improvement** - updates as business evolves

---

## Success Metrics

### System Health
- **Doc coverage**: % of critical business areas documented
- **Doc freshness**: % updated within target frequency
- **Command usage**: Uses per week
- **Decision time reduction**: Time to strategic decisions (before vs after)

### Business Impact
- **Estimation accuracy**: ±% variance (target: ±15%)
- **Capacity utilization**: % billable (target: 75-85%)
- **Client retention**: % annual (target: 90%+)
- **Win rate**: % on qualified opportunities (target: 40%+)
- **Margin achievement**: Actual vs target by service (target: ±5%)

---

## Roadmap

See [BUSINESS_BUILDER_ROADMAP.md](BUSINESS_BUILDER_ROADMAP.md) for detailed implementation plan.

**Quick version**:
- ✅ **Phase 0 (Week 1-2)**: Foundation setup - COMPLETE
- 🔄 **Phase 1 (Week 3-4)**: 5 core intelligence docs - IN PROGRESS
- ⬜ **Phase 2 (Week 5-6)**: Decision frameworks
- ⬜ **Phase 3 (Week 7-10)**: Department documentation
- ⬜ **Phase 4 (Week 11-13)**: Strategic planning layer
- ⬜ **Phase 5 (Week 14-16)**: Learning loop infrastructure
- ⬜ **Phase 6 (Week 17-20)**: Advanced intelligence (context engine)
- ⬜ **Phase 7 (Week 21-24)**: Rhythms & automation

---

## Contributing

This is your business intelligence system. As you use it:

1. **Add context continuously** - New interviews, meeting notes, data exports
2. **Update docs regularly** - Follow update frequencies in metadata
3. **Track actuals** - Log estimated vs actual, update intelligence docs
4. **Extract patterns** - Run postmortems, analyze wins/losses, identify trends
5. **Improve frameworks** - Refine decision criteria based on outcomes

**The system gets smarter as you feed it more context and close the learning loop.**

---

## Support & Documentation

- **Full roadmap**: [BUSINESS_BUILDER_ROADMAP.md](BUSINESS_BUILDER_ROADMAP.md)
- **System instructions**: [.claude/CLAUDE.md](.claude/CLAUDE.md)
- **Slash commands**: [.claude/commands/](.claude/commands/)
- **Inspiration**: Adapted from [proposal-builder](../proposal-builder/) system

---

## Next Actions

### Immediate (Next 48 hours)
1. ✅ Set up repository structure
2. ✅ Write CLAUDE.md and README
3. ✅ Build `/capture-context` command
4. ⬜ **Decide**: Which department to pilot? (Sales or Delivery recommended)
5. ⬜ **Gather**: Phase 1 data sources (Notion exports, financial data, client list)

### Week 1
- Create `business-core/context/` directory
- Add financial data (team costs, pricing, project budgets)
- Run `/capture-context unit-economics`
- Run `/capture-context service-catalog`

### Week 2
- Add historical project data (estimated vs actual hours)
- List current team with allocation
- List current clients with status
- Run `/capture-context estimation-accuracy`
- Run `/capture-context current-capacity`
- Run `/capture-context client-health`

### End of Week 2 Goal
**Answer these questions with data**:
- Can we take on a 12-week project starting next month?
- What's our actual margin on retainer clients vs fixed-price?
- Which clients are at risk this quarter and why?

---

**Let's build your second brain.** 🧠

---

*Last updated: 2026-01-11*
*Status: Phase 0 complete, Phase 1 starting*
