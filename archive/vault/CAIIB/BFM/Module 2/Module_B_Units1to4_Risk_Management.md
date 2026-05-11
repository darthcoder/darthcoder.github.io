# Module B — Units 1–4: Risk Management (Combined Heuristic Sheet)
### CAIIB BFM | Read Unit 0 first

---

## Unit 1: Credit Risk Management

### What It Is
```
Borrower doesn't pay → bank loses money → depositor is exposed.
Credit risk = the oldest risk in banking.
```

### Key Concepts

| Term | Plain English |
|---|---|
| **PD** (Probability of Default) | How likely is the borrower to not pay? |
| **LGD** (Loss Given Default) | If they don't pay, how much do we lose? |
| **EAD** (Exposure at Default) | How much are we owed when they default? |
| **Expected Loss** | PD × LGD × EAD |
| **NPA** | Loan overdue >90 days = Non Performing Asset |
| **Provisioning** | Setting aside money against expected NPA loss |

> **Formula you actually need:**  
> `Expected Loss = PD × LGD × EAD`  
> Everything else is a variation of this.

### Decision Tree

```
Q: Is this about measuring credit risk?
→ PD, LGD, EAD, Expected Loss

Q: Is this about managing credit risk?
→ Collateral, Guarantees, Credit Limits, Diversification

Q: Is this about pricing credit risk?
→ Higher risk = higher interest rate spread (risk premium)

Q: Is this about failed credit risk management?
→ NPA → Provisioning → Write-off (in that order, never skip)
```

### Elimination Rules
- "Eliminate credit risk completely" → **wrong, always**
- Best way to manage credit risk → **diversification + collateral + monitoring**
- Who decides credit policy? → **The Board** (not branch manager, not RBI)
- NPA classification is driven by → **days past due (90 days)**, not borrower's intent

---

## Unit 2: Market Risk & Interest Rate Risk Management

### What It Is
```
Market moves against you → your portfolio loses value.
Interest rate moves → your margins shrink or your bond prices fall.
```

### Two Sub-Risks to Keep Separate

| Risk | Trigger | Victim |
|---|---|---|
| **Market Risk** | Equity/forex/commodity prices move | Trading book |
| **Interest Rate Risk** | Interest rates move | Banking book (loans & deposits) |

> The exam loves to test whether you know WHICH book is affected.  
> **Trading book = market risk. Banking book = interest rate risk.**

### Key Concepts

| Term | Plain English |
|---|---|
| **VaR** (Value at Risk) | Maximum loss at X% confidence over Y days |
| **Duration** | How sensitive a bond is to interest rate changes |
| **NII** (Net Interest Income) | Interest earned minus interest paid |
| **NIM** (Net Interest Margin) | NII as % of assets |
| **Re-pricing Risk** | Assets and liabilities reprice at different times |

### The Duration Heuristic
```
Duration HIGH → bond price VERY sensitive to rate changes
Rate UP → Bond price DOWN (always, no exceptions)
Rate DOWN → Bond price UP

Long duration bond in rising rate environment = LOSS
Short duration bond in rising rate environment = SAFER
```

### The NII Heuristic
```
Bank is LIABILITY SENSITIVE → more liabilities reprice than assets
→ If rates RISE → NII FALLS (bank pays more, earns same)
→ If rates FALL → NII RISES

Bank is ASSET SENSITIVE → more assets reprice than assets
→ If rates RISE → NII RISES
→ If rates FALL → NII FALLS
```

### Decision Tree
```
Q: Does the question mention bonds / trading / VaR?
→ Market Risk → Trading Book

Q: Does the question mention loans / deposits / NII / NIM?
→ Interest Rate Risk → Banking Book

Q: Rate goes up — what happens?
→ Bond prices fall (trading book loss)
→ Check asset/liability sensitivity for NII impact

Q: How does bank manage market risk?
→ Limits (stop-loss, VaR limits), Hedging (derivatives), Diversification
```

### Elimination Rules
- VaR is NOT the maximum possible loss → it's max loss at a **given confidence level**
- "Rates rise → NII always falls" → **WRONG**, depends on asset/liability sensitivity
- Best measure of interest rate risk in banking book → **Duration / NII sensitivity**

---

## Unit 3: Operational Risk & Compliance

### What It Is
```
Not market. Not credit. Everything else that can go wrong internally.
People, Processes, Systems, External Events.
```

### The Basel Definition (Memorise This One)
```
Operational Risk = Risk of loss resulting from inadequate or failed:
  → Internal PROCESSES
  → PEOPLE
  → SYSTEMS
  → External EVENTS

Excludes: Strategic risk and Reputational risk
```

> Exam will test this definition directly. The four words are: **Processes, People, Systems, External Events.**

### Key Concepts

| Term | Plain English |
|---|---|
| **KRI** (Key Risk Indicator) | Early warning signal — fire alarm before the fire |
| **KPI** (Key Performance Indicator) | Measures performance, not risk |
| **RCSA** | Risk & Control Self Assessment — bank audits itself |
| **BIA** (Basic Indicator Approach) | Op risk capital = 15% of avg gross income |
| **TSA** (Standardised Approach) | Business line wise op risk capital |
| **AMA** (Advanced Measurement Approach) | Bank uses own model (RBI approval needed) |

