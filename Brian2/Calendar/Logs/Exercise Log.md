---
up: [[Logs]]
type: log
related: [[Health]]
---
X:: [[Health]]

# Exercise Log

```dataview
table without id
file.name as Date, exercise-type as Type, exercise-time as Time, exercise-route as Route, exercise-note as Note
from #log/journal 
where exercise-note
sort file.name desc
```


![[Tesuque Bike Routes.png]]




