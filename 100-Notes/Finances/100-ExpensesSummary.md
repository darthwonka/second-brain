---
subject: 
peoples: 
date: November 3, 2023 4:16 PM
cover: "https://i.imgur.com/ce8zJha.jpg"
created: 2023-11-03 16:11
type: note
---
# Due Today!!
```dataview
TASK 
FROM "100-Notes/Finances" 
WHERE (date(due) <= date(today))
```
# Due Next Week

```dataview
TASK 
FROM "100-Notes/Finances"
WHERE (date(today) <= date(due)) AND (date(due) <= date(today) + dur(7 day))
```
# Due Later this Month
```dataview
TASK 
FROM "100-Notes/Finances"
WHERE (date(today) + dur(7 day) <= date(due)) AND (date(due) <= date(today) + dur(14 day))
```