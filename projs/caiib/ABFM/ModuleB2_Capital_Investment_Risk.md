# ABFM Module B — Capital Investment, Risk & Decision Making
### CAIIB ABFM Paper 3 | Part 2 of 2

---

## The Master Frame (Read This First)

```
IDENTIFY PROJECT → ESTIMATE CASH FLOWS → EVALUATE (NPV/IRR/PI/Payback/ARR)
→ ADJUST FOR RISK → DECIDE
```

Capital investment decisions are IRREVERSIBLE. IIBF's evaluator is systematic,
uses discounted cash flow, and prefers NPV as the gold standard.

**The IIBF ranking of methods:**
```
NPV > IRR > PI > Payback Period > ARR
```
NPV always wins. Everything else is a proxy or a simplification.

---

## Part 1: Capital Investment Appraisal

### Cash Flows — What IIBF Tests

```
Relevant cash flows ONLY:
✓ Incremental cash flows (what changes because of this project)
✓ Opportunity costs (what you give up)
✓ Working capital changes (at start = outflow; at end = inflow)
✓ Terminal/salvage value (after-tax proceeds at project end)

NOT relevant:
✗ Sunk costs (already spent — cannot be recovered)
✗ Financing costs (captured in discount rate, not cash flows)
✗ Allocated overheads (not incremental)
```

> **Exam trap:** "Research already spent on this project" = SUNK COST. Ignore it.
> "If we take this project, we give up renting the building" = OPPORTUNITY COST. Include it.

### The 5 Methods — Comparison Table

| Method | Time Value? | Uses Cash Flow? | Key Formula | Decision Rule |
|---|---|---|---|---|
| **Payback Period** | NO | Yes (undiscounted) | Initial investment / Annual CF | Shorter = better |
| **ARR** | NO | NO (uses profit) | Avg profit / Avg investment | Higher % = better |
| **NPV** | YES | Yes | ΣCFt/(1+r)^t – Initial cost | Accept if NPV > 0 |
| **IRR** | YES | Yes | Rate where NPV = 0 | Accept if IRR > Cost of capital |
| **PI** | YES | Yes | NPV/Initial Cost (+1) or PV inflows/PV outflows | Accept if PI > 1 |

> **ARR trap:** ARR uses accounting PROFIT (after depreciation), not cash flow.
> Everything else uses cash flow. ARR is the odd one out.

### NPV — The Gold Standard

```
NPV = Σ [CFt / (1+r)^t] – Initial Investment

Accept: NPV > 0 (project creates value)
Reject: NPV < 0
Indifferent: NPV = 0 (just covers cost of capital)
```

**Why NPV wins:**
- Time value of money: ✓
- Absolute magnitude of value: ✓
- Additive (project NPVs can be added): ✓
- Not affected by sign changes in cash flows: ✓

### IRR — Popular but Flawed

```
IRR = discount rate that makes NPV = 0

Accept: IRR > Required rate of return (cost of capital)
Reject: IRR < Required rate of return
```

**IRR Problems IIBF Tests:**
```
Problem 1: Multiple IRRs when cash flows change sign more than once
Problem 2: Scale problem — a small project can have high IRR but low absolute value
Problem 3: Reinvestment assumption — IRR assumes reinvestment at IRR rate (unrealistic)

For MUTUALLY EXCLUSIVE projects with conflicting NPV/IRR rankings → NPV wins.
```

> **Pattern:** "Project A has IRR 20%, Project B has IRR 15%. Which to choose?"
> IF they're mutually exclusive → compare NPV, not IRR. NPV is the right tool.

### PI — For Capital Rationing

```
PI = (NPV / Initial Investment) + 1
   OR
PI = PV of Inflows / PV of Outflows

PI > 1 → Accept
PI < 1 → Reject

Use PI when capital is LIMITED — it ranks projects by bang-per-buck.
NPV can't do this when you can't take all positive-NPV projects.
```

> **Heuristic:** PI = value per rupee invested. When budget is constrained, rank by PI and take highest first.

### Payback Period

