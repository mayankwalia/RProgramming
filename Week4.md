# Week 4
## Lecture 13: Matrix Operations – Row, Column & Other Operations

`rownames(x)` : Changes the row names of the matrix
`colnames(x)` : Changes the column names of the matrix

```R
> x=matrix(nrow=4,ncol=3,data=c(1:12))
> x
     [,1] [,2] [,3]
[1,]    1    5    9
[2,]    2    6   10
[3,]    3    7   11
[4,]    4    8   12
> rownames(x)=c("r1","r2","r3","r4")
> x
   [,1] [,2] [,3]
r1    1    5    9
r2    2    6   10
r3    3    7   11
r4    4    8   12
> colnames(x)=c("c1","c2","c3")
> x
   c1 c2 c3
r1  1  5  9
r2  2  6 10
r3  3  7 11
r4  4  8 12
```

`data` : Default value
```R
> x=matrix(nrow=4,ncol=2,data=2)
> 
> x
     [,1] [,2]
[1,]    2    2
[2,]    2    2
[3,]    2    2
[4,]    2    2
```
`diag(values to put on diagonal, nrow=x,ncol=y)`: Diagonal Matrix 
```R
> d=diag(1,nrow=3,ncol=3)
> d
     [,1] [,2] [,3]
[1,]    1    0    0
[2,]    0    1    0
[3,]    0    0    1
> t=diag(25,nrow=2,ncol=2)
> t
     [,1] [,2]
[1,]   25    0
[2,]    0   25
> 
```
Try `matrix(nrow=2,ncol=3,data=20)`: Predict the output
Try `diag(5,nrow=3,ncol=3)`: Predict the output

*Question: Identity matrix of order 4*
```R
> d=diag(1,nrow=4,ncol=4)
> d
     [,1] [,2] [,3] [,4]
[1,]    1    0    0    0
[2,]    0    1    0    0
[3,]    0    0    1    0
[4,]    0    0    0    1
```
*Question: Command for putting `1,2,3,4` as the diagonal elements:*
```R
> d=diag(c(1,2,3,4),nrow=4,ncol=4)
> d
     [,1] [,2] [,3] [,4]
[1,]    1    0    0    0
[2,]    0    2    0    0
[3,]    0    0    3    0
[4,]    0    0    0    4
> 
```

### Transpose of a Matrix
Command: `t(x)`
Example 1:
```R
> x=matrix(nrow=4,ncol=2,data=1:8,byrow=T)
> x
     [,1] [,2]
[1,]    1    2
[2,]    3    4
[3,]    5    6
[4,]    7    8
> xt=t(x)
> xt
     [,1] [,2] [,3] [,4]
[1,]    1    3    5    7
[2,]    2    4    6    8
> 
```

`rowSums(x)` Finds the sum of numbers in rows
`colSums(x)` Finds the sum of numbers in columns
`rowMeans(x)` Finds the means of rows
`colMeans(x)` Finds the means of columns

```R
> x=matrix(nrow=4,ncol=2,data=c(1,2,3,4,5,6,7,8))
> x
     [,1] [,2]
[1,]    1    5
[2,]    2    6
[3,]    3    7
[4,]    4    8
> rowSums(x)
[1]  6  8 10 12
> colSums(x)
[1] 10 26
> rowMeans(x)
[1] 3 4 5 6
> colMeans(x)
[1] 2.5 6.5
>
```

*🔖 Practice these commands yourself. Don't move ahead without it*

## Lecture 14: Matrix Operations – Access and Mathematical Operations

