up:: [[R]]
tags:: #note/reference #on/R #on/DataVisualization 
X:: [[Data Visualization]]

## Pie Charts in R

Pie charts in [[R]] are bar charts with polar coordinates. eg.

```
ggplot(aes(x="", y=Percentage, fill = Browser)) +
	geom_bar(width = 1, stat = "identity", col = "black") +
	coord_polar(theta = "y")
```

NB **Pie charts are not usually a good idea** because they don't convey much information. Also, people have difficulty judging relative areas but can easily judge relative lengths.

---
### References

