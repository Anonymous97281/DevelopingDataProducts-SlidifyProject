---
title       : Mortgage Monthly Payment Calculator
subtitle    : Project for Developing Data Products Course
author      : Anonymous97281
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

Mortgage monthly payment calculation is a very commonly needed task for lots of people interested in buying or refinancing their home. This application helps such users do the calculation quickly and accurately.

--- .class #id 

## Application Inputs

The application takes primarily 3 inputs to calculate the monthly amount.

1. The loan/principal amount

    a. The loan amount can be any numeric value between 0 and 100,000,00

2. The loan term in years
    
    a. The loan term can have 5 possible values of 5, 10, 15, 20, 30.

3. The loan interest rate

    a. The loan interest rate can have values from 1 to 15 in increments of 0.5.

---

## Formula used in the Calculation
The formula used for calculating the monthly mortgage amount is as below

amount = loan * (1 + i)\^ n/((1 + i)\^ n - 1)  
where  
loan = loan amount  
i = interest rate per month (yearly interest rate / 12)  
n = loan term in number of months  
^ = implies power of.

---

## Example 
Let us take an example for this where  
loan = 100000  
interest rate = 5%  
term = 30 years  


```r
niLoanAmt <- 100000
niLoanTermYears <- 30
siLoanInterest <- 5

months <- as.numeric(niLoanTermYears) * 12
yearlyInterest <- as.numeric(siLoanInterest)
monthlyInterest <- yearlyInterest / 12 / 100
loanAmt <- as.numeric(niLoanAmt)
tmp1 <- (1 + monthlyInterest)^months
monthlyMortgage <- loanAmt * (monthlyInterest * tmp1)/ (tmp1 - 1)

monthlyMortgage
```

```
## [1] 536.8216
```
---
