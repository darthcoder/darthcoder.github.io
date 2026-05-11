# BRBL Module C — Important Acts Part B
### CAIIB BRBL Paper 4

---

## The Master Frame (Read This First)

```
EVIDENCE → BANKER-CUSTOMER → INSTRUMENTS (NI Act) → TAX COMPLIANCE
```

Module C is about the day-to-day legal machinery of banking — what counts as evidence, how banker-customer relationships work legally, the full NI Act (cheques, crossing, endorsement, dishonour), and the tax laws banks deal with (Income Tax + GST).

**IIBF's operating-law worldview:**
```
Bankers Books Evidence Act → your ledger entries ARE evidence in court
Banker-Customer law        → the relationship creates legal rights and duties
NI Act 1881                → the rules of the instruments (cheques, bills, notes)
Income Tax Act 1961        → TDS, heads of income, advance tax
GST                        → destination-based consumption tax on services
```

---

## Part 1: Bankers Books Evidence Act, 1891

### What It Does

```
Problem: Banks cannot stop business to produce original ledgers in court cases.
Solution: Certified copies of banking records are ADMISSIBLE as evidence in court.

S.2(3): "Banker's books" = ledgers, day books, cash books, account books
         maintained in ordinary course of banking business
         INCLUDES: printouts of computer-generated records (per amendment)

S.4: Certified copy of any entry in banker's books is admissible as evidence
     of the matters recorded — WITHOUT producing the original

S.5: A bank officer need NOT produce original books in court
     (production of certified copy is sufficient)
```

> **Exam rule:** Banker's books evidence = certified copy = admissible. Bank does not have to produce the original ledger. Certified printout of computerised records qualifies.

### Certification

```
Who certifies: An officer of the bank (not below a certain rank)
What the certificate states:
  → The copy is a true copy of the entry
  → The original entry was made in the course of the bank's ordinary business
  → The book is still in the custody of the bank

Court can also direct inspection of original books if it thinks fit (S.6)
```

---

## Part 2: Banker-Customer Relationship

### The Six Key Relationships

```
Transaction Type      Legal Relationship        Who is Who
─────────────────────────────────────────────────────────────────────
Deposit account       Debtor – Creditor         Bank = DEBTOR; Customer = CREDITOR
                      (bank owes the money; customer is lender to the bank)

Loan account          Creditor – Debtor         Bank = CREDITOR; Customer = DEBTOR

Safe custody          Bailor – Bailee           Customer = BAILOR; Bank = BAILEE
                      (bank takes custody; must return on demand)

Collection of cheque  Principal – Agent         Customer = PRINCIPAL; Bank = AGENT
                      (bank collects on behalf of customer)

Locker facility       Lessor – Lessee           Bank = LESSOR; Customer = LESSEE
                      (bank rents the locker space; not responsible for contents)

Safe deposit vault    Bailor – Bailee / Licensor-Licensee (depends on arrangement)
```

> **Exam trap (deposit):** "What is the relationship for a savings/current account?" → DEBTOR-CREDITOR. The bank OWES you the money. The customer is a creditor of the bank. Not a trustee relationship.

### Banker's Lien — S.171, Contract Act

```
General Lien (S.171): Banker has RIGHT TO RETAIN goods or securities
  → For any general balance due (not just for the specific goods/security)
  → Applies to all property of customer deposited with bank in course of banking
  → Includes bills sent for collection, documents deposited

Difference from pledge:
  → Lien = right to RETAIN (cannot sell without court order or agreement)
  → Pledge = right to RETAIN + SELL (upon default)

Exception: Property deposited for specific purpose (safe custody) ≠ subject to lien
```

> **Key rule:** Banker's lien is a GENERAL lien (not specific to one debt).
> Safe custody deposits are explicitly excluded — deposited for a specific purpose.

### Rights and Duties of Banker

```
Banker's duties:
  → Maintain secrecy of customer accounts (common law + Tournier case principles)
  → Honour cheques if sufficient funds + no stop payment instruction
  → Provide statement of account
  → Pay money on customer's written instruction (cheque/standing instruction)

Exceptions to secrecy (when bank CAN disclose):
  → Compulsion of law (court order, Income Tax, PMLA requirements)
  → Duty to public (disclosure to prevent fraud/crime)
  → With customer's consent (explicit or implied)
  → Common interest (within banking group — qualified privilege)

Banker's rights:
  → Right of general lien (S.171)
  → Right of set-off (combine accounts to adjust dues)
  → Right to charge interest + service charges (as agreed)
```

