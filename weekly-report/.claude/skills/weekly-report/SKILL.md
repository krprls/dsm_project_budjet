---
name: weekly-report
description: Run the Brightleaf weekly report workflow. Calls six agents in order (collector, cleaner, kpi-analyst, problem-finder, action-advisor, report-writer) and pauses for human review three times. Use when the user says "run the weekly report" or similar.
---

# Weekly report controller

Run the six agents **one at a time, in this order**, using the Agent tool with the matching `subagent_type`. Each agent reads the previous agent's files from `work/`, so never run two agents at once.

## Before you start
1. Check that `input/` contains files. If it is empty, stop and ask the user to add this week's files.
2. If `work/` already contains files from an earlier run, ask the user whether to **start fresh** (move the old `work/` to `work/archive/YYYY-MM-DD/`) or **resume** from the first step whose output is missing.

## Steps

| Step | Agent | Done when this exists | Then |
|---|---|---|---|
| 1 | `collector` | `work/01_collected/manifest.md` | If files are missing, tell the user and ask whether to continue |
| 2 | `cleaner` | `work/02_cleaning_log.md` | ⏸ **REVIEW 1** |
| 3 | `kpi-analyst` | `work/03_kpis.md` | continue |
| 4 | `problem-finder` | `work/04_problems.md` | ⏸ **REVIEW 2** |
| 5 | `action-advisor` | `work/05_actions.md` | ⏸ **REVIEW 3** |
| 6 | `report-writer` | `output/weekly_report_*.pdf` | Done: give the user the PDF path |

## Human review pauses (⏸)
At each pause, **stop and end your turn**. Do not continue until the user replies.

1. Show a short summary (at most 10 lines) of the step's output and the path to the full file.
2. Ask: "Reply **ok** to continue, or tell me what to change."
3. If the user asks for changes, either edit the file directly (small edits) or re-run that agent with their feedback added to the prompt. Then show the result and pause again.
4. Write the user's decision at the bottom of the reviewed file, under `## Human review` (date plus what they decided), so later agents follow it.

What to highlight at each pause:
- **REVIEW 1 (cleaning):** suspected duplicates and anything that was changed or flagged. Ask the user to decide on each flagged item.
- **REVIEW 2 (problems):** the problem list and each problem's confidence. Ask whether anything is missing or wrong.
- **REVIEW 3 (actions):** the action table. Ask the user to approve, edit or remove actions.

## When an agent fails
Tell the user which step failed and why, in plain language. Do not skip the step or invent its output.
