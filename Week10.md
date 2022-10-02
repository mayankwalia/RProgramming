```R
> sub("8","12","Foundations of")
[1] "Foundations of"
> sub("8","12","Foundations of R Software will be of 12 weeks duration")
[1] "Foundations of R Software will be of 12 weeks duration"
> gsub("Students in mathematics course","Students in statistics course","mathematics -250, statistics - 300") 
[1] "mathematics -250, statistics - 300"
> grep("cdab",c("cdabc","cdef","cbcdaba","adcdaba","cdabcdab")
+ )
[1] 1 3 4 5
> grep("[m-r]",letters)
[1] 13 14 15 16 17 18
> grepl("students",x)
[1] FALSE FALSE FALSE
> x=c("Students in mathematics course","Students in statistics course","mathematics -250, statistics - 300") 
> 
> c
function (...)  .Primitive("c")
> x
[1] "Students in mathematics course"     "Students in statistics course"     
[3] "mathematics -250, statistics - 300"
> grepl("students",x)
[1] FALSE FALSE FALSE
> grepl("Students",x)
[1]  TRUE  TRUE FALSE
> x=c("Germany","India","USA")
> y=c(10,20,30)
> cbind(x,y)
     x         y   
[1,] "Germany" "10"
[2,] "India"   "20"
[3,] "USA"     "30"
> rbind(x,y)
  [,1]      [,2]    [,3] 
x "Germany" "India" "USA"
y "10"      "20"    "30" 
> 
```
