---
up: [[Logs]]
type: log
related: [[Health]]
---
X:: [[Health]]

# Exercise Log

```dataview
table without id
file.name as Date, exercise-log as Notes
from #log/journal 
where file.ctime > date("2023-04-17")
sort file.name desc
```






