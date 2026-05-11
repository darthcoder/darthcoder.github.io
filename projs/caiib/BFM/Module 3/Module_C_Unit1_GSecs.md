# Module C — Unit 1: Government Securities Market
### CAIIB BFM | Heavy Numerical Unit | From Scratch

---

## What Is a G-Sec?

```
Government needs money → issues a bond → promises to pay:
  1. Fixed interest (coupon) every 6 months
  2. Face value back at maturity

You buy that bond → you are lending to the government.
Government = zero credit risk. Rate risk = very real.
```

### Anatomy of a G-Sec

```
Face Value (FV)    = Rs. 100 (always assume 100 unless stated)
Coupon Rate        = Fixed % paid on Face Value
Coupon Payment     = Every 6 months (semi-annual)
Maturity           = Date government repays Face Value
Market Price       = What the bond trades at TODAY (≠ Face Value)
```

**Example:**
```
8% G-Sec 2030 → FV = 100, Coupon = 8% per year
Semi-annual coupon = 100 × 8% ÷ 2 = Rs. 4 every 6 months
At maturity (2030) → Rs. 100 returned
```

---

## Part 1: Price & Yield — The Seesaw

### The Single Most Important Rule in G-Secs

```
PRICE and YIELD move in OPPOSITE directions. Always.

Price UP   → Yield DOWN
Price DOWN → Yield UP

This is not a formula. This is gravity. It never reverses.
```

### Why Does This Happen? (Intuition First)

```
Bond pays Rs. 8 per year on FV of Rs. 100.
Yield = what you actually earn on what you PAID.

If you paid Rs. 100 → Yield = 8/100 = 8%
If you paid Rs. 80  → Yield = 8/80  = 10% (same coupon, lower price = higher yield)
If you paid Rs. 110 → Yield = 8/110 = 7.3% (same coupon, higher price = lower yield)
```

### Current Yield Formula

```
Current Yield = (Annual Coupon ÷ Market Price) × 100

Example:
8% G-Sec, Market Price = Rs. 90
Annual Coupon = Rs. 8
Current Yield = (8 ÷ 90) × 100 = 8.89%

Bond trading BELOW face value → Yield ABOVE coupon rate ✓
```

### Price vs Yield Decision Tree

```
Q: Market interest rates RISE (RBI hikes repo)?
→ New bonds offer higher coupons
→ Old bonds become less attractive
→ Old bond prices FALL
→ Old bond yields RISE (to match new market rates)

Q: Market interest rates FALL?
→ Old bonds with higher coupons become attractive
→ Old bond prices RISE
→ Old bond yields FALL

Q: Bond trades at DISCOUNT?
→ Price < Face Value → Yield > Coupon Rate

Q: Bond trades at PREMIUM?
→ Price > Face Value → Yield < Coupon Rate

Q: Bond trades at PAR?
→ Price = Face Value → Yield = Coupon Rate
```

---

## Part 2: Yield to Maturity (YTM)

### What Is YTM?

```
Current Yield only accounts for coupon income.
YTM accounts for:
  1. Coupon income (every 6 months)
  2. Capital gain/loss (if you bought at discount/premium)
  3. Time value of money (all discounted to today)

YTM = total return if you hold the bond to maturity.
YTM is the most important yield measure in the exam.
```

### The Approximate YTM Formula (Use This in Exam)

```
         C + (FV - P) ÷ N
YTM =  ─────────────────────
           (FV + P) ÷ 2

Where:
C  = Annual Coupon (Rs.)
FV = Face Value (Rs. 100)
P  = Current Market Price
N  = Years to Maturity
```

### Worked Example

```
8% G-Sec, 5 years to maturity, Market Price = Rs. 90

C  = 8
FV = 100
P  = 90
N  = 5

Numerator   = 8 + (100 - 90) ÷ 5
            = 8 + 10 ÷ 5
            = 8 + 2
            = 10

Denominator = (100 + 90) ÷ 2
            = 190 ÷ 2
            = 95

YTM = 10 ÷ 95 = 10.53%
```

