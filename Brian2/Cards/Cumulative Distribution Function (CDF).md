up:: [[Probability and Statistics]]
tags:: #source/book #note/reference #on/PnS 
X:: [[Introduction to Data Science]] [[dnorm, pnorm, qnorm, rnorm]]

## Cumulative Distribution Function (CDF)


The probability that $X$ takes is less than or equal to $x$.
$$F(a)=P(X\le a)$$

The probability that $X$ lies in the semi-closed interval $(a,b]$.

$$P(a\lt X \le b)=F_x(b)-F_x(a)$$


In [[R]]:

```
library(tidyverse)
library(dslabs)
data(heights)
x <- 
  heights %>% 
  filter(sex == "Male") %>% 
  pull(height)
F <- function(a) mean(x<=a)
```
What is the chance he is taller than 70 inches?
```
1 - F(70)

## [1] 0.377
```

`pnorm(a, m, s)` provides the cumulative distribution for a normal distribution.


---

### References

[13 Probabilities](https://biscotty666.github.io/Data-Science-R-PH125x/docs/Pt13.html#cumulative-distribution-functions)
[Cumulative distribution function - Wikipedia](https://en.wikipedia.org/wiki/Cumulative_distribution_function)