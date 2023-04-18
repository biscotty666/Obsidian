dates:: {{date}}
tags:: #log/journal #note/daily 

---
## <% tp.file.title %>

### Quote

<% tp.web.daily_quote() %>

### Progress

### Today's Priorities

### Logs

#### Piano Log

#### Excercise Log

### Reflections

### Tasks

##### New


##### Overdue

```tasks
not done
due before today
```


##### Due today

```tasks
not done
due today
status.type is not IN_PROGRESS
```

##### High and medium priority

```tasks
not done
(priority is high) OR (priority is medium)
sort by priority
```

##### In Progress

```tasks
status.type is IN_PROGRESS
```

##### Others


```tasks
not done
(priority is not high) AND (priority is not medium) AND (is not recurring)
sort by priority
```


---
## Yesterday's Note

<%*
const yesterday = tp.date.yesterday("YYYY-MM-DD")
tR += "[[" + [[yesterday]] + "]]"
%>


