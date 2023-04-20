---
up: [[Logs]]
type: log
related: [[Health]]
---
X:: [[Health]]

# Exercise Log

```dataview
table without id
file.name as Date, exercise-type as Type, exercise-time as Time, exercise-note as Note
from #log/journal 
where exercise-type
sort file.name desc
```






