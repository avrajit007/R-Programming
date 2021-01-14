# R-Programming

#To find what is inside a package
find("matrixcalc")

#To get information about a package
library(help=matrixcalc)

#To get all information about a function
example(cat)

#To quit R
q()

#To install a package
install.packages("MASS")

#To load a package
library(MASS)
require(MASS)

#To remove/unload a package
detach(package:MASS)

#Assigning values
x1<- 20
x1=20
x1 #To call the vale of x1

#Combining numbers/ characters in a vector and assigning those values to a variable
y1<- c(12,21,103,4)
y1 #To call the value of y1
z1<- c("a","b","c")
z1 #To call the value of z1
y1[3] #To call the 3rd value of the vector y1
z1[2] #To call the 2nd value of the vector z1

#To get integer division (remainder is discarded)
5%/%2
#To get modulo division (to get only the remainder)
5%%2

#To find maximum & minimum values
max(c(1,3,-7))
min(c(1,3,-7))

#To get absolute values
abs(c(2,-7,-23))

#To get square root of a number
sqrt(c(25,79,144))

#To get a round value of a decimal number
round(c(25.5,29,55.8))

#To get floor and ceiling values of a decimal number
floor(c(12.2,29.9,25.5))
ceiling(c(12.2,29.9,25.5))

#To get loge, log2, log10 values
log(c(2,78,1000)) #log base e (default)
log2(c(2,78,1000)) #log base 2
log10(c(2,78,1000)) #log base 10

#To get exponential values
exp(c(0.6931472,4.3567088,6.9077553)) #values taken from the result of the loge function

#Trigonometric function
help(sin) #To get help on sin funtion
sinpi(c(1/2,1,5,3/2)) #answer given for radian value
cospi(c(1/2,1,5,3/2))
tanpi(c(1/2,1,5,4/3))
asin(c(1/2,1,5,3/2)) #cosec funtion
acos(c(1/2,1,5,3/2)) #sec function
atan(c(1/2,1,5,3/2)) #cot function

#Hyperbolic funtion
help(sinh) #To get help on sin hyperbolic funtion
sinhpi(c(1/2,1,5,3/2)) #answer given for radian value
coshpi(c(1/2,1,5,3/2))
tanhpi(c(1/2,1,5,4/3))
asinh(c(1/2,1,5,3/2)) #cosec funtion
acosh(c(1/2,1,5,3/2)) #sec function
atanh(c(1/2,1,5,3/2)) #cot function

#sum and product function
sum(c(2,8,73))
prod(c(2,8,73))

#To call a function
abc<- function(a)
{
  a^2
}
abc1<- function(a,b)
{
  a^2+b^3
}
abc(2) #to put the value of x in abc function
abc1(3,7) #to put the value of x,y in abc1 function

#Matrix calculations
library(help=matrixcalc) #to get help about this package
help("matrix") #to get help on matrices
library(matrixcalc) #to load this package
m<-matrix(nrow=3,ncol=2,data=c(1,2,3, 4,5,6), byrow=T) #creation of a 3x3 matrix
m #calling matrix m
m[3,2] #calling the value present in 3rd row and 2nd column of the matrix
m[ ,2] #call all values that are in the 2nd column,but they appears horizontally
m[1, ] #call all values that are in the 1st row

#To get dimension, no of rows/columns, mode of the matrix
dim(m) #3x2
nrow(m)
ncol(m)
mode(m) #numeric

#To create an identity matrix (special diagonal matrix)
id<-diag(1,nrow=3, ncol=3) #always a square matrix (thus, 3x3)
id

#To create transpose of a matrix
( mt<- t(m) ) #to call the matrix directly use first bracket on entire thing

#To get inverse of a matrix/ getting eigen value
inv<-solve(id) #has to be a square matrix, so cant get the inverse of matrix(m)
inv
eigen(id) #has to be a square matrix

#Operations on matrix
(mul<-4*m) #multiplication of matrix m by a constant value
(matrix_mul<-m %*% t(m)) #multiplication of matrix m with its transpose: for multiplication if m is (3x2), it can be only multiplied by a matrix(2x3)
(m+4*m) #addition of matrix
(6*m-m) #subtraction of matrix