### YTM Interpretation Rules

```
Bond at DISCOUNT (P < FV):
→ YTM > Current Yield > Coupon Rate
→ (You gain on price + earn coupon)

Bond at PREMIUM (P > FV):
→ YTM < Current Yield < Coupon Rate
→ (You lose on price, drag on return)

Bond at PAR (P = FV):
→ YTM = Current Yield = Coupon Rate
```

### Quick Sanity Check

```
After calculating YTM always verify:

Discount bond → Is YTM > Coupon? ✓ or ✗
Premium bond  → Is YTM < Coupon? ✓ or ✗

If your answer violates this → recalculate.
```

---

## Part 3: Duration & Modified Duration

### What Is Duration?

```
Duration = Weighted average time to receive all cash flows

Plain English:
"How many years does it take to get back your investment
through coupons and principal, on a time-weighted basis?"

Higher coupon → Duration LOWER (you get money back faster)
Longer maturity → Duration HIGHER (more time to wait)
Zero coupon bond → Duration = Maturity exactly
```

### Why Duration Matters

```
Duration measures PRICE SENSITIVITY to interest rate changes.

High Duration → Price changes A LOT when rates move
Low Duration  → Price changes A LITTLE when rates move

Long maturity bonds → High duration → More volatile
Short maturity bonds → Low duration → More stable
```

### Modified Duration Formula

```
Modified Duration = Duration ÷ (1 + YTM/m)

Where:
m = number of coupon payments per year
  = 2 for semi-annual (standard for G-Secs)

Modified Duration tells you:
"For every 1% change in yield, price changes by Modified Duration %"
```

### The Price Change Formula

```
% Change in Price = - Modified Duration × Change in Yield (%)

Negative sign because price and yield move OPPOSITE directions.

Example:
Modified Duration = 4 years
Yield rises by 1% (100 basis points)

% Change in Price = -4 × 1% = -4%
Bond price FALLS by 4%
```

### Worked Example

```
Bond: 8% coupon, 5 years maturity, YTM = 10%, semi-annual coupons

Step 1: Duration (simplified — exam usually gives this or uses approximation)
For exam purposes use:
Duration ≈ (1 + YTM/m) ÷ YTM  for a rough estimate
OR the exam will give Duration directly and ask for Modified Duration.

Step 2: Modified Duration
If Duration = 4.2 years, YTM = 10%, m = 2

Modified Duration = 4.2 ÷ (1 + 0.10/2)
                  = 4.2 ÷ (1 + 0.05)
                  = 4.2 ÷ 1.05
                  = 4.0 years

Step 3: Price impact if yields rise 50 bps (0.5%)
% Price Change = -4.0 × 0.5% = -2%
```

### Duration Rules (Memorise)

```
1. Duration of Zero Coupon Bond     = Maturity (always)
2. Duration rises with Maturity     (more time = more sensitive)
3. Duration falls with Coupon Rate  (higher coupon = get money back faster)
4. Duration falls as YTM rises      (higher discount = earlier cash flows worth more)
5. Modified Duration < Duration     (always, because dividing by >1)
```

### Decision Tree for Duration Questions

```
Q: Which bond is more price sensitive to rate changes?
→ Higher Modified Duration = more sensitive
→ Longer maturity / lower coupon / lower YTM = higher duration

Q: Rates rise by X% — what happens to price?
→ % Price Change = - Modified Duration × X%
→ Price falls (negative sign)

Q: Bank wants to REDUCE interest rate risk on portfolio?
→ Reduce portfolio duration
→ Shift to shorter maturity bonds or higher coupon bonds

Q: Zero coupon bond duration?
→ Always equals its maturity. No calculation needed.
```

---

## Part 4: G-Sec Auctions & Cut-Off Price

### How Government Borrows (Auction Mechanism)

