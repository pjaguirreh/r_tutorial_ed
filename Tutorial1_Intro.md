% Tutorial 1: Getting Started
% R Bootcamp HTML Slides
% Jared Knowles




# R
- R is an Open Source (and freely available) environment for statistical computinga nd graphics
- Available for Windows, Mac OS X, and Linux
- R is being actively developed with two major releases per year and dozens of releases of add on packages
- R can be extended with 'packages' that contain data, code, and documentation to add new functionality

# What Does it Look Like?
The R workspace in RStudio

<p align="center"><img src="img/workspacescreen.png" height="500" width="700"></p>

# Why Use R
- R is a common tool among data experts at major universities
- No need to go through procurement, R can be installed in any environment on any machine and used with no licensing or agreements needed
- R source code is very readable to increase transparency of processes
- R code is easily borrowed from and shared with others
- R is incredibly flexible and can be adapted to specific local needs
- R is under incredibly active development, improving greatly, and supported wildly by both professional and academic developers

# R Advantages Continued
- R is platform agnostic--Linux, Mac, PC, server, desktop, etc.
- R can output results in a variety of formats
- R can build routines straight out of a database for common and universal reporting

R Can Compliment Other Tools
------------------------------------
- R plays nicely with data from Stata, SPSS, SAS and others
- R can check work, produce output, visualize results from other programs
- R can do bleeding edge analysis that aren't available in proprietary packages yet
- R is becoming more prevalent in undergraduate statistics courses

# Google Scholar Hits
R has recently passed Stata on Google Scholar hits and it is catching up to the two major players SPSS and SAS

<p align="center"><img src="img/googlescholar.png" height="500" width="700"></p>

# R Has an Active Web Presence
R is linked to from more and more sites 

<p align="center"><img src="img/sitelinks.png" height="500" width="700"></p>

# R Extensions
These links come from the explosion of add-on packages to R

<p align="center"><img src="img/addons.png" height="500" width="700"></p>

# R Has an Active Community 
Usage of the R listserv for help has really exploded recently

<p align="center"><img src="img/rlistserv.png" height="500" width="700"></p>

# R Vocabulary
- **packages** are add on features to R that include data, new functions and methods, and extended capabilities. Think of them as ``apps'' on your phone.
- **terminal** this is the main window of R where you enter commands
- **scripts** these are where you store commands to be run in the terminal later, like syntax in SPSS or .do files in Stata
- **functions** commands that do something to an object in R
- **dataframe** the main element for statistical purposes, an object with rows and columns that includes numbers, factors, and other data types
- **workspace** the working memory of R where all objects in the current session are stored
- **vector** the basic unit of data in R

