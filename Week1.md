# Week 1

## L3

### Help

1. Search on Google
2. ```?command``` Example: ```?read.table```
4. ```help.search("data input")```
5. ```help.start()```
6. ```find("lowess")```
7. ```apropos("lm")```
8. Clear Screen ```Ctrl+L```

### Demonstrations/Examples
```R
example(lm)
demo(persp)
demo(graphics)
```
~~demo(graphic)~~
```
```
*demonstration function gives us step-by-step application of the given package and how to use it.*

## Packages and Libraries

### Packages

#### Base Package : 
* By defualt...only essential functionalities.
* `MASS`: Modern Applied Statistics using S-Plus
* `mgcv`: generalized additive models
#### Other libraries: User dependent and need based.
* For cluster analysis: Package `cluster` is available
* Functions and datasets are organized into libraries
`library(name_of_the_package)`
e.g. to load `spatial` library:
`library(spatial)`
* `spatial`
* `boot`

* R language is case-sensitive
`packageDescription("spatial")`
`library(help=spatial)`

🔖Note: *`packageDescription()` only gives a brief information about the package. However,  `library(help=)` opens the package documentation which provides all the specifics of the package including commands in it.*
### Installing Packages and Libraries
`install.packages("name")`
`install.packages("boot")`
`install.packages("cluster")`
* Select a CRAN mirror
* Progress screen
* Installed

`installed.packages()`
`remove.packages("package_name")`
`remove.packages("cluster")`
`update.packages("cluster")`
Alternatively, go to R console > Packages > Update Packages
`detach("package:cluster",unload=True)`
Not uninstalling. Error if package is not loaded
* Packages are local



## L4 Command Line and Data Editor
Use external software
*R Studio*
* Command line vs Scripts
[1] Need of text editor
`Built in- RGui` File> New Script
Execute: highlight and `Ctrl+R`

```R
# script
x = 20
y = 30
z = x + y
x
y
z
```

Editors:
- [X] R Studio
- [ ] Tin R

