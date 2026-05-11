# BRBL Module B — Important Acts Part A
### CAIIB BRBL Paper 4

---

## The Master Frame (Read This First)

```
DEBT RECOVERY → INSOLVENCY → SECTOR SUPPORT → CONSUMER PROTECTION → TIME LIMITS
```

Module B is about what happens AFTER lending goes wrong — and the legal machinery that exists to recover, resolve, or compensate. Every question is asking: **which law applies to this recovery/resolution situation, and what are the time limits and thresholds?**

**IIBF's recovery/resolution hierarchy:**
```
< ₹20 lakh debt      → Civil Court (not DRT)
≥ ₹20 lakh debt      → DRT Act 1993 (Debt Recovery Tribunal)
Secured debt + NPA   → SARFAESI Act 2002 (possession without court)
Corporate insolvency → IBC 2016 (NCLT, CIRP, 330-day deadline)
MSME disputes        → MSMED Act 2006 (Facilitation Council, 45-day payment rule)
Insurance complaints → IOS 2021 (Ombudsman, ≤ ₹30 lakh)
Consumer complaints  → Consumer Protection Act 2019 (three-tier courts)
Time-barred suits    → Limitation Act 1963 (3 years money, 12 years mortgage)
```

---

## Part 1: SARFAESI Act, 2002

### Full Name and Purpose

```
Securitisation and Reconstruction of Financial Assets and Enforcement of Security Interest Act

Three tools in one:
  1. Securitisation   → banks can convert NPAs into securities (Asset Reconstruction)
  2. Reconstruction   → ARCs can buy NPAs and manage recovery
  3. Enforcement      → banks can enforce security WITHOUT going to court
```

> **Why it matters for banks:** SARFAESI is the ONLY major law letting a bank seize and sell secured assets WITHOUT filing a court suit. Speed = recovery.

### Who Can Use SARFAESI?

```
Eligible secured creditors:
  → Scheduled commercial banks
  → Financial Institutions (SIDBI, NHB, NABARD, Exim Bank)
  → Asset Reconstruction Companies (ARCs)
  → Housing Finance Companies (registered with NHB)
  → NBFCs (if assets ≥ ₹100 crore)

NOT eligible:
  → Unsecured creditors
  → Individual lenders
```

### When Does SARFAESI Apply?

```
Conditions:
  ✓ Debt is a Non-Performing Asset (NPA)
  ✓ Security interest is created in favour of the bank (mortgage/hypothecation/pledge)
  ✓ Amount due ≥ ₹1 lakh (practical threshold)

EXCLUDED from SARFAESI:
  ✗ Agricultural land (absolutely excluded)
  ✗ Security interest < ₹1 lakh
  ✗ Personal properties (not used in business)
  ✗ Education loans (excluded in most cases)
  ✗ Security where 80%+ of debt is paid
```

> **Exam trap:** Agricultural land is ABSOLUTELY excluded. No SARFAESI on farm land ever.

### The SARFAESI Process — S.13

```
Step 1 (S.13(2)): Bank issues DEMAND NOTICE to borrower
  → 60 days to repay
  → Must state details of NPA and amount due

Step 2 (S.13(3A)): Borrower can make representation
  → Bank must REPLY within 15 days (either accept or reject with reasons)

Step 3 (S.13(4)): If no payment within 60 days, bank can:
  a) Take possession of secured assets
  b) Take over management of the business
  c) Appoint manager to manage secured assets
  d) Require persons holding money for borrower to pay bank directly

Step 4 (S.14): Taking physical possession
  → Bank can apply to Chief Metropolitan Magistrate / District Magistrate
  → CMM/DM facilitates possession within 30 days (extendable to 60 days)
  → No civil court suit needed
```

> **Key rule:** S.13(4) possession notice → borrower has 45 days to approach DRT (S.17).
> After 45 days: borrower loses the right to challenge possession.

### Borrower's Remedies — S.17

```
S.17: Borrower can approach DRT within 45 days of SARFAESI possession notice
  → DRT can grant stay if bank failed to comply with SARFAESI provisions
  → If DRT finds bank at fault → restore possession to borrower + compensation

S.18: Appeal from DRT to DRAT within 30 days
  → Must deposit 50% of amount claimed by secured creditor (unless DRAT waives)
```

### Asset Reconstruction Companies (ARCs)

```
ARC = company registered with RBI under SARFAESI S.3
  → Purchases NPAs from banks at a discount
  → Issues Security Receipts (SR) to Qualified Institutional Buyers (QIBs)
  → Manages/recovers the NPA asset

Key: ARCs are buying the RIGHT to recover — not the asset itself initially.
RBI regulates ARCs (capital requirements, limits on acquiring from related parties, etc.)
```