---

## Part 3: Negotiable Instruments Act, 1881 — Detailed

### The Three Instruments

```
Promissory Note (S.4):
  → Written promise to pay a fixed sum of money
  → Maker + Payee (TWO parties)
  → No acceptance needed
  → Example: "I promise to pay ₹10,000 to A or order"

Bill of Exchange (S.5):
  → Written order to pay a fixed sum
  → Drawer + Drawee + Payee (THREE parties; payee may be drawer)
  → Drawee must ACCEPT (sign) before becoming liable
  → Example: Trade bills, documentary bills

Cheque (S.6):
  → Bill of exchange drawn on SPECIFIED BANKER payable ON DEMAND
  → THREE parties: Drawer (customer) + Drawee (bank) + Payee
  → Valid for 3 months from date on cheque
```

### Endorsement

```
S.15: Endorsement = signing on back of instrument to transfer rights

Types of Endorsement:
  Blank endorsement      → only signature; makes it bearer instrument
  Full/Special           → specifies name of endorsee ("Pay to X" + signature)
  Restrictive            → "Pay to X only" — stops further negotiation
  Partial                → cannot endorse part of amount — INVALID
  Conditional            → valid (though court may ignore condition in some cases)
  Sans Recours           → "without recourse" — endorser not liable if dishonoured
```

### Crossing of Cheques

```
General Crossing (S.123):
  → Two parallel transverse lines (with or without "& Co." / "not negotiable")
  → Effect: MUST be paid through banking channel (not over the counter)

Special Crossing (S.124):
  → Bank name written between lines
  → Effect: Only that specific bank can collect the cheque

"Not Negotiable" Crossing (S.130):
  → Transferable, BUT transferee gets NO BETTER TITLE than transferor
  → Even a bona fide holder for value gets only what transferor had

"Account Payee" Crossing:
  → Not defined in NI Act; based on banking practice
  → Effect: Must be credited ONLY to named payee's account; not transferable
  → Most protective form of crossing
```

> **Elimination table:**
> "Protect against forgery" → Account Payee crossing (cannot be endorsed further).
> "Limit payout to banking channel" → General crossing.
> "Limit to one specific bank" → Special crossing.
> "Transferee gets no better title" → "Not Negotiable" crossing.

### Holder vs Holder in Due Course (HDC)

```
Holder (S.8): Person entitled to possess instrument and receive payment
  → May be payee or endorsee

Holder in Due Course (S.9): Holder who:
  → Received instrument for CONSIDERATION (paid value)
  → Received it BEFORE MATURITY
  → Received it WITHOUT NOTICE of defect in title

Privileges of HDC:
  → Gets BETTER title than transferor (even if instrument was defective)
  → All prior parties liable to HDC even if they have defences among themselves
  → "Not Negotiable" crossing negates this privilege — transferee = ordinary holder
```

> **Exam heuristic:** HDC = gold standard of protection. "Not Negotiable" = removes that gold standard. Once you take a "Not Negotiable" cheque, you cannot claim HDC status.

### Dishonour of Cheque — Full S.138 Framework

```
Criminal liability conditions (ALL must be satisfied):
  1. Cheque for legally enforceable DEBT or LIABILITY (not gift, donation)
  2. Cheque returned unpaid (insufficient funds / exceeds arrangement / stop payment)
  3. Holder sends WRITTEN NOTICE to drawer within 30 days of dishonour
  4. Drawer FAILS TO PAY within 15 days of receiving notice
  5. Complainant files complaint within 30 days of expiry of 15-day period

Offence: Punishable with imprisonment up to 2 years, or fine up to 2× cheque amount, or BOTH

S.139: Court shall PRESUME the cheque was for debt (rebuttable)
       → Drawer must prove cheque was not for debt

S.141: Offence by company → every person in charge at the time = guilty
       (Directors, MD, Manager etc. unless prove no knowledge/due diligence)

S.142A: Special courts for S.138 cases; jurisdiction = where cheque was drawn/presented

S.143: Summary trial (fast track) for cheque dishonour cases
S.143A: Interim compensation → up to 20% of cheque amount (at trial stage)
S.147: Offences under NI Act (including S.138) are COMPOUNDABLE
S.148: On appeal, appellate court directs DEPOSIT of minimum 20% of fine/compensation
```

