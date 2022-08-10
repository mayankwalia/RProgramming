# Week 2

```R
> RSiteSearch("mean")
A search query has been submitted to https://search.r-project.org
The results page should open in your browser shortly
> RSiteSearch(mean)
Error in as.character(x) : 
  cannot coerce type 'closure' to vector of type 'character'
> rsiteSearch(mean)
Error in rsiteSearch(mean) : could not find function "rsiteSearch"
> rsitesearch(mean)
Error in rsitesearch(mean) : could not find function "rsitesearch"
> RsiteSearch("mean")
Error in RsiteSearch("mean") : could not find function "RsiteSearch"
> x=20
> y="20"
> is.numeric(x)
[1] TRUE
> is.numeric(y)
[1] FALSE
> is.character(x)
[1] FALSE
> is.character(y)
[1] TRUE
> mode(x)
[1] "numeric"
> mode(y)
[1] "character"
> storage.mode(x)
[1] "double"
> storage.mode(y)
[1] "character"
> x=20
> y=20+Inf
> is.finite(x)
[1] TRUE
> is.finite(y)
[1] FALSE
> is.infinite(y)
[1] TRUE
> is.infinite(x)
[1] FALSE
> x=43
> y=x^3
> z=y^2+x^4
> z
[1] 6324781850
> 5-3+4/6*7-3^3*4-7/6*2-3**3/2+6-7+2
[1] -116.1667
> 15/(-5)*2+8^-3/(65/32)-4**3+4-81^(-1/4)+2^(-4**3)
[1] -66.33237
> c(12,13,15,17)/10+c(1.2,1.3,1.5,1.7)*10
[1] 13.2 14.3 16.5 18.7
> 15/(-5)*2+8^(-3)/(65/32)-4**3+4-81^(-1/4)+2^(-4**3)
[1] -66.33237
> 
```