```
RBI conducts auction on behalf of Government.
Banks and PDs bid for G-Secs.
Two types of auctions:

1. YIELD BASED AUCTION → Bidders quote yield they want
                       → Government accepts lowest yields first
                       → Cut-off = highest yield accepted

2. PRICE BASED AUCTION → Bidders quote price they will pay
                       → Government accepts highest prices first
                       → Cut-off = lowest price accepted
```

### Uniform Price vs Multiple Price Auction

```
UNIFORM PRICE (Dutch Auction):
→ All successful bidders pay the CUT-OFF price
→ Even if you bid lower yield (higher price), you pay cut-off
→ Encourages aggressive bidding

MULTIPLE PRICE (French Auction):
→ Each successful bidder pays THEIR OWN bid price
→ You bid high price, you pay high price
→ Discourages aggressive bidding (winner's curse)
```

### Cut-Off Price Logic

```
Yield Based Auction:
Bids come in at various yields.
RBI accepts from LOWEST yield upwards until issue amount is covered.
The LAST (highest) yield accepted = Cut-off yield.
Corresponding price = Cut-off price.

Price and Yield inverse → Cut-off yield highest = Cut-off price lowest.
```

### Worked Example

```
RBI wants to raise Rs. 10,000 Cr via 8% G-Sec auction.

Bids received:
Bidder A: Rs. 2000 Cr at yield 7.90%
Bidder B: Rs. 3000 Cr at yield 7.95%
Bidder C: Rs. 3000 Cr at yield 8.00%
Bidder D: Rs. 4000 Cr at yield 8.05%

Accept lowest yields first:
A: 2000 Cr at 7.90% ✓  (cumulative: 2000)
B: 3000 Cr at 7.95% ✓  (cumulative: 5000)
C: 3000 Cr at 8.00% ✓  (cumulative: 8000)
D: 2000 Cr at 8.05% ✓  (partial — only 2000 of 4000 needed)
                        (cumulative: 10000 — stop here)

Cut-off yield = 8.05%
Cut-off price = price corresponding to 8.05% yield

Bidder D is partially allotted.
Bidder D's remaining 2000 Cr = devolves on PDs.
```

### Devolvement

```
If auction is undersubscribed or bids exceed cut-off:
Unsubscribed portion DEVOLVES on Primary Dealers (PDs).
PDs are obligated to absorb the shortfall.
This is why PDs exist — underwriters of government borrowing.
```

### Decision Tree for Auction Questions

```
Q: Who conducts G-Sec auctions?
→ RBI (on behalf of Government of India)

Q: Yield based auction — who gets allotted?
→ Lowest yield bidders first (government wants to pay least)

Q: Price based auction — who gets allotted?
→ Highest price bidders first (government wants most money)

Q: Uniform price auction — what does everyone pay?
→ Cut-off price (regardless of individual bid)

Q: What happens to unsubscribed portion?
→ Devolves on Primary Dealers

Q: What is a PD?
→ Primary Dealer — SEBI registered, obligated to bid in auctions
                   market makers for G-Secs
```

---

## Master Heuristic: G-Sec Questions

```
Step 1: Is it a PRICE/YIELD question?
→ Apply the seesaw: rates up = price down = yield up

Step 2: Is it a YTM question?
→ Apply the approximate formula
→ Sanity check: discount bond = YTM > coupon

Step 3: Is it a DURATION question?
→ Modified Duration = Duration ÷ (1 + YTM/m)
→ Price change = -ModDur × yield change %
→ Zero coupon duration = maturity

Step 4: Is it an AUCTION question?
→ Yield based = accept lowest yields
→ Price based = accept highest prices
→ Uniform = all pay cut-off
→ Shortfall = devolves on PDs
```

---

## Key Numbers to Remember

| Item | Value |
|---|---|
| G-Sec Face Value | Rs. 100 (standard) |
| Coupon frequency | Semi-annual (every 6 months) |
| Minimum bid in auction | Rs. 10,000 (retail) |
| SLR maintained in | G-Secs (primarily) |
| Who clears G-Sec trades | CCIL |
| Trading platform | NDS-OM |

---

*CAIIB BFM — Module C, Unit 1 | Exam: First Sunday of June 2026*
