---
up: [[Logs]]
type: log
related: [[Health]]
---
X:: 

# Domestic Log

```dataview
table without id
file.name as Date, dom-log as Notes
from #log/journal 
where dom-log
sort file.name desc
```






