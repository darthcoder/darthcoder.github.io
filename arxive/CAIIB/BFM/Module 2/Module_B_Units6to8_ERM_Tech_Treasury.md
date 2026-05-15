# Module B — Units 6–8: ERM, Tech Risk & Treasury Risk
### CAIIB BFM | Read Unit 0 first

---

## Unit 6: Enterprise Risk Management (ERM)

### What It Is
```
Stop managing risks in silos.
ERM = one framework, all risks, whole organisation, Board level.
```

> If Units 1–4 are individual risk types, ERM is the operating system they all run on.

### The Core Idea
```
Individual risk managers see their own risk.
ERM asks: What is the AGGREGATE risk of the whole bank?
          Are we within our RISK APPETITE?
          Is the Board aware?
```

### Key Concepts

| Term | Plain English |
|---|---|
| **Risk Appetite** | How much risk the bank is *willing* to take |
| **Risk Tolerance** | The outer boundary — breach this and escalate |
| **Risk Capacity** | Maximum risk the bank *can* absorb (capital limit) |
| **Risk Profile** | Where the bank actually sits right now |
| **ICAAP** | Internal Capital Adequacy Assessment Process — bank's self-assessment |
| **SREP** | Supervisory Review — RBI checks the bank's ICAAP |

### The Hierarchy
```
Risk Capacity ≥ Risk Tolerance ≥ Risk Appetite ≥ Risk Profile

If Risk Profile > Risk Appetite → breach → escalate to Board
If Risk Profile > Risk Tolerance → breach → regulator notified
If Risk Profile > Risk Capacity → existential crisis
```

### The Three Lines of Defence

```
1st Line → Business units (they take the risk, they own it)
2nd Line → Risk Management & Compliance (they monitor it)
3rd Line → Internal Audit (they verify the whole system works)

External Audit + RBI = outside the three lines entirely
```

> **Exam trap:** "Who is responsible for risk?" → **The Board** sets appetite.  
> "Who manages risk day to day?" → **1st line** (business units).

### Decision Tree
```
Q: Is this about setting risk limits for the whole bank?
→ ERM → Risk Appetite Framework

Q: Is this about capital self-assessment?
→ ICAAP (bank does it) + SREP (RBI reviews it)

Q: Is this about who owns risk?
→ 1st line takes it, 2nd line monitors it, 3rd line audits it

Q: Risk profile exceeds appetite — what happens?
→ Escalate to Board → reduce exposure → never "ignore and continue"
```

### Elimination Rules
- ERM eliminates all risk → **WRONG** — optimises risk-return within appetite
- Risk appetite = risk capacity → **WRONG** — appetite is always ≤ capacity
- Compliance function is the 1st line → **WRONG** — compliance is 2nd line
- ICAAP is done by RBI → **WRONG** — bank does ICAAP, RBI does SREP

---

## Unit 7: Technology Risk & Cyber Security

### What It Is
```
Banks run on technology.
Technology fails or gets attacked → bank loses money, data, reputation.
This is operational risk with a digital face.
```

### Key Concepts

| Term | Plain English |
|---|---|
| **Cyber Risk** | External attack on bank's systems |
| **IT Risk** | Internal system failure, downtime, data loss |
| **BCP** (Business Continuity Plan) | Plan to keep operating during disruption |
| **DRP** (Disaster Recovery Plan) | Plan to restore systems after disruption |
| **RTO** (Recovery Time Objective) | How fast must systems be restored? |
| **RPO** (Recovery Point Objective) | How much data loss is acceptable? |
| **Phishing / Social Engineering** | Humans as the attack vector, not systems |

### BCP vs DRP
```
BCP = Keep the business RUNNING during an incident
    = "We can still operate from backup site"

DRP = Restore systems AFTER an incident
    = "Get primary systems back online"

BCP is broader. DRP is a subset of BCP.
```

### RTO vs RPO
```
RTO = Time → "Systems must be back in 4 hours"
RPO = Data → "We cannot lose more than 1 hour of transactions"

Lower RTO = faster recovery = more expensive infrastructure
Lower RPO = less data loss = more frequent backups = more expensive
```

### The CIA Triad (Cyber Security Basics)
```
C = Confidentiality → Only authorised people see the data
I = Integrity → Data is not tampered with
A = Availability → Systems are accessible when needed

Every cyber control maps to one of these three.
```

