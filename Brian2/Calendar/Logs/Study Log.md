---
up: [[Logs]]
type: log
related: [[Health]]
---
X:: 

# Study Log

```dataview
table without id
file.name as Date, study-log as Notes
from #log/journal 
where study-log
sort file.name desc
```





