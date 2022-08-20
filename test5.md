> x=c(10,80,90,101:200,NA)
> mean(x,na.rm=FALSE)
[1] NA
> mean(x,na.rm=TRUE)
[1] 147.8641
> mean(na.omit(x))
[1] 147.8641
> 
> x=3
> y=if(x==23){x=x^3+3} else{x=x^2-3}
> y
[1] 6
> x=23
> y=if(x==23){x=x^3+3} else{x=x^2-3}
> y
[1] 12170
> 
