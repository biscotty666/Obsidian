up::
tags:: #note/boat🚤 
X:: 

## Create a list of possibilities in R

```
n <- 6
outcomes <- c(0,1)
l <- rep(list(outcomes), n)
possibilities <- expand.grid(l)
```
`expand.grid(`

---
### References