### The Three Approaches (Capital for Op Risk)

```
BIA → Simplest → 15% of Gross Income → Small banks
TSA → Middle → Business line multipliers → Medium banks  
AMA → Complex → Internal models → Large banks (RBI approval)

Exam rule: More sophisticated = more accurate = more capital efficient
           BUT requires more data, more oversight, more RBI approval
```

### Compliance Sub-Layer
```
Compliance risk = risk of legal/regulatory penalty for non-compliance
→ KYC failure → AML breach → FEMA violation

Who owns compliance? → The Board (compliance is never "outsourced")
What's the fix? → Policies + Training + Audit + Escalation
```

### Decision Tree
```
Q: Is this about internal failure (fraud, error, system crash)?
→ Operational Risk

Q: Is this about measuring op risk capital?
→ BIA (simple) → TSA (medium) → AMA (complex)

Q: Is this about catching risk before it happens?
→ KRI (not KPI — that's performance)

Q: Is this about regulatory penalties?
→ Compliance Risk (subset of Op Risk)
```

### Elimination Rules
- Op risk includes external events (flood, pandemic) → **Yes, it does**
- Strategic risk is part of op risk → **No, excluded by Basel definition**
- KRI and KPI are the same → **No — KRI = risk signal, KPI = performance signal**
- AMA is available to all banks → **No — needs RBI approval**

---

## Unit 4: Liquidity Risk Management

### What It Is
```
Bank is solvent (assets > liabilities) but cannot pay TODAY.
Classic bank run scenario.
Liquidity risk ≠ insolvency. It's a timing problem.
```

### The Core Distinction
```
SOLVENCY = Do we have enough assets to cover liabilities? (long term)
LIQUIDITY = Can we pay what's due TODAY? (short term)

A bank can be solvent and illiquid at the same time.
This is what kills banks. Not insolvency — illiquidity.
```

### Key Concepts

| Term | Plain English |
|---|---|
| **LCR** (Liquidity Coverage Ratio) | Survive a 30-day stress scenario |
| **NSFR** (Net Stable Funding Ratio) | Stable funding over 1 year |
| **CRR** (Cash Reserve Ratio) | % of deposits parked with RBI (cash, no interest) |
| **SLR** (Statutory Liquidity Ratio) | % of deposits in govt securities (earns interest) |
| **Call Money** | Overnight borrowing between banks |
| **LAF** (Liquidity Adjustment Facility) | RBI's tool to inject/absorb liquidity |

### The RBI Liquidity Toolkit
```
RBI wants to INJECT liquidity → Repo Rate (banks borrow from RBI)
RBI wants to ABSORB liquidity → Reverse Repo (banks park with RBI)
RBI permanent floor → CRR (no return) + SLR (some return)

Rate UP → Liquidity tightens → credit slows → inflation cools
Rate DOWN → Liquidity loosens → credit grows → economy stimulated
```

### LCR vs NSFR
```
LCR = Short term (30 days)
    = High Quality Liquid Assets ÷ Net Cash Outflows ≥ 100%
    = "Can we survive a run for 30 days without RBI help?"

NSFR = Long term (1 year)  
     = Available Stable Funding ÷ Required Stable Funding ≥ 100%
     = "Is our funding structure stable enough for a year?"
```

### Decision Tree
```
Q: Is this about surviving a short-term crisis?
→ LCR (30 days)

Q: Is this about long-term funding stability?
→ NSFR (1 year)

Q: Is this about RBI mandatory reserves?
→ CRR (cash) and SLR (govt securities)

Q: RBI raises CRR — what happens?
→ Banks have less money to lend → credit tightens → liquidity in system falls

Q: How does a bank manage liquidity risk?
→ Maintain HQLA buffer + diversify funding sources + contingency funding plan
```

### Elimination Rules
- Liquidity risk = insolvency → **WRONG** — solvent bank can still face liquidity crisis
- LCR minimum = 90% → **WRONG** — it's 100% (RBI mandates 100%)
- CRR earns interest → **WRONG** — CRR earns zero. SLR earns interest.
- "Liquidity risk can be fully eliminated" → **WRONG** — managed, never eliminated

---

## Cross-Unit Heuristic (The Cascade)

```
Credit event (borrower defaults)
    ↓
Market Risk (portfolio value drops, provisions hit P&L)
    ↓
Liquidity Risk (market confidence drops, depositors withdraw)
    ↓
Operational Risk (staff errors, system failures under stress)
    ↓
Capital erodes → Basel ratios breach → Regulator steps in
```

> Every risk type feeds the next. Exam scenario questions test whether you see the cascade.  
> Answer: **"Identify the primary risk first, then note downstream impacts."**

---

*CAIIB BFM — Module B, Units 1–4 | Exam: First Sunday of June 2026*
