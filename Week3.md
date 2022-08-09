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