### Accessing Elements in a Matrix
```R
> x=matrix(nrow=5,ncol=3,byrow=T,data=1:15)
> x
     [,1] [,2] [,3]
[1,]    1    2    3
[2,]    4    5    6
[3,]    7    8    9
[4,]   10   11   12
[5,]   13   14   15
> x[3,] #Access 3rd row
[1] 7 8 9
> x[,2] #Access 2nd column
[1]  2  5  8 11 14
> x[4:5, 2:3]
     [,1] [,2]
[1,]   11   12
[2,]   14   15
> #4th-5th rows and 2rd-3th columns
> x[c(1,4), c(1,3)]
     [,1] [,2]
[1,]    1    3
[2,]   10   12
> # x[c(rownames), c(column names)] Select only specified rows and columns
> x[3,] #3rd row
[1] 7 8 9
> x[,3] #3rd column
[1]  3  6  9 12 15
> x[1:2,4:5]
Error in x[1:2, 4:5] : subscript out of bounds
> x[4:5,1:2]
     [,1] [,2]
[1,]   10   11
[2,]   13   14
> 
```
### Operations on a Matrix
```R
> x=matrix(nrow=4,ncol=2,data=1:8,byrow=T)
> x
     [,1] [,2]
[1,]    1    2
[2,]    3    4
[3,]    5    6
[4,]    7    8
> x+5
     [,1] [,2]
[1,]    6    7
[2,]    8    9
[3,]   10   11
[4,]   12   13
> x-5
     [,1] [,2]
[1,]   -4   -3
[2,]   -2   -1
[3,]    0    1
[4,]    2    3
> 5*x
     [,1] [,2]
[1,]    5   10
[2,]   15   20
[3,]   25   30
[4,]   35   40
> x*5
     [,1] [,2]
[1,]    5   10
[2,]   15   20
[3,]   25   30
[4,]   35   40
> x*0
     [,1] [,2]
[1,]    0    0
[2,]    0    0
[3,]    0    0
[4,]    0    0
> x/2
     [,1] [,2]
[1,]  0.5    1
[2,]  1.5    2
[3,]  2.5    3
[4,]  3.5    4
> x/3
          [,1]      [,2]
[1,] 0.3333333 0.6666667
[2,] 1.0000000 1.3333333
[3,] 1.6666667 2.0000000
[4,] 2.3333333 2.6666667
> x+10
     [,1] [,2]
[1,]   11   12
[2,]   13   14
[3,]   15   16
[4,]   17   18
```
### Additions and Subtractions of Matrix
⚠️ Both matrices should be of the same dimensions!
```R
> x=matrix(nrow=4,ncol=2,data=1:8,byrow=T)
> y=matrix(nrow=4,ncol=2,data=11:18,byrow=T)
> x
     [,1] [,2]
[1,]    1    2
[2,]    3    4
[3,]    5    6
[4,]    7    8
> y
     [,1] [,2]
[1,]   11   12
[2,]   13   14
[3,]   15   16
[4,]   17   18
> # should be of same dimensions to perform addition and subtraction
> x+y
     [,1] [,2]
[1,]   12   14
[2,]   16   18
[3,]   20   22
[4,]   24   26
> x-y
     [,1] [,2]
[1,]  -10  -10
[2,]  -10  -10
[3,]  -10  -10
[4,]  -10  -10
> y-x
     [,1] [,2]
[1,]   10   10
[2,]   10   10
[3,]   10   10
[4,]   10   10
> 
```

## Lecture 15: Matrix Operations – Mathematical and Other Operations
▶️ Follow the rules of that matrix operation in order to avoid unexpected outputs/errors.

