up::
tags:: #note/boat🚤 
X:: 

## Reorder gotcha in R

Using `data |> mutate(reorder(state, murder_rate)` does not work. Instead use `mutate(state = reorder(state, murder_rate))`.

---
### References

