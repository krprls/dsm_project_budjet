# Cleaning log (step 2)

Run date: 2026-10-04. Input: `work/01_collected/`. Output: `work/02_clean/`.
Period checked: Q3 2026 (2026-07-01 to 2026-09-30). No rows were deleted, no values were invented or estimated.

## 1. Changes made

| File | Row(s) | What changed | Why |
|---|---|---|---|
| `sales.csv` | all 36 + header | Line endings changed from CRLF (Windows) to LF. | Consistent format with the other tables. Values unchanged. |
| `sales.csv` | all 36 + header | New first column `month_start` added (`July` -> `2026-07-01`, `August` -> `2026-08-01`, `September` -> `2026-09-01`). The original `Month` column is kept. | Dates must be in `YYYY-MM-DD`. Sales only has a month name, so the first day of the month is used as the parseable key; it is not a sale date. |
| `sales.csv` | all | Sort by `month_start` checked: rows were already in July, August, September order. No rows moved. | Sort by date. |
| `targets.csv` | all 4 + header | Line endings changed from CRLF to LF. | Consistent format. Values unchanged. |
| `feedback.csv` | all 30 | New column `suspected_duplicate` added (blank or `yes: same comment as <customer_id> (<date>, <city>)`). | Mark repeated comments; see section 2. Nothing deleted. |
| `feedback.csv` | all 30 | New column `source_row` added (data row number in `01_collected/feedback.csv`, 1 = first row after header). | So every row can be traced back after sorting. |
| `feedback.csv` | 29 of 30 rows | Rows sorted by `date` (ties kept in original order). Rows that were out of sequence in the source: source row 10 (C1158, 2026-07-02) moved to position 2; rows 19-20 (C1275 2026-08-02, C1288 2026-08-05) moved to positions 11 and 13; rows 28-30 (C1392 2026-09-02, C1405 2026-09-05, C1418 2026-09-08) moved to positions 21, 22 and 24. All other rows shifted by one or more positions as a result. | Sort by date. |
| `feedback.csv` | all | Quote marks around `product` and `comment` values are now only written where needed (CSV standard minimal quoting). | Side effect of rewriting the CSV; values unchanged. |
| `review.txt`, `meeting_notes.txt`, `launch_brief.txt` | n/a | Copied unchanged. | No tabular data to clean. |

Checked and no change needed:
- **Dates in feedback:** all 30 already valid `YYYY-MM-DD`; all fall inside Q3 2026 and inside the month block they were listed under in the source file.
- **Names:** product names (4: Assam Breakfast, Darjeeling First Flush, Masala Chai Blend, Chamomile Calm), city names (3: Bengaluru, Mumbai, Delhi NCR) and channels (4: Website, Email, WhatsApp, Instagram) are spelled, spaced and cased identically in `sales.csv`, `targets.csv` and `feedback.csv`. No leading/trailing spaces found.
- **Numbers:** no missing values, no negative values, no text in number columns (`Units sold`, `Revenue (Rs)`, `Units returned`, `Q3 unit target`, `rating`). Ratings are all 1-5.
- **Revenue / units:** every sales row gives exactly one constant price per product: Assam Breakfast Rs 349, Darjeeling First Flush Rs 599, Masala Chai Blend Rs 299, Chamomile Calm Rs 449. Sensible, no outliers.
- **Exact duplicate rows:** none in any table. `sales.csv` has exactly one row per Month x Product x City (36 = 3 x 4 x 3). `customer_id` is unique in `feedback.csv`.

## 2. Flagged, not changed

### Suspected duplicates in `feedback.csv` (10 pairs, 20 rows)

Every September comment repeats a July comment word for word, with a new customer ID and the same product, rating and channel. In 9 of 10 pairs the city is different. The September block of feedback is therefore entirely repeated text.

| July row (source row) | September row (source row) | Same product / rating / channel | City July -> Sept | Comment |
|---|---|---|---|---|
| C1041, 2026-07-02 (1) | C1301, 2026-09-08 (21) | yes | Bengaluru -> Delhi NCR | Best chai I have had outside my own kitchen... |
| C1054, 2026-07-05 (2) | C1314, 2026-09-11 (22) | yes | Mumbai -> Bengaluru | Paid for express delivery and it still came late. |
| C1067, 2026-07-08 (3) | C1327, 2026-09-14 (23) | yes | Delhi NCR -> Mumbai | Support took four days to reply about my refund. |
| C1080, 2026-07-11 (4) | C1340, 2026-09-17 (24) | yes | Mumbai -> Mumbai | Box arrived crushed and two sachets were torn open. |
| C1093, 2026-07-14 (5) | C1353, 2026-09-20 (25) | yes | Mumbai -> Bengaluru | Great taste. A subscription option would be useful. |
| C1106, 2026-07-17 (6) | C1366, 2026-09-23 (26) | yes | Delhi NCR -> Mumbai | Please launch a monthly subscription... |
| C1119, 2026-07-20 (7) | C1379, 2026-09-26 (27) | yes | Bengaluru -> Delhi NCR | Loved it but it has been out of stock for three weeks. |
| C1132, 2026-07-23 (8) | C1392, 2026-09-02 (28) | yes | Mumbai -> Bengaluru | Helps me sleep. A bit expensive for 20 sachets. |
| C1145, 2026-07-26 (9) | C1405, 2026-09-05 (29) | yes | Delhi NCR -> Mumbai | Order cancelled after a week because of no stock... |
| C1158, 2026-07-02 (10) | C1418, 2026-09-08 (30) | yes | Bengaluru -> Delhi NCR | Strong and fresh. Delivery took six days though. |

