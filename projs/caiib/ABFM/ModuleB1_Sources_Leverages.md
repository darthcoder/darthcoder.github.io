# ABFM Module B — Sources of Finance & Leverages
### CAIIB ABFM Paper 3 | Part 1 of 2

---

## The Master Frame (Read This First)

```
RAISE CAPITAL → DEPLOY CAPITAL → MEASURE RISK → CONTROL RISK
```

Module B is about WHERE money comes from and HOW MUCH risk that creates.
Every question is really asking: "Who bears this risk, and at what cost?"

**IIBF's finance worldview:**
- Equity = expensive (no tax shield, market expectations)
- Debt = cheap (tax shield) BUT increases financial risk
- The optimal structure minimizes WACC while keeping risk manageable
- Retained earnings = cheapest source (no flotation costs, no dilution)

---

## Part 1: Sources of Finance

### The Decision Tree

```
Need funds?
    ├── Internal sources first (cheapest, no dilution)
    │   ├── Retained earnings (ploughback)
    │   └── Depreciation funds
    └── External sources (costlier, more complex)
        ├── Equity (expensive, permanent)
        ├── Preference shares (hybrid)
        ├── Debt instruments (cheap, fixed obligation)
        └── Short-term instruments (CP, commercial deposits)
```

### Internal Sources

| Source | Key Feature | Exam Trap |
|---|---|---|
| **Retained earnings** | No explicit cost; cheapest source | Still has OPPORTUNITY COST = return shareholders could earn elsewhere |
| **Depreciation** | Non-cash expense; generates funds WITHOUT raising external capital | NOT profit — it's a cash source that reduces tax |

> **Exam rule:** "Retained earnings have no cost" → **WRONG.**
> Opportunity cost = cost of equity. IIBF acknowledges implicit cost.

### External Equity Sources

| Instrument | Key Feature | India Specifics |
|---|---|---|
| **Equity shares** | Residual claim; voting rights; no fixed obligation | Most expensive — no tax deductibility |
| **Rights issue** | Existing shareholders get proportional new shares at discount | Avoids dilution of voting power |
| **Bonus shares** | Capitalisation of reserves; no cash inflow | No new money — just reshuffles balance sheet |
| **GDR** | Global Depository Receipt — issued in international markets (Europe) | Foreign investors; foreign currency |
| **ADR** | American Depository Receipt — listed on US exchanges | SEC-regulated |
| **IDR** | Indian Depository Receipt — foreign companies raising in India | Issued to Indian investors |

> **Elimination rule:** GDR = Europe. ADR = America. IDR = Indians investing in foreign companies' Indian instrument.

### Preference Shares

```
Preference shares = between debt and equity:
- Fixed dividend (like interest) BUT not tax-deductible
- Priority over equity in dividends AND liquidation
- Voting rights ONLY if dividend unpaid for 2+ years (Sec 47)
- Redeemable: maximum 20 years (Sec 55, Companies Act)
```

> **Exam favorite:** Do preference dividends get tax benefit? **NO.**
> Debt interest = tax-deductible. Preference dividend = NOT (paid from after-tax profits).

### Debt Instruments

| Instrument | Feature | Exam Point |
|---|---|---|
| **Debentures** | Interest = tax-deductible; fixed obligation | Secured/unsecured; can be converted |
| **Term loans** | Banks/FIs; fixed tenure, secured | Common for project finance |
| **Public Deposits** | Companies accepting deposits from public | Max = 25% of paid-up capital + free reserves |
| **Commercial Paper (CP)** | Short-term, unsecured; money market instrument | Min 7 days, max 1 year; min Rs 5 lakh denomination; needs min A2 credit rating |

> **CP heuristic:** Think of it as corporate IOU to institutional investors. Banks and mutual funds buy it. Companies avoid banks. CP is CHEAPER than a bank loan but requires credit rating.

### FCCBs (Foreign Currency Convertible Bonds)

```
FCCB = Bond issued outside India + denominated in foreign currency
     + convertible to equity at the holder's option

Why companies issue FCCBs:
- Lower coupon than plain debt (conversion option has value)
- Cheaper interest (issued in low-rate foreign currencies)
- If stock price rises → investor converts → no cash repayment

Risk:
- If stock price falls → no conversion → company must repay in foreign currency
- Foreign currency risk borne by issuer
```