> **Exam sequence:** Dishonour → 30 days notice → 15 days to pay → 30 days to complain.
> Total maximum window = 30 + 15 + 30 = 75 days from dishonour to last day to complain.

### Material Alteration — S.87

```
Material alteration = changes that affect the rights and liabilities of parties
  → Altering date, amount, payee's name, place of payment, adding/removing endorsee

Effect: Instrument becomes void as against all parties who did NOT consent
        → But valid against those who consent/sign after alteration

Bank's duty: Compare signature + look for alterations. Bank bears risk of paying
             an materially altered cheque (loss falls on bank, not customer).
```

---

## Part 4: Income Tax Act, 1961

### Five Heads of Income

```
Head 1: Income from Salaries
  → Basic salary, DA, HRA, special allowances, perquisites
  → Exemption: HRA (S.10(13A)), LTA (S.10(5)), gratuity (S.10(10))

Head 2: Income from House Property
  → Actual rent received / deemed rent / annual value
  → Deduction: Municipal taxes paid + 30% standard deduction + interest on loan

Head 3: Profits and Gains of Business or Profession (PGBP)
  → All business income (net of allowable expenses)
  → Depreciation (WDV method), audit of accounts mandatory above thresholds

Head 4: Capital Gains
  → Short-term (held ≤ 24 months for assets; ≤ 12 months for equity)
  → Long-term (held > 24/12 months)
  → LTCG on listed equity: 10% above ₹1 lakh gain (no indexation)
  → STCG on equity: 15%

Head 5: Income from Other Sources
  → Interest on FDs, savings accounts, gifts, lottery, horse racing
  → Residual head — anything not covered in other four heads
```

> **Exam pattern:** "Bank interest received by individual" → Head 5 (Other Sources). NOT business income unless bank IS the business.

### Key Sections for Banks

```
TDS (Tax Deducted at Source):
  → Banks deduct TDS on FD interest if annual interest > ₹40,000
    (₹50,000 for senior citizens)
  → Rate: 10% TDS (if PAN given); 20% TDS (if no PAN)
  → Form 15G/15H: Self-declaration for NIL TDS (if total income below exemption limit)

PAN mandatory for:
  → Opening bank account
  → FD/TD > ₹50,000
  → Cash transactions > ₹50,000 (per transaction)
  → Cash deposits > ₹10 lakh in a year in savings account

Advance Tax (for companies and high income individuals):
  Due Date      Cumulative % of Tax Liability
  June 15       15%
  Sep 15        45%
  Dec 15        75%
  Mar 15        100%
```

### Penalties and Prosecution

```
S.276B: Failure to deduct TDS or failure to pay deducted TDS to government
  → Rigorous imprisonment: 3 months to 7 years + fine

S.234E: Late filing of TDS return
  → Penalty: ₹200 per day of default (max = TDS amount due)

S.10: Major exempt incomes:
  → Agricultural income
  → HUF income from impartible estate
  → Share of profit from partnership firm
  → Interest on NRE account (for NRIs as long as NRI status continues)
  → Provident Fund receipts (after 5 years of contribution)
```

### Key Deductions Under Chapter VI-A

```
S.80C: Max ₹1.5 lakh (PF, PPF, LIC, ELSS, NSC, home loan principal, school fees)
S.80D: Medical insurance premium
  → Self/family: ₹25,000 (₹50,000 for senior citizens)
  → Parents: additional ₹25,000 (₹50,000 for senior parents)
S.80E: Interest on education loan (no upper limit, 8 years)
S.80G: Donations to approved funds/institutions
```

---

## Part 5: Goods and Services Tax (GST)

### Background

```
GST enacted: April 12, 2017 (101st Constitutional Amendment)
GST in force: July 1, 2017 (not July 8 — July 1 is the official date)
Replaced: Central Excise, Service Tax, VAT, CST, Octroi (multiple indirect taxes)

Nature: Destination-based consumption tax
  → Tax goes to the STATE/CENTRE where goods/services are CONSUMED
  → Not where they are produced or sold from
```