Both rows of each pair are marked in `suspected_duplicate`. A human must decide which (if either) is genuine. Until then, counts by month, city or theme will double-count these themes (only 20 distinct comments exist among the 30 rows).

### Odd values and conflicts

- **Out-of-stock complaints dated July:** C1119 (2026-07-20, "out of stock for three weeks") and C1145 (2026-07-26, "cancelled... because of no stock") are about Darjeeling First Flush, but the review and meeting notes place the stockout in **September**, and July sales of Darjeeling are normal (459 units vs 436 in August, 276 in September). Either the July dates are wrong or the September copies are the originals. Ties in with the duplicate question above.
- **Support delay timing:** the review says support slowed "during August", but the only "four days to reply" comment is dated July (C1067) and September (C1327, a duplicate). No August feedback mentions support speed.
- **Chamomile Calm returns in Mumbai:** 20, 21 and 22 returned units (about 9% of units sold) vs about 2% for every other product/city row. Consistent with the review; not an error, but a real outlier the analysis should highlight.
- **Revenue is gross:** `Revenue (Rs)` equals units sold x list price exactly, so it does not net off returned units (272 units in Q3). Confirm whether the report should use gross or net revenue.
- **Meeting notes date:** `meeting_notes.txt` is dated "Monday 5 October 2026", one day after this run date (2026-10-04). Check whether the date is a typo or the notes are a pre-written agenda.
- **Feedback source order:** rows 10, 19-20 and 28-30 were out of date order in the source (see section 1). All within their month, so no date is wrong; noted only in case the order carried meaning.

## 3. Totals check

### Row counts

| File | Rows before (excl. header) | Rows after | Columns before -> after |
|---|---|---|---|
| `sales.csv` | 36 | 36 | 6 -> 7 (+`month_start`) |
| `targets.csv` | 4 | 4 | 2 -> 2 |
| `feedback.csv` | 30 | 30 | 7 -> 9 (+`suspected_duplicate`, +`source_row`) |

### Sales totals vs `review.txt`

| Measure | From `sales.csv` | Quoted in review | Difference |
|---|---|---|---|
| Total units Q3 | 11,177 | 11,177 | 0 |
| Total revenue Q3 | Rs 41,70,273 | Rs 41,70,273 | 0 |
| Assam Breakfast units / revenue | 3,277 / Rs 11,43,673 | 3,277 / Rs 11,43,673 | 0 |
| Darjeeling First Flush units / revenue | 1,171 / Rs 7,01,429 | 1,171 / Rs 7,01,429 | 0 |
| Masala Chai Blend units / revenue | 4,641 / Rs 13,87,659 | 4,641 / Rs 13,87,659 | 0 |
| Chamomile Calm units / revenue | 2,088 / Rs 9,37,512 | 2,088 / Rs 9,37,512 | 0 |
| % of target (vs `targets.csv`) | 99.3% / 78.1% / 116.0% / 104.4% | 99% / 78% / 116% / 104% | 0 (rounding only) |

Other review statements checked against `sales.csv`: Masala Chai Blend grew every month (1,326 -> 1,525 -> 1,790 units) - correct; it is the largest product by units - correct; Bengaluru is the top city for every product in every month - correct; Darjeeling fell sharply in September (436 -> 276 units) - correct.

Monthly totals for reference: July 3,519 units / Rs 13,42,881; August 3,771 / Rs 14,18,429; September 3,887 / Rs 14,08,963. Total units returned Q3: 272.

## Please check:
1. The 10 duplicate comment pairs in `feedback.csv`: every September comment copies a July one under a new ID (city usually changed). Decide which rows to keep.
2. The July-dated Darjeeling "out of stock" complaints (C1119, C1145) conflict with the September stockout; the July dates may be wrong.
3. Whether revenue should be reported gross (as in the data and review) or net of the 272 returned units.
4. The meeting notes are dated 5 October 2026, one day after this run.
5. `month_start` in `sales.csv` is a derived first-of-month key, not an actual sale date.
Sales totals, per-product figures and target percentages match the review exactly.

## Human review
**Review 1, 2026-10-04.** Decisions:
1. **Repeated feedback comments:** drop the 10 September copies, so the analysis uses the 20 distinct comments. September has no feedback of its own.
2. **Revenue:** use gross revenue (units × list price), Rs 41,70,273, which matches the Q3 review. Returns are reported separately as a returns rate.
3. **July Darjeeling stockout complaints (C1119, C1145):** keep both rows unchanged and add a note in the report about the date mismatch.
4. **Meeting notes dated 5 Oct and the added `month_start` column:** accepted as they are.