> **Exam trap:** FCCB investors are typically hedge funds and foreign investors.
> The conversion happens at a preset conversion ratio + price set at 20–30% premium to current market price.

---

## Part 2: Operating and Financial Leverage

### What Leverage Actually Means

```
Leverage = using fixed costs to amplify returns (and losses)

Operating leverage  = fixed OPERATING costs amplify EBIT changes
Financial leverage  = fixed FINANCIAL costs (interest) amplify EPS changes
Combined leverage   = both together — the full amplification
```

The leverage question IIBF keeps asking: "If sales change by X%, what happens to EPS?"
Work through it in two steps: sales → EBIT (operating leverage), then EBIT → EPS (financial leverage).

### Operating Leverage (DOL)

```
DOL = Degree of Operating Leverage
    = % change in EBIT / % change in Sales
    = Contribution / EBIT

where Contribution = Sales – Variable Costs
      EBIT        = Contribution – Fixed Operating Costs
```

> **High DOL → high fixed costs → risky.**
> A company with lots of machinery (capital-intensive) has HIGH DOL.
> A software company with mostly variable labor costs → LOW DOL.

**Intuition:** When sales rise by 10%, EBIT rises by (DOL × 10%).
When sales FALL, the damage is amplified by the same DOL.

### Financial Leverage (DFL)

```
DFL = Degree of Financial Leverage
    = % change in EPS / % change in EBIT
    = EBIT / (EBIT – Interest)

(If preference dividends exist: EBIT / [EBIT – Interest – PD/(1–t)])
```

> **High DFL → high interest burden → financially risky.**
> All-equity firm: DFL = 1 (no amplification).
> The more debt, the higher the DFL.

### Combined / Total Leverage (DCL)

```
DCL = DOL × DFL
    = Contribution / (EBIT – Interest)
    = % change in EPS / % change in Sales
```

**The master formula to remember:**

| Lever | Formula | What it measures |
|---|---|---|
| DOL | Contribution / EBIT | Operating risk |
| DFL | EBIT / (EBIT – I) | Financial risk |
| DCL | Contribution / (EBIT – I) | Total risk (DOL × DFL) |

### Leverage Exam Patterns

> **Pattern 1:** "Company has high DOL and high DFL" → VERY high combined risk. Any sales decline = disaster for EPS.

> **Pattern 2:** "Company wants to reduce financial risk without changing operations" → Reduce debt (lower DFL), not change product mix.

> **Pattern 3:** "A pure equity company's financial leverage is..." → **1.** No interest = no financial amplification.

> **Pattern 4:** "Indifference point between debt and equity plans" → the EBIT level at which EPS is equal under both plans. Below this EBIT: equity plan better. Above: debt plan better (tax shield wins).

### Indifference Analysis (EBIT–EPS)

```
At the indifference point:
EPS(debt plan) = EPS(equity plan)

EPS = (EBIT – Interest)(1 – Tax) / No. of equity shares
```

IIBF uses this to test which financing plan is better at a given EBIT level.
**Rule:** Above indifference EBIT → debt is better (leverage helps). Below → equity is safer.

---

## Master Meta-Heuristic: Module B Part 1

```
Q: What is the cheapest source of finance?
→ Retained earnings (no flotation cost, no dilution)
  — BUT not zero cost; opportunity cost exists.

Q: Preference dividend vs. debt interest — which is tax-deductible?
→ Debt interest ONLY. Preference dividend is NOT.

Q: What does a high DOL mean?
→ High fixed operating costs. Profits are sensitive to sales changes.

Q: What does DFL = 1 mean?
→ No debt. All-equity. No financial risk amplification.

Q: DCL = ?
→ DOL × DFL. The total amplification from sales to EPS.

Q: GDR vs ADR vs IDR?
→ GDR = Europe. ADR = America. IDR = foreigners in India (Indian investors get it).

Q: Can FCCB holders be forced to convert?
→ No. Conversion is at the HOLDER's option. If stock price falls, they won't convert.
   Company must then repay in foreign currency — currency risk.
```

### The IIBF Finance Worldview

```
Tax shield on debt = real benefit → use some debt
But excessive debt = financial distress risk → balance it
Retained earnings = always first preference
Flotation costs reduce the attractiveness of external finance
No source is free — everything has a cost (explicit or implicit)
```

---

*CAIIB ABFM — Module B Part 1 | Paper 3*
