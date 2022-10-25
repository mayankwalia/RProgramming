# Live Session
```R
> x=1:10
> plot(x)
> plot(x*x)
> plot(x^2-x)
> plot((4%/%x*x))
> plot(x,col="red")
> plot(x,col="blue")
> plot(x,col="blue",main="Title")
> plot(x,col="blue",main="Title",xlim=c(0,20),ylim=c(-2,12),xlab="order",ylab="element")

> dice<-sample(1:3,7,replace=TRUE)
> dice
[1] 1 2 3 1 2 2 2
> dice2<-sample(1:3,7)
Error in sample.int(length(x), size, replace, prob) : 
  cannot take a sample larger than the population when 'replace = FALSE'
  
> plot(dice)
> 
> dice<-sample(1:3,50,replace=TRUE)
> plot(dice)
> table(dice)
dice
 1  2  3 
16 14 20 
> plot(table(dice))
> # Barplot
> table(dice)/length(dice)
dice
   1    2    3 
0.32 0.28 0.40 
> barplot(table(dice)/length(dice))
> barplot(table(dice))
> barplot(table(dice),col=c("red"))
> barplot(table(dice),col=c("red","blue"))
> barplot(table(dice),col=c("red","blue","green"))
> barplot(table(dice),col=c("red","blue","green"),border="cyan")
> barplot(table(dice),col=c("red","blue","green"),border="brown")
> barplot(table(dice),col=c("red","blue","green"),border="brown",legend.text = c("One","Two","Three"))
> barplot(table(dice),col="black",border="red",legend.text = c("One","Two","Three"),horiz=TRUE)
> dice*x
 [1]  1  4  6 12  5 12 14 16  9 10
[11]  1  2  9  8 15 18 21  8 27 30
[21]  2  2  9 12  5 12 21 24  9 10
[31]  1  4  3  4 15  6 14 16 27 20
[41]  2  6  3 12 15 12 21 24 27 30
> dice
 [1] 1 2 2 3 1 2 2 2 1 1 1 1 3 2 3
[16] 3 3 1 3 3 2 1 3 3 1 2 3 3 1 1
[31] 1 2 1 1 3 1 2 2 3 2 2 3 1 3 3
[46] 2 3 3 3 3
> x
 [1]  1  2  3  4  5  6  7  8  9 10
> length(dice*x)
[1] 50
> m1=matrix(data=(dice*x)[1:20],nrow=5,ncol=4)
> m1
     [,1] [,2] [,3] [,4]
[1,]    1   12    1   18
[2,]    4   14    2   21
[3,]    6   16    9    8
[4,]   12    9    8   27
[5,]    5   10   15   30
> barplot(m1)
> barplot(m1,col=c("blue","green","blue","yellow","red"))
> barplot(m1,col=c("blue","green","black","yellow","red"))
> barplot(m1,col=c("blue","green","black","yellow","red"),legend.text=c("M","T","W","Th","F"))
> 
> # Pie Charts
> pie(dice)
> barplot(dice)
> barplot(table(dice))
> pie(table(dice))
> par(mfrow=c(2,1));
> barplot(m1,col=c("blue","green","black","yellow","red"),legend.text=c("M","T","W","Th","F"))
Error in plot.new() : figure margins too large

> barplot(m1,col=c("blue","green","black","yellow","red"),legend.text=c("M","T","W","Th","F"))
> par(mfrow=c(1,2))
> barplot(table(dice))
> pie(table(dice))
> hist(x*dice)
> par(mfrow=c(1,1))
> hist(x*dice)
> y=x*dice
> y
 [1]  1  4  6 12  5 12 14 16
 [9]  9 10  1  2  9  8 15 18
[17] 21  8 27 30  2  2  9 12
[25]  5 12 21 24  9 10  1  4
[33]  3  4 15  6 14 16 27 20
[41]  2  6  3 12 15 12 21 24
[49] 27 30
> hist(y,main="Marks obtained",col="blue",xlim=c(-1.31),ylim=c(0,20),density=3,angle=30,breaks=9)
Error in plot.window(xlim, ylim, "", ...) : invalid 'xlim' value
> hist(y,main="Marks obtained",col="blue",xlim=c(-1,31),ylim=c(0,20),density=3,angle=30,breaks=9)
> z=hist(y,main="Marks obtained",col="blue",xlim=c(-1,31),ylim=c(0,20),density=3,angle=30,breaks=9)
> z
$breaks
[1]  0  5 10 15 20 25 30

$counts
[1] 14 11 11  4  5  5

$density
[1] 0.056 0.044 0.044 0.016 0.020 0.020

$mids
[1]  2.5  7.5 12.5 17.5 22.5 27.5

$xname
[1] "y"

$equidist
[1] TRUE

attr(,"class")
[1] "histogram"
> z$counts
[1] 14 11 11  4  5  5
> height=sample(100:200,20,replace=TRUE)
> height
 [1] 152 119 132 181 187 183 187 175 119 114
[11] 190 181 108 198 151 147 104 164 115 133
> weight=sample(50:90,20,replace=TRUE)
> plot(height,weight,xlab="height",ylab="weight")
> install.packages("scatterplot3d")
package ‘scatterplot3d’ successfully unpacked and MD5 sums checked
> library("scatterplot")
Error in library("scatterplot") : 
  there is no package called ‘scatterplot’
> library("scatterplot3d")
> scatterplot3d(height,weight,xlab="height",ylab="weight")
> scatterplot3d(height,weight,xlab="height",ylab="weight",type="l")
> scatterplot3d(height,weight,xlab="height",ylab="weight",type="b")
> r=sqrt(2*x+y^2)
> r
 [1]  1.732051  4.472136  6.480741
 [4] 12.328828  5.916080 12.489996
 [7] 14.491377 16.492423  9.949874
[10] 10.954451  1.732051  2.828427
[13]  9.327379  8.485281 15.329710
[16] 18.330303 21.330729  8.944272
[19] 27.331301 30.331502  2.449490
[22]  2.828427  9.327379 12.328828
[25]  5.916080 12.489996 21.330729
[28] 24.331050  9.949874 10.954451
[31]  1.732051  4.472136  3.872983
[34]  4.898979 15.329710  6.928203
[37] 14.491377 16.492423 27.331301
[40] 20.493902  2.449490  6.324555
[43]  3.872983 12.328828 15.329710
[46] 12.489996 21.330729 24.331050
[49] 27.331301 30.331502
> f=funtion(x,y){r=sqrt(2*x+y^2);sin(r)/r}
Error: unexpected '{' in "f=funtion(x,y){"
> f=function(x,y){r=sqrt(2*x+y^2);sin(r)/r}
> z=outer(x,y,f)
> y=1:50
> persp(x,y,z)
> persp(x,y,z,theta=60,phi=10,col="blue")
```
