# Week 5 

## Lecture 18: Missing Data Handling

### Missing data
R represents missing observations through the data value NA
We can detect missing values using is.na

The command is.na() returns a logical vector with TRUE in
the element locations that contain missing values represented
by NA.

is.na() will work on vectors, lists, matrices, and data frames.
```R
> x = NA # assign NA to variable x
> is.na(x) # is it missing?
[1] TRUE
```

Now try a vector to know if any value is missing?
```R
> x = c(11, NA, 13, NA)
> is.na(x)
[1] FALSE TRUE FALSE TRUE
```


> Example : How to work with missing data
```R
> x = c(11,NA,13, NA) # vector
> mean(x)
[1] NA
> mean(x, na.rm = TRUE) # NAs can be removed
[1] 12
```


### NA versus NULL
- The null object, called NULL, is returned by some functions and
expressions.

- Note that NA and NULL are not the same.

- NA is a placeholder for something that exists but is missing.

- NULL stands for something that never existed at all.


### Missing data: Location of missing values

To identify the location of NAs, use `which()` function as
`which(is.na( ))`
```R
> x = c(11,NA,13,NA)
> x
[1] 11 NA 13 NA

> which(is.na(x))
[1] 2 4
```

It indicates that the missing values occur at 2nd and 4th places.


To count of NAs the number of NAs , use sum() function as
sum(is.na( ))
```R

> x = c(11,NA,13,NA)
> x

[1] 11 NA 13 NA

> sum(is.na(x))
[1] 2
```

It indicates that there are 2 missing values.

### Missing data: Finding complete cases

To find complete cases, use `complete.cases()` function
which returns a logical vector identifying rows which are
complete cases.

```R
> x = c(11,NA,13,NA)
> x

[1] 11 NA 13 NA

> complete.cases(x)
[1] TRUE FALSE TRUE FALSE
```
It indicates that the values at 1st and 3rd places are not missing.


### Missing data: Finding complete data set
The function `na.omit()` returns the object with listwise
deletion of missing values. Drop out any rows with missing
values anywhere in them and forgets them forever.

```R
> x = c(11,NA,13,NA)
> x
[1] 11 NA 13 NA
> y = na.omit(x)
> y
[1] 11 13
attr(,"na.action")
[1] 2 4
attr(,"class")
[1] "omit" 10

```
### Missing data: Handling values

```R
> x = c(11,NA,13,NA)
> y = na.omit(x)
> y
[1] 11 13
attr(,"na.action")
[1] 2 4
attr(,"class")
[1] "omit"
# Alternative to mean(x,na.rm=TRUE)
> mean(x)
[1] NA
> mean(y)
[1] 12
```
### ✏️ Lecture Summary
```R
> x=NA
> y=5
> is.na(x)
[1] TRUE
> is.na(y)
[1] FALSE
> x=c(1,NA,3,NA)
> is.na(x)
[1] FALSE  TRUE FALSE  TRUE
> mean(x)
[1] NA
> mean(x,na.rm=TRUE)
[1] 2
> y=na
Error: object 'na' not found
> y=Na
Error: object 'Na' not found
> y=NA
> y
[1] NA
> x
[1]  1 NA  3 NA
> which(is.na(x))
[1] 2 4
> sum(is.na(x))
[1] 2
> complete.cases(x)
[1]  TRUE FALSE  TRUE FALSE
> y=na.omit(x)
> y
[1] 1 3
attr(,"na.action")
[1] 2 4
attr(,"class")
[1] "omit"
> mean(x)
[1] NA
> mean(y)
[1] 2
```

## 📗Lecture 19: Conditional Executions – If and If‐Else
### 📘 Control Structures
1. Conditional execution: 
### `if()`
`if(condition){execute commands if condition is TRUE}`
### `if else()`
`if(condition){execute commands if condition is TRUE} else{execute commands if condition is  FALSE}`

`&&` and `||` can be used in complex conditions/expressions.


```R
> x=5
> if (x > 4) x*3
[1] 15
> x=3
> if (x>4) x*3
> # No response for above condition
> if (x>4) {x*3}
> x=5
> if (x>4) {x*3}
[1] 15
> 
> x=6
> if(x>3){
+ print("The value is more than 3")
+ }
[1] "The value is more than 3"
> 
> x=2
> if(x>3){
+ print("The value is more than 3")
+ }
> # No output
> 
> x=5
> if(x==3){x=x-1} else{x=2*x}
> x
[1] 10
> 
> x=3
> if(x==3){x=x-1} else{x=2*x}
> x
[1] 2
> 
> x=6
> if(x>3){
+ print("x is more than 3
+ ")
+ } else{
+ print("x is more than 3")
+ }
[1] "x is more than 3\n"
>
```
## 📗 Lecture 20: Conditional Executions – Nested if else if and ifelse

### 1. Conditional execution: if()
Syntax
`if (condition) {execute commands if condition is TRUE}`

The code in the {} is evaluated if the logical test contained in the ()
is TRUE.

If the logical test is FALSE, R will ignore all of the code in the {}.

### 2. Conditional execution: if else()
Syntax
`if (condition) {executes commands if condition is TRUE}
else { executes commands if condition is FALSE }`


