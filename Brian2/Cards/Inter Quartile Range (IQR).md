up::  [[Probability and Statistics]]
tags:: #source/book #note/reference #on/R #on/PnS 
X:: [[Data Science]] [[Syntax]] [[Introduction to Data Science]]

## Inter Quartile Range (IQR)

The IQR is the difference between the 3rd (75th) and 1st (25%) quantile.

The IQR is best visualized with a [[Box and Whiskers Plot]].

Like the [[Median]], the IQR is robust with respect to outliers.

[[R]] provides the `IQR()` function for this purpose.

```
IQR(x, na.rm = FALSE, type = 7)
```
