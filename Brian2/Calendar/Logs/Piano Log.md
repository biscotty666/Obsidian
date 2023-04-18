---
up: [[Logs]]
type: log
related: [[Music]]
---
X:: [[Music]]

# Piano Practice Log

```dataview
table without id
file.name as Date, piano-log as Notes
from #log/journal 
where file.ctime > date("2023-04-17")
sort file.name desc
```






