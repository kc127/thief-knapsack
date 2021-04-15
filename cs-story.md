#### Thief's Knapsack

A Thief has a knapsack that can hold X lbs of stolen goods
Each stolen good is worth a certain amount of cash, but
the stolen good also weighs a certain weight. This means that
the thief has to pick an optimal combination of items!
The Thief can't pick the same item twice.

#### What is the maximum worth of goods that the thief can steal?

##### Solution:

Let's say we have the following:

Total weight our knapsack can hold: (W) 15 lbs

We have 7 goods, each good has a specific dollar value and weight.
```
goods:   (g)           1, 2,  3, 4, 5,  6, 7
dollars: (d, dollars)  5, 10, 0, 25, 2,  12, 25
weights: (w, lbs)      2, 3,  5, 7, 1,  4,  1
```

Let's say x is an array that contains all the goods that the thief plans to take.
```
x = [x1, x2, ....] where 0 = x1 || x1 = 1 .
```
#### Should the thief steal goods with maximum profit?

Pros: this would translate to more money quickly
Cons: this might make the bag heavy and we might exceed the max weight knapsack can carry

#### or should we steal goods with less weight?

Pros: this would mean we have room for many goods
Cons: this may not necessarily yield high profit

#### Maybe a combination of both? But how?

How about we calculate dollars per weight for each object and select goods based on highest dollars by weight?
```
goods:          (g)           1,     2,     3,    4,      5,   6,     7
dollars:        (d, dollars)  5,     10,    0,    25,     2,   12,    25
weights:        (w, lbs)      2,     3,     5,    7,      1,   4,     1
dollar/weight   (d/w)         5/2,   10/3,  0/5,  25/7,   2/1, 12/4,  25/1
                              2.5,   3.33,  0,    3.57,   2,   3,     25

```
Let's arrange our goods based on dollar/weight
```
goods:          (g)            7,     4,    2,  6,   1,  5,  3
dollar/weight   (d/w)         25,  3.57, 3.33,  3, 2.5,  2,  0
```
Now, let's start filling our array x whose total weight has to be <= 15 lbs
```
x1 = good 7 with weight 1, Remaining W = 15 - 1 = 14 lbs, Total Dollars so far = 5 dollars
x2 = good 4 with weight 7, Remaining W = 14 - 7 = 7 lbs,  Total Dollars so far = 5 + 25 = 30 dollars
x3 = good 2 with weight 3, Remaining W = 7 - 3 = 4 lbs, Total Dollars so far = 30 + 10 = 40 dollars
x4 = good 6 with weight 4, Remaining W = 4 - 4 = 0 lbs, Total Dollars so far = 40 + 12 = 52 dollars
```
Our knapsack will contain the following goods:
```
 x = [7, 4, 2, 6] with total of 52 dollars and total weight of 15 lbs.
```



