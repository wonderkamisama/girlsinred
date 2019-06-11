---
title: Calculation/計算
author: wanda
date: '2019-05-18'
slug: calculation
categories:
  - R
tags: []
---
心血來潮地想要嘗試一些運算,需要安裝一個新的包ggplot2
## 一元方程
ax+b=0,设a=5,b=10,求x

```r
f1<-function(x,a,b) a*x+b
a<-5
b<-10
result<-uniroot(f1,c(-10,10),a=a,b=b,tol=0.00001)
result$root
```

```
## [1] -2
```

```r
x<-seq(-5,5,by=0.01)
y<-f1(x,a,b)
df<-data.frame(x,y)
ggplot2::aes(x,y)
```

```
## Registered S3 methods overwritten by 'ggplot2':
##   method         from 
##   [.quosures     rlang
##   c.quosures     rlang
##   print.quosures rlang
```

```
## Aesthetic mapping: 
## * `x` -> `x`
## * `y` -> `y`
```

```r
ggplot2::geom_line(col="red")
```

```
## geom_line: na.rm = FALSE
## stat_identity: na.rm = FALSE
## position_identity
```

```r
ggplot2::geom_vline(yintercept=0)
```

```
## Warning: Ignoring unknown parameters: yintercept
```

```
## geom_vline: na.rm = FALSE
## stat_identity: na.rm = FALSE
## position_identity
```

```r
ggplot2::geom_hline(yintercept=0)
```

```
## mapping: yintercept = ~yintercept 
## geom_hline: na.rm = FALSE
## stat_identity: na.rm = FALSE
## position_identity
```

```r
ggplot2::ggtitle(paste("y=",a,"*x+",b))
```

```
## $title
## [1] "y= 5 *x+ 10"
## 
## attr(,"class")
## [1] "labels"
```

