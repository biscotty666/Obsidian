up:: [[Introduction to Data Science]]
tags:: #source/book #note/reference #on/PnS 
X::  [[Data Science]] [[Probability and Statistics]]

## The Birthday Problem

In a room with 50 people, what is the chance that at least two people have the same birthday. This is an example of the [[Monte Carlo Simulation]] in [[R]]

```
n <- 50
B <- 10000

same_birthday <- function(n) {
  bdays <- sample(1:365, n, replace = TRUE)
  any(duplicated(bdays))
}

results <- replicate(B, same_birthday(50))
```