# ABFM Module C — Corporate Valuation & Mergers and Acquisitions
### CAIIB ABFM Paper 3

---

## The Master Frame (Read This First)

```
VALUE = present worth of all future cash flows to the owner
```

Every valuation question resolves to: **What are the cash flows? What is the right discount rate?**
When the exam gives you a scenario, ask: which valuation METHOD fits this situation?

**The IIBF valuation hierarchy:**
```
DCF (discounted cash flow) = theoretically correct; most credible
Relative valuation          = practical; used for listed companies
Asset-based valuation       = used for liquidation/distressed/holding companies
```

---

## Part 1: What Is Value? (Unit 1 — Corporate Valuations)

### Three Measures of Value

```
Book Value     = Net Assets per Share (Balance Sheet based)
               = (Total Assets – Total Liabilities) / Shares outstanding
               = Historical cost; ignores future

Market Value   = Share Price × Shares outstanding (market capitalisation)
               = What the market thinks today; based on expectations

Enterprise Value (EV) = Equity value + Debt + Preferred Stock – Cash
               = Total value of the business to ALL claimants
               = Market cap + Net debt (approximately)
```

> **Exam trap:** EV ≠ Market Cap. EV includes debt but SUBTRACTS cash (cash reduces the
> effective cost to a buyer). A company with lots of cash has lower EV than market cap.

### IVS 105: Three Approaches to Valuation

| Approach | Logic | Methods |
|---|---|---|
| **Market Approach** | Comparable transactions/companies | Trading multiples, Transaction multiples |
| **Income Approach** | PV of future economic benefits | DCF, DDM, Capitalisation of earnings |
| **Cost Approach** | FMV of net assets at current prices | Adjusted book value |

> **Elimination rule:** "Company is similar to listed peers" → Market Approach.
> "Project will generate steady cash flows" → Income Approach.
> "Asset-heavy company being liquidated" → Cost Approach.

### Four Indian Methods for Firm Valuation

```
1. Adjusted Book Value     → Net assets at fair market value (not historical cost)
2. Stock & Debt            → Market Cap + Market Value of Debt
3. Direct Comparison       → Comparable company multiples applied to subject firm
4. DCF                     → Most rigorous; explicit cash flow projections
```

---

## Part 2: DCF Valuation (Unit 2)

### The 6-Step DCF Process

```
Step 1: Analyse historical performance (understand economics of the business)
Step 2: Estimate NOPLAT for each forecast year
Step 3: Compute Free Cash Flow (FCF) for each year
Step 4: Estimate Cost of Capital (WACC)
Step 5: Estimate Terminal Value (what happens beyond the forecast period)
Step 6: Calculate total firm value = PV(FCFs) + PV(Terminal Value) + Non-operating assets
```

### The Key DCF Formulas

```
NOPLAT = EBIT × (1 – Tax Rate)
       = Net Operating Profit Less Adjusted Taxes
       (NOPLAT = operating profit after taxes, before financing)

ROIC   = NOPLAT / Operating Invested Capital
       (ROIC > WACC → firm is creating value)

Net Investment = Change in Operating Invested Capital
(= Capex + ΔWorking Capital – Depreciation)

FCF    = NOPLAT – Net Investment
       = Gross Cash Flow – Gross Investment
```

> **Exam trap:** FCF is NOT the same as net profit. FCF = NOPLAT – Net Investment.
> A high-growth company reinvests heavily → low or NEGATIVE FCF despite being profitable.

### Terminal Value

```
Terminal Value (Gordon Growth Model):
  TV = FCF(t+1) / (WACC – g)

  where FCF(t+1) = FCF in first year beyond forecast period
        g        = sustainable long-term growth rate (must be < WACC, or TV → ∞)

PV of TV = TV / (1 + WACC)^n
```

> **Exam pattern:** Terminal value often represents 60–80% of total firm value.
> If discount rate < growth rate → terminal value explodes → model breaks → always flag this.

### Value of the Firm

```
Value of Firm = PV of FCFs (explicit period) + PV of Terminal Value + Non-operating assets

Value of Equity = Value of Firm – Market Value of Debt
```

### WACC (Cost of Capital) in DCF Context

```
WACC = wd × rd(1–t) + wp × rp + we × re

Rule: Use TARGET capital structure weights (not current), because
WACC reflects the long-run financing mix of the firm
```

