---
title: "Math 300 NTI Lesson 31"
subtitle: "Interpreting Hypothesis Tests"
author: "Professor Bradley Warner"
date: "July, 2022"
output:
  html_document: 
    theme: lumen
    toc: yes
    toc_float: yes
    css: NTI.css
    keep_md: yes
  pdf_document:
    toc: yes
---




## Objectives

1. Correctly use terminology and notation of interpreting hypothesis tests.     



## Reading 

[Chapter 9.4](https://moderndive.com/9-hypothesis-testing.html#ht-interpretation)


## Lesson 

*Remember that you will be running this more like a lab than a lecture. You want them using `R` and answering questions. Have them open the notes rmd and work through it together.*

Work through the learning checks LC 9.5 - LC 9.8. We suggest you work through terminology using the criminal court analogy. 

+ This section is conceptually difficult. We are setting up a contradiction but it is based on empirical data. Thus the language becomes somewhat confusing. The criminal trial analogy is a good reference to put the ideas into context. There is a large number of terms.  

+ The "fail to reject" idea is tricky since people want to "accept the null hypothesis". Remember there is a difference between "not guilty" and "innocent" in a trial. 

+ This framework helps:  
a - The defendant is truly either “innocent” or “guilty.” These are the two possible outcomes of the test.  
b - The defendant is presumed “innocent until proven guilty.” "Innocent" is the null hypothesis.   
c - The defendant is found guilty only if there is strong evidence that the defendant is guilty. The phrase “beyond a reasonable doubt” is often used as a guideline for determining a cutoff for when enough evidence exists to find the defendant guilty. "Beyond a reasonable doubt" is the level of significance $\alpha$.  
d - The defendant is found to be either “not guilty” or “guilty” in the ultimate verdict. This is "reject" or "fail to reject". Note that we do not find a defendant "innocent". Note that "fail to reject" is a weak conclusion. 

+ Write conclusion in the context of the problem. For example "We found enough evidence in this data to suggest that there was gender discrimination at play in bank promotions" or "we did not find enough evidence to conclude gender discrimination was at play."   

+ The names **Type I** and **Type II** are not informative. False positive and false negative make more sense in the context that a positive is rejecting the null hypothesis. 

***

### Libraries 


```r
library(tidyverse)
library(infer)
library(moderndive)
library(nycflights13)
library(ggplot2movies)
```




### LC 9.5 (Objective 1)


**(LC9.5)**  What is wrong about saying, "the defendant is innocent," based on the US system of criminal trials?


**Solution**:  

Failing to prove the defendant is guilty is not equivalent to proving that the defendant is innocent. There will always be the possibility of making errors in the trial. The default assumption is that the defendant is innocent and you must prove, based on evidence, that the defendant is guilty. If you fail, all that can be concluded is that you failed to prove the defendant is guilty.  

### LC 9.6 (Objective 1)

**(LC9.6)**  What is the purpose of hypothesis testing?

**Solution**:  

The purpose of hypothesis testing is to determine whether there is enough statistical evidence to support an alternative hypothesis about a population; this is evaluated by the use of a single number metric and its sampling distribution. 

### LC 9.7 (Objective 1)

**(LC9.7)**  What are some flaws with hypothesis testing? How could we alleviate them?

**Solution**:  

The use of a $p$-value and the binary decision of rejecting or failing to reject can lead to decision makers not thinking about the data and the problem. If the $p$-value is 0.049, you can reject but it is really borderline. Also the use of $p$-values can lead to data snooping issues where a researcher keeps conducting hypothesis tests with the same data until a significant result is found. We personally prefer confidence intervals. However, you need to be aware of hypothesis testing and $p$-values because they are still being used. 

### LC 9.8 (Objective 1)

**(LC9.8)**  Consider two $\alpha$ significance levels of 0.1 and 0.01. Of the two, which would lead to a more *liberal* hypothesis testing procedure? In other words, one that will, all things being equal, lead to more rejections of the null hypothesis $H_0$.

**Solution**:  

The greater $\alpha$ of 0.1 will lead to a more liberal hypothesis testing procedure, because the required $p$-value to reject the null hypothesis $H_0$ can be greater. There is a higher chance that the $p$-value will be less than $\alpha$. In the example of a court case, consider "reasonable doubt" to "absolutely convinced" as a criteria. Which leads to more guilty defendants being let go?



## Documenting software 

  * File creation date: 2022-07-08
  * R version 4.1.3 (2022-03-10)
  * `tidyverse` package version: 1.3.1
  * `moderndive` package version: 0.5.4
  * `infer` package version: 1.0.2

