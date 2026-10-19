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
Replace this line with the rule that decides this case.

## P05
Replace this line with the rule that decides this case.

## P06
Replace this line with the rule that decides this case.

## P07
Replace this line with the rule that decides this case.

## P08
Replace this line with the rule that decides this case.

## P09
Replace this line with the rule that decides this case.

## P10
Replace this line with the rule that decides this case.

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
