---
same: [[R]]
---
up:: [[Introduction to Data Science]]
tags:: #source/book #note/reference
X:: [[R]] [[Data Science]]

## Conditional Probabilities

$$
\mbox{Pr}(A \mid B) = \mbox{Pr}(A)
$$
For this we need to calculate __permutations__ with `permutations()`. 

Using the deck of cards created in [[Construct a deck of cards in R]]:

### When order matters

To get the number of possible 2-card hands __when order matters__:

```
hands <- permutations(52, 2, v = deck)

first_card <- hands[,1]
second_card <- hands[,2]
```

To see the number of hands where the first card is a King:

```
kings <- paste("King", suits)
sum(first_card %in% kings)

## [1] 204
```

The conditional probability of the second card being a King _given that the first card was a king_ would be:

```
sum(first_card %in% kings & second_card %in% kings) / 
  sum(first_card %in% kings)

## [1] 0.0588
```

Alternatively the same result can be obtained using averages instead of counts:

```
mean(first_card%in%kings & second_card%in%kings) / mean(first_card%in%kings)

## [1] 0.0588
```

$$
\frac{\mbox{Pr}(A \mbox{ and } B)}{ \mbox{Pr}(A)}
$$

### When order doesn't matter

To compute the changes of a natural 21 in Blackjack:

```
aces <- paste("Ace", suits)
facecard <- c("Ten", "Jack", "Queen", "King")
facecard <- expand.grid(number = facecard, suit = suits)
facecard <- paste(facecard$number, facecard$suit)

hands <- combinations(52, 2, v = deck)

mean((hands[,1] %in% aces & hands[,2] %in% facecard) | 
    (hands[,2] %in% aces & hands[,1] %in% facecard))

## [1] 0.0483
```





