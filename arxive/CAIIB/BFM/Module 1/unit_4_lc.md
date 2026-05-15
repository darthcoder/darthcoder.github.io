# CAIIB BFM Module A: Unit 4
## Documentary Letters of Credit (LC)

---

## What Problem Does LC Solve? (Why It Exists)

### The Trade Dilemma (1500s onwards)

Imagine: Silk merchant in Venice wants to buy spices from merchant in India.

**The Problem:**
- Venetian merchant: "I'm not shipping payment (gold) 6 months before I see goods. You'll vanish."
- Indian merchant: "I'm not shipping spices 6 months before I see payment. You'll never pay."
- Both don't trust each other. Deal dies.

**Before LC existed:** One party always ate the risk. Usually the exporter (goods shipped first, payment hoped-for later).

### The Solution (LC Invented)

**Third party guarantee:** A bank.

- Venetian merchant: Ask their bank to "promise in writing" to pay Indian merchant IF Indian merchant ships goods and proves it with documents (Bill of Lading, Invoice, etc.)
- Indian merchant: Receives LC from Venetian's bank. Now ships goods. Receives payment from bank (not from Venetian directly).
- Venetian merchant: Receives goods. Reimburses their bank later.

**Who wins?**
- Indian merchant: Gets paid by bank (guaranteed), not merchant (risky)
- Venetian merchant: Gets goods before they pay anyone (docs prove shipment)
- Bank: Takes fee for guarantee

**Problem solved:** Strangers 6,000km apart can now trade.

---

## What IS a Letter of Credit? (Grok Definition)

**LC = A bank's written promise to pay a seller IF the seller proves shipment via documents.**

Not a check. Not a guarantee the goods are good. Just: "If you submit perfect documents, I (the bank) will pay."

**Why perfect documents matter:**
- Bank can't inspect cargo (it's 6,000km away at sea)
- Bank can only verify papers (invoice, bill of lading, insurance certificate, inspection report)
- If papers match the LC terms exactly, bank assumes shipment happened and goods are on the way
- Bank pays exporter. Done.

**Why exporter loves this:**
- Gets paid by bank (safe) the moment docs are accepted
- Doesn't wait for importer to receive goods, inspect, and then pay (could take weeks)
- Doesn't chase importer for payment later (risky)

**Why importer accepts this:**
- Gets goods (eventually)
- Only pays once goods are shipped (docs prove it)
- Way better than "pay first, then we'll ship" (old way)

---

## Anatomy of an LC

### Parties Involved

**1. Importer** = Buyer (wants goods, opens LC at their bank)  
**2. Exporter** = Seller (ships goods, presents documents to bank)  
**3. Importer's Bank** = Issuing Bank (opens LC, promises to pay)  
**4. Exporter's Bank** = Advising Bank (tells exporter about LC, may confirm it)

### The Flow

```
1. Importer asks their bank: "Open an LC for USD 100K favoring exporter XYZ"
2. Importer's bank issues LC with terms (e.g., "Ship by Dec 15, Documents by Dec 31")
3. LC sent to exporter's bank (advising bank)
4. Exporter receives LC: "If you ship by Dec 15 and send perfect docs by Dec 31, importer's bank will pay you USD 100K"
5. Exporter ships goods, gets Bill of Lading
6. Exporter collects all docs (invoice, BL, insurance, inspection certificate) matching LC terms exactly
7. Exporter submits docs to their bank (advising bank)
8. Advising bank checks docs. If perfect: accepts them (buys the bill)
9. Exporter gets paid immediately (USD 100K from advising bank)
10. Advising bank sends docs to Issuing Bank (importer's bank)
11. Issuing Bank checks docs. If perfect: pays advising bank
12. Importer receives docs. Can now claim goods from shipping company
```

---

## Types of LC (Not All Created Equal)

### Revocable vs Irrevocable (Critical Distinction)

**Revocable LC:**
- Importer can cancel or modify LC anytime, without exporter's consent
- Exporter has NO protection
- Rare in practice (exporters refuse these)
- Example: Importer opens LC, ships goods, then cancels LC → Exporter stuck

