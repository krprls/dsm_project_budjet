# KPIs (step 3)

Run date: 2026-10-04. Input: `work/02_clean/`, with the human decisions in `work/02_cleaning_log.md` (Review 1) applied. Latest period = **September 2026**, previous period = **August 2026** (sales are monthly; Q3 = 1 Jul to 30 Sep 2026). All figures computed in Python (pandas). Numbers only, no interpretation.

## 1. Headline KPIs

| KPI | Latest | Previous | Change |
|---|---|---|---|
| Total units sold (Sep) | 3,887 | 3,771 in Aug | +3.1% |
| Gross revenue (Sep) | Rs 14,08,963 | Rs 14,18,429 in Aug | -0.7% |
| Average price per unit (Sep) | Rs 362.48 | Rs 376.14 in Aug | -3.6% |
| Returns rate (Sep) | 2.47% | 2.39% in Aug | +0.08 pp |
| Q3 units vs Q3 target (all products, to 30 Sep) | 103.5% | 67.5% at end of Aug | +36.0 pp |
| Average feedback rating (Aug, latest month with feedback) | 3.80 / 5 (n=10) | 3.30 in Jul (n=10) | +0.50 |

Notes: revenue is gross (units x list price), per human decision 2. September has no feedback after the 10 September copies were dropped (decision 1), so the rating line compares August with July. Q3 totals: 11,177 units, Rs 41,70,273 gross revenue, Rs 373.11 average price, 272 units returned (2.43%).

## 2. Detail tables

### 2.1 Totals by month

| Month | Units sold | Gross revenue | Avg price / unit | Units returned | Returns rate |
|---|---|---|---|---|---|
| Jul | 3,519 | Rs 13,42,881 | Rs 381.61 | 86 | 2.44% |
| Aug | 3,771 | Rs 14,18,429 | Rs 376.14 | 90 | 2.39% |
| Sep | 3,887 | Rs 14,08,963 | Rs 362.48 | 96 | 2.47% |
| **Q3** | **11,177** | **Rs 41,70,273** | **Rs 373.11** | **272** | **2.43%** |

### 2.2 Units and gross revenue by product

| Product | Units Jul | Units Aug | Units Sep | Units Q3 | Share of Q3 units | Rev Aug | Rev Sep | Rev Sep vs Aug | Rev Q3 | Share of Q3 rev |
|---|---|---|---|---|---|---|---|---|---|---|
| Assam Breakfast | 1,071 | 1,114 | 1,092 | 3,277 | 29.3% | Rs 3,88,786 | Rs 3,81,108 | -2.0% | Rs 11,43,673 | 27.4% |
| Darjeeling First Flush | 459 | 436 | 276 | 1,171 | 10.5% | Rs 2,61,164 | Rs 1,65,324 | -36.7% | Rs 7,01,429 | 16.8% |
| Masala Chai Blend | 1,326 | 1,525 | 1,790 | 4,641 | 41.5% | Rs 4,55,975 | Rs 5,35,210 | +17.4% | Rs 13,87,659 | 33.3% |
| Chamomile Calm | 663 | 696 | 729 | 2,088 | 18.7% | Rs 3,12,504 | Rs 3,27,321 | +4.7% | Rs 9,37,512 | 22.5% |

### 2.3 Units and gross revenue by city

| City | Units Jul | Units Aug | Units Sep | Units Q3 | Share of Q3 units | Rev Aug | Rev Sep | Rev Sep vs Aug | Rev Q3 | Share of Q3 rev |
|---|---|---|---|---|---|---|---|---|---|---|
| Bengaluru | 1,380 | 1,479 | 1,524 | 4,383 | 39.2% | Rs 5,56,321 | Rs 5,52,376 | -0.7% | Rs 16,35,317 | 39.2% |
| Mumbai | 1,173 | 1,256 | 1,296 | 3,725 | 33.3% | Rs 4,72,394 | Rs 4,69,754 | -0.6% | Rs 13,89,775 | 33.3% |
| Delhi NCR | 966 | 1,036 | 1,067 | 3,069 | 27.5% | Rs 3,89,714 | Rs 3,86,833 | -0.7% | Rs 11,45,181 | 27.5% |

### 2.4 % of Q3 unit target by product