#Operations on missing data (not available data)
n <- NA #assigning 'not available' to n
is.na(n) #returns TRUE
n1<- c(4,NA,6)
mean(n1, na.rm=T) #to find mean of n1, removing NA, returns 5

#Logical operators (!= not equal to, ! negation/not/don't want, & AND, |(key above enter) OR, xor Either or OR)
isTRUE(8<6) #returns FALSE

op <- 5
(op<10) && (op>2) #returns TRUE

op1 <- 10
op2 <- 20
(op1==1) & (op2==20) #returns FALSE

op3<-1:6
op3[(op3>2) & (op3<5)] #calling values of op3 which is greater than 2 and less than 5
(op3[4]>2) & (op3[4]<5) #to check if 4th value (i.e. 4) is greater than 2 and less than 5, returns TRUE

#Difference between && AND & operator
(op3>2) & (op3<5) #returns F,F,T,T,F,F
(op3>2) && (op3<5) #returns F

#More logical operations from truth table
op4=T
op5=F
(op4 & op5) #returns FALSE
(op4 | op5) #returns TRUE
!op4 #not op4 = FALSE as op4 is assigned as TRUE

#Conditional execution (if-else) (vector can't be used in this method, else only first value will be taken)
help("ifelse")

p<-5 #assigned 5 to a, not 3, so returns 2*a
if (p==3) {print(p-1)} else {print(2*p)} #don't break and write, returns 10

q<-1:6 #can be used for vectors
ifelse(q<3, q^2, q+1) #if q is less than 3,then print q^2 else print q+1

#Loops (for, while, repeat)
for (i in 1:5) #for loop when number of repetitions are known
{
  print (i^2)
}

for (i in c(2,4,6))
{
  print (i+22)
}

i<-1 
while (i<=5) #while loop when number of repetitions are not known
{
  print (i^2)
i<-i+1
}

i<- 1
repeat #doesn't test any condition
{
  print (i^2)
  i<-i+1
  if (i>10) break
}

i<-1
repeat
{
  i<-i+1
  if (i<10) next #do i+1 until i equals to 10, after that do i^2, until i > 13
  print (i^2)
  if (i>13) break
}

#Sequences
help("seq")
seq (from= -4, to=4, by=2) #returns -4,-2,0,2,4
seq (length=4, from=2, by=5) #returns 2,7,12,17
seq (length=4, to=4, by=4) #returns -8,-4,0,4

sx<-2
seq(from=-1, to=sx, by=sx/4) #returns -1, -0.5, 0, 0.5,  1, 1.5, 2

sx1<- c(9, 12, 7, 6)
index<- seq(along=sx1)
index  #returns 1,2,3,4
sx1[index[2]] #returns 12

#Sequence of Date & Time
Sys.Date() #returns today's date
Sys.time() #returns today's both date and time

#Go to help and check format for dates
seq(as.Date("1992/9/23"), as.Date("2020/9/23"), "years") # to, from, by
seq(as.Date("1992/9/23"), by="years", length.out=5)

start_date<- as.Date("1992/9/23")
end_date<- as.Date("2020/9/23")
out<- seq(start_date, end_date, by= "1 year") # 1 then space, then year
out

#Sequence of alphabets (total 26 letters)
letters[c(2,10,19)] #lower case
LETTERS[c(2,10,26)] #upper case

#Repeat commands (to repeat integer or characters)
help("rep")
rep(1:4, times=2) #returns 1,2,3,4, 1,2,3,4
rep(1:3, times=2, each=2) #returns 1,1, 2,2, 3,3, 1,1, 2,2, 3,3
rep(1:3, 2:4) #returns 1,1, 2,2,2, 3,3,3,3

#Sorting (by increasing or decreasing)
help("sort")
num<-c(8,5,7,6)
sort(num, decreasing=F) #increasing order
sort(num, decreasing=T) #decreasing order(default)

