# Display_highest_value
Display only only those rows which is having highest value comparing comparing few selexted column
library(data.table)

set.seed(3)
DT <- data.table(aa = sample(0:10, 20, replace = TRUE),
                 bb = sample(0:10, 20, replace = TRUE),
                 cc = sample(0:10, 20, replace = TRUE),
                 dd = sample(0:10, 20, replace = TRUE),
                 ee = sample(0:10, 20, replace = TRUE),
                 ff = sample(0:10, 20, replace = TRUE),
                 gg = sample(0:10, 20, replace = TRUE))


DT_clean <- DT[aa > bb & aa > cc & aa > dd & 
                 ee > bb & ee > cc & ee > dd &
                 ff > bb & ff > cc & ff > dd &
                 gg > bb & gg > cc & gg > dd &
                 ee != 0 & ff != 0 & gg != 0]
###Output:
> DT
    aa bb cc dd ee ff gg
 1:  4  8  0  2 10 10  0
 2:  9  7  2  3  9 10  8
 3:  6  5  5  1  3  4  9
 4:  3  1  3  0  8  8  4
 5:  9  8  8  3  4  9  6
 6:  7  7  9  5  5  9  1
 7: 10  5  6  0  6  6  4
 8:  7  2  9  1  6  0  2
 9:  3  5  0  4  2  9  3
10:  9  7  8  1  7  7  2
11:  6  9  0  7  3  7  9
12:  7 10  8  6 10  8  2
13:  7  6  4  6  4  1  8
14:  7  2  1  9  9  1  0
15:  4  4  5  5  7  6  3
16:  1  6  7  2  6  2  9
17:  4  5 10  0  8  0  7
18:  7  7  9  9 10  5  1
19:  4  9  3  1  1  5  2
20:  8  3  8  4  8  7  8

> DT_clean
   aa bb cc dd ee ff gg
1:  9  7  2  3  9 10  8
