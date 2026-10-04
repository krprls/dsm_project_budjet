# Problems (step 4)

Run date: 2026-10-04. Inputs: `work/03_kpis.md`, `work/02_clean/feedback.csv` (20 distinct comments; the 10 September copies are excluded per human decision 1), `work/01_collected/review.txt`, `meeting_notes.txt`, `launch_brief.txt`.
Ordered by business impact. **Fact** = read directly from the data or documents. **Guess** = interpretation or estimate. All rupee impacts are gross, at list price, and are **estimates**.

---

## 1. Darjeeling First Flush stockout cut September sales and left the product 329 units short of target

**What:** Darjeeling First Flush ran out of stock in September after a supplier delay, so sales fell by more than a third and orders were cancelled.

**Evidence**
- Fact (KPIs): September units 276 vs 436 in August (**-36.7%**, -160 units); revenue Rs 1,65,324 vs Rs 2,61,164 (-Rs 95,840).
- Fact (KPIs): Q3 78.1% of target, gap **-329 units**, the only product clearly below target.
- Fact (KPIs): total September revenue fell 0.7% even though total units rose 3.1%; average price per unit fell 3.6% to Rs 362.48. Darjeeling is the highest-priced product (Rs 599), so losing its units pulls the average down.
- Fact (KPIs): Darjeeling has the second-lowest Q3 rating, 2.75 / 5 (n=4).
- Customer: "Order cancelled after a week because of no stock. Disappointed." (C1145, rating 1); "Loved it but it has been out of stock for three weeks." (C1119, rating 3).
- Review: "Darjeeling First Flush fell sharply in September after a supplier delay left it out of stock for three weeks."
- Meeting notes: "the Darjeeling supplier can only confirm the next batch by 20 October." "Team agreed we cannot enter the festive season with a single supplier."

**Date mismatch (note, per human decision 3):** both stock complaints (C1119, C1145) are dated **July** (20 and 26 July), but the review and meeting notes place the stockout in **September**, and July Darjeeling sales were normal (459 units). Either the feedback dates are wrong, or there was an earlier, smaller stock problem in July that sales do not show. The data cannot tell these apart; the missing data is stock-on-hand or out-of-stock days by month.

**Impact (estimate)**
- Lost September sales: if September had matched the July-August average (447.5 units), about 170 more units would have sold, roughly **Rs 1,03,000** of gross revenue (estimate).
- Q3 target gap: 329 units x Rs 599 = about **Rs 1,97,000** (estimate of revenue the target implied).
- Forward risk (guess): the next batch is not confirmed until 20 October, so the stockout may continue into the festive season. Each further month at September's level instead of the July-August average would cost roughly another Rs 1,00,000 (estimate). Cancelled orders may also lose repeat customers; no data on this.

**Confidence: High** that the stockout happened and cost sales (sales drop, review and meeting notes all agree). **Medium** on the size of the forward risk, because the supplier date is unconfirmed and the complaint dates are inconsistent.

---

## 2. Chamomile Calm in Mumbai is returned at 4.5 times the normal rate, with repeated damaged-box complaints

**What:** About 1 in 11 Chamomile Calm orders in Mumbai is returned, and customers there report crushed, torn and wet boxes.

**Evidence**
- Fact (KPIs): Chamomile Calm x Mumbai returns rate **9.05%** in Q3 (63 returned / 696 sold) vs **1.99%** for every other product-city row combined (209 / 10,481). It is 9.05% in each of July, August and September, so it is not improving.
- Fact (KPIs): this one row drives Chamomile Calm's product returns rate to 4.36% vs about 2% for the other products.
- Fact (KPIs): all 3 "packaging" complaints are Chamomile Calm in Mumbai, rated 2, 1 and 2. They are 3 of the 5 reviews rated 1-2. Chamomile Calm has the lowest Q3 rating (2.80) and Mumbai the lowest city rating (3.11).
- Customer: "Second time the packaging was damaged. Please fix this." (C1197, rating 1); "Box arrived crushed and two sachets were torn open." (C1080); "Nice tea but the outer box was wet and dented." (C1249).
- Review: "Chamomile Calm returns in Mumbai are far above every other product and city. Customers report crushed and wet boxes."
- Meeting notes: "Rohan thinks the thin outer carton is the problem, not the courier. Aisha is not convinced. No decision yet. Need data on returns by courier before choosing."

**Fact vs guess on the cause:** the damage is a fact. The cause is **not known**. The data cannot separate the two explanations raised in the meeting (thin carton vs courier handling), and it also cannot rule out a Mumbai-specific factor such as monsoon moisture ("wet" box). Missing data: returns by courier, returns reason codes, and whether other products shipped to Mumbai use the same carton and courier (other products in Mumbai return at about 2%, which fits a Chamomile-specific carton better than a Mumbai-wide courier problem, but this is a guess). Dev is due to pull returns by courier and product for Mumbai by 9 October.

Side note (fact): the returns rate is exactly 9.05% in all three months (20/221, 21/232, 22/243). This is unusually regular for real returns and may be worth checking at source.