---

## Part 3: Equity Valuation Models (Unit 2 continued)

### Dividend Discount Models (DDM)

| Model | Formula | Use Case |
|---|---|---|
| **Constant Growth (Gordon)** | P₀ = D₁ / (r – g) | Stable dividend payers |
| **Zero Growth** | P₀ = D / r | Preferred stock or fixed dividend |
| **Two-Stage** | High growth (explicit) + stable growth (terminal) | Growth companies transitioning to maturity |
| **H Model** | P₀ = D₀[(1+gn) + H(ga – gn)] / (r – gn) | Growth rate declines linearly; H = half-life of high growth |
| **Three-Stage** | High growth → transition → stable | Complex; rarely tested in CAIIB numerically |

> **H Model key:** H = number of years of high growth / 2.
> If high-growth period = 10 years, then H = 5.

**When DDM applies:**
```
Use DDM when: company pays regular dividends + dividend policy is stable
Don't use DDM for: non-dividend paying companies, companies with unstable dividends
Use FCFE for: non-dividend paying companies, companies with excess cash
```

### FCFE vs FCFF — Critical Distinction

```
FCFF (Free Cash Flow to Firm)  = cash flow available to ALL investors (debt + equity)
                               → Discount at WACC
                               → Gives FIRM value

FCFE (Free Cash Flow to Equity) = cash flow available to equity holders ONLY
                               = FCFF – Interest(1–t) + Net Borrowing
                               → Discount at cost of equity (re)
                               → Gives EQUITY value directly
```

> **Exam trap:** "Analyst used FCFE but discounted at WACC" → WRONG.
> FCFE → discount at cost of equity.
> FCFF → discount at WACC.
> Mixing these is the most common DCF error IIBF tests.

### APV Model (Adjusted Present Value)

```
APV = Value of unlevered firm + PV of tax shield on debt

Value of unlevered firm = FCF discounted at cost of unlevered equity (r₀)
PV of tax shield = Tax rate × Debt (if debt is permanent)

Use APV when: debt level changes significantly, LBO transactions, project finance
Use WACC when: capital structure is stable
```

---

## Part 4: Relative Valuation / Multiples (Unit 3)

### Equity Multiples — The Exam Shortlist

```
P/E  = Price per share / EPS
     = (1–b) / (r – ROE×b)
     where b = retention ratio, r = required return, ROE = return on equity

P/B  = Price / Book Value per share
     = ROE × (1–b) / (r – g)

P/S  = Price / Sales per share
     = NPM × (1+g) × (1–b) / (r – g)
     where NPM = net profit margin

PEG  = P/E / Earnings Growth rate
     (PEG < 1 → possibly undervalued; PEG = 1 → fairly valued)
```

> **Exam pattern:** These formulas always appear together.
> Key driver: **The higher the ROE relative to required return, the higher the justified P/B.**
> A company with ROE < required return deserves P/B < 1 (destroying value).

### Enterprise Value Multiples

```
EV/EBITDA = (ROIC–g)(1–DA)(1–t) / [ROIC(WACC–g)]
           Most common for capital-intensive companies; avoids depreciation distortions

EV/EBIT    = (1–t)(1–reinvestment rate) / (WACC–g)
           Good for comparing companies with similar capex

EV/FCFF    = 1 / (WACC–g)
           Simplest; assumes all FCF is paid out

EV/BV      = (ROIC–g) / (WACC–g)
           ROIC > WACC → EV/BV > 1 (value creation)

EV/Sales   = After-tax operating margin × (1+g) × (1–reinvestment) / (WACC–g)
```

> **EV multiples heuristic:**
> When ROIC > WACC → firm creates value → EV/BV > 1
> When ROIC = WACC → firm earns exactly its cost → EV/BV = 1
> When ROIC < WACC → EV/BV < 1 (destroy value → candidate for restructuring)

### Which Multiple to Use — Decision Rules

```
Profitable company with stable earnings → P/E (but excludes balance sheet)
Capital-intensive companies (utilities, manufacturing) → EV/EBITDA
Companies in early growth (no earnings yet) → P/S or EV/Sales
Asset-heavy: banks, real estate, insurance → P/B
Growth company → PEG (but mechanically simple, misses quality differences)
```

---

## Part 5: Special Valuation Cases (Unit 4)

### Startup Valuation (7-Step Framework)