#Ordering (sorting by the index/ position)
help("order")
order(num,decreasing=F) #returns 2,4,3,1 (index values of vector num arranged in increasing order)

#Lists (contains numbers, characters or both)
l1<- list(c("water","oil","alcohol"), rep(1:3, times=2), matrix(data=1:9,nrow=3,ncol=3,byrow=T)) 
l1 #generation of a list (contains characters, repetition of numbers, a matrix)
l1[[1]][2] #returns oil (calling 2nd value of the 1st group of the list)

#Vector indexing
v1<- 1:10
v1[v1>7] #returns 8,9,10
v1[v1%%2==0] #modulo division(remainder is taken), returns 2,4,6,8,10

v1[5]<- NA #assigned 'not available' value to 5th element of v1
(v2<-v1[!is.na(v1)] )#returns all values except 5 {we used na.rm=T (while calculating mean)}
v1[-(1:7)] #returns 8,9,10

#Some more problems on list
l2<-list(k1=1, k2="m", k3=1:3)
l2
names(l2) #returns k1, k2, k3
names(l2)[3] #returns k3
l2[[3]][1] #returns 1 (1st value of k3 i.e. 1)
l3<-c(water=1, oil=2, alcohol=3)
l3["alcohol"] #returns 3

#To convert a list into a matrix
l4<- list(1,2,3, "x", "y", "z")
dim(l4)<-c(2,3) #since only 6 elements are present in the list
print(l4)

#Factors (let male=1: female=2)
help("factor")
mode(factor("x", "y", "z")) #returns numeric

#Dice rolled 7 times
d1<-c(1,4,3,5,4,2,4)
possible.diceface<- c(1,2,3,4,5,6) #levels
label.diceface<-c("one","two","three","four","five","six") #labels
fac<-factor(d1, levels=possible.diceface, labels=label.diceface)
fac

d2<-factor(c("oil","water","alcohol"))
d2
d3<-unclass(d2) #temporary remove the effect of class
class(d3) #returns integer
class(d2) #returns factor

d4<-factor(c("oil","oil","alcohol","oil","water"), levels=c("water","alcohol","oil"))
d4 #returns what is typed
unclass(d4) #returns 3,3,2,3,1 (as instructed in levels)

#Ordered factors
income<-ordered(c("high","high","low","med","med", levels=c("low","med","high")))
income
unclass(income) #returns 1,1,2,3,3,2,3,1

#To convert vector into factor
d5<-c(4,5,1,2,3,3,4,4,5,6)
d6<- as.factor(d5)
d6 #returns 1:6 levels

#Strings (print, cat & paste)
print(sqrt(2), digits=10) #prints 9 digits after decimal and 1 digit before decimal
cat("zero occurs at", 2*pi, "radians") #'print' can only print 1 thing at a time but 'cat' function can print multiple things at a time

da<-date()
cat("today is", da, "\n") #next line

names <- c("Dey", "Nayak", "Mitra", "Banerjee")
paste(names, "is a good boy") #prints all names separately and adds "is a good boy" to them
paste(names, "is good", collapse=", ") #write all phrases and uses comma & 'space' in between, Also sep=" " can be used instead of 'collapse' to get space in between

#Splitting strings
sp<- "I& am& a& good& boy"
strsplit(sp,"&") #shows every word separately in inverted commas

#Replacement of a string
nchar("I love food") #counts number of characters including the space

re<-"Number of players are 25"
sub(25, 30, re) #substitute characters in a string

#Difference between sub & gsub function
re1<-("dey is clever, dey is an idot")
sub("dey", "nayak", re1) #substitutes only the first letter not everywhere
gsub("dey", "nayak", re1) #replaces everywhere

#Examples of grep function
help("grep")
st<-c("R course", "excercises", "examples of R")
grep("ex", st, value=T) #search for 'ex' in all the strings and shows it
grep("ex", st, value=F) #search for 'ex' and gives the index values

#Data frames (e.g: iris, mtcars)
help("cbind") #column bind in matrix
help("rbind") #row bind in matrix
(m1<-cbind(1, 1:7)) #1st column all '1', 2nd column from '1' to'7'
(m2<-rbind(1, 1:5)) #1st row all 1, 2nd row from 1 to 5

