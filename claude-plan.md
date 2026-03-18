# Farm Management AI Toolkit — Master Build Plan

## Overview

A suite of 12 AI system prompts designed to help farmers make better decisions across financial, agronomic, and business operations. Each prompt is a standalone system instruction that can be used in Claude projects, custom instructions, or integrated into farm management applications.

**Already Completed:**
- ✅ Crop Fertility Advisor (`crop_fertility_advisor_prompt.md`)

---

## Phase 1 — Crop Year Financial Decisions (Build First)

These prompts address time-sensitive decisions that directly impact profitability for the current crop year. The Breakeven Calculator feeds into nearly every other tool, so it's the foundation.

### 1. Breakeven Calculator & Grain Marketing Advisor
**File:** `breakeven_grain_marketing_prompt.md`
**Status:** 🔲 Not Started
**Priority:** Highest — every marketing and insurance decision depends on knowing your breakeven

**What it does:**
- Collects all variable and fixed costs per acre per crop (seed, fertilizer, chemicals, fuel, machinery, labor, insurance, rent/mortgage, taxes)
- Calculates breakeven price per bushel at various yield scenarios
- Compares breakeven to current futures prices and local cash bids
- Walks through marketing strategies based on the farmer's risk profile:
  - Forward cash contracts (pros, cons, timing)
  - Basis contracts
  - Hedge-to-arrive contracts
  - Put options (floor price protection)
  - Call options (re-ownership after selling)
  - Minimum price contracts
- Recommends a marketing plan that spreads sales across multiple price points
- Factors in storage costs vs. selling at harvest
- Generates a marketing calendar with target prices and action triggers

**Key data to collect:**
- All production costs (or pull from fertility advisor if already built)
- Fixed costs (mortgage, rent, taxes, insurance)
- Current and historical basis for the farmer's local elevator
- Farmer's risk tolerance (conservative, moderate, aggressive)
- Storage capacity and associated costs
- Existing forward contracts or hedges already in place

---

### 2. Crop Insurance Decision Helper
**File:** `crop_insurance_prompt.md`
**Status:** 🔲 Not Started
**Priority:** High — signup deadlines are firm (March 15 for spring crops in most states)

