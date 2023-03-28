date_created: 2023-03-27

Status: #idea #incomplete
Tags:
```dataview
LIST
FROM "05 Daily Notes"
```
```dataview
LIST
FROM outgoing([[Obsidian]])
```

```dataview
LIST
FROM [[Obsidian]]
```
```dataview
TABLE file.name as Name, file.size as Size
WHERE file.size > 500
SORT file.size desc
```

```dataview
LIST
WHERE length(file.tags) = 0
```

---
## References