| Product | Q3 target | Units to end Aug | % of target at end Aug | Units Q3 (to 30 Sep) | % of target Q3 | Gap to target (units) |
|---|---|---|---|---|---|---|
| Assam Breakfast | 3,300 | 2,185 | 66.2% | 3,277 | 99.3% | -23 |
| Darjeeling First Flush | 1,500 | 895 | 59.7% | 1,171 | 78.1% | -329 |
| Masala Chai Blend | 4,000 | 2,851 | 71.3% | 4,641 | 116.0% | +641 |
| Chamomile Calm | 2,000 | 1,359 | 68.0% | 2,088 | 104.4% | +88 |
| **Total** | **10,800** | **7,290** | **67.5%** | **11,177** | **103.5%** | **+377** |

Targets are for the whole quarter only, so there is no monthly target; "end Aug" is cumulative Jul+Aug units against the full Q3 target.

### 2.5 Returns rate by product x city

| Product | City | Jul | Aug | Sep | Sep vs Aug | Q3 returned / sold | Q3 rate |
|---|---|---|---|---|---|---|---|
| Assam Breakfast | Bengaluru | 1.90% | 2.06% | 2.10% | +0.04 pp | 26 / 1,285 | 2.02% |
| Assam Breakfast | Mumbai | 1.96% | 1.89% | 1.92% | +0.04 pp | 21 / 1,092 | 1.92% |
| Assam Breakfast | Delhi NCR | 2.04% | 1.96% | 2.00% | +0.04 pp | 18 / 900 | 2.00% |
| Darjeeling First Flush | Bengaluru | 2.22% | 1.75% | 1.85% | +0.10 pp | 9 / 459 | 1.96% |
| Darjeeling First Flush | Mumbai | 1.96% | 2.07% | 2.17% | +0.10 pp | 8 / 390 | 2.05% |
| Darjeeling First Flush | Delhi NCR | 2.38% | 1.67% | 2.63% | +0.96 pp | 7 / 322 | 2.17% |
| Masala Chai Blend | Bengaluru | 1.92% | 2.01% | 1.99% | -0.01 pp | 36 / 1,820 | 1.98% |
| Masala Chai Blend | Mumbai | 2.04% | 1.97% | 2.01% | +0.04 pp | 31 / 1,547 | 2.00% |
| Masala Chai Blend | Delhi NCR | 1.92% | 1.91% | 2.04% | +0.13 pp | 25 / 1,274 | 1.96% |
| Chamomile Calm | Bengaluru | 1.92% | 1.83% | 2.10% | +0.27 pp | 16 / 819 | 1.95% |
| Chamomile Calm | Mumbai | 9.05% | 9.05% | 9.05% | +0.00 pp | 63 / 696 | 9.05% |
| Chamomile Calm | Delhi NCR | 2.20% | 2.09% | 2.00% | -0.09 pp | 12 / 573 | 2.09% |

By product (all cities), Q3: Assam Breakfast 1.98%; Darjeeling First Flush 2.05%; Masala Chai Blend 1.98%; Chamomile Calm 4.36%.
All rows except Chamomile Calm x Mumbai, Q3: 209 / 10,481 = 1.99%.

### 2.6 Month-over-month change in units by product

| Product | Jul | Aug | Sep | Aug vs Jul | Sep vs Aug | Sep vs Aug (units) |
|---|---|---|---|---|---|---|
| Assam Breakfast | 1,071 | 1,114 | 1,092 | +4.0% | -2.0% | -22 |
| Darjeeling First Flush | 459 | 436 | 276 | -5.0% | -36.7% | -160 |
| Masala Chai Blend | 1,326 | 1,525 | 1,790 | +15.0% | +17.4% | +265 |
| Chamomile Calm | 663 | 696 | 729 | +5.0% | +4.7% | +33 |
| Total | 3,519 | 3,771 | 3,887 | +7.2% | +3.1% | +116 |

By city, Sep vs Aug units: Bengaluru +3.0%; Mumbai +3.2%; Delhi NCR +3.0%.

### 2.7 Feedback

Rows used: 20 distinct comments (10 July, 10 August, 0 September). Rating scale 1-5.

**Average rating by product**

| Product | Jul (n) | Aug (n) | Aug vs Jul | Q3 (n) |
|---|---|---|---|---|
| Assam Breakfast | 3.50 (2) | 4.33 (3) | +0.83 | 4.00 (5) |
| Darjeeling First Flush | 2.00 (3) | 5.00 (1) | +3.00 | 2.75 (4) |
| Masala Chai Blend | 4.67 (3) | 4.00 (3) | -0.67 | 4.33 (6) |
| Chamomile Calm | 3.00 (2) | 2.67 (3) | -0.33 | 2.80 (5) |

**Average rating by city**

