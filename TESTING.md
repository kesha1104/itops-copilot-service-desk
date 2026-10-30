# Manual test plan — ITOps Copilot

Use only fictional data. For reproducible tests, open the live demo in a fresh browser profile (or clear demo data after exporting your own test records). Note that resetting the demo overwrites your browser-local tickets.

| ID | Test case | Expected outcome |
| --- | --- | --- |
| T01 | Load a fresh demo | Eight fictional tickets and matching dashboard counts appear |
| T02 | Create ticket with valid title, category, description | New ticket appears; total count increases |
| T03 | Attempt a blank title or blank description | Form prevents the save and displays validation |
| T04 | Change priority from High to Medium | Saved ticket shows Medium; timeline logs old and new values |
| T05 | Change status Open → In Progress → Resolved | Each saved change appears in timeline with timestamp |
| T06 | Assign/reassign technician | New technician appears; timeline captures assignment changes |
| T07 | Add a troubleshooting note | Note appears in timeline after saving |
| T08 | Select a troubleshooting category | The relevant prewritten, clearly labeled checklist appears |
| T09 | Search for a specific ticket title or ID | Matching results only; nonmatch shows an empty state |
| T10 | Filter by status, priority, and category | Only qualifying rows are displayed |
| T11 | Refresh page in same browser context | Ticket changes remain in localStorage |
| T12 | Export JSON | Download contains demo ticket records |
| T13 | Open public site in private/incognito window | App loads with independent fictional sample data |
| T14 | Narrow browser viewport | Content remains usable without losing core ticket editing |

## Known limitations

- Ticket data is stored per-browser using `localStorage`, not synchronized across visitors.
- Browser-private data may disappear when the private session closes.
- The troubleshooting panel is rule-based and is **not a live AI model**.
- This prototype does not support secure production authentication, authorization, shared audit logs, or real remote remediation.
- Import JSON is **not** implemented in this version; only Export JSON is available.
- Earlier v1 field changes cannot retroactively appear in the v2 history.

## Suggested reviewer scenario

Create an incident for a simulated VPN problem, change status twice, add a note, and confirm the ticket history and dashboard update after refresh.