**Irrevocable LC:**
- Importer CANNOT cancel or modify without ALL parties' consent
- Exporter is protected
- Standard in international trade
- **Exam rule: Unless stated, assume LC is Irrevocable**

### Confirmed vs Unconfirmed (Risk Distribution)

**Unconfirmed LC:**
- Only issuing bank (importer's bank) is liable to pay
- Exporter's bank just passes information
- Risk: If issuing bank is weak or country is unstable, payment uncertain
- Exporter bears country risk

**Confirmed LC:**
- Advising bank (exporter's bank) ADDS its own commitment to pay
- If issuing bank fails, advising bank pays
- Exporter has double protection
- Advising bank charges extra fee for this guarantee

### Sight vs Usance (Payment Timing)

**Sight LC:**
- Bank pays immediately upon presentation of perfect documents
- "At sight" = instant payment

**Usance LC (Time LC):**
- Bank accepts docs but pays after fixed period (e.g., 90 days)
- Exporter receives "acceptance" (promise to pay in 90 days)
- Exporter can sell acceptance to another bank at discount to get immediate cash
- Importer gets 90 days to receive goods before paying

---

## The Heuristic (Decision Tree)

### Core Rule: Strict Compliance Doctrine

**BANK EXAMINES DOCUMENTS ONLY, NOT GOODS.**

If documents match LC terms exactly → Bank MUST pay (no choice, legally bound)  
If ANY discrepancy found → Bank CAN refuse (bank has legal right to protect itself)

### Decision Tree for LC Questions

```
Q: What happens in this LC scenario?

A) "Bank receives perfect documents. Will bank pay?"
   → YES (Strict compliance = bank must pay if docs match)

B) "One document has discrepancy (e.g., invoice date wrong). Will bank pay?"
   → NO (Bank can refuse, bank protects itself)

C) "Goods are defective but all documents are perfect. Will bank pay?"
   → YES (Bank only checks docs, not goods. Importer stuck)

D) "Exporter submits docs on Jan 1. LC says 'Last date for presentation Dec 31.' Will bank pay?"
   → NO (Discrepancy = after deadline. Bank can refuse)

E) "BL dated Dec 20. LC says 'Latest shipment date Dec 15.' Bank pays?"
   → NO (Shipment after deadline = discrepancy. Bank refuses)

F) "Can bank refuse even if docs are perfect?"
   → NO (Strict compliance = if perfect, bank has no legal ground to refuse)

G) "Can importer reject LC payment if goods are bad?"
   → NO (Bank already paid exporter. Importer's recourse: sue exporter, or insurance claim)
```

---

## The Gotchas (Where Exam Tricks Hide)

### Gotcha 1: Strict Compliance Doesn't Mean Strict Quality

**What students think:** "LC ensures goods are good quality."  
**What actually happens:** "LC ensures documents are perfect. Goods could be garbage."

**Real example:** Exporter ships sawdust in cocoa beans boxes. Documents say "Cocoa beans, 1000 bags, premium grade, weight 50,000 kg." All docs are perfect. Bank pays. Importer opens boxes in warehouse: sawdust. Bank immune. Exporter has cash. Importer has garbage.

**Why?** Bank examines papers, not boxes. Strict compliance protects bank from liability, NOT importer from fraud.

### Gotcha 2: Discrepancy Definition Is Strict

Bank looks for EXACT match between document and LC term.

**Examples of discrepancies:**
- Invoice says "USD 100,000" but LC says "USD 100,050" (even $50 difference = discrepancy)
- LC says "Goods: Premium Steel Rods" but Invoice says "Steel Rods" (missing "Premium")
- BL says "Shipped: 1000 bags" but invoice says "1010 bags" (quantity mismatch)
- Invoice dated after BL (timing mismatch)

**Even tiny typos = discrepancy.** Bank can refuse.

### Gotcha 3: Grace Periods & Deadlines

**LC expires on Dec 31** → Does that mean docs must be presented by Dec 31?

**NO.** Usually:
- Documents must be presented within 21 days of shipment
- OR within 21 days of LC expiry date (whichever is later)

**Example:** LC expires Dec 31. Goods shipped Dec 30. Exporter has 21 days = until Jan 20 to present docs. Not Dec 31.

**Exam trick:** "LC expires Dec 15. Docs presented Dec 20. Bank pays?" 
- Answer: NO (unless grace period extends, usually doesn't for expired LC)

### Gotcha 4: UCP 600 Rules (Exam Favorite)

**UCP** = Uniform Customs and Practice for Documentary Credits (international LC rules)

Key rules:
- Bank has 5 business days to decide if docs are acceptable
- Bank looks at docs in isolation (not against invoice to goods, just docs-to-LC)
- If bank rejects, must state reason in writing
- Discrepancy = bank refuses, but doesn't harm exporter's credit (exporter can work around via negotiation)

**Exam question:** "Bank found discrepancy. Must bank state reason?"  
**Answer:** YES (UCP 600 requires written reason)

### Gotcha 5: Negotiation vs Acceptance

**Negotiation:**
- Advising bank buys the bill from exporter (gives exporter cash immediately)
- Advising bank becomes liable (takes payment risk)
- Exporter walks with money

**Acceptance:**
- Bank accepts docs but doesn't pay immediately (usance LC)
- Bank gives "acceptance" letter
- Exporter can sell acceptance to another party at discount, or wait 90 days

**Exam distinction:** If LC is "negotiable," exporter can get instant cash. If LC is "accepted" (usance), exporter must wait or sell at discount.

### Gotcha 6: Confirmed LC vs Country Risk

**Scenario:** LC issued by bank in unstable country (currency crisis, political tension).  
**Question:** "Is exporter safe?"

**Answer:** Depends if LC is confirmed.
- If unconfirmed: Exporter bears country risk. Bank might default.
- If confirmed by local bank in exporter's country: Exporter protected.

**Exam trick:** "LC from weak-country bank. Exporter asks for confirmation. Why?"  
**Answer:** To transfer country risk from exporter to strong-country bank.

---

## Common LC Question Patterns (Exam Ready)

### Pattern 1: Discrepancy Detection
"Here are LC terms. Here are submitted docs. Will bank pay?"  
**Approach:** Check each doc against LC term. ANY mismatch = NO.

### Pattern 2: Timeline Issues
"LC expires X. Goods shipped Y. Docs presented Z. Will bank pay?"  
**Approach:** Check if Z is within grace period. Usually 21 days from shipment.

### Pattern 3: Goods Quality Issues
"Docs perfect. Goods defective. What happens?"  
**Approach:** Bank paid. Exporter immune. Importer stuck. Not bank's problem.

### Pattern 4: Confirmation Strategy
"Bank is weak. What should exporter ask for?"  
**Approach:** Confirmation by stronger bank.

### Pattern 5: Payment Timing
"LC is usance 90 days. Docs presented. When does exporter get cash?"  
**Approach:** If bank accepts, exporter can negotiate/sell acceptance. OR wait 90 days. OR ask for discounting.

---

## Quick Reference (Exam Night Prep)

- **LC = Promise to pay if docs are perfect** (not promise that goods are good)
- **Strict compliance = Bank checks docs only, refuses on ANY discrepancy**
- **Irrevocable LC = Standard (unless stated otherwise)**
- **Confirmed LC = Extra protection (advising bank also liable)**
- **Sight LC = Instant payment. Usance LC = Payment after fixed period**
- **Discrepancy = ANY mismatch between doc and LC term, even tiny**
- **Grace period = Usually 21 days from shipment (or from LC expiry, whichever later)**
- **Exporter gets paid = Bank pays, not importer (importer pays bank later)**
- **Importer stuck if goods bad = LC only protects docs, not goods quality**
- **Bank immune = Only checks papers, no liability for cargo**
