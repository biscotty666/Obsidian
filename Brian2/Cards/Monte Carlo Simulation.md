up:: [[Introduction to Data Science]]
tags:: #source/book #note/reference #on/PnS 
X:: [[Data Science]] [[Probability and Statistics]]

## Monte Carlo Simulation

A simulation that models the probability of different outcomes by repeating a random process enough times that the results are similar to what would be observed it the process repeated forever.

In [[R]] we use `sample()` together with `replicate()`

```
B <- 10000
events <- replicate(B, sample(beads, 1))](<runners %3C- c("Jamaica", "Jamaica", "Jamaica", 
             "USA", "Ecuador", "Netherlands", 
             "France", "South Africa")

B <- 10000
set.seed(1)
all_from_jamaica <- replicate(B, {
  simulation <- sample(runners, 3)
  all(simulation == "Jamaica")
})
mean(all_from_jamaica)
```
