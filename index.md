---
title       : DS9 Project
subtitle    : Learning Shiny, Slidify, etc...
author      : CChevalier
job         : Data Science Learner

framework   : io2012
theme       : default
highlighter : highlight.js
hitheme     : solarized_light
widgets     : [mathjax]
mode        : selfcontained

---
## Remember Course DS6 - Statistical Inference?

In the first project of this course we investigated the exponential distribution and the Central Limit Theorem.


```r
lambda <- 0.2; n <- 40; nosim <- 1000
demo_exp  <- rexp(n, lambda)
```

The mean of the exponential distribution is: $\mu = 1/\lambda$ and the standard deviation  is: $\sigma = 1/\lambda$


```r
# Mean of the demo distribution: Theory vs Computed demo 
c(1/lambda, mean(demo_exp))
```

```
## [1] 5.000000 6.555591
```

```r
# Standard deviation of the demo distribution: Theory vs Computed demo
c(1/lambda, sd(demo_exp))
```

```
## [1] 5.000000 5.837617
```

--- 
## The Central Limit Theorem
We generated 1000 simulations of 40 samples each from the exponential distribution with rate = lambda and computed the mean value of each simulation


```r
simus <- matrix(rexp(nosim * n, lambda), ncol = n, byrow = TRUE)
simus_mean <- apply(simus, 1, mean)
```

According to the Central Limit Theorem (CLT), the distribution of sample means, $\bar X$, is approximately normal with mean = $\mu$ and variance = $\sigma^2/n$


```r
# Overall mean: CLT Theory vs Simulated
c(1/lambda, mean(simus_mean))
```

```
## [1] 5.000000 4.985637
```

```r
# Variance: CLT Theory vs Simulated
c((1/lambda)^2 /n, var(simus_mean))
```

```
## [1] 0.6250000 0.6627873
```



--- 
## Now there is a webapp for that!
Available on shinyapp.io: https://cchevalier.shinyapps.io/ds9-playground

  

  

---
## Slide 5
  
  
Thank you!