library(MASS)
head(painters) #painters is one of the many datasets present in R (like iris)
summary(painters) #gives basic statistical values of the datasets (min, max, mean, 1st quartile, 2nd quartile, 3rd quartile)

df1<-1:9
df2<-matrix(df1, nrow=3, byrow=T)
df3<-letters[1:9]
df<- data.frame(df1, df2, df3) #data frame has to have same number of items (here 9), unlike lists
df #generation of a data frame

#Information about a data frame by 'str' function
str(iris) #gives information about a data frame

#To show a particular column in the dataset (here School column)
painters$School

#To show a particular value
painters["Da Vinci", "Drawing"] #since calling values, need to use[], returns 16

#No need for '$'
attach(painters)
Drawing #can call 'Drawing' directly without using  'painters$Drawing', because of attach function
detach(painters) #removes the effects of 'attach' function

help("subset")
#To show rows having only specific values (here painters who have 'A' in school)
subset(painters, School=="A")
subset(painters, Composition<=6) #showing only those rows(painters) whose 'Composition' value is '6'

#To show only selected columns and not show he other columns
subset(painters, select= c(-3,-5)) #removing 3rd & 5th column

#Splitting of datasets
split(painters, painters$School) #splits the whole dataset based on school rating (from 'A' to 'H', into 8 tables)

#Importing files from other software to R (websites, csv, txt, xlsx, spss)
getwd() #to know the present working directory of R, returns 'c:/user/Avrajit/Documents'
setwd("c/users/Avrajit/Downloads") #to change directory of R to 'Downloads' from 'Documents'
getwd() #returns 'c:/users/Avrajit/Downloads'

data1 <- read.table(file= "URL", header=T) #from websites, header is 'TRUE' if heading is present in the table
data2 <- read.table("avrajit.txt", header=T) #to read text file
data3 <- read.csv("avrajit.csv", header=T) #to read csv file named avrajit

install.packages("xlsx")
library(xlsx)
data4 <- read.xlsx("avrajit.xlsx") #default header=F, to read excel file

#To read excel file having sheet number/ sheet name
data5 <- read.xlsx("avrajit.xlsx", sheetIndex=2) #when sheet is not renamed, to read table from sheet 2
data6 <-read.xlsx("avrajit.xlsx", sheetName="blr") #when sheet is renamed

#To read SPSS file
install.packages("foreign")
library(foreign)
data7<-read.spss("avrajit.spss", header=T)

#Other format that can be read in R using foreign package
read.octave("") #MATLAB or octave
read.systat("") #systat
raad.xport("") #SAS
read.dta("") #stata

#Sending output of R to other file format (Exporting)
output<- cat("The sum of 6 & 8 is", 6+8) #some random output is created in R
         #Now save this output in R as anew file in the working directory
sink ("sum.txt") #file named 'sum.txt' is created in the working directory, any other type of files can be created as well
source("save.R") #the content of newly saved R file is copied in the text file
sink()

#Sending output to csv file
out1<- matrix(data=1:4, nrow=2) 
write.csv (out1, file="matrix.csv", row.names=F)
sink() #to show out put in R console again

#Statistical functions in R (graphical & analytical tools)
#example1 (gender)- 10 humans are present, out of that 6 are males &4 are females
#example2 (pizza)- 3 pizza delivery stations present (east, west, central), 5 delivery boys present, number of pizza delivered & final bill calculated from these 3 stations
#example3 (marks)- marks of 10 students in a class
#example4 (water, temp)- water demand in liters in a town for 15 days & temperature on those days in degree centigrade 
#example5 (height, weight, age)- height (in cms), weight (in kgs) & age (in years) data of 5 random man in a club

gender<- c(1,2,2,1,1,2,2,1,2,2) #1-female; 2-male
table(gender) #gives absolute frequency (no. of males & females)
(table(gender)/ length(gender)) #relative frequency, returns 0.4, 0.6

