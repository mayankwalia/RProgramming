```R
> x<-'Indian Institute of Technology Madras!\n'
> print(x)
[1] "Indian Institute of Technology Madras!\n"
> cat(x)
Indian Institute of Technology Madras!
> print(paste("R course has", 10*2:4, "students"))
[1] "R course has 20 students" "R course has 30 students"
[3] "R course has 40 students"
> x<-36
> y<-27
> cat("the sq root of", "x", "is", sqrt(x), "and the cube root of y is", y^(1/3), "!\n")
the sq root of x is 6 and the cube root of y is 3 !
> x<-7
> cat("the approximate value of sq root of", x, "is", format(sqrt(x), digits=3), "\n")
the approximate value of sq root of 7 is 2.65 
> paste("The age of 3 students are", c("!8 years", "19 years", "20 years"),collapse=", and ");
[1] "The age of 3 students are !8 years, and The age of 3 students are 19 years, and The age of 3 students are 20 years"
> paste("Students in class 1,2 and 3 are:,50:52,sep=":")
+ 
+ 
+ 
Error: unexpected end of input
> paste("Students in class 1,2 and 3 are",50:52,sep=":")
[1] "Students in class 1,2 and 3 are:50" "Students in class 1,2 and 3 are:51"
[3] "Students in class 1,2 and 3 are:52"
> paste("Total number of pages in books are", 200:202, sep="+", collapse="")
[1] "Total number of pages in books are+200Total number of pages in books are+201Total number of pages in books are+202"
> 
> y=strsplit("Landlord of House Number 100::Landlord of House Number 100::
+ 
Error: unexpected end of input
> y=strsplit("Landlord of House Number 100::Landlord of House Number 200::Landlord of House Number 300","::")
> y
[[1]]
[1] "Landlord of House Number 100" "Landlord of House Number 200"
[3] "Landlord of House Number 300"

> y[1][3]
[[1]]
NULL

> y[3][1]
[[1]]
NULL

> y[[3]][1]
Error in y[[3]] : subscript out of bounds
> [[3]][1]
Error: unexpected '[[' in "[["
> y[[1]][3]
[1] "Landlord of House Number 300"
> nchar("NPTEL - National Programme on Technology Enhanced Learning- is a joint initiative of the IITs and IISc.")
[1] 103
> nzchar("NPTEL - National Programme on Technology Enhanced Learning- is a joint initiative of the IITs and IISc.")
[1] TRUE
> x=c("NPTEL - National Programme on Technology Enhanced Learning-", "is a joint initiative of the", "IITs and IISc.")
> x
[1] "NPTEL - National Programme on Technology Enhanced Learning-"
[2] "is a joint initiative of the"                               
[3] "IITs and IISc."                                             
> nzchar(x)
[1] TRUE TRUE TRUE
> tolower("InDIan InStItUtE Of TEchNOloGY")
[1] "indian institute of technology"
> toupper("Institute of National Importance in India")
[1] "INSTITUTE OF NATIONAL IMPORTANCE IN INDIA"
> 
```