---

## Part 2: Recovery of Debts Due to Banks and Financial Institutions Act, 1993 (DRT Act)

### Purpose and Jurisdiction

```
DRT Act 1993 created special tribunals for fast recovery of bank debts.

DRT jurisdiction: debts ≥ ₹20 lakh due to banks and FIs
  → If debt < ₹20 lakh → civil court has jurisdiction (not DRT)
  → Multiple banks can file jointly for combined dues

DRAT = Debt Recovery Appellate Tribunal (one tier above DRT)
```

> **Threshold to remember:** ₹20 lakh = DRT jurisdiction trigger. Below this → civil court.

### DRT Process

```
Step 1: Bank files Original Application (OA) in DRT with jurisdiction
Step 2: DRT issues summons to borrower/guarantor
Step 3: DRT hears case; issues RECOVERY CERTIFICATE (RC)
Step 4: Recovery Officer enforces RC (seizes/sells property)

Time limit for bank to file OA: governed by Limitation Act (3 years from date of default)
Defendant can file counter-claim if bank has liability to borrower
```

### Appeal to DRAT

```
Any aggrieved party (bank or borrower) can appeal to DRAT
  → Within 30 days of DRT order
  → Borrower must deposit 50% of the debt OR as directed by DRAT
     (DRAT has discretion to reduce this deposit requirement)

From DRAT: Appeal goes to High Court
```

> **Exam trap:** "Bank loses at DRT — what's the appeal deposit?" → Bank files appeal. 50% deposit requirement applies to borrower/defendant, not the bank when it appeals. Bank can appeal without depositing.

---

## Part 3: Insolvency and Bankruptcy Code, 2016 (IBC)

### What IBC Does

```
IBC 2016 consolidated all insolvency laws into ONE code:
  → Companies + LLPs: NCLT (National Company Law Tribunal)
  → Individuals + Partnership firms: DRT (Debt Recovery Tribunal)
  → Insolvency Professionals (IPs) handle the process
  → IBBI (Insolvency and Bankruptcy Board of India) = regulator
```

### Key Definitions

```
Financial Creditor (FC): provides finance with time-value consideration
  → Banks, debenture holders, bond holders
  → FC can INITIATE CIRP directly (without proving operational claim)

Operational Creditor (OC): claim in respect of goods/services/salary/govt dues
  → Suppliers, employees, workmen, government
  → OC must give 10-day demand notice before filing

Corporate Debtor: company/LLP that owes the debt
  → Can self-initiate CIRP
```

### Corporate Insolvency Resolution Process (CIRP)

```
Initiation threshold: Default of ≥ ₹1 crore
  (Raised from ₹1 lakh; COVID-19 period raised to ₹1 crore by notification)

CIRP Timeline:
  Day 0:   NCLT admits application; declares moratorium
  Day 1:   Interim Resolution Professional (IRP) appointed
  Day 30:  Committee of Creditors (CoC) constituted
  Day 180: Deadline to approve resolution plan
  Day 270: Extension (90 more days) if needed
  Day 330: HARD DEADLINE — must liquidate if no plan approved

Moratorium (S.14): During CIRP, NO:
  → Suits/legal proceedings against corporate debtor
  → Recovery/enforcement of security interest
  → Transfer of assets
  → Termination of supply contracts
```

> **Exam trap:** Moratorium under IBC = AUTOMATIC upon admission. SARFAESI stops during moratorium.
> Banks CANNOT enforce SARFAESI during IBC moratorium.

### Committee of Creditors (CoC)

```
CoC = only Financial Creditors (OCs are NOT members)
  → Votes weighted by debt amount
  → Key decisions require 66% vote (earlier 75%)
  → Appoint/remove Resolution Professional
  → Approve resolution plan (66% needed)
  → Approve liquidation (66% needed)
```

### Resolution Plan and Liquidation

```
Resolution Plan (approved by 66% CoC) must:
  → Not discriminate among similarly-situated creditors
  → Pay operational creditors at least what they'd get in liquidation
  → Be approved by NCLT

Waterfall in Liquidation (Order of Priority):
  1. CIRP costs (insolvency professional fees, etc.)
  2. Insolvency resolution process costs
  3. Secured creditors + workmen dues (24 months)
  4. Other employee dues (12 months)
  5. Unsecured financial creditors
  6. Government dues
  7. Remaining secured creditors
  8. Equity shareholders
```