#To get the quartile of a vector using 'quantile' function
marks<-c(68,82,63,86,34,96,41,89,96,72)
quantile(marks) #returns 0%-34, 25%- 64.25 (i.e. 64.25 marks falls under 25 percentile)
quantile(marks, probs=c(0.2, 0.5, 0.8, 1)) #if we want to mention the percentile manually

#Barplot/ pie-chart/ histogram
help("barplot")
barplot(table(gender)) #barplot of absolute frequency, have to use table function else not give barplot of absolute frequency

help("pie")
pizza<- c(3,1,2,3,3,2,3,1,3,3,3,3,2,1,1,2,3,2,2,1) #20 observations
table(pizza) #absolute frequency
pie(table(pizza)) #shows pie-chart of absolute frequency

help("hist")
hist(pizza) #do not use 'table' function here, as histogram only gives measure of absolute frequency

#Central tendency (mean, median, mode, geometric mean, harmonic mean)
mean(marks) #average
median(marks)
(prod(marks)/(1/length(marks))) #geometric mean- product of n terms to the power of 1/n
1/mean(1/(marks)) #harmonic mean- reciprocal of mean of (1/x)

#Variation of data (variance, std deviation, std error, mean deviation)
var(marks) #variance
sqrt(var(marks)) #SD
IQR(marks) #inter-quartile range(3rd quartile - 1st quartile)
IQR(marks)/2 #quartile deviation
sum(abs(marks-mean(marks))/length(marks)) #mean-deviation- sum(mod(x-mean))/n
boxplot(marks) #shows mean, median, max, min, quartiles

#Structure and shape of data (skewness, kurtosis, symmetricity)
install.packages("moments")
library(moments)
skewness(marks) # <0 (negatively skewed,right-sided), >0 (positively skewed), =0 (un-skewed)
kurtosis(marks) # <3 (platy-kurtic), >3 (lepto-kurtic), =3 (meso-kurtic)

#Relationship between two linear variables (graphical tools)
water <- c(337,316,334,327,340,360,374,330,352,353,370,380,384,398,413)
temp <- c(23,25,25,26,27,28,30,26,29,32,33,34,35,38,39)
plot(water,temp) #scatter-plot using dots (default)
plot(water,temp, "l") #scatter-plot using lines
plot(water,temp, "b") #scatter-plot using both lines & dots
plot(water,temp, "o") #scatter-plot using both lines & dots, but lines are joining the dots
plot(water,temp, "h") #scatter-plot using histogram (straight lines connecting the dots)
scatter.smooth(water, temp) #smooth line considering approximate value of the dots

#Creation of matrix scatterplots
pairs (cbind (water,temp), labels=c("water demad","temp(c)" )) #cbind-combining two rows to form a matrix

#3-D plots
install.packages("scatterplot3d")
require(scatterplot3d)
height <- c(100,120,150,176,180)
weight <- c(28,35,55,74,85)
age <- c(5,8,15,18,25)
scatterplot3d(height,weight,age, angle=120)

#More functions for 3D plots
help("contour")
contour() #for contour lines
dotchart() #for dot charts
image() #3D pictures with colours 
persp() #perspective surface over X-Y plane
mossaicplot()

#Degree of linear relationship (regression, cor-relation coefficients, rank coefficients, cor-relation ratio)
cov(water,temp) #co-variance (sum[(x-mean(x))*(y-mean(y))]/n)
cor(water,temp) #cor-relation coefficient (b/w -1 to 1) (cov/[sd(x)*sd(y)])

#Solving a mathematical equation using a program
  #([(x+ln y)/y]*{exp[(x+ln y)/y]}^2/3)/5 + [(x+ln y)/y]^3

g<-function(x,y) #using a 3rd function to write the equation easily
{((x+log(y))/y)}

f<-function(x,y) #cannot define the function using 'g'
{(g(x,y)^2/(5+g(x,y)^3))*(exp(g(x,y)))^(2/3)} #have to use g(x,y) else not work

g(2,3) #value of g for x=2 & y=3
f(2,3) #value of f for x=2 & y=3