```
1. Current standing (where is the company today?)
2. Revenue growth estimation (past growth, comparable industry)
3. Target operating margin (what does mature firm in this sector earn?)
4. Reinvestment needs (how much capital needed to grow?)
5. Risk / Discount rate (very high for startups — 25-40% typical)
6. Firm value (DCF with high discount rate)
7. Equity value (subtract debt)
```

> **Key startup trap:** Traditional DCF undervalues startups because early FCFs are negative.
> The value is in TERMINAL VALUE (years 5-10 onwards). Discount that back at HIGH rate.
> IIBF acknowledges: survival is a real risk; discount rates must reflect this.

### Financial Services Firms (Banks, Insurance)

```
Problem: Cannot easily calculate FCF for banks
         (deposits are both liabilities AND production inputs)

Methods:
1. Dividend Discount Model (DDM) → most appropriate
2. FCFE model (equity cash flows directly)
3. Asset-based (for liquidation)

AVOID: FCFF or EV-based multiples for banks
→ "Net debt" is meaningless for banks (debt IS the business)
```

> **Elimination rule:** "Value a bank using FCFF" → WRONG. Banks = DDM or FCFE.

### Distressed Firms — Equity as a Call Option

```
Equity in a leveraged firm = call option on the firm's assets:
  Payoff to equity = max(V – D, 0)
  where V = firm value, D = face value of debt

Implication:
→ Even if firm value < debt face value, EQUITY has option value (hope)
→ High volatility = GOOD for equity holders (increases option value)
→ Volatility HURTS debt holders (more chance of default)

IIBF uses Black-Scholes to value equity in distressed firms:
  S (stock price) = V × N(d₁) – D × e^(-rT) × N(d₂)
  where V = firm value, D = debt face value, T = time to maturity
```

### Cyclical Companies

```
Problem: Earnings fluctuate with the business cycle
→ Using current earnings at peak → overvalues firm
→ Using current earnings at trough → undervalues firm

Solution: Normalise earnings
→ Use average earnings over a full cycle (5-7 years)
→ Apply P/E on normalised EPS
```

### Holding Companies

```
Holding company = company that owns stakes in other companies
Value method: SUM OF PARTS (SOTP)

Value of holding company = Σ (Market value of each subsidiary stake)
                           + Cash and other assets
                           – Holding company discount (10-30% typically)

Why the discount?
→ Investors can buy subsidiaries directly (avoids double layer of management)
→ Conglomerate discount is real and well-documented
```

---

## Part 6: Mergers and Acquisitions (Units 5 & 6)

### M&A Definitions — IIBF Loves These

```
Merger (Amalgamation) = A + B → AB (both disappear; Companies Act governs)
Acquisition           = A acquires B; B may or may not survive as subsidiary
Reverse Merger        = unlisted company acquires listed company (gets listing without IPO)
```

### Types of Mergers

| Type | Companies Involved | Exam Trigger |
|---|---|---|
| **Horizontal** | Same industry, direct competitors | "Two steel companies merge" |
| **Vertical** | Buyer-supplier relationship | "Manufacturer acquires its raw material supplier" |
| **Conglomerate** | Unrelated businesses | "FMCG acquires IT firm" |
| **Cogeneric** | Related but not same product/market | "Two banks in different geographic markets" |
| **Reverse** | Unlisted acquires listed | "Company lists through shell acquisition" |

### Synergy — The Engine of M&A

```
Synergy: V(AB) > V(A) + V(B)

Benefit of merger = PVAB – (PVA + PVB)

NPV to Acquirer (cash deal) = Benefit – Cost
                            = [PVAB – (PVA + PVB)] – (Cash paid – PVB)
                            = PVAB – PVA – Cash paid

Stock deal:
  α = fraction of combined firm given to B's shareholders
  Cost = α × PVAB – PVB
  (Note: if synergy is large, stock deal shares the upside with the target)
```

> **Cash vs Stock deal exam pattern:**
> Cash deal → acquirer keeps all synergy upside
> Stock deal → target shares in synergy gain (acquirer gives them a piece of combined firm)
> If uncertain about synergy → prefer cash deal (doesn't share upside if synergy doesn't materialise)

### SEBI Takeover Code — Key Numbers

```
Trigger points:
  Disclosure: when shareholding crosses 5% (must disclose)
  Open Offer: triggered when acquirer crosses 25% shareholding
  Open Offer size: must offer to buy additional 26% from public shareholders
```

