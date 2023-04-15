up:: [[Introduction to Data Science]]
tags:: #source/book #note/reference
X:: [[R]] [[Data Science]]

## Show a slice of a smooth density plot

```
d >- with(heights, density(height[sex == "Male"]))
tmp <- data.frame(height = d$x, density = d$y)
tmp |>
  ggplot(aes(height, density)) +
  geom_line() +
  geom_area(aes(x = height, density),
            data = filter(tmp, between(height, 65, 68)),
            alpha = 0.4,
            fill = "darkgoldenrod")
```

![[Pasted image 20230413090523.png]]