> **Heuristic:** In liquidation, CIRP costs come FIRST. Secured creditors come before unsecured. Equity shareholders = last.

### Section 29A — Disqualification

```
S.29A: These persons CANNOT submit resolution plan:
  → Wilful defaulters
  → Persons whose account NPA > 1 year
  → Convicted of offences (10+ years sentence)
  → Disqualified directors
  → Persons with connected persons disqualified

Purpose: Promoters who drove the company into insolvency cannot buy it back cheap.
```

> **Exam pattern:** "Can original promoter buy back company through resolution plan?" → NO (S.29A blocks it).

---

## Part 4: MSMED Act, 2006

### Classification of Enterprises (Revised 2020)

```
                    Investment in Plant & Machinery    Annual Turnover
Micro Enterprise:   ≤ ₹1 crore                        ≤ ₹5 crore
Small Enterprise:   ≤ ₹10 crore                       ≤ ₹50 crore
Medium Enterprise:  ≤ ₹50 crore                       ≤ ₹250 crore

BOTH criteria must be satisfied (investment AND turnover thresholds)
Udyam Registration: mandatory online registration portal (replacing EM-II)
```

> **Exam trap (pre-2020 vs post-2020):** Old classification used investment only. New (2020) uses BOTH investment + turnover. If question says "as per revised 2020 classification" — use both.

### Payment Protection — Key Provisions

```
S.15: Buyer must pay MSME supplier within agreed period
  → If no agreement: within 15 days
  → In any case: CANNOT exceed 45 days from acceptance of goods

S.16: If payment delayed beyond 45 days:
  → Interest at 3× RBI's bank rate
  → COMPOUNDED MONTHLY
  → No deduction of interest for tax purposes for buyer

S.17: Right of MSME supplier to recover amount + interest

S.18: Disputes referred to Micro and Small Enterprises Facilitation Council (MSEFC)
  → Conciliation first; then arbitration if unresolved
  → Arbitration under Arbitration and Conciliation Act 1996
```

> **Critical exam number:** 45 days = maximum payment period to MSME. Interest = 3× bank rate, compounded monthly.

### Bank Credit to MSMEs

```
Priority Sector: MSME loans classified as priority sector
  → Banks required to lend to MSME sector (40% of ANBC target)
  → Collateral-free loans to micro/small enterprises up to ₹10 lakh (under CGTMSE)

CGTMSE: Credit Guarantee Fund Trust for Micro and Small Enterprises
  → Guarantee cover for collateral-free loans
```

---

## Part 5: Insurance Ombudsman Scheme, 2021 (IOS 2021)

### Framework

```
IOS 2021 replaced IOS 2017
Purpose: Resolve insurance complaints quickly and cheaply (no cost to complainant)
Ombudsman appointed by: Council for Insurance Ombudsmen (Governing Body)
```

### Jurisdiction

```
Who can complain: Policyholder / legal heir / nominee / assignee
                  (only policies for PERSONAL/FAMILY use — not commercial)

Against whom: All life and general insurance companies regulated by IRDAI

Complaint value: ≤ ₹30 lakh (earlier ₹20 lakh under IOS 2017)

Time limit to file: Within 1 year of final reply from insurance company
                    OR 1 year from expiry of 30-day waiting period (if no reply)
```

> **Key exam numbers:** IOS 2021 limit = ₹30 lakh. Filing window = 1 year from insurer's final reply.

### Award

```
Ombudsman Award:
  → BINDING on insurance company (must comply within 30 days)
  → NOT binding on complainant (can still approach consumer courts/civil courts)
  → Ombudsman can also recommend; insurer must respond within 15 days
```

> **Elimination rule:** "Ombudsman award is binding on whom?" → Binding on INSURER. NOT binding on complainant — complainant can reject and go to court.

---

## Part 6: Consumer Protection Act, 2019

### Key Upgrades from 1986 Act

```
New in 2019 Act:
  → Central Consumer Protection Authority (CCPA) — new regulatory body
  → Product liability provisions (manufacturer/seller/service provider)
  → E-commerce and online transactions covered
  → Mediation cells at each commission level
  → Online/electronic filing of complaints
  → Class action suits simplified
```

### Three-Tier Court System

| Court Level | Jurisdiction (Complaint Value) | Appeal Goes To |
|---|---|---|
| **District Consumer Commission** | Up to ₹1 crore | State Commission |
| **State Consumer Commission** | ₹1 crore to ₹10 crore | National Commission |
| **National Consumer Commission** | Above ₹10 crore | Supreme Court |