**What it does:**
- Collects APH (Actual Production History) yields and unit structure
- Compares Revenue Protection (RP) vs. RP with Harvest Price Exclusion vs. Yield Protection
- Evaluates coverage levels (50%-85%) with premium vs. expected indemnity tradeoffs
- Incorporates ARC/PLC interaction (can't stack certain coverages)
- Calculates premium cost per acre at each coverage level
- Shows "what if" scenarios: what yield or price drop triggers a payment?
- Compares enterprise units vs. optional units vs. basic units
- Factors in SCO (Supplemental Coverage Option) and ECO (Enhanced Coverage Option)
- Addresses Prevented Planting provisions
- Recommends a coverage strategy based on breakeven and risk tolerance

**Key data to collect:**
- APH yields by unit (farm/county/enterprise)
- Number of units and acres per unit
- County and crop
- Expected commodity price (from RMA projected price)
- Farmer's breakeven price per bushel (from Breakeven Calculator)
- Previous years' insurance elections and any indemnity history
- Risk tolerance level

---

### 3. Government Program Navigator (ARC/PLC, EQIP, CRP)
**File:** `government_programs_prompt.md`
**Status:** 🔲 Not Started
**Priority:** High — ARC/PLC elections and EQIP signup windows are time-sensitive

**What it does:**
- Walks through ARC-CO (Agriculture Risk Coverage - County) vs. PLC (Price Loss Coverage) election
  - Compares expected payments under each program given current price forecasts
  - Explains interaction with SCO/ECO crop insurance
  - Accounts for payment limitations and AGI caps
- Evaluates EQIP (Environmental Quality Incentives Program) opportunities
  - Identifies eligible practices for the farmer's operation (cover crops, nutrient management, drainage water management, etc.)
  - Estimates cost-share payment rates
  - Walks through application ranking factors
- Assesses CRP (Conservation Reserve Program) eligibility
  - General signup vs. continuous signup vs. SAFE
  - Compares CRP rental rates to farming profitability
  - Evaluates whether marginal ground should go into CRP
- Covers other programs: CSP, ACEP, emergency programs (LFP, ELAP, NAP)

**Key data to collect:**
- FSA farm numbers and base acres
- PLC payment yields and ARC benchmark yields
- Current ARC/PLC election status
- Adjusted Gross Income (for payment limitation purposes)
- Conservation needs and resource concerns on the farm
- Any existing conservation plans or contracts
- Soil productivity ratings for CRP evaluation

---

### 4. Equipment Buy vs. Lease vs. Custom Hire Analyzer
**File:** `equipment_analyzer_prompt.md`
**Status:** 🔲 Not Started
**Priority:** Medium-High — affects cost per acre in all other calculations

**What it does:**
- Collects current equipment inventory and condition
- For a specific equipment need, compares three options:
  - **Buy (new or used):** Purchase price, financing terms, depreciation (tax and economic), maintenance, insurance, repair history curves, salvage value
  - **Lease:** Annual payment, terms, buyout option, included maintenance
  - **Custom hire:** Local custom rates, availability/timeliness risk, quality control
- Calculates cost per acre and cost per hour for each option
- Factors in timeliness value — what does a 3-day planting delay cost in yield?
- Considers tax implications (Section 179, bonus depreciation, MACRS schedules)
- Evaluates the "minimum acres to justify ownership" threshold
- Addresses the hidden costs: storage, shop space, labor for maintenance

**Key data to collect:**
- Total acres farmed (and crops — different equipment intensity)
- Current equipment list with ages, hours, and estimated condition
- Specific equipment being evaluated (make, model, new vs. used, price quotes)
- Financing terms available (rate, down payment, term)
- Local custom hire rates and availability
- Annual use hours or acres expected
- Tax bracket and entity structure (for depreciation analysis)
- Shop and storage availability

---

## Phase 2 — Field-Level Agronomy (Spring Planning)

These prompts help with in-season crop management decisions that directly affect yield.

### 5. Planting Decision Advisor
**File:** `planting_advisor_prompt.md`
**Status:** 🔲 Not Started

**What it does:**
- Hybrid/variety selection based on soil type, maturity zone, disease pressure, and trait packages
- Seeding rate recommendations by soil productivity zone (not one-rate-fits-all)
- Planting date windows and yield penalty curves for late planting
- Row spacing considerations
- Seed treatment evaluation
- Population adjustments for soil type, drainage, and planting date
- Estimates seed cost per acre at recommended rates

**Key data to collect:**
- County and soil types in each field
- Maturity zone / relative maturity targets
- Disease and pest pressure history (e.g., sudden death syndrome, corn rootworm, SCN)
- Trait package preferences (herbicide tolerance system, Bt traits)
- Planting equipment (row spacing, planter capabilities)
- Budget constraints on seed
- Seed brand preferences or dealer relationships

---

### 6. Herbicide & Pest Management Planner
**File:** `herbicide_pest_prompt.md`
**Status:** 🔲 Not Started

**What it does:**
- Builds a complete weed management program based on crop, rotation, and weed species present
- Addresses herbicide resistance management (especially waterhemp/Palmer amaranth and marestail)
- Pre-emergence vs. post-emergence timing recommendations
- Tank mix compatibility guidance
- Insect scouting thresholds and treatment decisions
- Fungicide application economics (preventive vs. scouting-based)
- Generates a spray program with products, rates, timing, and cost per acre
- Considers drift restrictions, buffer zones, and label requirements

**Key data to collect:**
- Crops and rotation for each field
- Weed species present and severity (especially resistant species)
- Herbicide tolerance system in the crop (Roundup Ready, Enlist, Xtend, Liberty Link)
- Historical herbicide use (resistance risk assessment)
- Insect pressure history
- Disease history
- Application equipment (boom sprayer, aerial, etc.)
- Budget for crop protection per acre

---

### 7. Cover Crop & Soil Health Planner
**File:** `cover_crop_prompt.md`
**Status:** 🔲 Not Started

**What it does:**
- Recommends cover crop species and mixes based on goals (erosion control, nitrogen fixation, compaction remediation, weed suppression, forage)
- Seeding rates and methods (drilled, broadcast, aerial, interseeded)
- Planting windows based on cash crop harvest timing and location
- Termination timing and method (herbicide, roller-crimper, winterkill)
- Estimates costs vs. benefits (seed, planting, termination, N credit, yield impact)
- Addresses potential issues (green bridge for disease, allelopathy, volunteer problems)
- Integrates with government cost-share programs (EQIP, CSP)
- Tracks soil health metrics over time (OM%, aggregate stability, infiltration)

**Key data to collect:**
- Cash crop rotation and harvest timing
- Soil health goals (what are they trying to improve?)
- Equipment available for cover crop establishment
- Budget for cover crops
- Livestock integration potential (grazing cover crops?)
- Existing soil health baseline (OM%, compaction, erosion issues)
- Herbicide carryover concerns

---

### 8. Drainage & Tile Planning Advisor
**File:** `drainage_tile_prompt.md`
**Status:** 🔲 Not Started

**What it does:**
- Evaluates fields for drainage improvement potential
- Estimates yield increase from proper drainage based on soil type and current conditions
- Pattern tile spacing recommendations by soil type
- Outlet assessment and main sizing
- Cost estimation (per acre and total) for systematic tiling
- ROI and payback period calculation
- Compares pattern tile vs. targeted drainage vs. surface improvements
- Addresses environmental considerations (controlled drainage, saturated buffers, bioreactors)
- Regulatory requirements (permits, setbacks, outlet agreements)

**Key data to collect:**
- Field locations and soil types
- Current drainage status (existing tile? surface drains? age and condition?)
- Problem areas (ponding, wet spots, yield maps showing low spots)
- Topography and available outlet
- Yield drag estimated from poor drainage
- Budget and financing options
- Environmental regulations in their county/watershed

---

## Phase 3 — Long-Term Business Strategy

These prompts address bigger-picture decisions that shape the farm operation over years.

### 9. Cash Rent vs. Farm It Yourself Analyzer
**File:** `cash_rent_analyzer_prompt.md`
**Status:** 🔲 Not Started

**What it does:**
- Side-by-side comparison of cash renting ground vs. farming it
- Full cost accounting for farming (all variable + fixed + labor + risk)
- Factors in opportunity cost of farmer's time and capital
- Risk quantification — farming has yield and price risk, cash rent is guaranteed
- Break-even acreage analysis — at what scale does farming make more sense?
- Sensitivity analysis on commodity prices, yields, and input costs
- Considers the soil fertility investment question (building fertility on rented ground)
- Flex rent and crop share alternatives as middle ground

**Key data to collect:**
- Acres in question
- Current cash rent rates in the area
- Full production cost budget (from Breakeven Calculator)
- Equipment situation (owned, shared, would need to acquire)
- Farmer's alternative income / time value
- Risk tolerance
- Lease terms and length
- Relationship with landlord

---

### 10. Land Purchase / Mortgage Analyzer
**File:** `land_purchase_prompt.md`
**Status:** 🔲 Not Started

**What it does:**
- Evaluates whether buying farmland makes financial sense at current prices
- Calculates affordable price per acre based on earning potential
- Compares land payment to expected farming income or cash rent income
- Amortization schedules at various terms and rates
- Cash flow analysis — can the farm cash flow the payment?
- Considers appreciation potential and long-term wealth building
- Tax implications of land ownership (depreciation of improvements, interest deduction, 1031 exchanges)
- Evaluates financing options (FSA beginning farmer loans, commercial ag lenders, seller financing)
- Risk assessment — what happens if commodity prices drop 20%?

**Key data to collect:**
- Asking price and acreage
- Soil productivity ratings (CSR2 or equivalent)
- Current cash rent rates for comparable ground
- Financing terms (rate, term, down payment)
- Farmer's current financial position (balance sheet, income, existing debt)
- Expected farming income or rental income from the parcel
- Tax situation and entity structure

---

### 11. Farm Succession & Transition Planner
**File:** `succession_planner_prompt.md`
**Status:** 🔲 Not Started

**What it does:**
- Guides multi-generational farm families through transition conversations
- Identifies key decisions: who farms, who owns, who manages, who gets what
- Explores entity structures (LLC, trust, partnership, corporation) and their implications
- Addresses "fair vs. equal" — farming heirs vs. non-farming heirs
- Estate planning considerations (gifting strategies, life estates, installment sales)
- Tax planning for transition (stepped-up basis, capital gains, estate tax thresholds)
- Buy-in structures for the next generation
- Life insurance as a succession tool
- Timeline and milestone planning
- Identifies when to involve an attorney, CPA, and financial planner

**Key data to collect:**
- Family structure (who's involved, who wants to farm, who doesn't)
- Current ownership and entity structure
- Asset inventory (land, equipment, livestock, buildings) and estimated values
- Debt position
- Current generation's retirement needs and timeline
- Next generation's financial position and farming experience
- Existing estate planning documents
- Family dynamics and potential conflicts (handled sensitively)

**Note:** This prompt must include strong disclaimers that it is not legal or tax advice, and should consistently recommend working with qualified professionals. The AI's role is to help organize thinking, identify questions to ask, and prepare for professional consultations.

---

### 12. Livestock Integration Advisor
**File:** `livestock_integration_prompt.md`
**Status:** 🔲 Not Started

**What it does:**
- Evaluates adding cattle (cow-calf, stockers, or feedlot) to a grain operation
- Assesses available resources (crop residue, cover crops, pasture, facilities, water, labor)
- Enterprise budget for the livestock operation
- Synergies with grain operation (residue grazing, cover crop grazing, manure value)
- Infrastructure requirements and costs (fencing, water, handling facilities, feed storage)
- Marketing options (direct sale, retained ownership, contract grazing)
- Risk assessment (cattle market cycles, drought, disease, labor)
- Regulatory requirements (nutrient management plans, environmental permits)
- Break-even analysis and expected returns
- Cash flow impact on the overall operation

**Key data to collect:**
- Available land (pasture, crop residue acres, cover crop acres)
- Existing infrastructure (fencing, water, barns, corrals)
- Labor availability (farmer's time, hired help)
- Capital available for startup
- Feed resources (crop residue, hay, grain)
- Local cattle market access
- Experience level with livestock
- Goals (income diversification, utilizing resources, building soil with manure)

---

## File Structure

```
farm-ai-toolkit/
├── plan.md                              ← This file (master build plan)
├── crop_fertility_advisor_prompt.md     ← ✅ COMPLETED
├── breakeven_grain_marketing_prompt.md  ← Phase 1
├── crop_insurance_prompt.md             ← Phase 1
├── government_programs_prompt.md        ← Phase 1
├── equipment_analyzer_prompt.md         ← Phase 1
├── planting_advisor_prompt.md           ← Phase 2
├── herbicide_pest_prompt.md             ← Phase 2
├── cover_crop_prompt.md                 ← Phase 2
├── drainage_tile_prompt.md              ← Phase 2
├── cash_rent_analyzer_prompt.md         ← Phase 3
├── land_purchase_prompt.md              ← Phase 3
├── succession_planner_prompt.md         ← Phase 3
└── livestock_integration_prompt.md      ← Phase 3
```

## Build Notes

- Each prompt should be self-contained — a farmer should be able to use any single prompt without needing the others
- However, prompts should reference each other where useful (e.g., "if you've already calculated your breakeven with the Breakeven Calculator, provide that number here")
- All prompts should follow the same conversational approach: gather info in natural dialogue, don't overwhelm with questions, use plain language, be honest about uncertainty
- All prompts should offer to generate downloadable spreadsheets or documents as final deliverables
- All financial prompts must include disclaimers that the AI is not a financial advisor, tax professional, or attorney
- Prompts should be region-aware — recommendations vary significantly by state (e.g., Ohio Tri-State recommendations vs. Iowa State vs. Purdue)
