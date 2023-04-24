---
up: [[Logs]]
type: log
related: [[Music]]
---
tags:: #on/Music 
X:: [[Music]]

# Piano Practice Log

```dataview
table without id
file.name as Date, piano-log as Notes, piano-time as Time
from #log/journal 
where piano-log
sort file.name desc
```






