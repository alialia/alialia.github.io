---
layout: post
title: 第一篇文章
---


这篇文章是用来试验网站的功能的

##你好世界！！！

从下面的截图可以看到：
![有帮助的截图]({{ site.url }}/assets/123.jpg)

你可以直接 [下载 PDF]({{ site.url }}/assets/mydoc.pdf).

行间公式

$$
W({X_t}) =Max\{ g(X_t),{E}[{e^{ - \int_t^{t + \varepsilon } {{r_s}} ds}}W({X_{t + \varepsilon }})]|{X_{t - }} = x)\}
$$

这是一个行内公式$$\theta$$


###试验一下代码高亮
{% highlight R%}

data <- read.table("F:/Program Files/RStudio/vixmon.txt")
summary(ts)
require(moments)
skewness(ts)
kurtosis(ts)
jarque.test(coredata(ts))
acf(ts,lag.max=1)
logts <- log(ts)

qqnorm(ts)
qqline(ts)
qqnorm(logts)
qqline(logts)

if(False){
hist(ts,freq=F,nclass=40,col="blue")
x <- seq(min(ts),max(ts),0.01)
y <- dnorm(x, mean= mean(coredata(ts)),sd=sd(coredata(ts)))
lines(x,y,col="red")

hist(logts,freq=F,nclass=40,col="blue")
x <- seq(min(logts),max(logts),0.01)
y <- dnorm(x, mean= mean(coredata(logts)),sd=sd(coredata(logts)))
lines(x,y,col="red")
}

{% endhighlight %}