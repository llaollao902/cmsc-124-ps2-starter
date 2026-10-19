# Reasoning Before Execution

Write the rule behind each case before you commit your predictions. Replace
every placeholder line below with one to three sentences that name the rule
producing that case's value, type, length, and dimensions. One rule is enough.
After you run and find a miss, add a short correction entry under that case in a
later commit.

## P01
The coercion ladder runs logical, integer, double, character, and the vector takes the highest type present. The third value `3.5` is a double which is the highest type in this vector, so `TRUE` will become `1` and `2L` will become `2`. Therefore, in this case, the value is [1,2,3.5] with type double, length three, and no dimension.

## P02
The coercion ladder runs logical, integer, double, character, and the vector takes the highest type present. The second value `"2"` is character which is the highest type, so `1L` becomes `"1"` and  `TRUE` becomes `"TRUE"`. Therefore, in this case, the value is ["1","2","TRUE"] with type character, length three, and no dimensions.

## P03
Vector arithmetic works element by element, and the shorter operand `c(1L, 2L)` is recycled from its start (repeated twice) to match the length of longer operand (length four), so the sums are 10+1, 20+2, 30+1, and 40+2. Integer plus integer stays integer, so no coercion up the ladder happens. Therefore in this case, the value is [11,22,31,42] with type integer, length four, and no dimensions.

## P04
Positive indexing selects by position, so `c(3L, 1L)` picks the third and then the first element, in that order, and each selected value keeps its name (third and first). Selecting integers from an integer vector leaves the type integer. Therefore, in this case, the value is [third=9,first=8], with type integer, with length two, matching the two indices, and no dimensions.

## P05
A negative index excludes positions, so `-2L` drops the second element `7L` and keeps the first and third. Also, indexing doesn't change the storage, so the integer vector stays integer. Therefore, in this case, the value is [4,9] with type integer, length two and no dimensions.

## P06
The logical index `is.na(x) | x > 10L` evaluated the vector x per position resulting to  FALSE, TRUE, TRUE, FALSE, because at the missing element `TRUE | NA` is `TRUE` and `12L > 10L` is true. Only the `TRUE` positions are kept, and `NA_integer_` keeps the vector integer. Therefore, in this case, the value is [NA,12] with type integer, length two, since two positions were selected, and no dimensions.

## P07
A factor stores integer codes that point at level labels, so the factor has a type of integer even though the values print as text. The explicit `levels` argument fixes the label order as low, high, so in this case, the codes are 1, 2, 1. Grader notation writes a factor as the element labels in order, then `;levels=` and the levels in order, unquoted and without spaces because a factor isn't a character vector, which gives factor[low,high,low];levels=[low,high]. Moreover, the length of the factor is three (since one per element rather than per level) and there are no dimensions.

## P08
A list is its own storage type that keeps unlike elements separate instead of coercing them to one type, so the type is list even though `scores` is integer and `label` is character. Grader notation writes a list as `list{` named components as name=value `}`, with each item in vector notation, so the integers stay unquoted and `"A"` keeps its quotes, giving list{scores=[3,5],label=["A"]}. Moreover, the length counts the components, not the three values inside them, and a plain list has no dimensions, so dimensions are none.

## P09
Data frame is an S3 vector built on top of a list, so its storage type is list. Columns must have equal length and here, `id = 1:2` (integer) and `passed = c(TRUE, FALSE)` (logical) both have two elements, so there are two rows and two columns, and grader notation writes each column in vector notation inside `data.frame[RxC]{...}`, giving data.frame[2x2]{id=[1,2],passed=[TRUE,FALSE]}. The length counts the two columns, not the two rows, and unlike a plain list a data frame carries dimensions of rows by columns, so dim is 2x2.

## P10
A matrix is an atomic vector with a dim attribute, and R fills it by columns, so `matrix(1:6, nrow = 2L)` is stored as 1, 2, 3, 4, 5, 6 with dimensions two rows by three columns. The shorter operand `c(10L, 20L)` is recycled down that stored order as 10, 20, 10, 20, 10, 20, so the top row gets +10 and the bottom row gets +20, and grader notation lists the values in storage order, giving matrix[2x3](11,22,13,24,15,26). Integer plus integer stays integer, the length counts all six cells rather than the two rows, and the result keeps its dim of 2x3.

## P11
Replace this line with the rule that decides this case.

## P12
Replace this line with the rule that decides this case.

## P13
Replace this line with the rule that decides this case.

## P14
Replace this line with the rule that decides this case.

## P15
Replace this line with the rule that decides this case.

## P16
Replace this line with the rule that decides this case.