### RBI's Cyber Security Framework
```
Banks must have:
→ Board approved IT/Cyber Security Policy
→ CISO (Chief Information Security Officer)
→ SOC (Security Operations Centre) — monitor threats 24/7
→ Incident reporting to RBI within defined timelines
→ Third party / vendor risk management
```

### Decision Tree
```
Q: Attack from outside (hacker, ransomware, phishing)?
→ Cyber Risk → CIA triad → SOC response → RBI reporting

Q: System failure, downtime, data corruption (internal)?
→ IT / Operational Risk → BCP/DRP → RTO/RPO

Q: How fast must bank recover?
→ RTO (time) and RPO (data)

Q: Who owns tech risk policy?
→ Board approves → CISO manages → Audit reviews
```

### Elimination Rules
- Cyber risk is separate from operational risk → **WRONG** — it's a subset of op risk
- BCP and DRP are the same thing → **WRONG** — BCP = continuity, DRP = recovery
- RTO measures data loss → **WRONG** — RTO = time, RPO = data
- Technology risk can be fully outsourced → **WRONG** — accountability stays with the bank

---

## Unit 8: Risk Management in Treasury Operations

### What It Is
```
Treasury is where the bank manages its own money.
It takes risk to earn returns on the bank's portfolio.
But treasury risk = market risk + liquidity risk + operational risk
all happening in one room, simultaneously, at high speed.
```

### The Treasury Risk Stack

| Risk | In Treasury Context |
|---|---|
| **Market Risk** | Bond prices fall, forex moves, equity drops |
| **Liquidity Risk** | Can't unwind a position fast enough |
| **Credit Risk** | Counterparty in a deal defaults |
| **Operational Risk** | Dealer error, system failure, mis-booking |
| **Regulatory Risk** | Breach of investment limits, SLR, exposure norms |

### Key Controls in Treasury

| Control | What it does |
|---|---|
| **Deal Size Limits** | No single bet too large |
| **Stop Loss Limits** | Exit before losses compound |
| **Counterparty Limits** | Don't concentrate exposure on one party |
| **Mid-Office** | Independent P&L and risk monitoring |
| **Back Office** | Settlement, confirmation, reconciliation |
| **Front Office** | Dealers — they take the positions |

### The Three Office Model
```
FRONT OFFICE → Takes risk (dealers, traders)
MID OFFICE   → Measures and monitors risk (independent of front)
BACK OFFICE  → Settles and confirms (independent of front)

Front office must NEVER control mid or back office.
Separation = the entire control framework.
```

> **Exam trap:** Any option that allows front office to also settle or confirm deals → **eliminate immediately.**

### The ALM Connection
```
Treasury manages:
→ Short term liquidity (call money, LAF, CRR/SLR)
→ Investment portfolio (G-Secs, bonds)
→ Forex positions

ALM Committee (ALCO) sets the framework.
Treasury executes within it.
ALCO > Treasury in the hierarchy.
```

### Decision Tree
```
Q: Dealer took a large loss — what failed?
→ Stop loss limits not enforced → Mid office failure

Q: Settlement went wrong — what failed?
→ Back office failure

Q: Who monitors treasury risk independently?
→ Mid office (not front, not back)

Q: Treasury breached SLR — what type of risk?
→ Regulatory / Compliance risk within treasury

Q: Who sets treasury risk limits?
→ Board → ALCO → Treasury policy → Dealers operate within it
```

### Elimination Rules
- Front office can do its own risk monitoring → **WRONG** — that's mid office's job
- Stop loss limits are optional in treasury → **WRONG** — mandatory control
- ALCO reports to Treasury → **WRONG** — Treasury operates under ALCO
- Counterparty risk in treasury = credit risk → **YES, this one is correct**

---

## Cross-Unit Pattern (Units 6–8)

```
ERM sets the appetite (Unit 6)
     ↓
Tech risk threatens operational continuity (Unit 7)
     ↓
Treasury executes within the framework ERM defined (Unit 8)
     ↓
All of it gets reviewed by Internal Audit (3rd line)
     ↓
Board is accountable for all of it. Always.
```

---

*CAIIB BFM — Module B, Units 6–8 | Exam: First Sunday of June 2026*
