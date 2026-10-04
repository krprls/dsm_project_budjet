# Weekly Report Workflow

Turns this week's business files into a **one-page PDF report**. Six AI agents each do one step, and you check the work at three points.

```
input/ → 1 Collect → 2 Clean → ⏸ you check → 3 KPIs → 4 Problems → ⏸ you check
       → 5 Actions → ⏸ you approve → 6 Report → output/weekly_report_DATE.pdf
```

## How to use it

1. **Put this week's files in `input/`:**
   - sales spreadsheet (`.xlsx`, with a targets sheet)
   - customer feedback (`.csv`)
   - business review (`.pdf`)
   - team meeting notes (`.docx`)
   - launch brief (`.txt`)

   The Brightleaf sample files are already there, so you can try it right away.
2. **Open Claude Code in this `weekly-report` folder**, not the folder above it. Otherwise Claude will not find the agents.
3. Type: **`run the weekly report`**
4. Claude will stop three times and show you a short summary. Reply **ok** to continue, or say what to change, for example "remove the duplicate rows" or "drop action 3".
5. Your PDF will appear in `output/`.

## What is in each folder

| Folder | What it holds |
|---|---|
| `input/` | your source files (you add these) |
| `work/` | each agent's result, numbered by step. Open any of them to see how the report was made |
| `output/` | the finished PDF (plus the HTML it was built from) |
| `.claude/agents/` | the six agent instruction files. Edit one to change how that step works |
| `.claude/skills/weekly-report/` | the controller that runs the steps in order and pauses for you |

## Next week
Replace the files in `input/` and run it again. Claude will ask whether to archive the old `work/` folder.
