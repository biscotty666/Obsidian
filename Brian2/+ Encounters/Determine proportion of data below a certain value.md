up:: [[Introduction to Data Science]]
tags:: #source/book #note/reference #on/R #on/Statistics 
X:: [[R]] [[Statistics]]

## Determine proportion of data below a certain value

Use the __empirical cumulative distribution function (eCDF)__. 

```
ggplot(aes(x)) +
  stat_ecdf()
```
