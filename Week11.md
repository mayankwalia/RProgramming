> x=1
> y=1:19
> y
 [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19
> z=c("A","B")
> z
[1] "A" "B"
> student=data.frame(x,y,z)
Error in data.frame(x, y, z) : 
  arguments imply differing number of rows: 1, 19, 2
> 
> x=11:20
> y=c("A","B")
> z=c("Peter","Paul","Ramesh","Albert","John")
> student=data.frame(x,y,z)
> student
    x y      z
1  11 A  Peter
2  12 B   Paul
3  13 A Ramesh
4  14 B Albert
5  15 A   John
6  16 B  Peter
7  17 A   Paul
8  18 B Ramesh
9  19 A Albert
10 20 B   John
> student$x
 [1] 11 12 13 14 15 16 17 18 19 20
> student$y
 [1] "A" "B" "A" "B" "A" "B" "A" "B" "A" "B"
> student=data.frame("Roll"=x,"Grade"=y,"Teacher"=z)
> student
   Roll Grade Teacher
1    11     A   Peter
2    12     B    Paul
3    13     A  Ramesh
4    14     B  Albert
5    15     A    John
6    16     B   Peter
7    17     A    Paul
8    18     B  Ramesh
9    19     A  Albert
10   20     B    John
> student=data.frame("Roll"=x,"Grade"=y,"Teacher"=z,row.names=letters[1:10])
> student
  Roll Grade Teacher
a   11     A   Peter
b   12     B    Paul
c   13     A  Ramesh
d   14     B  Albert
e   15     A    John
f   16     B   Peter
g   17     A    Paul
h   18     B  Ramesh
i   19     A  Albert
j   20     B    John
> student=data.frame(x,y,z)
> studeny
Error: object 'studeny' not found
> studeny
Error: object 'studeny' not found
> student
    x y      z
1  11 A  Peter
2  12 B   Paul
3  13 A Ramesh
4  14 B Albert
5  15 A   John
6  16 B  Peter
7  17 A   Paul
8  18 B Ramesh
9  19 A Albert
10 20 B   John
> `row.names<-`(student,letters[12:21])
   x y      z
l 11 A  Peter
m 12 B   Paul
n 13 A Ramesh
o 14 B Albert
p 15 A   John
q 16 B  Peter
r 17 A   Paul
s 18 B Ramesh
t 19 A Albert
u 20 B   John
> `colnames<-`(student,letters[2:4])
    b c      d
1  11 A  Peter
2  12 B   Paul
3  13 A Ramesh
4  14 B Albert
5  15 A   John
6  16 B  Peter
7  17 A   Paul
8  18 B Ramesh
9  19 A Albert
10 20 B   John
> student$b
NULL
> student
    x y      z
1  11 A  Peter
2  12 B   Paul
3  13 A Ramesh
4  14 B Albert
5  15 A   John
6  16 B  Peter
7  17 A   Paul
8  18 B Ramesh
9  19 A Albert
10 20 B   John
> student$x
 [1] 11 12 13 14 15 16 17 18 19 20
> student["l","x"]
[1] NA
> student[q,"x"]
Error in xj[i] : invalid subscript type 'closure'
> student[1,"x"]
[1] 11
data_h=read.csv('data.csv')
> View(data_h)
> data_h
   Student.id Course.id Marks
1        1001      2001    56
2        1002      2001    67
3        1003      2001    78
4        1004      2001    90
5        1005      2001    45
6        1001      2002    58
7        1002      2002    98
8        1009      2002    12
9        1007      2002    99
10       1008      2002    39
11       1003      2003    34
12       1004      2003    43
13       1000      2003    25
14       1060      2003    60
15       1090      2003    88
16       1005      2004    81
17       1080      2004    59
18       1030      2004    87
19       1001      2004    35
20       1090      2004    33
> type(data_h)
Error in type(data_h) : could not find function "type"
> typeof(data_h)
[1] "list"
> data_h$Student.id[1:3]
[1] 1001 1002 1003
> mean(data_h$Student.id[1:3])
[1] 1002
> names(data_h)=c("A","B","C")
> data_h
      A    B  C
1  1001 2001 56
2  1002 2001 67
3  1003 2001 78
4  1004 2001 90
5  1005 2001 45
6  1001 2002 58
7  1002 2002 98
8  1009 2002 12
9  1007 2002 99
10 1008 2002 39
11 1003 2003 34
12 1004 2003 43
13 1000 2003 25
14 1060 2003 60
15 1090 2003 88
16 1005 2004 81
17 1080 2004 59
18 1030 2004 87
19 1001 2004 35
20 1090 2004 33
> summary(data_h)
       A              B              C        
 Min.   :1000   Min.   :2001   Min.   :12.00  
 1st Qu.:1002   1st Qu.:2002   1st Qu.:38.00  
 Median :1004   Median :2002   Median :58.50  
 Mean   :1020   Mean   :2002   Mean   :59.35  
 3rd Qu.:1014   3rd Qu.:2003   3rd Qu.:82.50  
 Max.   :1090   Max.   :2004   Max.   :99.00  
> 
