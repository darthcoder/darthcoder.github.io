# CAIIB BFM Heuristic Framework
## Solve Questions by Incentive Logic (Not Formula Memorization)

---

## Core Principle: Banks Never Voluntarily Lose Money

All forex, LC, and trade finance questions hinge on this: **Banks capture value through margins, spreads, and premiums.**

---

## VOCAB SET 1: Bid-Ask & Margin Mechanics

### What Banks Quote (Direct: Home/Foreign)
- **BID** (first number) = Bank BUYS from customer (lower rate, unfavorable to customer)
- **ASK** (second number) = Bank SELLS to customer (higher rate, unfavorable to customer)
- **Spread** = ASK - BID = Bank's profit zone

**Quick Rule:** Customer ALWAYS gets the worse rate.

### TT Buying vs TT Selling (What the names mean!)
- **TT Buying Rate** = Bank BUYS from customer (applies to exports, remittances OUT)
  - Heuristic: Customer receives funds → bank uses BID rate, then DEDUCTS margin
  - Customer gets LESS than interbank
  
- **TT Selling Rate** = Bank SELLS to customer (applies to imports, payments OUT)
  - Heuristic: Customer pays bank → bank uses ASK rate, then ADDS margin
  - Customer pays MORE than interbank

**Pattern:** Margin is ALWAYS deducted from customer benefit, never added.

### Exchange Margin (percentage)
- Applied as: Rate ± (Rate × Margin %)
- Direction: ALWAYS works against customer
- Example: 83.60 - (83.60 × 0.10%) = 83.5164 (customer gets less)

---

## VOCAB SET 2: Forward Mechanics (Premium/Discount)

### Forward Premium (Forward Rate > Spot Rate)
- Heuristic: **Market expects HOME currency to WEAKEN**
- Who benefits? 
  - EXPORTERS (earn foreign currency, want it to be worth more) ✓
  - IMPORTERS (pay foreign currency, want it to be worth less) ✗

### Forward Discount (Forward Rate < Spot Rate)
- Heuristic: **Market expects HOME currency to STRENGTHEN**
- Who benefits?
  - IMPORTERS (pay less at future date) ✓
  - EXPORTERS (earn less at future date) ✗

**Quick Rule:** Premium favors exporters. Discount favors importers.

### Annualized Premium/Discount Formula Logic
- If you see "6-month" or "3-month", you're scaling to 12 months
- Formula: (Premium Amount / Spot) × (12 / Months) × 100
- **Heuristic:** Longer the tenure, smaller the absolute premium appears (same rate differential spread over more days)

---

## VOCAB SET 3: TT Rates (Telegraphy Transfer Rates)

### TT Buying Rate (Exporter/Remitter Perspective)
```
TT Buying = Spot BID Rate - (Bid × Margin %)
```
**Why Bid rate?** Bank buys from customer (uses buying price)
**Why deduct margin?** Bank keeps commission
**Heuristic:** Customer gets LEAST amount (2 penalties: spread + margin)

### TT Selling Rate (Importer/Receiver Perspective)
```
TT Selling = Spot ASK Rate + (Ask × Margin %)
```
**Why Ask rate?** Bank sells to customer (uses selling price)
**Why add margin?** Bank keeps commission
**Heuristic:** Customer pays MOST amount (2 penalties: spread + margin)

---

## VOCAB SET 4: Bills & Realization

### Export Bill Buying (Post-shipment finance)
- Exporter delivers goods, asks bank to buy export bill
- Bank uses **TT BUYING RATE** (lower, favorable to bank)
- Plus deducts margin
- **Heuristic:** Exporter gets least rupees; bank captures spread

### Import Bill Selling (Pre-shipment/payment)
- Importer asks bank to pay foreign supplier
- Bank uses **TT SELLING RATE** (higher, favorable to bank)
- Plus adds margin
- **Heuristic:** Importer pays most rupees; bank captures spread

---

## VOCAB SET 5: Cross Rates

### Cross Rate = Intermediate Currency Bridge
Example: SGD to INR (no direct quote)
```
1 SGD = ? INR
Step 1: SGD to USD
Step 2: USD to INR
Step 3: Multiply (chain rule)
```

**Heuristic:** 
- Every conversion step = opportunity for bank to apply margin
- Customer gets worse rate each step
- Final rate is multiplicatively worse, not additively

---

## VOCAB SET 6: LC (Letter of Credit) Gotchas

### Strict Compliance Doctrine
- **Bank examines DOCUMENTS only, not goods**
- If documents match LC terms exactly → bank MUST pay
- If even 1 discrepancy → bank CAN refuse

**Heuristic:** In LC questions asking "will bank pay?"
- YES if docs match (bank has no choice legally)
- NO if discrepancy found (bank protects itself)

### Common LC Discrepancies (Gotcha List)
1. Invoice amount ≠ LC amount
2. Bill of Lading date > Last shipment date (late shipment proof)
3. Insurance cert missing (required in CIF terms)
4. Description of goods ≠ LC description
5. Signature missing or forged

**Heuristic:** If question mentions discrepancy, answer is "Bank will REJECT"

---

## VOCAB SET 7: Export/Import Finance

### Pre-Shipment Finance (PSC - Pre-shipment Credit)
- Given BEFORE shipment
- Security: Stock/hypothecation
- **Heuristic:** Riskier (goods not yet shipped) → higher interest rate

