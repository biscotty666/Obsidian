up:: [[Probability and Statistics]]
tags:: #source/book #note/reference #on/Statistics 
X::  [[Introduction to Data Science]]

## Gamma distribution

A continuous probability distribution used to model the time that elapses before $\alpha$ occurrences of a randomly occurring event.

Let $X$ equal the elapsed time before the $\alpha^\text{th}$ event and $\theta$ be the average time between occurrences. The [[Cumulative Distribution Function (CDF)]] of $X$ is

$$
F(x) = P(X\le x) = 1 - P(\text{fewer than }\alpha \text{ occurrences before time }x)
$$
__Because we are looking at a certain number of occurrences in a fixed amount of time this is a [[Poisson distribution]].

The gamma distribution takes two parameters, shape $k$ and scale $\theta$ .

![[Pasted image 20230419210956.png]]

![[Pasted image 20230419211006.png]]