```
Payback = time to recover initial investment from cash flows

Simple payback = Year when cumulative CF turns positive

Discounted payback = same but using PV of cash flows (better version)
```

**Why IIBF keeps Payback around:**
- Simple to compute
- Measures liquidity (how quickly do we get our money back?)
- Good for short-life projects or high-risk environments
- Used in practice alongside NPV, not instead of it

> **Exam trap:** "Payback period accounts for time value of money" → **WRONG (unless specified as discounted payback).**

---

## Part 2: Cost of Capital (CAPM and WACC)

### CAPM — Systematic Risk Only

```
E(R) = Rf + β × [E(Rm) – Rf]

E(R)  = expected return on asset
Rf    = risk-free rate (government bond yield)
β     = beta (sensitivity to market movements)
E(Rm) = expected market return
[E(Rm) – Rf] = market risk premium (MRP)
```

**Beta interpretation:**
```
β = 0   → risk-free asset (no market sensitivity)
β = 1   → moves exactly with the market
β > 1   → more volatile than market (aggressive)
β < 1   → less volatile (defensive)
β < 0   → moves opposite to market (gold, some bonds)
```

> **CAPM rule:** Only SYSTEMATIC risk (market risk, β) is rewarded.
> Unsystematic risk (company-specific) can be diversified away → NOT compensated.
> The exam will present unique/idiosyncratic risk as something investors should worry about → WRONG under CAPM.

### WACC — The Cost of the Whole Capital Structure

```
WACC = wd × rd(1–t) + wp × rp + we × re

wd = weight of debt    rd = cost of debt before tax    t = tax rate
wp = weight of pref    rp = cost of preference shares (no tax benefit)
we = weight of equity  re = cost of equity (from CAPM or DDM)
```

**Key WACC rules:**
```
1. Use AFTER-TAX cost of debt: rd(1-t)
   Reason: interest is tax-deductible, so effective cost is lower

2. Preference dividend is NOT tax-deductible → use gross rp (no tax adjustment)

3. Use MARKET VALUE weights (not book value) when possible

4. WACC is the hurdle rate: accept projects that return more than WACC
```

> **Exam trap:** "Company's WACC is 12%. It should accept a project with 11% return to diversify risk" → **WRONG.** Accept ONLY if return ≥ WACC. Diversification argument doesn't apply to capital budgeting hurdle rates.

---

## Part 3: Risk Adjustment in Capital Budgeting

### Four Methods — Know the Difference

| Method | What Changes | What It Shows | IIBF Exam Trigger |
|---|---|---|---|
| **Sensitivity Analysis** | One variable at a time | Which variable most affects NPV ("critical variable") | "Most sensitive to changes in..." |
| **Scenario Analysis** | Multiple variables together | NPV under best/base/worst case | "If oil prices AND demand both change..." |
| **Simulation (Monte Carlo)** | Probability distributions assigned to each variable | Distribution of NPVs | "Thousands of trials", "probability distribution of outcomes" |
| **Decision Tree** | Sequential decisions at nodes | Optimal path through uncertain future | "Should we invest now or wait for demand info?" |

> **Sensitivity vs Scenario:**
> Sensitivity = one variable at a time.
> Scenario = all variables change simultaneously (realistic package).

### Decision Tree — The Fold-Back Method

```
Step 1: Draw the tree (decisions = squares, chance nodes = circles)
Step 2: Assign probabilities and outcomes to chance nodes
Step 3: FOLD BACK (work right to left):
         At chance node → calculate expected value (Σ probability × outcome)
         At decision node → choose the branch with highest EV
Step 4: The highest-value path = optimal decision
```

> **IIBF decision tree heuristic:** The option to gather more information BEFORE committing is valuable. A decision tree makes the value of that waiting/information explicit.

### Risk-Adjusted Discount Rate vs Certainty Equivalents

```
Risk-Adjusted Discount Rate (RADR):
  → Higher risk = higher discount rate = lower NPV
  → Simple to use; used in practice

Certainty Equivalent (CE):
  → Adjust the cash flows downward (α < 1 for risky CF)
  → Discount adjusted CFs at risk-free rate
  → More theoretically correct; less used in practice
```

