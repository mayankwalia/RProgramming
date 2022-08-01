# Week 2

## Lecture 5: Introduction to R Studio
- Helping hand.
- 4 windows:
  - Scirpt Section `<Write commands here>`
  - Console `<R program window appears here>`
  - Environment Window <Defined Variables (env) `Variables,type of data,values,..many more`>
  - Output Window `<Output of programmes>`
    - Tick mark the package to load it
    - Untick mark the package to detach it
    - Packages> Install,Update
    - Help > Search box (e.g. type `hist` to get information on *histograms*)
    - 

```R
> library(MASS) #loading the MASS package
> attach(bacteria) 
> fix(bacteria) #Data editor by using fix function <source button in RStudio>

```

`CTRL+Enter` or `Highlight and Run`

## Problem 1
- Create a bar diagram of values 1,2,1,1,2,3,1,2,3,1,2,2,3
```R
x=c(1,2,1,1,2,3,1,2,3,1,2,2,3)
barplot(table(x))
```
- Output
  - See all the four windows
  ![image](https://user-images.githubusercontent.com/86161735/182145296-032a6541-25bb-4f4c-9691-a58b782d092f.png)
  - Click on red cross to remove the plot (Window 4)

*RStudio is only a helping tool which is providing more GUI oriented. The bottomline is still the R command line.*
**To learn RStudio better explore it more**



## Lecture 6: Basic Operations in R

### Contents in the working directory
```R
ls() #if nothing is there then it will show `character(0)`
getwd() #Get working directory
setwd("c:/Rcourse") #Set working directory
getwd()
```
- Unix/Macintosh based path
- Intereupt a running computation by pressing `Esc` key
- Cleaning GUI window `Ctrl+L`
- Search web for info and answers regarding R `RSiteSearch("keyword")`
  - To search for "mode" use : `RSiteSearch("mode")` on R console
  - It searches from ![http://search.r-project.org](http://search.r-project.org)
  - ![image](https://user-images.githubusercontent.com/86161735/182154653-c092558f-452d-492c-920c-2a1070bb6976.png)
- Numbers in [] present the position index i.e. count of the starting number.
  - Try this `x=1:200` and `x` and check the first column.
  - Now try reducing the width and try again the same commands.
  - `x:101:150`
- Reloading packages when restarting R:
- Libraries loaded through `library` need to be reloaded on restart.
- Meaning of e in R
- `5.1234e+7` is <math>5.1234x10<sup>7</sup></math>
```R
> x=1
> x
[1] 1
> x=3
> x
[1] 3
> y=3
> z=5
> rm(x)
> x
Error: object 'x' not found
> rm(y)
> rm(z)
> y
Error: object 'y' not found  
```
Removing variables: 
`rm()` 
`rm(x,y,z)`
`detach()` Detaches objects from the Search Path (`search()`)
`rm(list=ls())`
```R
> library(cluster)
> 
> detach(package:cluster)
> 
```

Type `q()` to quit R.

*Now, jump into the well and start doing!*

## Lecture 7: Some More Basic Operations in R

`>` is the prompt sign
Assignment 
Only `<-` was available in the beginning (Coming from S-software which is like the forefather of R). 
But as popularity of R grows `=` sign is also incorportated as equality sign.
Don't confuse too much now both mean the same thing.
`> x <- 20
> x
[1] 20
> y <- 30
> y
[1] 30
> z = 40
> z
[1] 40
> y = x*2
> z = x+y
> y
[1] 40
> z
[1] 60
> x
[1] 20
# Stings
> x="apple"
> x
[1] "apple"
> y<-"banana"
> y
[1] "banana"
`
### Knowing numbers and characters
`is.character() is.numeric()` - `True` or `False`
`
> x="apple"
> x
[1] "apple"
> z
[1] 60
> x.isnumeric(x)
Error in x.isnumeric(x) : could not find function "x.isnumeric"
> is.numeric(x)
[1] FALSE
> is.numeric(z)
[1] TRUE
> is.character(x)
[1] TRUE
> is.character(z)
[1] FALSE

> a=10
> is.numeric(a)
[1] TRUE
> y=as.character(x)
> is.numeric(y)
[1] FALSE
> is.character(y)
[1] TRUE
`
Converting numbers and characters
`as.numeric(x)` `as.character(x)`
Warning can come as:
Do Slides
```R
> y<-"India"
> is.numeric(y)
[1] FALSE
> is.character(y)
[1] TRUE
> x=as.numeric(y)
Warning message:
NAs introduced by coercion 
> is.numeric(x)
[1] TRUE
> is.numeric(y)
[1] FALSE
> # y is a country
```
Comments with `#`
Case sensitivity 
*Pay attention to this if you're coming from SQL 🙂*
```R
> x=20
> X
Error: object 'X' not found
> X=30
> x
[1] 20
> X
[1] 30
> x is the age
Error: unexpected symbol in "x is"
> # x is age
> 1+2
[1] 3
> # 1+2
> 
```
### Combinig values in Vector
```
> y=1,2,3,4,5
Error: unexpected ',' in "y=1,"
> y=(1,2,3,4,5)
Error: unexpected ',' in "y=(1,"
> y=c(1,2,3,4,5)
> y
[1] 1 2 3 4 5

```

### Use mode for determinig type of value. 
⚠️Don't confuse `mode()` with the mode fxn from statitics.
ℹ️ `storage.mode()` returns the storage mode of its argument. Used when calling functions written in other languages such as FORTAN (Physicts still use it 😏),C.
```
> x
[1] 20
> y
[1] 1 2 3 4 5
> mode(x)
[1] "numeric"
> mode(y)
[1] "numeric"
> z="apple"
> mode(z)
[1] "character"
> z
[1] "apple"
# Storage mode
> x
[1] 20
> storage.mode(x)
[1] "double"
> x=TRUE
> storage.mode(x)
[1] "logical"
> x="lorem ipsum"
> storage.mode(x)
[1] "character"
> 
```

### Infinity
*Divide 3 apples among 0 friends. How much each one get ❔*
```R
> 3/0
[1] Inf
> 5+Inf
[1] Inf
> x=5+Inf
> is.finite(x)
[1] FALSE
> is.infinite(x)
[1] TRUE
> 
```
*Try executing the commands yourself.*

## Lecture 8: R as a Calculator with Scalars and Data Vectors : Addition, Subtraction, Multiplication & Division

- R works just like a calci
```R
> 2+3
[1] 5
> 2*3
[1] 6
> 2-3
[1] -1
> 2/3
[1] 0.6666667
> #Lets combine them
> 2*3-4+5/6
[1] 2.833333
```

- BODMAS is applicable
```R
> (3+5)*(2-1)
[1] 8
> 3+(5*2)-1
[1] 12
> 3+5*(2-1)
[1] 8
>(2+3*(4/2)-3)/2
[1] 2.5
> 
```
- No significance of space during mathematical calculations
```R> 2+10
[1] 12
> 2    +   10
[1] 12
> 2    +                10
[1] 12
> 
 ```
- Scalars and Vectors in R
- A Scalar and a (data) Vector
```R
> c(1,2,3,4)+5
[1] 6 7 8 9
> c(1,2,3,4)*5
[1]  5 10 15 20
> c(1,2,3,4)-5
[1] -4 -3 -2 -1
> c(1,2,3,4)/5
[1] 0.2 0.4 0.6 0.8
> c(1,2,3,4)**5
[1]    1   32  243 1024
```
*Don't fear from R Software. It is created by the humans and for the humans.*

```R
> x=43
> y=x^3
> z=y^2+x^4
> z
[1] 6324781850
> 5-3+4/6*7-3^3*4-7/6*2-3**3/2+6-7+2
[1] -116.1667
> 15/(-5)*2+8^(-3)/(65/32)-4**3+3-81^(-1/4)+2^(-4**3)
[1] -67.33237
> 15/(-5)*2+8^(-3)/(65/32)-4**3+4-81^(-1/4)+2^(-4**3)
[1] -66.33237
> c(12,13,15,17)/10+c(1.2,1.3,1.5,1.7)*10
[1] 13.2 14.3 16.5 18.7
> 
```
