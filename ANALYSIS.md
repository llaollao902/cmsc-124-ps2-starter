# Vector and Scalar Evaluation

Replace this paragraph after your checks pass. Trace one input, including the
missing value, through `clean_scores_vector()` and `clean_scores_scalar()`.
Compare the two evaluation models, identify where recycling would change the
answer, and explain which implementation you would keep in an R program.

`clean_scores_vector()` processes the scores using whole-vector operations rather than handling one element per pass. First, `is.na(scores)` checks all elements at once and produces a logical vector identifying missing values. Then, `ifelse()` replaces each `NA` with `0` and doubles every non-missing score. Next, `clean[clean > 20] <- 20` checks all resulting values and caps those exceeding `20`. For example, Linus's score of `12` becomes `24` and is then capped at `20`, while Grace's `NA` becomes `0`. Each operation applies to the elements selected by its condition, leaving the other values unchanged. The code performs these vectorized operations in sequence and the names are preserved in the final output

In `clean_scores_scalar()`, the `for (i in seq_along(out))` loop makes evaluation order visible by processing one element per iteration in a fixed sequence. Each pass retrieves the current score and checks whether it is `NA`. If it is `NA`, the score is replaced with `0`; otherwise, it is doubled and capped at `20` if it exceeds the limit. For example, Ada's score changes from `8` to `16` on the first pass, while Grace's `NA` becomes `0` on the second. Each iteration updates only the current element, leaving all other elements unchanged until their respective turns. Therefore, the processing order does not affect the final output because each score is handled independently.