> **When both are used:** RADR is the practical choice. CE is the theoretically rigorous one. If question mentions "risk-free rate" and "adjusting cash flows", think CE.

---

## Part 4: Decision Making Tools (CVP and ABC)

### Cost-Volume-Profit (CVP) / Break-even Analysis

```
Key definitions:
  Contribution per unit  = Selling Price – Variable Cost per unit
  Contribution Margin %  = (Contribution / Sales) × 100
  Break-even (units)     = Fixed Costs / Contribution per unit
  Break-even (Rs)        = Fixed Costs / Contribution Margin %
  Margin of Safety (MoS) = Actual Sales – Break-even Sales
  MoS %                  = MoS / Actual Sales × 100
  P/V Ratio              = Contribution / Sales (same as Contribution Margin %)
```

> **Exam favourite:** "What is the margin of safety?" → Actual – Break-even.
> "High margin of safety" = company is safely above its break-even = lower risk.
> "High P/V ratio" = each rupee of sales generates more contribution = better.

**CVP assumptions (IIBF tests these):**
```
1. Selling price is constant (no volume discounts)
2. Variable cost per unit is constant
3. Fixed costs don't change within relevant range
4. Product mix is constant (single product or fixed mix)
```

> If question says "new product added" or "volume discount offered" → CVP assumptions violated. Flag it.

### ABC Costing vs Traditional Costing

```
Traditional Costing:
  → Overhead allocated based on volume (labour hours / machine hours)
  → Simple but DISTORTS costs when overhead is large + product mix is complex

Activity-Based Costing (ABC):
  → Overhead allocated to COST POOLS (activities)
  → Each product charged based on HOW MUCH of each activity it uses
  → More accurate; reveals true cost of each product/customer
```

| Traditional | ABC |
|---|---|
| Single overhead rate | Multiple cost drivers |
| Volume-based allocation | Activity-based allocation |
| Simple | Complex but accurate |
| Distorts in complex product mix | Reveals true costs |
| Better for simple, single-product firms | Better when overheads are large + products differ widely in complexity |

> **IIBF's ABC heuristic:** When a company finds that its "profitable" high-volume products are actually unprofitable after proper costing, it's an ABC story. ABC reveals cross-subsidization.

**Cost hierarchy in ABC:**
```
Unit level activities      → cost per unit produced (machine time)
Batch level activities     → cost per batch (setup, inspection)
Product level activities   → cost per product line (engineering changes, design)
Facility level activities  → period costs (building, security) — cannot be traced to products
```

---

## Master Meta-Heuristic: Module B Part 2

```
Q: Best capital investment method?
→ NPV. Always. For mutually exclusive projects, NPV beats IRR.

Q: When to use PI?
→ Capital rationing. Rank projects by PI when budget is limited.

Q: IRR has multiple values. Why?
→ Cash flows change sign more than once. NPV method handles this; IRR fails.

Q: What does beta measure?
→ Systematic (market) risk. Non-diversifiable. This is what investors are paid for.

Q: WACC components — which gets the (1-t) adjustment?
→ Debt cost ONLY. Preference and equity have no tax adjustment.

Q: Break-even formula?
→ Fixed Costs / Contribution per unit.

Q: What is margin of safety?
→ Actual Sales – Break-even Sales. Higher = safer cushion.

Q: When does ABC outperform traditional costing?
→ When: (1) overheads are large relative to direct costs, AND
          (2) products differ significantly in complexity / resource use.
```

### IIBF's Capital Investment Worldview

```
Discounting is non-negotiable — time value is real
Sunk costs are irrelevant — forward-looking decisions only
NPV gives absolute value; IRR gives a rate — when they conflict, NPV wins
Risk adjustments are necessary — higher risk needs higher return
CVP is a SHORT-RUN tool — fixed costs are not really fixed long-run
ABC reveals truth — traditional costing hides cross-subsidization
```

---

*CAIIB ABFM — Module B Part 2 | Paper 3*