# Components of an R Setup
- **R** - obviously we need R. R works in the command line of any OS, but also comes with a basic GUI to operate on its own in Windows and Mac [download](http://cran.r-project.org/)
- **RStudio** - a much better way to work in R that allows editing of scripts, operation of R, viewing of the workspace, and R help all on one screen [download](http://rstudio.org/download/)
- **LaTeX** - for producing documents using R this is less necessary, but still useful. download [WIN](http://miktex.org/2.9/setup) [MAC](http://www.tug.org/mactex/2011/)

** ADVANCED **

- **Dev Tools for R** - on Windows this is Rtools, on Linux and Mac it is installing the development mode of R download [WIN](http://www.stats.ox.ac.uk/pub/Rtools/R215x.html) [MAC](http://cran.r-project.org/bin/macosx/tools/)
- **Git** - for version control, sharing code, and collaboration this is essential. It integrates well with RStudio. [download](http://git-scm.com/download)
- **pandoc** - for converting output into other formats for sharing with non-user**R**s! [download](http://johnmacfarlane.net/pandoc/installing.html)

# Installing R on Windows
<p align='center'><iframe src="http://www.screenr.com/embed/kzT8" width="650" height="396" frameborder="0"></iframe></p>


# R As A Calculator



```r
2 + 2  # add numbers
```



```
## [1] 4
```



```r
2 * pi  #multiply by a constant
```



```
## [1] 6.283
```



```r
7 + runif(1, min = 0, max = 1)  #add a random variable
```



```
## [1] 7.552
```



```r
4^4  # powers
```



```
## [1] 256
```



```r
sqrt(4^4)  # functions
```



```
## [1] 16
```




# Using the Workspace
- To do more we need to learn how to manipulate the 'workspace'.
- This includes all the scalars, vectors, datasets, and functions stored in memory.
- All R objects are stored in the memory of the computer, limiting the available space for calculation to the size of the RAM on your machine.
- R makes organizing the workspace easy.


```r
x <- 5  #store a variable with <-
x  #print the variable
```



```
## [1] 5
```



```r
z <- 3
ls()  #list all variables
```



```
## [1] "x" "z"
```



```r
ls.str()  #list and describe variables
```



```
## x :  num 5
## z :  num 3
```



```r
rm(x)  # delete a variable
ls()
```



```
## [1] "z"
```




# R as a Language
- R is more than statistical software, it is a computer language
- Like any language it has rules (some poorly enforced), and conventions
- You will learn more as you go, but we'll go over a few to start

1. Case sensitivity matters


```r
a <- 3
A <- 4
print(c(a, A))
```



```
## [1] 3 4
```



  * <font color="red">**a** &#8800; **A**</font> 
2. What happens if I type **print(a,A)**?
  * So what does **c** do?


```r
A <- c(3, 4)
print(A)
```



```
## [1] 3 4
```



  * **c** stands for concatenate and allows vectors to have multiple elements

# Data Modes in R
- R allows users to implement a number of different types of data
- The three basic data types are numeric data, character data, and logical data
-**numeric** includes valid numbers


```r
is.numeric(A)
```



```
## [1] TRUE
```



```r
print(A)
```



```
## [1] 3 4
```



-**character** is known as strings in other software, any characters that have no numeric meaning


```r
b <- c("one", "two", "three")
print(b)
```



```
## [1] "one"   "two"   "three"
```



```r
is.numeric(b)
```



```
## [1] FALSE
```



```r
print(b)
```



```
## [1] "one"   "two"   "three"
```



-**logical** is TRUE or FALSE values, useful for logical testing and programming


```r
c <- c(TRUE, TRUE, TRUE, FALSE, FALSE, TRUE)
is.numeric(c)
```



```
## [1] FALSE
```



```r
is.character(c)
```



```
## [1] FALSE
```



```r
is.logical(c)  # Results in a logical value
```



```
## [1] TRUE
```




# Data Structures in R
- R has a number of basic data classes as well as arbitrary specialized object types for various purposes
-**vectors** are the basic data class in R and can be thought of as a single column of data (even a column of length 1)
-**matrices** are rows and columns of all the same mode data
-**dataframes** are rows and columns where the columns can represent different data types

# Vectors 
- Everything is a vector in R, even single numbers


```r
print(1)
```



```
## [1] 1
```



```r
# The 1 in braces means this element is a vector of length 1
print("This tutorial is awesome")
```



```
## [1] "This tutorial is awesome"
```



```r
# This is a vector of length 1 consisting of a single 'string of
# characters'
print(LETTERS)
```



```
##  [1] "A" "B" "C" "D" "E" "F" "G" "H" "I" "J" "K" "L" "M" "N" "O" "P" "Q"
## [18] "R" "S" "T" "U" "V" "W" "X" "Y" "Z"
```



```r
# This vector has 26 character elements
print(LETTERS[6])
```



```
## [1] "F"
```



```r
# The sixth element of this vector has length 1
length(LETTERS[6])
```



```
## [1] 1
```



```r
# The length of that element is a number with length 1
```




# Language
- In language there are a number of ways to say the same thing
  *  <font color="green">The dog chased the cat.</font> 
  *  <font color ="blue">The cat was chased by the dog.</font>
  *  <font color ="red">By the dog, the cat was chased.</font>
- Some ways are more elegant than others, all convey the same message. 


```r
a <- runif(100)  # Generate 100 random numbers
b <- runif(100)  # 100 more
c <- NULL  # Setup for loop (declare variables)
for (i in 1:100) {
    # Loop just like in Java or C
    c[i] <- a[i] * b[i]
}
d <- a * b
identical(c, d)  # Test equality
```



```
## [1] TRUE
```



- Which is nicer?

# Reading Data In
- To read data in we have to tell R where it currently is on the filesystem by setting a working directory
- Then we have to tell it where to look for the dataset and what format that dataset is in
- CSV files are **simplest** for beginning use cases, but R is flexible


```r
# Set working directory to the tutorial director In RStudio can do this in
# 'Tools' tab
setwd("~/r_tutorial_ed")
```



```
## Error: cannot change working directory
```



```r
# Load some data
df <- read.csv("data/smalldata.csv")
# Note if we don't assign data to 'df' R just prints contents of table
```




# Objects
- Everything in R is an object--even functions
- Objects can be manipulated many ways
- A common example is applying the `summary' function to a variety of object types and seeing how it adapts


```r
summary(df[, 28:31])  #summary look at df object
```



```
##    schoollow         readSS        mathSS           proflvl    
##  Min.   :0.000   Min.   :252   Min.   :210   advanced   : 788  
##  1st Qu.:0.000   1st Qu.:430   1st Qu.:418   basic      : 523  
##  Median :0.000   Median :495   Median :480   below basic: 210  
##  Mean   :0.242   Mean   :496   Mean   :483   proficient :1179  
##  3rd Qu.:0.000   3rd Qu.:562   3rd Qu.:543                     
##  Max.   :1.000   Max.   :833   Max.   :828                     
```



```r
summary(df$readSS)  #summary of a single column
```



```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##     252     430     495     496     562     833 
```



-The **$** says to look for object **readSS** in object **df**

# Graphics too



```r
library(ggplot2)  # Load graphics Package
qplot(readSS, mathSS, data = df, geom = "point", alpha = I(0.3)) + 
    theme_bw() + opts(title = "Test Score Relationship") + geom_smooth()
```

![Student Test Scores](figure/slides-graphics1.svg) 


# Handling Data in R
- R handles data differently than many other statistical packages
- In R, all elements are objects


```r
length(unique(df$school))
```



```
## [1] 173
```



```r
length(unique(df$stuid))
```



```
## [1] 1200
```



- Results of function calls can be stored


# Reproducible research

It is good to include the session info, e.g. this document is produced with **knitr** version `0.5`. Here is my session info:



```r
print(sessionInfo(), locale = FALSE)
```



```
## R version 2.15.0 (2012-03-30)
## Platform: i386-pc-mingw32/i386 (32-bit)
## 
## attached base packages:
## [1] grid      stats     graphics  grDevices utils     datasets  methods  
## [8] base     
## 
## other attached packages:
## [1] hexbin_1.26.0  lattice_0.20-6 ggplot2_0.9.1  knitr_0.5     
## 
## loaded via a namespace (and not attached):
##  [1] codetools_0.2-8    colorspace_1.1-1   dichromat_1.2-4   
##  [4] digest_0.5.2       evaluate_0.4.2     formatR_0.4       
##  [7] highlight_0.3.1    labeling_0.1       MASS_7.3-18       
## [10] memoise_0.1        munsell_0.3        parser_0.0-14     
## [13] plyr_1.7.1         proto_0.3-9.2      RColorBrewer_1.0-5
## [16] Rcpp_0.9.10        RCurl_1.91-1.1     reshape2_1.2.1    
## [19] scales_0.2.1       stringr_0.6        tools_2.15.0      
## [22] XML_3.9-4.1       
```