🧠 ![image](https://user-images.githubusercontent.com/86161735/184466008-2071057f-0e4c-45c1-b841-ea2c15b2ff84.png)
Matrix multiplication : `%*%`
```R
> x=matrix(nrow=4,ncol=2,data=1:8,byrow=T)
> x
     [,1] [,2]
[1,]    1    2
[2,]    3    4
[3,]    5    6
[4,]    7    8
> 4*x
     [,1] [,2]
[1,]    4    8
[2,]   12   16
[3,]   20   24
[4,]   28   32
> x+4*x
     [,1] [,2]
[1,]    5   10
[2,]   15   20
[3,]   25   30
[4,]   35   40
> 4*x-x
     [,1] [,2]
[1,]    3    6
[2,]    9   12
[3,]   15   18
[4,]   21   24
> # All of these have the same order (4x2)
> x=matrix(nrow=4,ncol=2,data=1:8,byrow=T)
> y=matrix(nrow=2,ncol=4,data=11:18,byrow=T)
> x
     [,1] [,2]
[1,]    1    2
[2,]    3    4
[3,]    5    6
[4,]    7    8
> y
     [,1] [,2] [,3] [,4]
[1,]   11   12   13   14
[2,]   15   16   17   18
> x%*%y
     [,1] [,2] [,3] [,4]
[1,]   41   44   47   50
[2,]   93  100  107  114
[3,]  145  156  167  178
[4,]  197  212  227  242
> y%*%x
     [,1] [,2]
[1,]  210  260
[2,]  274  340
> 
```
Orders : `x(4x2)`, `y(2x4)`, `x%*%y(4x4)`, `y%*%x(2x2)`
For finding `t(x)%*%x`: `crossprod(x)`
```R
atrix(nrow=4,ncol=2,data=1:8,byrow=T)
> crossprod(x)
     [,1] [,2]
[1,]   84  100
[2,]  100  120
> t(x) %*% x
     [,1] [,2]
[1,]   84  100
[2,]  100  120
> # crossprod is much faster than usual %*% multiplication
> 
```
*🔖Note: Command `crossprod()` executes the multiplication faster than the conventional method with t(x)%*%x*

### Concatenating matrices

Concatenating matrices row wise: `rbind(x, y)`
Concatenating matrices column wise: `cbind(x, y)`
```R
> x=matrix(nrow=3,ncol=2,data=1:6,byrow=T)
> y=matrix(nrow=3,ncol=2,data=11:16,byrow=T)
> x
     [,1] [,2]
[1,]    1    2
[2,]    3    4
[3,]    5    6
> y
     [,1] [,2]
[1,]   11   12
[2,]   13   14
[3,]   15   16
> rbind(x,y)
     [,1] [,2]
[1,]    1    2
[2,]    3    4
[3
[4,]   11   12
[5,]   13   14
[6,]   15   16
> cbind(x,y)
     [,1] [,2] [,3] [,4]
[1,]    1    2   11   12
[2,]    3    4   13   14
[3,]    5    6   15   16
```

### Inverse
```R
> y=matrix(nrow=2,ncol=2,byrow=T,data=c(84,100,100,120))
> y
     [,1] [,2]
[1,]   84  100
[2,]  100  120
> solve(y)
      [,1]  [,2]
[1,]  1.50 -1.25
[2,] -1.25  1.05
> x=solve(y)
> y%*%x
     [,1] [,2]
[1,]    1    0
[2,]    0    1
```
🔴 `A x inv(A)` ~ Identitiy Matrix (ALWAYS) 

### Eigen values and eigen vectors of matrix 
Characteristic values and Characteristic vectors
Command : `eigen()`
```R
> y=matrix(nrow=2,ncol=2,byrow=T,data=c(84,100,100,120))
> y
     [,1] [,2]
[1,]   84  100
[2,]  100  120
> eigen(y)
eigen() decomposition
$values
[1] 203.6070864   0.3929136

$vectors
          [,1]       [,2]
[1,] 0.6414230 -0.7671874
[2,] 0.7671874  0.6414230
```
🟡 *There is a long list of matrix multiplications.*

## Lecture 17: Relational and Logical Operators

🟢 ![image](https://user-images.githubusercontent.com/86161735/184470058-2a027b84-108a-4444-9f6c-0adbdca2226c.png)
![image](https://user-images.githubusercontent.com/86161735/184470558-31fffe87-d426-4b18-8118-78600806295e.png)

```R
> x=8
> (x<10) || (x<2)
[1] TRUE
> x=18
> (x<10) || (x<2)
[1] FALSE
> x=c(8,18)
> (x<10) || (x<2) #operates only on the first elements
[1] TRUE
Warning message:
In (x < 10) || (x < 2) : 'length(x) = 2 > 1' in coercion to 'logical(1)'
> (x<10) | (x<2) #operates on all the elements
[1]  TRUE FALSE
> x=5
> (x<10) && (x>2)
[1] TRUE
> x=15
> (x<10) && (x>2)
[1] FALSE
> x=c(8,18)
> (x<10) && (x>2)
[1] TRUE
Warning messages:
1: In (x < 10) && (x > 2) :
  'length(x) = 2 > 1' in coercion to 'logical(1)'
2: In (x < 10) && (x > 2) :
  'length(x) = 2 > 1' in coercion to 'logical(1)'
> (x<10) & (x>2)
[1]  TRUE FALSE
> x =1:6
> x
[1] 1 2 3 4 5 6
> # or x=c(1,2,3,4,5,6)
> (x>2) & (x<5)
[1] FALSE FALSE  TRUE  TRUE FALSE FALSE
> x[(x>2) & (x<5)]
[1] 3 4
> # x[.conditionals.] Finds which values are TRUE for the condition
> # x[condition] Finds which values are TRUE for the condition
> x =1:6
> (x>2) | (x<5)
[1] TRUE TRUE TRUE TRUE TRUE TRUE
> x[(x>2) | (x<5)]
[1] 1 2 3 4 5 6
> x=11:18
> x
[1] 11 12 13 14 15 16 17 18
> x[1]
[1] 11
> x[4]
[1] 14
> # Indexing starts from 1 instead of 0
> (x>2) && (x<5)
[1] FALSE
Warning messages:
1: In (x > 2) && (x < 5) : 'length(x) = 8 > 1' in coercion to 'logical(1)'
2: In (x > 2) && (x < 5) : 'length(x) = 8 > 1' in coercion to 'logical(1)'
> #Above is equivalent to
> (x[1]>2) && (x[1]<5)
[1] FALSE
```

## Lecture 17: Relational and Logical Operators

| **x** | **y** | **x or y** | **x and y** |
|:-----:|:-----:|:----------:|:-----------:|
| FALSE | FALSE |    FALSE   |    FALSE    |
| FALSE |  TRUE |    TRUE    |    FALSE    |
|  TRUE | FALSE |    TRUE    |    FALSE    |
|  TRUE |  TRUE |    TRUE    |     TRUE    |

```R
> x=TRUE
> y=FALSE
> x&y
[1] FALSE
> x|y
[1] TRUE
> !x
[1] FALSE
> !y
[1] TRUE
> Logical1=(x>2)
> Logical1
[1] FALSE
> x=5
> Logical1=(x>2)
> Logical1
[1] TRUE
> is.logical(Logical1)
[1] TRUE
> Logical2=(x<10)
> Logical2
[1] TRUE
> is.logical(Logical2)
[1] TRUE
> Logical3=(x!=5)
> Logical3
[1] FALSE
> is.logical(Logical3)
[1] TRUE
> x=5
> Logical4=(2*x>11)
> Logical4
[1] FALSE
> is.logical(Logical4)
[1] TRUE
> Logical5=(3*x><20)
Error: unexpected '<' in "Logical5=(3*x><"
> Logical5=(3*x<20)
> Logical5
[1] TRUE
> is.logical(Logical5)
[1] TRUE
> x=c(1,2,3)
> y=c(4,5,6)
> x>y
[1] FALSE FALSE FALSE
> x<y
[1] TRUE TRUE TRUE
> x!=y
[1] TRUE TRUE TRUE
> x==y
[1] FALSE FALSE FALSE
> isTRUE(8<6)
[1] FALSE
> 8<6
[1] FALSE
> isFALSE(8<6)
[1] TRUE
> !(8<6)
[1] TRUE
> isTRUE(8>6)
[1] TRUE
> isFALSE(8>6)
[1] FALSE
> !(8>6)
[1] FALSE
> 
```


