up:: [[Probability and Statistics]]
tags:: #source/book #note/reference #on/PnS 
X:: 

## Expected Value

American Roulette Payout (Winnings)

Assuming a $1 bet on green with a $17 dollar payout. In [[R]]:

```
green <- 2
black <- 18
red <- 18

p_green <- green / (green+black+red)
p_not_green <- 1 - p_green

winnings <- sum(c(17,-1)*c(p_green, p_not_green))
```