| City | Jul (n) | Aug (n) | Aug vs Jul | Q3 (n) |
|---|---|---|---|---|
| Bengaluru | 4.00 (3) | 4.50 (2) | +0.50 | 4.20 (5) |
| Mumbai | 3.00 (4) | 3.20 (5) | +0.20 | 3.11 (9) |
| Delhi NCR | 3.00 (3) | 4.33 (3) | +1.33 | 3.67 (6) |
| **All** | **3.30 (10)** | **3.80 (10)** | **+0.50** | **3.55 (20)** |

Rating distribution, Q3: 1 star: 2, 2 star: 3, 3 star: 3, 4 star: 6, 5 star: 6.

**Reviews rated 1-2:** 5 of 20 (25%): Jul 3, Aug 2, Sep 0.

| Date | Customer | Product | City | Rating | Comment |
|---|---|---|---|---|---|
| 2026-07-05 | C1054 | Darjeeling First Flush | Mumbai | 2 | Paid for express delivery and it still came late. |
| 2026-07-11 | C1080 | Chamomile Calm | Mumbai | 2 | Box arrived crushed and two sachets were torn open. |
| 2026-07-26 | C1145 | Darjeeling First Flush | Delhi NCR | 1 | Order cancelled after a week because of no stock. Disappointed. |
| 2026-08-11 | C1197 | Chamomile Calm | Mumbai | 1 | Second time the packaging was damaged. Please fix this. |
| 2026-08-23 | C1249 | Chamomile Calm | Mumbai | 2 | Nice tea but the outer box was wet and dented. |

**Complaint / request themes** (one theme per comment)

| Theme | Jul | Aug | Q3 | Products | Customer IDs |
|---|---|---|---|---|---|
| packaging | 1 | 2 | 3 | Chamomile Calm 3 | C1080, C1197, C1249 |
| product request | 2 | 2 | 4 | Masala Chai Blend 3, Assam Breakfast 1 | C1093, C1106, C1275, C1262 |
| delivery | 2 | 0 | 2 | Assam Breakfast 1, Darjeeling First Flush 1 | C1158, C1054 |
| stock | 2 | 0 | 2 | Darjeeling First Flush 2 | C1119, C1145 |
| support | 1 | 0 | 1 | Assam Breakfast 1 | C1067 |
| price | 1 | 0 | 1 | Chamomile Calm 1 | C1132 |
| other (taste) | 0 | 1 | 1 | Masala Chai Blend 1 | C1288 |
| none (positive only) | 1 | 5 | 6 | Masala Chai Blend 2, Assam Breakfast 2, Chamomile Calm 1, Darjeeling First Flush 1 | C1041, C1171, C1184, C1210, C1223, C1236 |

Most common themes: product request (4: subscription x2, 500 g pack, less sweet version), packaging (3, all Chamomile Calm in Mumbai, ratings 2, 1, 2), then delivery (2) and stock (2, both Darjeeling First Flush, July-dated, see note). 6 comments contain no complaint.

## 3. How calculated

**Rows excluded**
- `feedback.csv`: the 10 September rows flagged as copies of July comments were dropped (human decision 1): C1392, C1405, C1301, C1418, C1314, C1327, C1340, C1353, C1366, C1379. 20 rows remain, all distinct comments. September therefore has no feedback.
- No sales or target rows excluded (all 36 sales rows and 4 targets used).

**Rows kept despite flags**
- C1119 and C1145 (Darjeeling First Flush "out of stock" complaints dated July) kept unchanged (human decision 3). Their July date conflicts with the September stockout in the review and meeting notes; the report should note this mismatch. They are counted in July.

**Formulas**
- Total units = sum of `Units sold`; gross revenue = sum of `Revenue (Rs)` (= units x list price; returns not netted off, decision 2).
- Average price per unit = gross revenue / units sold (a mix effect: list prices did not change).
- % of target = Q3 units sold / `Q3 unit target`. Change shown is versus cumulative Jul+Aug units / Q3 target.
- Returns rate = `Units returned` / `Units sold`, per product x city x month; aggregates are sum(returned) / sum(sold), not averages of rates. Change in percentage points (pp).
- Month-over-month change = (units this month / units previous month - 1) x 100.
- Average rating = mean of `rating`; low reviews = rating 1 or 2.
- Themes: each comment hand-mapped to one theme from its text (delivery, packaging, stock, support, price, product request; "other (taste)" for C1288 "too much ginger", which fits none of the listed themes). Positive-only comments (incl. C1171 "quick delivery", C1184 "arrived on time", C1223 "nice packaging") count as no complaint. C1275 ("good value... larger 500 g pack") counted as product request, not price.
- Rounding: percentages to 1 or 2 decimals, prices to 2 decimals; all sums exact. Rupee amounts in Indian grouping.