### 3. Conditional execution: Nested if else if()
The if...else...if statement allows to execute a block of code
when there are more than two alternatives.

It extends the earlier if else () condition.

### 3. Conditional execution: Nested if else if()
Syntax
`if (condition1) {
executes commands if condition1 is TRUE
} else if (condition2) {
executes commands if condition2 is TRUE
} else if (condition3) {
executes commands if condition3 is TRUE
}

else {
executes commands if all conditions are FALSE
}
`


3. Conditional execution: Nested if else if()
Example 1:
`x = 5
if ( x==3 ) {
x = x-1
} else if ( x < 3 ) {
x = x+5
} else { x = 2*x }
x
[1] 10`

Interpretation:

If x = 3, then execute x = x – 1.
- If x < 3, then execute x = x + 5.
- If x > 3, then execute x = 2*x.

In this case, x = 5, so x > 3. Thus x = 2*5


3. Conditional execution: Nested if else if()
Example 2:
`x = 2
if ( x==3 ) {
x = x-1
} else if ( x < 3 ) {
x = x+5
} else { x = 2*x }
x
[1] 7`

Interpretation:
- If x = 3, then execute x = x – 1.
- If x < 3, then execute x = x + 5.
- If x > 3, then execute x = 2*x.

In this case, x = 2, so x < 3. Thus x = 2+5

3. Conditional execution: Nested if else if()
Example 3:
`x = 3
if ( x==3 ) {
x = x-1
} else if ( x < 3 ) {
x = x+5
} else { x = 2*x }
x
[1] 2`

Interpretation:
- If x = 3, then execute x = x – 1.
- If x < 3, then execute x = x + 5.
- If x > 3, then execute x = 2*x.

In this case, x = 3. Thus x = 3‐1

### 4. Conditional execution: ifelse()
Syntax
🟨 `ifelse(test, yes, no)`

- 🟡 Useful when: We want Vector‐valued evaluation of conditions .

- For the components in the vector‐valued logical expression test
which provide the value TRUE, the operations given by yes are
executed.

- For the components in the vector‐valued logical expression test
which provide the value FALSE, the operations given by no are
executed.

Example 4:
`> x = 1:10
> x
[1] 1 2 3 4 5 6 7 8 9 10
> ifelse( x<6, x^2, x+1 )
[1] 1 4 9 16 25 7 8 9 10 11`

Interpretation
- If x < 6 (TRUE), then x = x<sup>2</sup> (YES) .
- If x ≥ 6 (FALSE), then x = x + 1 (NO).

- So for x = 1, 2, 3, 4, 5, we get x = x<sup>2</sup>=1, 4, 9, 16, 25

- For x=6, 7, 8, 9, 10, we get x= x+1 = 7, 8, 9, 10, 11 11

Example 5:
```R
x = c(7,9,8,4)
ifelse(x %% 2 == 0,"even number","odd number")
[1] "odd number" "odd number" "even number" "even number"
```
*%%: Modulo Division‐ Finds the remainder after division of one number by
another.*

Interpretation
If the remainder of x divided by 2
- is 0, then print ”even number” (YES) .
- is not equal to 0, then print ”odd number” (NO).
So for x = 7, 9, we get x = "odd number" and
for x=8, 4, we get x= "even number" 13

## 📗Lecture 21: Functions for Conditional Executions – switch and which commands
- `switch()`
- ![Uploading image.png…](Switch)
- `switc(expr,case1,case2,case3,default)`
- ![image](https://user-images.githubusercontent.com/86161735/185751341-95ddeb70-9b48-4cca-b543-fdeacf0e7709.png)

```R
> switch(2,"apple","banana","orange")
[1] "banana"
> switch(1,"apple","banana","orange")
[1] "apple"
> 
> switch("color","color"="blue","gender"="male","volume"=50)
[1] "blue"
> switch("volume","color"="blue","gender"="male","volume"=50)
[1] 50
> 
> switch(4,"apple","banana","orange")
> # No outcome
> switch("size","color"="blue","gender"="male","volume"=50)
> # No outcome
> 
```

```R
> x=c(10,15,8,14,6,12)
> x
[1] 10 15  8 14  6 12
> which(x==14)
[1] 4
> which(x!=12)
[1] 1 2 3 4 5
> which(x>10)
[1] 2 4 6
> 
> x=c(5,7,10,20,13)
> which(x==14)
integer(0)
> which(x==10)
[1] 3
> which(x!=10)
[1] 1 2 4 5
> which(x>=10)
[1] 3 4 5
> which(x<=10)
[1] 1 2 3
> 
> x=matrix(nrow=3, ncol=3, data=1:9)
> x
     [,1] [,2] [,3]
[1,]    1    4    7
[2,]    2    5    8
[3,]    3    6    9
> which.max(x)
[1] 9
> which.min(x)
[1] 1
> which(x%%2==1)
[1] 1 3 5 7 9
> which(x%%2==1, arr.ind=TRUE)
     row col
[1,]   1   1
[2,]   3   1
[3,]   2   2
[4,]   1   3
[5,]   3   3
```
