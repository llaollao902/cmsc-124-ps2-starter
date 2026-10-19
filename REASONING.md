# Reasoning Before Execution

Write the rule behind each case before you commit your predictions. Replace
every placeholder line below with one to three sentences that name the rule
producing that case's value, type, length, and dimensions. One rule is enough.
After you run and find a miss, add a short correction entry under that case in a
later commit.

## P01
Replace this line with the rule that decides this case.

## P02
Replace this line with the rule that decides this case.

## P03
Replace this line with the rule that decides this case.

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
When a double gets assigned the other items get coerced into the common type which is chosen by the highest in the ladder

## P14
```
adjusted <- ifelse(is.na(scores), 0, scores * 2)
``` 
This line checks each item in scores and assigns the value to zero when it finds a missing value else it doubles the existing value, it's then assigned to the adjusted vector.
```
adjusted[adjusted > 15] <- 15
```
This selects every item that with a value greater than 15 and assigns 15 to the item value.  
This leaves us with a final double vector of
```
[14, 0, 15, 8]
```

## P15
This will create a two 2x2 matrices in order to hold a total of with 4 elements in each matrice stored as an array of the dimension of 2x2x2.  
Although the dimensions used integers, the vector laid into the row contains double since there was no explicit casting as an integer.  
Correction: R's `:` operator builds an `integer` sequence. I totally forgot

Each number will fill the matrices from the left column to the right column going down and filling a column before moving on to the next one. Once one of the matrices is filled up the remaining numbers fill the next matrix

## P16
`c(4L, 7L, 9L)` creates a vector of integer type and the succeeding `[0L]` selects an index that is outside of the vector's index range so it will output a zero length integer
