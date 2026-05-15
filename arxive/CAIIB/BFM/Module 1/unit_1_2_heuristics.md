# CAIIB BFM Module A: Units 1-2 Heuristics
## Exchange Rates & Forex Business + Liberalized Remittance Scheme

---

## UNIT 1: EXCHANGE RATES & FOREX BUSINESS

### Core Principle
**Banks never quote losses to themselves.**

---

### Key Vocab (Minimal)

**Spot Rate** = Exchange rate for T+2 settlement (today's rate)  
**Forward Rate** = Rate locked today for future delivery (30/60/90/180 days)

**Bid Rate** (first number) = Bank BUYS from customer (lower, bad for customer)  
**Ask Rate** (second number) = Bank SELLS to customer (higher, bad for customer)  
**Spread** = Ask - Bid = Bank's profit

**Forward Premium** = Forward Rate > Spot Rate (market expects home currency to WEAKEN)  
**Forward Discount** = Forward Rate < Spot Rate (market expects home currency to STRENGTHEN)

---

### The Heuristic

**"Bid-Ask Spread + Margin = Bank Always Wins"**

When customer needs forex:
- If money moving OUT (exporter, remitter): Bank uses BID rate - margin deduction → customer gets LESS
- If money moving IN (importer, receiver): Bank uses ASK rate + margin addition → customer pays MORE

**Formula (don't memorize, understand the logic):**
```
TT Buying Rate (exporter remitting OUT) = Bid Rate - (Bid × Margin %)
TT Selling Rate (importer paying OUT) = Ask Rate + (Ask × Margin %)
```

**Why?** Bank captures commission both ways.

---

### Decision Tree for Unit 1 Questions

```
Q: What rate does customer get?

A) Money moving OUT (remitting/exporting)?
   → Use BID rate (lower) - Margin
   → Customer gets LESS rupees per dollar
   → Eliminate options that use Ask rate

B) Money moving IN (importing/receiving)?
   → Use ASK rate (higher) + Margin
   → Customer pays MORE rupees per dollar
   → Eliminate options that use Bid rate

C) Forward premium/discount?
   → Forward > Spot = Premium (exporter wins, importer loses)
   → Forward < Spot = Discount (importer wins, exporter loses)
   → Match question intent to answer

D) Cross-rate (SGD to INR)?
   → Multiply step-by-step (SGD→USD→INR)
   → Each step has margin = final rate worst for customer
   → Answer is NOT simple average
```

---

### Example Application

**Q: Spot USD/INR = 83.50/83.60, Margin = 0.10%. NRE customer remits USD to overseas. What TT Buying rate?**

Using heuristic:
- Customer: NRE remitting OUT
- Rate type: TT BUYING
- Logic: Use BID (lower) - margin
- Math: 83.60 - (83.60 × 0.10%) = 83.5165
- Answer: 83.5165 ✓

---

### Gotchas

1. **Higher INR/USD = rupee WEAKING (not strengthening)**
   - 82→83 per USD = rupee lost value
   - Bad for importers, good for exporters

2. **Forward premium ≠ "currency will depreciate"**
   - It's a market signal + interest rate differential
   - Exporter locking premium = protection + bet that rupee weakens
   - If rupee strengthens instead, exporter loses the hedging fee

3. **Margin is ALWAYS deducted from customer benefit**
   - Never added to customer's advantage
   - Bank always extracts

---

---

## UNIT 2: LIBERALISED REMITTANCE SCHEME (LRS)

### Core Principle
**RBI wants to liberalize small remittances (USD 250K) but control large/business ones.**

---

### Key Vocab (Actual Facts)

**LRS Limit** = USD 250,000 per financial year (April-March)  
**Eligible Purposes** = Education, travel, medical, gifting, investment abroad  
**Ineligible Purposes** = Business, loan repayment to foreign entities

**Approval** = Self-declaration (no RBI individual approval needed within limit)  
**Any Bank** = Authorized dealer (any bank can process, no RBI pre-clearance)

---

### The Heuristic

**"LRS = Pre-Approved Remittance Bucket (USD 250K/FY)"**

```
IF remittance ≤ USD 250,000 per FY
  AND purpose is personal (education/travel/medical/gifting/investment)
  THEN instant approval via self-declaration
  AND bank processes immediately
  AND no RBI individual approval needed

IF remittance > USD 250,000 per FY
  OR purpose is business/loan-repayment
  THEN needs formal RBI approval
  AND goes into slow lane (scrutiny)
```

---

### Decision Tree for Unit 2 Questions

```
Q: What's the question asking?

A) "Can resident remit USD X?"
   → X ≤ 250K + personal purpose? YES (instant, self-declaration)
   → X > 250K? NO (needs RBI approval)
   → X = business purpose? NO (ineligible)

B) "What approval needed?"
   → Within LRS? None (self-declaration)
   → Outside LRS? RBI formal approval
   → Business? RBI approval (not eligible for LRS)

C) "Same FY or new FY?"
   → April-March = 1 FY
   → If January remit 250K, then July remit another 250K?
   → Different FY = fresh 250K bucket = ALLOWED

D) "Who processes?"
   → Any authorized dealer (bank)
   → No RBI individual clearance (if within LRS limit)
```

---

### Example Applications

**Q1: Resident remits USD 150K for daughter's education abroad. Approval?**
- Logic: 150K < 250K + education = eligible
- Answer: Self-declaration only (instant) ✓

**Q2: Resident remits USD 250K in January. In July wants USD 50K more. Allowed?**
- Logic: January (FY1) + July (FY2) = different FY
- Answer: YES (fresh 250K bucket in new FY) ✓

**Q3: Resident wants to remit USD 300K for business venture. What approval?**
- Logic: Business purpose = ineligible for LRS
- Answer: Formal RBI approval (not self-declaration) ✓

---

### Gotchas

1. **LRS is per PERSON, per FINANCIAL YEAR**
   - Not per account, not per day
   - New FY = fresh limit

2. **"Personal investment abroad" IS eligible**
   - But not business
   - Resident buying property overseas = eligible under investment
   - Resident starting business overseas = ineligible

3. **Loan repayment to foreign entities = ineligible**
   - Even if personal loan
   - RBI controls this

4. **Self-declaration ≠ no documentation**
   - Still need KYC, purpose proof, source of funds
   - But NO RBI pre-approval needed

---

---

## Units 1-2 Combined: The Meta-Pattern

Both units follow the same incentive logic:

**RBI + Banks want to:**
- Liberalize small, personal, low-risk flows (forex, remittances)
- Control/scrutinize large, business, high-risk flows
- Capture value via spreads + margins (banks)
- Maintain forex management oversight (RBI)

**In exam questions:**
- Small legitimate transactions = instant, fewer options
- Large/business transactions = approval needed, more complexity
- Margin/spread = always captured from customer
- Customer = always gets worse rate than interbank

---

## Quick Test Yourself

**Unit 1:** Spot 82/83, Margin 0.05%. Importer buys USD to pay supplier. Rate?
- Answer: 83 + (83 × 0.05%) = 83.04 (ASK + margin)

**Unit 2:** Resident remits USD 180K in July for medical treatment. Approval?
- Answer: Self-declaration (within 250K + eligible purpose)

---

**Ready for Unit 3?** Just say "Unit 3" and we'll extract Correspondent Banking + NRI heuristic.
