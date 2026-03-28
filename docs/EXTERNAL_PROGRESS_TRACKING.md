# External progress tracking (outside GitHub)

GitHub is for **code**. Use one lightweight tool so **everyone sees status without opening Issues.**

## Recommended: Notion

### Step 1 — Create workspace
- Go to [notion.so](https://www.notion.so) → create teamspace **“CSC-215 Bravo”**.

### Step 2 — Create “Tasks” database

Add these properties:

| Property | Type |
|----------|------|
| Name | Title |
| Week | Select → W1, W2, W3, W4, W5 |
| Owner | Person (invite teammates) or Select → M1–M5 |
| Status | Select → Todo, Doing, Blocked, Done |
| Due date | Date |
| GitHub | URL (Issue or PR) |
| Notes | Text |

### Step 3 — Seed rows (copy from master plan)

Create **one row per item** in `PROJECT_MASTER_PLAN.md` §7 (W1-01 … W5-04). Minimum **first week**: W1-01 through W1-13.

### Step 4 — Views
- **Board** grouped by `Status` (Kanban).  
- **Table** filtered by `Week = W2`.  
- **By Owner** for 1:1 check-ins.

### Step 5 — Weekly ritual (Friday)
- PM sets next week’s tasks to **Todo** with due dates.  
- Each member moves their rows to **Done** only after **merge to `main`** or **Overleaf section drafted** (as specified on card).

---

## Alternative: Trello

- **Board:** Bravo CSC-215  
- **Lists:** `Backlog` | `W1` | `W2` | `W3` | `W4` | `W5` | `Done`  
- **Card:** Title + Description (owner M1–M5) + Due + **Attachment** = GitHub link  
- **Power-up (optional):** Calendar for due dates.

---

## Alternative: Google Sheets

Shared spreadsheet, columns:

`Task_id | Description | Owner | Week | Status | Due | GitHub_link | Blocker`

Use **Data → Filter views** → one view per week.

---

## What the PM checks each week

1. Every §7 deliverable has a **card/row**.  
2. **No** task without an **Owner**.  
3. **Blocked** items have a **name** in Notes (“waiting on M3 PR #12”).  
4. Screenshot or paste summary into `docs/meetings/YYYY-MM-DD.md` (optional).
