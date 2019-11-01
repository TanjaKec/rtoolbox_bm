---
date: "2016-04-09T16:50:16+02:00"
title: Data Types
output: 
  learnr::tutorial
weight: 7
---

The examples we have used in the 'How to Use R' section are all dealing with numbers (quantitative numerical data). Those of you familiar with programming will know that numerical objects can be classified as real, integer, double or complex. To check if an object is numeric and what type it is, you can use the `mode()` and `class()` functions respectively.

Let us go back into our R project and type the following into the open script file and run the code.😃


```r
x <- 1:10
mode(x)
```

```
## [1] "numeric"
```

```r
class(x)
```

```
## [1] "integer"
```

In R to enter strings of characters as objects you need to enter them using quote marks around them. By default it expects all inputs to be numeric and unless you use quote marks around the strings you wish to enter, it will consider them as numbers and subsequently will return an error message.


```r
x <- c("UK", "Spain", "Serbia", "France", "Germany", "Italy")
mode(x)
```

```
## [1] "character"
```

It is common in statistical data to have attributes also known as categorical variables. In R such variables should be specified as **factors**. Attribute variable has a set of levels indicating possible outcomes. Hence, to deal with x as an attribute variable with five levels we need to make it a factor in R.


```r
x <- c("UK", "Spain", "Serbia", "France", "Germany", "Italy")
x <- factor(x)
x
```

```
## [1] UK      Spain   Serbia  France  Germany Italy  
## Levels: France Germany Italy Serbia Spain UK
```

{{% notice note %}}
💡: Note that R codes the factor levels in their alphabetical order. However, attribute variables are usually coded and you would usually enter them as such.
{{% /notice %}}


```r
quality <- factor(c(3, 3, 4, 2, 2, 4, 0, 1))
levels(quality)
```

```
## [1] "0" "1" "2" "3" "4"
```

```r
quality
```

```
## [1] 3 3 4 2 2 4 0 1
## Levels: 0 1 2 3 4
```

You might need to deal from time to time with **logical** data type. This is when something is recorded as TRUE or FALSE. It is most likely that you would use this data type when checking what type of data the variable is that you are dealing with. For example


```r
x <- c("UK", "Spain", "Serbia", "France", "Germany", "Italy")
is.numeric(x)
```

```
## [1] FALSE
```

```r
is.factor(x)
```

```
## [1] FALSE
```

### Data Frames

Statistical data usually consists of several vectors of equal length and of various types that resemble a table. Those vectors are interconnected across so that data in the same position comes from the same experimental unit, ie. observation. R uses data frame for storing this kind of data table and it is regarded as primary data structure.

Let us consider a study of share prices of companies from three different business sectors. As part of the study a random sample (n=15) of companies was selected and the following data was collected:


```r
share_price <- c(880, 862, 850, 840, 838, 799, 783, 777, 767, 746, 692, 689, 683, 661, 658)
profit <- c(161.3, 170.5, 140.7, 115.7, 107.9, 135.2, 142.7, 114.9, 110.4, 98.9, 90.2, 80.6, 85.4, 91.7, 137.8)
sector <- factor(c(3, 3, 3, 3, 3, 2, 2, 2, 2, 2, 1, 1, 1, + 1, 1)) # 1:IT, 2:Finance, 3:Pharmaceutical
#
share_price
```

```
##  [1] 880 862 850 840 838 799 783 777 767 746 692 689 683 661 658
```

```r
profit
```

```
##  [1] 161.3 170.5 140.7 115.7 107.9 135.2 142.7 114.9 110.4  98.9  90.2
## [12]  80.6  85.4  91.7 137.8
```

```r
sector
```

```
##  [1] 3 3 3 3 3 2 2 2 2 2 1 1 1 1 1
## Levels: 1 2 3
```

Rather than keeping this data as a set of individual vectors in R, it would be better to keep whole data as a single object, i.e. data frame.

```
share.data <- data.frame(share_price, profit, sector)
share.data
```

Individual vectors from the data frame can be accessed using `$` symbol:

```
share.data$sector
```

Now, as we have mastered the basics let us learn how to access existing data from R.




-----------------------------
© 2019 Tatjana Kecojevic
