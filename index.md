---
title       : Reproducible Pitch Presentation
subtitle    : 
author      : Johan Larsson B
job         : Coursera Student
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [shiny, quiz, bootstrap]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## mtcars Explorer

- mtcars Explorer is an interactive Shiny application that allows the user to explore the variables in the mtcars dataset.

- The application has two input controls:
  - One drill-down list for selecting the variable to analyse
  - One slider for guessing the mean
  
- The output contains of:
  - A histogram of the selected variable
  - The guessed mean (mu) plotted as a red vertical line in the histogram
  - The current guessed mean (mu) and the Mean Square Error (MSE) printed above the histogram

---  

## Example Cylinder Distribution



```r
library(datasets)
library(manipulate)
data(mtcars)
variable <- "cyl"
variable_mean <- mean(as.numeric(mtcars[ , variable]), na.rm = TRUE)
variable_min <- min(as.numeric(mtcars[ , variable]), na.rm = TRUE)
variable_max <- max(as.numeric(mtcars[ , variable]), na.rm = TRUE)
myHist <- function(mu){
    dist <- as.numeric(mtcars[ , variable])
    hist(dist, xlab=variable, col='lightblue', main='Histogram')
    lines(c(mu, mu), c(0, 200),col="red",lwd=5)

}
manipulate(myHist(mu), mu = slider(variable_min, variable_max, initial = variable_mean, step = 0.5))
```

---  

## Example Cylinder Distribution

![plot of chunk unnamed-chunk-2](assets/fig/unnamed-chunk-2-1.png) 

---  &checkbox

## Evaluation

1. _Is this presentation created by using Slidify or Rstudio Presenter?_
2. _Does it have 5 pages?_
3. _Is it hosted on github or Rpubs?_
4. _Does it contain some embedded R code that gets run when slidifying the document?_

*** .hint

Check the box in front of all questions to which the answer is yes.

*** .explanation

All the questions should be checked for ful score.
---
