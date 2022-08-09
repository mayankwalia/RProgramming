# Week 3

## Lecture 9: Calculations with Data Vectors : Addition, Subtraction, Multiplication & Division

### 9 Calculations
##### 9.1 Addition
```R
> c(2,3,5,7) + c(-2,-3,-5,8)
[1]  0  0  0 15
```
- Both the data vectors have the same no. of elements
- 1st position value in the 1st and 2nd data vector will add up, then the same will happen with second position and so on.

```R
> c(2,3,5,7) + c(8,9) #Attention
[1] 10 12 13 16
```
- No. of elements aren't same.
- First two values will be repeated.
- ![image](https://user-images.githubusercontent.com/86161735/183559204-7223b2c1-9d45-4d9d-b1c2-c47afdc8f03d.png)
- `2+8, 3+9, 5+8, 7+9`

```R
> c(2,3,5,7)+c(8,9,10) #warning/error message
[1] 10 12 15 15
Warning message:
In c(2, 3, 5, 7) + c(8, 9, 10) :
  longer object length is not a multiple of shorter object length
```
![image](https://user-images.githubusercontent.com/86161735/183559576-4f7e9d47-39d2-4fe3-9328-0565cc01720e.png)
---
#### 9.1.1 Summary
![image](https://user-images.githubusercontent.com/86161735/183559653-fa9ae5b2-f6fd-4d66-887e-a6fe494ffd4b.png)
---
#### 9.2 Subtration
```R
> c(2,3,5,7) - c(-2,-3,-5,8)
[1]  4  6 10 -1
> c(2,3,5,7) - c(8,9) #Attention
[1] -6 -6 -3 -2
> c(2,3,5,7) - c(8,9,10) #error message
[1] -6 -6 -5 -1
Warning message:
In c(2, 3, 5, 7) - c(8, 9, 10) :
  longer object length is not a multiple of shorter object length
```

#### 9.3 Multiplication
```R
> c(2,3,5,7) * c(-2,-3,-5,8)
[1]  -4  -9 -25  56
> c(2,3,5,7) * c(8,9) #Attention
[1] 16 27 40 63
> c(2,3,5,7) * c(8,9,10) #error message
[1] 16 27 50 56
Warning message:
In c(2, 3, 5, 7) * c(8, 9, 10) :
  longer object length is not a multiple of shorter object length
> c(2,3,4,5) * C(-2,-3,-5,8)
Error in C(-2, -3, -5, 8) : object not interpretable as a factor
> c(2,3,4,5) * c(7,8,9,10)
[1] 14 24 36 50
> c(2,3,4,5) * c(7,8)
[1] 14 24 28 40
> c(2,3,4,5) * c(7,8,9)
[1] 14 24 36 35
Warning message:
In c(2, 3, 4, 5) * c(7, 8, 9) :
  longer object length is not a multiple of shorter object length
```

#### 9.4 Division
```R
> c(24,20,8,16) / c(3,4,2,8)
[1] 8 5 4 2
> c(24,20,8,16) / c(4,2)
[1]  6 10  2  8
> c(24,20,8,16) / c(4,2,8)
[1]  6 10  1  4
Warning message:
In c(24, 20, 8, 16)/c(4, 2, 8) :
  longer object length is not a multiple of shorter object length
> c(4,8,12,16) / c(2,8,4,8)
[1] 2 1 3 2
> c(4,8,12,16) / c(2,8)
[1] 2 1 6 2
> c(4,8,12,16) / c(2,8,4)
[1] 2 1 3 8
Warning message:
In c(4, 8, 12, 16)/c(2, 8, 4) :
  longer object length is not a multiple of shorter object length
> c(3,4,5,6) / c(1,2,3)
[1] 3.000000 2.000000 1.666667 6.000000
Warning message:
In c(3, 4, 5, 6)/c(1, 2, 3) :
  longer object length is not a multiple of shorter object length
> c(3,4,5,6) / c(-1,-2,-3)
[1] -3.000000 -2.000000 -1.666667 -6.000000
Warning message:
In c(3, 4, 5, 6)/c(-1, -2, -3) :
  longer object length is not a multiple of shorter object length
> c(3,-4,5,-6) / c(1,-2,-3)
[1]  3.000000  2.000000 -1.666667 -6.000000
Warning message:
In c(3, -4, 5, -6)/c(1, -2, -3) :
  longer object length is not a multiple of shorter object length
```
⏭️** Take different combinations (USE BODMAS rule) and try out yourself.**
  
## Lecture 10: R as a Calculator with Scalars and Data Vectors : Power operations, Integer and Modulo divisions

### 10.1 Powers
```R
> 2^3
[1] 8
> 2**3
[1] 8
> #Above two commands are for power operator
> #Now finding square root
> 2**0.5
[1] 1.414214
> 2^0.5
[1] 1.414214
> 2^-0.5
[1] 0.7071068
> 2**-0.5
[1] 0.7071068
> c(2,3,5,7)^2 #application to a vector
[1]  4  9 25 49
> c(2,3,5,7)^c(2,3) #Attention
[1]   4  27  25 343
> c(1,2,3,4,5,6)^c(2,3,4) 
[1]    1    8   81   16  125 1296
> c(2,3,5,7)^c(2,3,4) 
[1]   4  27 625  49
Warning message:
In c(2, 3, 5, 7)^c(2, 3, 4) :
  longer object length is not a multiple of shorter object length
> 3^2
[1] 9
> 3**2
[1] 9
> 3^-2 # Compute inverse of 3^2 
[1] 0.1111111
> 3**-2 # Compute inverse of 3^2 
[1] 0.1111111
> c(2,3,4,5)^3
[1]   8  27  64 125
> c(2,3,4,5)^-2
[1] 0.2500000 0.1111111 0.0625000 0.0400000
> c(2,3,4,5)**2
[1]  4  9 16 25
> c(2,3,4,5)^c(5,4,3,2)
[1] 32 81 64 25
> c(2,3,4,5)^c(3,2)
[1]  8  9 64 25
> c(2,3,4,5)^c(-3,-2)
[1] 0.1250000 0.1111111 0.0156250 0.0400000
> c(2,3,4,5)^-c(3,2)
[1] 0.1250000 0.1111111 0.0156250 0.0400000
> c(2,3,4,5)^c(5,4,3)
[1]   32   81   64 3125
Warning message:
In c(2, 3, 4, 5)^c(5, 4, 3) :
  longer object length is not a multiple of shorter object length
> 
```
### Integer division 
📑Just like `//` in Python 
✔️Returns the fractional part
```R
> 2 %/% 2
[1] 1
> 5 %/% 2
[1] 2
> 7 %/% 3
[1] 2
> c(2,3,5,7) %/% 2
[1] 1 1 2 3
> c(2,3,5,7) %/% c(2,3)
[1] 1 1 2 2
> c(2,3,5) %/% c(2,3)
[1] 1 1 2
Warning message:
In c(2, 3, 5)%/%c(2, 3) :
  longer object length is not a multiple of shorter object length
> 7 %/% 2
[1] 3
> c(5,6,7,8) %/% 2
[1] 2 3 3 4
> c(5,6,7,8) %/% c(2,3,4,5)
[1] 2 2 1 1
> c(5,6,7,8) %/% c(2,3,4,9)
[1] 2 2 1 0
> c(5,6,7,8) %/% c(4,3)
[1] 1 2 1 2
> c(5,6,7,8) %/% c(4,3,2)
[1] 1 2 3 2
Warning message:
In c(5, 6, 7, 8)%/%c(4, 3, 2) :
  longer object length is not a multiple of shorter object length
```
### 10.3 Modulo Division (x mod y) 
📑Just like `%` in Python 
✔️Returns the remainder part
```R
> 2 %% 2
[1] 0
> 3 %% 2
[1] 1
> 7 %% 3
[1] 1
> 7 %% 4
[1] 3
> c(2,3,5,7) %% 2
[1] 0 1 1 1
> c(2,3,5,7) %% -2
[1]  0 -1 -1 -1
> c(2,3,5,7) %% c(2,3)
[1] 0 0 1 1
> c(2,3,5,7) %% c(2,3,5)
[1] 0 0 0 1
Warning message:
In c(2, 3, 5, 7)%%c(2, 3, 5) :
  longer object length is not a multiple of shorter object length
> c(2,3,5,7) %% c(12,13,15)
[1] 2 3 5 7
Warning message:
In c(2, 3, 5, 7)%%c(12, 13, 15) :
  longer object length is not a multiple of shorter object length
> c(2,3,5,7) %% c(1,2,3,4)
[1] 0 1 2 3
> c(2,3,5,7) %% c(1,2,3,4,5)
[1] 0 1 2 3 2
Warning message:
In c(2, 3, 5, 7)%%c(1, 2, 3, 4, 5) :
  longer object length is not a multiple of shorter object length
> c(2,3,5) %% c(2,3)
[1] 0 0 1
Warning message:
In c(2, 3, 5)%%c(2, 3) :
  longer object length is not a multiple of shorter object length
> 7%%3
[1] 1
> c(7,9)%%4
[1] 3 1
> c(7,9,3,4)%%c(2,3,2,3)
[1] 1 0 1 1
> c(7,9,3,4)%%c(3,2,3)
[1] 1 1 0 1
Warning message:
In c(7, 9, 3, 4)%%c(3, 2, 3) :
  longer object length is not a multiple of shorter object length
> 
```
🔖*Take a paper and verify the outputs of the command with pen-paper calculations. Now try to combine all the topic learnt so far.*
*`c(elements)` is used to create a data vector*
## Lecture 11: Built in Functions and Assignments

 Built-in functions:
- `max` : Same output with (individual elements) or without data vector
- `min` : Same output with (individual elements) or without data vector
- ⚠️`mean` : Different output

```R
> max(1.2,3.4,-7.8)
[1] 3.4
> max(c(1.2,3.4,-7.8))
[1] 3.4
> max(0,-1,-2)
[1] 0
> min(1.2,3.4,-7.8)
[1] -7.8
> min(c(1.2,3.4,-7.8))
[1] -7.8
> mean(2,3,4)
[1] 2
> mean(c(2,3,4))
[1] 3
> max(23,170,-98)
[1] 170
> min(23,170,-98)
[1] -98
> min(c(23,170,-98))
[1] -98
> max(c(23,170,-98))
[1] 170
```
Different functions are implimented by different developers. Some use `c` command to input the data and some don't use `c` command.

❓What should you do? Which one is correct way?
✔️ Solution 1: When you use `c` command (data vector command) while providing input, you will always correct output.

`mean(a,b,c)` will return a. It will read first value and find the mean i.e. `mean(a,b,c)=mean(a)=a/1=a`
```R
> mean(1,2,3)
[1] 1
> mean(1)
[1] 1
```
### 11.2 Some other useful functions:
🔖*Most of them are similar to Python, isn't it.*
**Note**
- `sin(x)` : Calculate the sine of x 
- `asin(x)` : Calculate the sine inverse of x 
- `sinh(x)` : Calculate the hyperbolic sine of x 
- `asinh(x)` : Calculate the inverse of hyperbolic sine of x 
![image](https://user-images.githubusercontent.com/86161735/183578003-b7616244-22be-4c56-85cd-5a141227e908.png)

Examples
```R
> abs(-4)
[1] 4
> abs(c(-1,-2,-3,4,5))
[1] 1 2 3 4 5
> sqrt(4)
[1] 2
> sqrt(c(1,2,3,4,5))
[1] 1.000000 1.414214 1.732051 2.000000 2.236068
> sqrt(c(1,4,9))
[1] 1 2 3
> sqrt(c(-1,-4,-9))
[1] NaN NaN NaN
Warning message:
In sqrt(c(-1, -4, -9)) : NaNs produced
> sum(c(2,3,4,5)
+ )
[1] 14
> prod(c(2,3,4,5))
[1] 120
> round(1.23)
[1] 1
> round(1.5)
[1] 2
> round(1.51)
[1] 2
> round(1.50)
[1] 2
> round(2.50)
[1] 2
> round(2.51)
[1] 3
> round(2.555)
[1] 3
> round(2.465)
[1] 2
> round(1.465)
[1] 1
> round(1.46)
[1] 1
> round(0.1)
[1] 0
> round(-0.1)
[1] 0
> round(-0.5)
[1] 0
> round(0.5)
[1] 0
> round(1.5)
[1] 2
> round(-1.5)
[1] -2
> log(10) #Natural log to the base e
[1] 2.302585
> log(exp(1))
[1] 1
> log(c(10,100,1000))
[1] 2.302585 4.605170 6.907755
> log10(10)
[1] 1
> log10(100)
[1] 2
> log10(c(10,100,1000))
[1] 1 2 3
```
**More examples**
```R
> abs(-8)
[1] 8
> abs(c(-8,-9,1,2))
[1] 8 9 1 2
> sqrt(9)
[1] 3
> sqrt(2)
[1] 1.414214
> 2^0.5
[1] 1.414214
> sqrt(c(2,3,4,5))
[1] 1.414214 1.732051 2.000000 2.236068
> sqrt(c(2,3,4,-5))
[1] 1.414214 1.732051 2.000000      NaN
Warning message:
In sqrt(c(2, 3, 4, -5)) : NaNs produced
> sum(c(2,3,4,5))
[1] 14
> prod(c(2,3,4,5))
[1] 120
> 2+3+4+5
[1] 14
> 2*3*$*5
Error: unexpected '$' in "2*3*$"
> 2*3*4*5
[1] 120
> round(100.4)
[1] 100
> round(100.5)
[1] 100
> round(100.6)
[1] 101
> round(101.4)
[1] 101
> round(101.)
[1] 101
> round(101.5)
[1] 102
> round(101.6)
[1] 102
> log(10)
[1] 2.302585
> log(c(10,12,14))
[1] 2.302585 2.484907 2.639057
> log10(c(100,200,300))
[1] 2.000000 2.301030 2.477121
```

### 11.3 Assignments
```R
= c(1,2,3,4)
> x1
[1] 1 2 3 4
> x2 = x1^2
> x2
[1]  1  4  9 16
> c(1,2,3,4) + sum(c(1,2,3,4)) * prod(c(1,2))
[1] 21 22 23 24
> abs( c(1,2,3,4) - sum(c(1,2,3,4))*prod(c(1,2,3,4)))
[1] 239 238 237 236
> abs( c(1,2,3,4) - sum(c(1,2,3,4))*prod(c(1,2)))
[1] 19 18 17 16
```

*Builtin functions aren't difficult at all.*

## Lecture 12: Matrices
*Basics. These are the backbone of ML and DL Models🥲
![image](https://user-images.githubusercontent.com/86161735/183583409-c22d1d1d-0015-40fb-9da9-42a0bd8f6db8.png)
Command: `matrix`
Parameters to be passed:
`nrow` - No of rows in the matrix
`ncol` - No of columns in the matrix
`data` - Actual data values
`Arrangement` - Written column-wise by default
```R
> x = matrix(nrow=4,ncol=2,data=c(1,2,3,4,5,6,7,8))
> x
     [,1] [,2]
[1,]    1    5
[2,]    2    6
[3,]    3    7
[4,]    4    8
> 
```
### 12.2 Accessing
```R
> x
     [,1] [,2]
[1,]    1    5
[2,]    2    6
[3,]    3    7
[4,]    4    8
> x[3,2] #[row,col]
[1] 7
> x[1,1] #[row,col]
[1] 1
> x[-1,-1] #[row,col]
[1] 6 7 8
> x[1,2]
[1] 5
```
```R
> x
     [,1] [,2]
[1,]    1    5
[2,]    2    6
[3,]    3    7
[4,]    4    8
> x[4,2]
[1] 8
> x[2,4]
Error in x[2, 4] : subscript out of bounds
> x(2,2)
Error in x(2, 2) : could not find function "x"
> #Use only square brackets
 ```
### 12.3 Entering data column wise in a matrix:
> Till Now
> ![image](https://user-images.githubusercontent.com/86161735/183586134-2730c884-0200-4bb2-aed3-d374a8bb86af.png)
Use `byrow` parameter. It take boolean value `TRUE` or `FALSE` 
`byrow=FALSE` : By defualt
```R
> x = matrix(nrow=4,ncol=2,data=c(1,2,3,4,5,6,7,8),byrow=TRUE)
> x
     [,1] [,2]
[1,]    1    2
[2,]    3    4
[3,]    5    6
[4,]    7    8
> 
```
Recap 
```R
> x = matrix(nrow=4,ncol=2,data=c(1,2,3,4,5,6,7,8)

> x = matrix(nrow=4,ncol=2,data=c(1,2,3,4,5,6,7,8))
> x
     [,1] [,2]
[1,]    1    5
[2,]    2    6
[3,]    3    7
[4,]    4    8
> x = matrix(nrow=4,ncol=2,data=c(1,2,3,4,5,6,7,8),byrow=FALSE)
> x
     [,1] [,2]
[1,]    1    5
[2,]    2    6
[3,]    3    7
[4,]    4    8
> y = matrix(nrow=4,ncol=2,data=c(1,2,3,4,5,6,7,8),byrow=TRUE)
> y
     [,1] [,2]
[1,]    1    2
[2,]    3    4
[3,]    5    6
[4,]    7    8
> 
```
![image](https://user-images.githubusercontent.com/86161735/183586527-d2db6bb2-2742-47b9-9b74-a7879c261a23.png)

### 12.4 Properties of a Matrix
`dim(x)` : Tells the dimension of the matrix
`row(x)` : Tells the no. of rows of the matrix
`col(x)` : Tells the no. of columns of the matrix
`mode(x)` : Informs the type/storage mode of an object e.g. `numerical`,`logical` etc.
`attributes(x)` : Provides all attrinbutes of an object. Informs the dimension of matrix.
`help("matrix")`

```R
> x
     [,1] [,2]
[1,]    1    5
[2,]    2    6
[3,]    3    7
[4,]    4    8
> dim(x)
[1] 4 2
> nrow(x)
[1] 4
> ncol(x)
[1] 2
> mode(x)
[1] "numeric"
> attributes(x)
$dim
[1] 4 2

> help("matrix")
starting httpd help server ... done
```
-define
- read
- extract
- operations