### Amalgamation Under Companies Act

```
Process:
1. Board approval (both companies)
2. NCLT (National Company Law Tribunal) approval
3. Shareholder approval: 75% majority required (3/4 vote)
4. Creditor approval where required
5. NCLT order → scheme becomes effective
```

### Anti-Takeover Defenses — Pre and Post Offer

**Pre-Offer Defenses** (before hostile bid arrives):
```
Poison Pill   → existing shareholders get right to buy cheap shares (dilutes acquirer)
Poison Put    → bondholders can demand early repayment (makes acquisition expensive)
Golden Parachute → large severance for executives if fired post-takeover (raises cost)
```

**Post-Offer Defenses** (after hostile bid is received):
```
Greenmail       → pay acquirer to go away (buy back their shares at premium)
Pac-Man         → target counter-bids for the acquirer
White Knight    → find a friendly acquirer instead
Sell Crown Jewels → sell the most attractive assets (make yourself less attractive)
Creeping Enhancement → management buys shares to increase friendly holding
```

> **India-specific defenses:** Sell Crown Jewels + Creeping Enhancement + White Knight.

### Tax Treatment in M&A (Sections to Know)

```
Section 47(vi):
  Transfer of assets from amalgamating to amalgamated company
  → NO capital gains tax (not treated as a "transfer")
  Condition: Amalgamated company must be an Indian company

Section 72A (Carry Forward of Losses):
  Target company's accumulated losses can be set off by acquiring company IF:
  ✓ Target in business for 3+ years
  ✓ 75%+ of fair market value of assets held for 2 years before amalgamation
  ✓ Business continues for 5 years after amalgamation
  ✓ Production capacity ≥ 50% within 4 years of amalgamation

MAT (Minimum Alternate Tax):
  Section 115JB → MAT = 15% of book profits
  If regular tax < MAT → pay MAT; MAT credit carried forward under Sec 115JAA
```

> **Tax exam pattern:** "Amalgamation — any capital gains?" → No, Sec 47(vi) exempts it.
> "Target company had Rs 100 crore losses. Can acquirer use them?" → Yes, if Sec 72A conditions met.

### Deal Structuring and Cross-Border M&A

```
Payment options: Cash | Stock | Mix | Convertibles (deferred payment)

Cross-border structures:
  Inbound (foreign buys Indian): FDI + SPV in India; or FOCC (Wholly Owned Subsidiary)
  Outbound (Indian buys foreign): Indian holding company → overseas SPV → target

FOCC restriction: cannot borrow from Indian banks; can issue NCDs to FPIs instead

IBC 2016 (Insolvency and Bankruptcy Code):
  → Enables acquisition of distressed companies quickly through NCLT
  → CIRP (Corporate Insolvency Resolution Process)
```

---

## Master Meta-Heuristic: Module C

```
Q: EV vs Market Cap — which is bigger?
→ Depends on debt. EV = Market cap + Net debt. Cash reduces EV.

Q: FCFE vs FCFF — what's the discount rate?
→ FCFE → cost of equity. FCFF → WACC. Never mix them.

Q: Terminal value = FCF/(WACC-g). What if g > WACC?
→ Model breaks. Flag this. Sustainable g must be < WACC (and < GDP growth rate, roughly).

Q: Which valuation method for a bank?
→ DDM or FCFE. Never FCFF/EV multiples for banks.

Q: Cash deal vs stock deal?
→ Cash: acquirer keeps all synergy. Stock: target shares the upside.

Q: Anti-takeover defense received AFTER bid is announced?
→ Greenmail / Pac-Man / White Knight. Pre-bid = Poison Pill / Poison Put / Golden Parachute.

Q: Does amalgamation attract capital gains tax?
→ No — Sec 47(vi) exempts it.

Q: SEBI takeover trigger?
→ 25% crossing = mandatory open offer for 26% of public shares.
```

### The IIBF Valuation Worldview

```
DCF is king, but only if inputs are rigorous
Relative valuation is useful, but comparables must actually be comparable
Synergy must justify the premium paid — overpaying destroys acquirer value
Tax benefits in M&A are real and must be modelled
Equity in distressed firms ≠ zero; it has option value
Book value is a floor, not the answer
```

---

*CAIIB ABFM — Module C | Paper 3*