> **Exam trap:** GST is DESTINATION-based (not origin-based). State where goods are consumed gets the revenue.

### GST Structure

```
Intra-state transactions (within one state):
  CGST (Central GST) + SGST (State GST) = split equally

Inter-state transactions (between states):
  IGST (Integrated GST) = Centre collects and distributes to destination state

Union Territories (without legislature):
  UTGST instead of SGST

Import of goods: IGST applicable
```

### GST Council

```
GST Council: Constitutional body (Article 279A)
  → Chairperson: Union Finance Minister
  → Members: State Finance Ministers
  → Decisions by 3/4 majority (Centre has 1/3 weightage; states have 2/3)
  → Recommends rates, exemptions, threshold limits, etc.
```

### Key GST Concepts for Banking

```
GST on Banking Services:
  → Most banking fee-based services attract 18% GST
  → Free services (no explicit charge) = no GST
  → Interest on loans = EXEMPT from GST (treated as financial service)
  → Processing fees, cheque return charges, account maintenance = 18% GST

Input Tax Credit (ITC):
  → Banks can claim ITC on inputs used for taxable services
  → Cannot claim ITC on exempt supplies (like interest income)
  → Proportionate ITC = ITC × (taxable turnover / total turnover)

Threshold for Registration:
  → Regular businesses: ₹20 lakh aggregate turnover (₹10 lakh in special category states)
  → Composition scheme: Up to ₹1.5 crore turnover (pay fixed % tax; no ITC)
```

### GST Compliance — Key Returns

```
GSTR-1:  Outward supplies (sales); monthly or quarterly
GSTR-3B: Monthly summary return + payment
GSTR-9:  Annual return (by December 31 of next financial year)
GSTR-9C: Reconciliation statement + Auditor's certificate (if turnover > ₹5 crore)
```

> **CTT (Commodities Transaction Tax):** Tax on non-agricultural commodity derivatives (futures/options). Not part of GST — separate tax. Banks deduct this on certain commodity transactions.

---

## Master Meta-Heuristic: Module C

```
Q: What is a banker's book? Can a printout be admitted as evidence?
→ Yes. S.2(3) includes computer-generated records; certified printout = admissible.

Q: Relationship for savings/current account?
→ Debtor (bank) – Creditor (customer). Bank OWES you the money.

Q: Relationship for locker?
→ Lessor (bank) – Lessee (customer). Bank rents space; NOT responsible for contents.

Q: What is banker's general lien?
→ S.171 Contract Act. Right to RETAIN all property of customer for any general balance.
   Cannot SELL (unlike pledge). Safe custody property excluded.

Q: "Not Negotiable" crossing vs "Account Payee" crossing?
→ "Not Negotiable" = transferable but no better title than transferor.
→ "Account Payee" = NOT transferable; must be collected for named payee only.

Q: Timeline for cheque dishonour complaint?
→ Dishonour → 30 days notice → 15 days to pay → 30 days to file complaint.

Q: S.143A — interim compensation under NI Act?
→ Up to 20% of cheque amount. At trial stage.

Q: S.148 — appeal deposit under NI Act?
→ Minimum 20% of fine/compensation.

Q: Which head of income for bank FD interest?
→ Income from Other Sources (Head 5).

Q: TDS on FD — what is the threshold and rate?
→ Interest > ₹40,000 (₹50,000 for seniors) → TDS @ 10% (20% if no PAN).

Q: Advance tax — what % is due by September 15?
→ 45% of annual tax liability.

Q: GST on loan interest?
→ EXEMPT from GST. Processing fee = taxable at 18%.

Q: IGST applies when?
→ Inter-state transactions. Collected by Centre; distributed to destination state.
```

### The IIBF Banking Operations Worldview

```
Banker's books evidence = practical necessity; certified copy has same weight as original
Banker-customer relationships = each type has distinct legal consequences (don't mix up)
Cheque dishonour is a criminal offence — not just civil remedy
NI Act timelines are strict — missing notice period or complaint period = no criminal case
Income Tax compliance is mandatory for banks (TDS is government's collection mechanism)
GST on banking: fee-based services taxed; interest exempt (otherwise double burden on borrowers)
Material alteration = bank bears the risk if it pays without detecting alteration
```

---

*CAIIB BRBL — Module C | Paper 4*
