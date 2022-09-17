```R
> x=list("UP","MP","J&K","Bihar",20,40,"60+40")
> append(x,200)
[[1]]
[1] "UP"

[[2]]
[1] "MP"

[[3]]
[1] "J&K"

[[4]]
[1] "Bihar"

[[5]]
[1] 20

[[6]]
[1] 40

[[7]]
[1] "60+40"

[[8]]
[1] 200

> x=list("UP","MP","J&K","Bihar",20,40,"60+40")
> append(x,200,after=2)
[[1]]
[1] "UP"

[[2]]
[1] "MP"

[[3]]
[1] 200

[[4]]
[1] "J&K"

[[5]]
[1] "Bihar"

[[6]]
[1] 20

[[7]]
[1] 40

[[8]]
[1] "60+40"

> x=list("UP","MP","J&K","Bihar",20,40,"60+40")
> x[2:3]
[[1]]
[1] "MP"

[[2]]
[1] "J&K"

> z=list(x1="class",x2=20:25)
> 
> z
$x1
[1] "class"

$x2
[1] 20 21 22 23 24 25

> names(z)[2]=y2
Error: object 'y2' not found
> names(z)[2]="y2"
> 
> z
$x1
[1] "class"

$y2
[1] 20 21 22 23 24 25

> z
$x1
[1] "class"

$y2
[1] 20 21 22 23 24 25

> factor(c(10,10,20,20,30,30))
[1] 10 10 20 20 30 30
Levels: 10 20 30
> data=c(4,4,2,2,6,6,9)
> factor(data)
[1] 4 4 2 2 6 6 9
Levels: 2 4 6 9
> levels(data)=c('A','B','C','D')
> data
[1] 4 4 2 2 6 6 9
attr(,"levels")
[1] "A" "B" "C" "D"
> x=factor(c(10,20,20,50,10,20,10,50,60,60),levels=c(10,20,50,60),ordered=TRUE)
> x
 [1] 10 20 20 50 10 20 10 50 60 60
Levels: 10 < 20 < 50 < 60
> factor(c(rep("head",3),rep("tale",4)))
[1] head head head tale tale tale tale
Levels: head tale
> unclass(factor(c("high school","graduation","post graduation","graduation","high school","post graduation","high school","post graduation"),levels=c("high school","graduation","post graduation")))
[1] 1 2 3 2 1 3 1 3
attr(,"levels")
[1] "high school"     "graduation"      "post graduation"
> as.factor(c(1,2,2,3,3,3,4,4,5,5,5))
 [1] 1 2 2 3 3 3 4 4 5 5 5
Levels: 1 2 3 4 5
> print(2/3,digits=6)
[1] 0.666667
> print("The average marks of the class is",(40+10)/3,"in first year.",digits=5)
[1] "The average marks of the class is"
> print("My house has");print(2+4);print("rooms.")
[1] "My house has"
[1] 6
[1] "rooms."
> format(12345678910,big.mark="*")
[1] "12*345*678*910"
> print(format(2.5,digits=6,nsmall=10))
[1] "2.5000000000"
> 
```