**Impact (estimate)**
- Excess returns: at the normal 1.99% rate, about 14 units would have come back instead of 63, so about **49 excess returned units, roughly Rs 22,000** of gross revenue in Q3 (estimate; excludes shipping, replacement and handling costs, which are not in the data).
- Exposure: Chamomile Calm in Mumbai is Rs 3,12,504 of Q3 gross revenue and growing (221 -> 232 -> 243 units/month).
- Guess: repeat damage ("second time") risks losing repeat buyers and lowers ratings in the second-largest city.

**Confidence: High** that the problem is real and concentrated in Chamomile Calm x Mumbai. **Low** on the cause, because the team disagrees (carton vs courier) and there is no returns-by-courier data yet.

---

## 3. Customer support is slow, with no agreed fix date, ahead of a launch that will add load

**What:** Support replies reportedly take three to four days, and the team has no date to bring them back under 24 hours.

**Evidence**
- Fact (KPIs): 1 of 20 distinct comments is a support complaint (C1067, rating 3). No reply-time KPI exists in the data.
- Customer: "Support took four days to reply about my refund." (C1067, 8 July).
- Review: "Customer support replies slowed to three or four days during August."
- Meeting notes: "Dev: bring support reply time back under 24 hours. No date agreed."
- Launch brief, risks: "Customer support is already slow and launch week will add more questions."

**Fact vs guess:** the only customer evidence is dated July, while the review says the slowdown was in August; no August comment mentions support. The review and meeting notes both say support is slow, so the problem is likely real, but its size and trend are unknown. Missing data: ticket volumes and reply times by week.

**Impact (estimate):** cannot be put in rupees from the data. Guess: slow refund replies add to the pain of problems 1 and 2 (cancelled Darjeeling orders, damaged Chamomile boxes, which both create refund and complaint tickets), and launch week adds questions from up to 400 targeted first-time customers.

**Confidence: Low**, because the evidence is one customer comment plus statements in the review and notes; there are no reply-time numbers, and the timing (July vs August) conflicts.

---

## 4. Some deliveries are slow, including paid express orders

**What:** A few customers report late deliveries, including one who paid for express.

**Evidence**
- Fact (KPIs): 2 of 20 comments are delivery complaints, both July (0 in August).
- Customer: "Paid for express delivery and it still came late." (C1054, Darjeeling First Flush, Mumbai, rating 2); "Strong and fresh. Delivery took six days though." (C1158, Bengaluru, rating 4).
- Counter-evidence: two August comments praise delivery: "Quick delivery this time." (C1171), "it arrived on time." (C1184).

**Fact vs guess:** August comments suggest delivery may already have improved, but with 10 comments a month this cannot be confirmed. It is also unknown whether this is linked to the Mumbai courier question in problem 2. Missing data: delivery times by courier and city, express vs standard on-time rate.

**Impact (estimate):** small on current evidence. Guess: a paid express order arriving late risks a refund of the express fee and a lost customer; no data on how often this happens.

**Confidence: Low**, because there are only 2 complaints, both in July, and later comments are positive.

---

## Upcoming risk: Kashmiri Kahwa launch (15 November 2026)

- **Stock timing.** Fact: launch brief risk "Stock arrives late, as happened with Darjeeling First Flush in September." Meeting notes: Aisha wants pre-orders from 1 November; "Rohan is worried about stock arriving in time." No stock arrival date is given in any document. Estimate: the 30-day goal is 1,200 units x Rs 549 = about **Rs 6,59,000** of gross revenue at risk if stock is late, against a fixed budget of Rs 2,50,000. Guess: pre-orders opened before stock is in hand could repeat the Darjeeling pattern of cancelled orders and complaints (problem 1).
- **Ambitious target (fact vs guess).** Fact: the goal is 1,200 units in 30 days. For comparison, Darjeeling First Flush sold 1,171 units in the whole of Q3, and the best-selling product (Masala Chai Blend) sold 1,790 units in September across three cities. Guess: 1,200 units in the first month for a new product is a stretch.
- **Support load.** See problem 3. Launch week adds questions on top of an already slow queue; 400 first-time customers are targeted.
- **Mumbai packaging.** Fact: open decision in the brief on whether to ship Mumbai orders in the new thicker carton (Rs 14 more per box). The cause of Mumbai damage is not yet known (problem 2), so the launch could inherit the same return rate in Mumbai.
- **Festive-season Darjeeling.** Fact: next Darjeeling batch confirmed only by 20 October; backup suppliers shortlisted by 12 October. Guess: if Darjeeling is still short during the festive season, the launch gift bundles and marketing will be competing for attention with an out-of-stock premium product.

## Data gaps that limit this analysis

- **No September feedback.** All 10 September comments were copies of July comments and were dropped (human decision 1), so customer sentiment during the actual Darjeeling stockout month is not directly measured.
- **Stock data:** no stock-on-hand or out-of-stock days, so the July vs September date mismatch for the stock complaints (C1119, C1145) cannot be resolved.
- **Returns by courier and reason:** needed to separate carton vs courier for Mumbai (due from Dev 9 October).
- **Support reply times and ticket volumes:** none in the data.
- **Small sample:** 20 comments in total (10 per month), so feedback averages and theme counts move a lot with one comment.

Please check: are these the right problems, and is anything missing?

## Human review
**Review 2, 2026-10-04.** Approved as written: all 4 problems plus the Kahwa launch risks.
