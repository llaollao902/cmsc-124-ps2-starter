# Vector and Scalar Evaluation

Replace this paragraph after your checks pass. Trace one input, including the
missing value, through `clean_scores_vector()` and `clean_scores_scalar()`.
Compare the two evaluation models, identify where recycling would change the
answer, and explain which implementation you would keep in an R program.

`clean_scores_vector()` runs four whole-vector steps in order, and none of them needs to refer to a single position. First, `is.na(scores)` tests every element at once and returns a same-length logical vector with the names kept. Second, `scores * 2` doubles all four elements together, so Grace's `NA` stays `NA`. Third, `ifelse()` uses the logical vector to choose a value for every position at once: `0` where the test is TRUE, the doubled score otherwise. Grace's doubled `NA` is computed but never chosen, so `0` goes into `clean` instead. Finally, `clean[clean > 20] <- 20` builds a mask over all four positions and overwrites only Linus (24 becomes 20), leaving the other values and the names untouched. The code never orders the elements and the only ordering is between these steps, while the element-by-element work happens inside R's compiled internals.

In `clean_scores_scalar()`, the `for (i in seq_along(out))` loop makes evaluation order visible by processing one element per iteration in a fixed sequence. Each pass retrieves the current score and checks whether it is `NA`. If it is `NA`, the score is replaced with `0`; otherwise, it is doubled and capped at `20` if it exceeds the limit. For example, Ada's score changes from `8` to `16` on the first pass, while Grace's `NA` becomes `0` on the second. Each iteration updates only the current element, leaving all other elements unchanged until their respective turns. Therefore, the processing order does not affect the final output because each score is handled independently.
