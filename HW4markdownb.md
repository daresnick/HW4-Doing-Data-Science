# Homework 4 Bootstrap CL theorem
Damon Resnick  
October 5, 2016  

### The code and histogram below show the illustration of the central limit theorem applied to a random sampling of a population by random sampling the sample of the population 1000 times and plotting the histogram of the means of each sample of the sample and comparing the means and standard deviations of the sample and the sample of the sample.

#### The explanation of the code is given in the first instance below while the repeated codes don't have the full explanation.



```r
x1<-rnorm(50,22,5) # generates 50 random normal obs from a population of mean = 22 and sd = 5
xbar1<-mean(x1) # Mean of the random sample.
xbar1
```

```
## [1] 21.26837
```

```r
# The sample mean is different than the population mean of 22!
nsims<-1000
bootnorm1<-numeric(nsims) # Making sure the nsims is numeric and of the correct length.

# The loop below is a for loop that populates bootnorm1 with 1000 means of the ranodom sample of the rnorm sample.
for(i in 1:nsims){
        temp<-sample(x1,50,replace = TRUE)
        bootnorm1[i]<-mean(temp)
        
}
summary(bootnorm1) # Checking to make sure bootnorm1 makes sense.
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   18.98   20.81   21.29   21.27   21.75   23.57
```

```r
hist(bootnorm1) # Histogram showing the distribution of the 1000 means sampled.

sd(bootnorm1)
```

```
## [1] 0.7228036
```

```r
sd(x1)
```

```
## [1] 5.117739
```

```r
sd(x1)/sqrt(50)
```

```
## [1] 0.7237576
```

```r
## The sd of bootnorm1 is very close but not the same as the expected sd from the central limit theorem!
## Clearly demostrating the central limit theorem as the distribution of the means is normal close to centered on the mean of the original sample.

abline(v=xbar1,col="red",lwd=2)
abline(v=mean(bootnorm1),col="blue",lwd=2,lty=2)
abline(v=22,col="cyan",lwd=3,lty=3)
```

![](HW4markdown_files/figure-html/unnamed-chunk-1-1.png)<!-- -->

```r
est.bias<-xbar1-mean(bootnorm1)
est.bias
```

```
## [1] 0.0003821961
```

```r
## There is bias however noting the small difference between the blue and red lines. And you can see (lite blue dashed line) that the population mean was 22 and the sample does not have exactly the same mean.
```



```r
x2<-rnorm(100,20,4) # generates 100 random normal obs from a population of mean = 20 and sd = 4
xbar2<-mean(x2)
xbar2
```

```
## [1] 20.56342
```

```r
nsims<-1000
bootnorm2<-numeric(nsims)

for(i in 1:nsims){
        temp<-sample(x2,100,replace = TRUE)
        bootnorm2[i]<-mean(temp)
        
}
summary(bootnorm2)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   19.35   20.27   20.55   20.55   20.82   21.74
```

```r
hist(bootnorm2)

sd(bootnorm2)
```

```
## [1] 0.395407
```

```r
sd(x2)
```

```
## [1] 4.03684
```

```r
sd(x2)/sqrt(100)
```

```
## [1] 0.403684
```

```r
## The sd of bootnorm2 is very close but not the same as the expected sd from the central limit theorem!
## Clearly demostrating the central limit theorem as the distribution of the means is normal close to centered on the mean of the original sample.

abline(v=xbar2,col="red",lwd=2)
abline(v=mean(bootnorm2),col="blue",lwd=2,lty=2)
abline(v=20,col="cyan",lwd=3,lty=3)
```

![](HW4markdown_files/figure-html/unnamed-chunk-2-1.png)<!-- -->

```r
est.bias<-xbar2-mean(bootnorm2)
est.bias
```

```
## [1] 0.008702436
```

```r
## There is bias however noting the small difference between the blue and red lines. And you can see (lite blue dashed line) that the population mean was 20 and the sample does not have exactly the same mean.
```




```r
x3<-rexp(50) # generates 50 random exponential obs
xbar3<-mean(x3)
xbar3
```

```
## [1] 0.7579705
```

```r
nsims<-1000
bootnorm3<-numeric(nsims)

for(i in 1:nsims){
        temp<-sample(x3,50,replace = TRUE)
        bootnorm3[i]<-mean(temp)
        
}
summary(bootnorm3)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##  0.5112  0.6934  0.7514  0.7560  0.8148  1.0700
```

```r
hist(bootnorm3)

sd(bootnorm3)
```

```
## [1] 0.08991851
```

```r
sd(x3)
```

```
## [1] 0.6355912
```

```r
sd(x3)/sqrt(50)
```

```
## [1] 0.08988618
```

```r
## The sd of bootnorm3 is very close but not the same as the expected sd from the central limit theorem!
## Clearly demostrating the central limit theorem as the distribution of the means is normal close to centered on the mean of the original sample.

abline(v=xbar3,col="red",lwd=2)
abline(v=mean(bootnorm3),col="blue",lwd=2,lty=2)
```

![](HW4markdown_files/figure-html/unnamed-chunk-3-1.png)<!-- -->

```r
est.bias<-xbar3-mean(bootnorm3)
est.bias
```

```
## [1] 0.00195238
```

```r
## There is bias however but less with a larger sample size.
```



```r
x4<-rexp(100) # generates 100 random exponential obs
xbar4<-mean(x4)
xbar4
```

```
## [1] 0.9447948
```

```r
nsims<-1000
bootnorm4<-numeric(nsims)

for(i in 1:nsims){
        temp<-sample(x4,100,replace = TRUE)
        bootnorm4[i]<-mean(temp)
        
}
summary(bootnorm4)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##  0.6929  0.8752  0.9396  0.9433  1.0100  1.2770
```

```r
hist(bootnorm4)

sd(bootnorm4)
```

```
## [1] 0.1005854
```

```r
sd(x4)
```

```
## [1] 1.023771
```

```r
sd(x4)/sqrt(100)
```

```
## [1] 0.1023771
```

```r
## The sd of bootnorm4 is very close but not the same as the expected sd from the central limit theorem!
## Clearly demostrating the central limit theorem as the distribution of the means is normal close to centered on the mean of the original sample.

abline(v=xbar4,col="red",lwd=2)
abline(v=mean(bootnorm4),col="blue",lwd=2,lty=2)
```

![](HW4markdown_files/figure-html/unnamed-chunk-4-1.png)<!-- -->

```r
est.bias<-xbar4-mean(bootnorm4)
est.bias
```

```
## [1] 0.001494775
```

```r
## There is bias however but less with a larger sample size.
```