### Post-Shipment Finance (PSC - Post-shipment Credit)
- Given AFTER shipment (documents submitted)
- Security: Goods (via BL) + LC (if confirmed)
- **Heuristic:** Less risky (goods exist, docs verified) → lower interest rate
- Tenure: up to 180 days typically (depends on LC/guarantee)

### Advance Licensing (Pre-Import)
- Importer imported goods BEFORE shipment (raw materials)
- Gets customs duty EXEMPTION for materials used in exports
- **Heuristic:** Importer avoids duty burden upfront

### Duty Drawback (Post-Export)
- Exporter GETS REFUND of duties paid on imported materials used in exports
- Reduces exporter's cost, improves margins
- **Heuristic:** Government incentivizes exports (duty refund)

---

## HEURISTIC DECISION TREE

### Q: Does bank earn from this transaction?
- YES → Bank will do it, customer gets worse terms
- NO → Bank avoids it or charges premium

### Q: Is margin/spread mentioned?
- YES → Always deducted from customer benefit
- NO → Assume bid-ask spread applies by default

### Q: Who moves first (exporter or importer)?
- **Exporter DELIVERS goods first** → Importer has bargaining power → Exporter gets worse terms
- **Importer PAYS first** → Exporter has bargaining power → Importer pays premium

### Q: Forward or Spot?
- **Forward = Lock-in for risk** → Whoever locked locks in benefits (exporter in premium, importer in discount)
- **Spot = Today** → Use bid-ask spread only

### Q: Multiple currencies (cross-rate)?
- **Multiply step-by-step** → Each step has margin → Final rate worse than linear sum

---

## QUICK REFERENCE: Option Elimination

### For TT Buying Rate (exporter remitting):
- ❌ Eliminate: Spot ask price exactly (no margin)
- ❌ Eliminate: Spot bid price exactly (wrong rate type)
- ✅ Keep: Bid price - small deduction (margin captured)

### For TT Selling Rate (importer paying):
- ❌ Eliminate: Spot bid price exactly (no margin)
- ❌ Eliminate: Spot ask price exactly (no margin)
- ✅ Keep: Ask price + small addition (margin captured)

### For Forward Rates:
- If premium and exporter locked: ✓ Favorable
- If discount and exporter locked: ✗ Unfavorable
- If premium and importer locked: ✗ Unfavorable
- If discount and importer locked: ✓ Favorable

### For LC Discrepancy:
- Bank always asks: "Does doc match LC term exactly?"
- YES → Pay (no choice)
- NO → Reject (bank protects itself)

---

## EXAMPLE PATTERNS TO RECOGNIZE

### Pattern 1: "Customer wants to REMIT FUNDS OUT"
- You need: TT BUYING rate
- Logic: Bank buys rupees from customer (uses BID), deducts margin
- Eliminate: Anything higher than bid

### Pattern 2: "Bank PAYS IMPORT BILL for customer"
- You need: TT SELLING rate
- Logic: Bank sells forex to customer (uses ASK), adds margin
- Eliminate: Anything lower than ask

### Pattern 3: "Export bill comes in 30/60/90 days"
- You need: Spot rate + forward differential - margin
- Logic: Exporter locks forward, gets protection
- Eliminate: Spot rates (forward is locked)

### Pattern 4: "LC expires on X, last shipment date is Y"
- Compare Y to expiry + grace period
- If Y > (Expiry + 21 days for presentation): Too late, shipment invalid
- Eliminate: "Bank will pay" if shipment after deadline

---

## VOCAB CHEAT SHEET

| Term | Means | Who Benefits |
|------|-------|--------------|
| TT Buying | Bank buys forex from customer | Bank |
| TT Selling | Bank sells forex to customer | Bank |
| Bid Rate | Bank's buying rate (lower) | Bank |
| Ask Rate | Bank's selling rate (higher) | Bank |
| Spread | Bid-Ask difference | Bank |
| Margin | Commission % | Bank |
| Forward Premium | Forward > Spot | Exporter |
| Forward Discount | Forward < Spot | Importer |
| PSC (Pre) | Before shipment | Bank (asks collateral) |
| PSC (Post) | After shipment | Bank (lower risk) |
| LC | Buyer's commitment to pay | Exporter (insured) |
| Discrepancy | Doc doesn't match LC | Bank (rejects safely) |
| Strict Compliance | Docs examined literally | Bank (protected) |

---

## REAL-EXAM GOTCHAS (Your Heuristic Catches)

1. **Option A:** Exactly interbank rate
   - Too good to be true? It is. Eliminate.
   
2. **Option B:** Slightly worse than interbank
   - This captures margin. Likely answer.
   
3. **Option C:** Much worse than interbank
   - Unless justified by major margin/premium, eliminate.
   
4. **Option D:** Mirrors interbank bid (when sell expected)
   - Backwards. Eliminate.

---

**Key Insight:** You don't need to remember every formula. You need to remember:
- WHO MOVES FIRST (exporter or importer) → determines who has power
- WHICH RATE (bid or ask) → determines direction
- WHERE'S THE MARGIN (always deducted from customer) → determines magnitude

Practice until spotting these patterns takes 10 seconds per question. That's mastery for 50 marks.
