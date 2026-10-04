# Collector manifest (step 1)

Run date: 2026-10-04. Source folder: `input/`. Output folder: `work/01_collected/`.

## Converted files

| Source file | Converted to | Rows (tables, excl. header) | Method |
|---|---|---|---|
| `brightleaf_q3_sales.xlsx` (sheet "Q3 sales") | `sales.csv` | 36 | openpyxl; columns: Month, Product, City, Units sold, Revenue (Rs), Units returned |
| `brightleaf_q3_sales.xlsx` (sheet "Q3 targets") | `targets.csv` | 4 | openpyxl; columns: Product, Q3 unit target |
| `brightleaf_customer_feedback.csv` | `feedback.csv` | 30 | byte-for-byte copy; columns: date, customer_id, city, product, rating, channel, comment |
| `brightleaf_q3_review.pdf` (1 page) | `review.txt` | n/a | `pdftotext -layout` |
| `brightleaf_team_meeting_notes.docx` | `meeting_notes.txt` | n/a | python-docx (paragraphs; document has no tables) |
| `brightleaf_kahwa_launch_brief.txt` | `launch_brief.txt` | n/a | byte-for-byte copy |

All spreadsheet cells were plain integers/text (no formulas); numbers are written exactly as stored, with no rounding or reformatting.

## Missing expected files

None. All five expected inputs (sales + targets, feedback, review, meeting notes, launch brief) were found.

## Files that could not be read

None.

## Notes

- `review.txt`: bullet glyphs in the PDF list sections ("What went well", "What went wrong", "Open questions for Q4") did not extract; list items appear as indented lines with no bullet character. Text content is otherwise complete.
- All inputs carry the line "Sample document for training. Brightleaf Tea Co. is a fictional company."
