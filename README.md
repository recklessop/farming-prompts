# Farm Management AI Toolkit

A suite of 14 expert-level AI system prompts designed to help farmers make better decisions across financial, agronomic, and business operations. Each prompt turns an AI into a specialized paid farm advisor — not a chatbot, but a knowledgeable consultant that gathers data, runs analysis, and delivers actionable recommendations.

## Getting Started

There are several ways to use this toolkit, depending on how you interact with Claude. Pick the method that fits your workflow.

### Option 1: Claude Projects (Recommended — No Setup Required)

[Claude Projects](https://claude.ai) let you attach files that Claude references throughout a conversation. This is the easiest way to use the toolkit.

1. Go to [claude.ai](https://claude.ai) and create a new Project
2. Download the files you want from this repo (or clone the whole repo — see Option 3)
3. Add `CLAUDE.md` to the project's **Project Knowledge** — this is the router that directs Claude to the right advisor based on your question
4. Add the `prompts/` folder contents to Project Knowledge as well, so Claude can load the specialized prompts when needed
5. Start a conversation and just describe what you need help with — Claude will take it from there

**Tip:** You don't have to add all 14 prompts. If you only need help with grain marketing and crop insurance, just add those two prompt files plus `CLAUDE.md`.

### Option 2: Use a Single Prompt Directly

If you know exactly which advisor you need, skip the router entirely:

1. Open any conversation with Claude (claude.ai, the Claude app, or the API)
2. Copy the contents of the specific prompt file you want (e.g., `prompts/financial/breakeven-grain-marketing.md`)
3. Paste it as your first message, or use it as a **System Prompt** if you're using the API
4. Start your conversation — Claude will follow that prompt's data collection and analysis process

This works great for focused, single-topic sessions.

### Option 3: Claude Code (For Developers / Power Users)

If you use [Claude Code](https://claude.ai/claude-code) (Anthropic's CLI tool), this repo works automatically:

1. Clone the repo:
   ```bash
   git clone https://github.com/recklessop/farming-prompts.git
   cd farming-prompts
   ```
2. Run `claude` from inside the repo directory
3. Claude Code automatically reads the `CLAUDE.md` file and has access to all prompt files in the repo
4. Just ask your question — Claude will read the appropriate prompt file and follow its instructions

### Option 4: Other AI Tools (ChatGPT, etc.)

These prompts work with any AI that accepts system prompts or custom instructions:

1. Copy the contents of the prompt file you want to use
2. Paste it into the system prompt, custom instructions, or "GPT builder" instructions field
3. Start your conversation

**Note:** The `CLAUDE.md` router relies on the AI being able to read files from the project, which is specific to Claude Projects and Claude Code. For other tools, use individual prompts directly (Option 2).

### Which Option Should I Pick?

| Situation | Best Option |
|---|---|
| I'm a farmer who just wants to ask questions on claude.ai | **Option 1** — Claude Projects |
| I need help with one specific topic right now | **Option 2** — Single prompt, paste it in |
| I'm a developer or use the terminal | **Option 3** — Claude Code |
| I use ChatGPT or another AI | **Option 4** — Copy/paste individual prompts |

## The Toolkit

### Financial Decisions

| Prompt | What It Does |
|---|---|
| [Breakeven & Grain Marketing](prompts/financial/breakeven-grain-marketing.md) | Calculates cost of production, breakeven prices at multiple yield scenarios, and builds a grain marketing plan with forward contracts, basis contracts, options strategies, and target price triggers |
| [Crop Insurance](prompts/financial/crop-insurance.md) | Compares RP vs. YP vs. RP-HPE, evaluates coverage levels 50-85%, analyzes unit structure options, factors in SCO/ECO, and recommends coverage based on breakeven and risk tolerance |
| [Government Programs](prompts/financial/government-programs.md) | Navigates ARC-CO vs. PLC elections, EQIP cost-share opportunities, CRP eligibility, and other USDA programs with payment estimates and deadline tracking |
| [Equipment Analyzer](prompts/financial/equipment-analyzer.md) | Buy vs. lease vs. custom hire analysis with full cost-per-acre calculations, timeliness value quantification, and tax depreciation scenarios (Section 179, MACRS) |
| [Farm Labor & Hiring](prompts/financial/farm-labor-hiring.md) | Full hiring analysis including W-2 vs. 1099 classification, family employment tax strategies, loaded cost calculations, ag labor law compliance, and recruitment channels (FFA, 4-H, H-2A) |

### Agronomy & Field Management

| Prompt | What It Does |
|---|---|
| [Crop Fertility Advisor](prompts/agronomy/crop-fertility-advisor.md) | Builds a complete fertilizer plan from soil test data — N/P/K/S rates, product selection, cost per acre, and timing recommendations using MRTN and Tri-State guidelines |
| [Planting Advisor](prompts/agronomy/planting-advisor.md) | Hybrid/variety selection by soil type and maturity zone, variable seeding rates by productivity zone, planting date windows with yield penalty curves, and seed treatment evaluation |
| [Herbicide & Pest Management](prompts/agronomy/herbicide-pest-management.md) | Complete spray program design with resistance management front and center — pre/post herbicide selection, insect scouting thresholds, fungicide ROI analysis, and drift/buffer compliance |
| [Cover Crop & Soil Health](prompts/agronomy/cover-crop-soil-health.md) | Species and mix recommendations by goal, planting windows, termination strategies, cost-benefit analysis, herbicide carryover risk assessment, and EQIP/CSP integration |
| [Drainage & Tile](prompts/agronomy/drainage-tile.md) | Field drainage evaluation, pattern tile spacing by soil type, cost estimation, ROI/payback calculation, and environmental considerations (controlled drainage, saturated buffers) |

### Business Strategy & Long-Term Planning

| Prompt | What It Does |
|---|---|
| [Cash Rent Analyzer](prompts/business-strategy/cash-rent-analyzer.md) | Side-by-side comparison of cash renting vs. farming with full cost accounting, risk quantification, breakeven acreage analysis, and flex rent/crop share alternatives |
| [Land Purchase](prompts/business-strategy/land-purchase.md) | Farmland acquisition analysis — affordable price per acre, amortization schedules, cash flow projections, financing options (FSA, commercial, seller), and stress-test scenarios |
| [Succession Planner](prompts/business-strategy/succession-planner.md) | Guides multi-generational farm families through transition decisions — entity structures, fair vs. equal, buy-in strategies, estate tax planning, and timeline milestones |
| [Retirement Planner](prompts/business-strategy/retirement-planner.md) | Personal financial independence planning for farmers — Social Security optimization, converting illiquid farm wealth to income, healthcare bridge strategies, and tax-efficient drawdown |
| [Livestock Integration](prompts/business-strategy/livestock-integration.md) | Evaluates adding cattle to a grain operation — enterprise budgets, infrastructure costs, stocking rates, grain/livestock synergies, and market cycle risk assessment |

## Design Principles

- **Expert advisor, not chatbot.** Every prompt positions the AI as a paid consultant who gathers data methodically, runs real analysis, and gives honest recommendations.
- **Conversational data gathering.** Questions come in natural groups of 2-3, not a 20-item checklist. The AI builds on what the farmer shares.
- **Plain language first.** Technical terms are introduced with context. "Phosphorus" before "P2O5."
- **Region-aware.** Recommendations account for geography — soil types, university extension guidelines, basis levels, labor laws, and program availability all vary by location.
- **Interconnected.** Prompts cross-reference each other where decisions overlap (breakeven feeds into marketing and insurance; succession and retirement are two sides of the same coin).
- **Actionable deliverables.** Every prompt offers to generate spreadsheets, summaries, or documents the farmer can take to their lender, landlord, insurance agent, or family meeting.
- **Honest about limits.** Financial prompts include disclaimers and recommend working with CPAs, attorneys, commodity brokers, and insurance agents where appropriate.

## Project Structure

```
farming-prompts/
├── CLAUDE.md                              # Router — start here
├── claude-plan.md                         # Master build plan
├── prompts/
│   ├── agronomy/
│   │   ├── crop-fertility-advisor.md
│   │   ├── planting-advisor.md
│   │   ├── herbicide-pest-management.md
│   │   ├── cover-crop-soil-health.md
│   │   └── drainage-tile.md
│   ├── business-strategy/
│   │   ├── cash-rent-analyzer.md
│   │   ├── land-purchase.md
│   │   ├── succession-planner.md
│   │   ├── retirement-planner.md
│   │   └── livestock-integration.md
│   └── financial/
│       ├── breakeven-grain-marketing.md
│       ├── crop-insurance.md
│       ├── government-programs.md
│       ├── equipment-analyzer.md
│       └── farm-labor-hiring.md
```

## Contributing

Ideas for new prompts or improvements to existing ones are welcome. Each prompt should follow the established structure: role statement, approach, data collection, analysis framework, key principles, reference data, and output format.

## License

This project is licensed under the [GNU General Public License v3.0](LICENSE). You're free to use, modify, and distribute these prompts, but any derivative work must also be released under GPL v3 and include attribution. This ensures improvements stay open and accessible to the farming community.