> **Exam trap (2019 revised limits):** District = up to ₹1 crore (not ₹20 lakh as under 1986 Act). If question uses old limits → incorrect post-2019.

### Key Definitions

```
Consumer = buys goods/services for personal use (NOT for commercial purpose/resale)
  Exception: goods bought for self-employment = consumer

Deficiency of service = fault/imperfection/shortcoming in the service
Unfair trade practice = false representation, misleading advertisements

6 Consumer Rights:
  1. Right to safety
  2. Right to information
  3. Right to choose
  4. Right to be heard
  5. Right to redressal
  6. Right to consumer education
```

### Product Liability (New under 2019 Act)

```
Who is liable:
  → Manufacturer (if product has manufacturing defect)
  → Product seller (if made incorrect representation)
  → Service provider (if service deficient)

Consumer need NOT prove negligence for product liability claim
(Strict liability in many cases)
```

---

## Part 7: Limitation Act, 1963

### The Core Rule

```
S.3: Court SHALL dismiss suit filed after limitation period expires
  → Even if defendant does not raise limitation as defence
  → Court takes notice of limitation on its own
```

> **Exam rule:** Limitation is not a procedural defence — it is a JURISDICTIONAL bar. Court must apply it even without objection.

### Key Limitation Periods for Banking

```
Type of Suit                          Limitation Period   Starting Point
Money recovery (unsecured loan)       3 years             From date of default
Mortgage enforcement (secured debt)   12 years            From date mortgage money due
Guarantee recovery                    3 years             From date of demand on guarantor
NI Act dishonoured cheque             3 years             From date of accrual of cause of action
Recovery from surety                  3 years             From date of demand

Notes:
  → Acknowledgment of debt (S.18): restarts limitation (must be in writing + signed)
  → Part payment (S.19): restarts limitation from date of payment
  → Promise to pay barred debt (S.25): must be in writing + signed + consideration
```

> **Exam trap:** "Bank can sue for mortgage debt even after 3 years" → YES, mortgage limitation = 12 years.
> "What resets limitation?" → Written acknowledgment (S.18) or part payment (S.19). Both must be before expiry.

### S.5 — Condonation of Delay

```
S.5: Court can condone delay if "sufficient cause" shown
  → Available for appeals and applications
  → NOT available for original suits (suits must be filed within time — period)

Banks often rely on S.18 (acknowledgment) rather than S.5 to keep suits alive.
```

---

## Master Meta-Heuristic: Module B

```
Q: What is the DRT jurisdiction threshold?
→ ₹20 lakh. Below this → civil court. Above → DRT.

Q: SARFAESI notice period?
→ 60 days demand notice (S.13(2)) → borrower has 45 days to approach DRT after possession.

Q: What is excluded from SARFAESI always?
→ Agricultural land. Always. No exceptions.

Q: IBC — what is the CIRP hard deadline?
→ 330 days (180+90+60 day extension). Must liquidate after this.

Q: IBC moratorium — does it stop SARFAESI?
→ YES. Once NCLT admits CIRP, all enforcement (including SARFAESI) stops.

Q: IBC — who is in the Committee of Creditors?
→ Only Financial Creditors. OCs are NOT CoC members.

Q: MSME payment deadline?
→ Max 45 days from acceptance. Interest = 3× bank rate, compounded monthly.

Q: IOS 2021 — who is the award binding on?
→ INSURER only. Complainant is free to go to court instead.

Q: Consumer court for ₹50 lakh complaint?
→ District Consumer Commission (up to ₹1 crore).

Q: Mortgage suit — how many years to file?
→ 12 years (not 3 years which is for unsecured money recovery).

Q: What resets limitation under Limitation Act?
→ Written acknowledgment of debt (S.18) or part payment (S.19) — both before expiry.

Q: S.29A IBC — who cannot submit resolution plan?
→ Wilful defaulters, NPA account holders (>1 year), convicted persons.
```

### The IIBF Recovery Worldview

```
SARFAESI = fast track for secured creditors (no court, just DRT oversight)
DRT = faster than civil courts but slower than SARFAESI
IBC = comprehensive but time-bound (hard deadlines exist for a reason)
MSMED = protects small suppliers from large buyer abuse
IOS = free, fast, binding on insurers — model for financial complaint resolution
Consumer Protection = tier courts by amount; CCPA fills regulatory gap
Limitation = discipline for creditors; acknowledgment and part payment = safety valves
No system is a magic wand — combination of tools is always used in practice
```

---

*CAIIB BRBL — Module B | Paper 4*
