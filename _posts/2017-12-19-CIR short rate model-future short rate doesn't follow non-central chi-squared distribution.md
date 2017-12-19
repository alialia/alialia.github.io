# CIR short rate model-future short rate doesn't follow non-central chi-squared distribution

今天在看Stochastic Calculus for Finance关于term structure的章节，在其中提到了CIR模型。模型中的未来的短期利率并不是一个服从正态分布的随机变量，也没办法写成关于布朗运动积分的形式，而是服从non-central chi-squared distribution。在看这个模型的时候我想看一下这个分布和正态分布会有什么区别，所以就写了一个[蒙特卡洛模拟](https://github.com/alialia/Quant/blob/master/CIR_simulation.m)来看一下实际的分布。

https://en.wikipedia.org/wiki/Noncentral_chi-squared_distribution中给出了均值，方差，偏度和峰度关于degrees of freedom $k$ 和 non-centrality parameter $\lambda$ 的公式。通过均值和方差可以反推出$k$和$\lambda$这两个参数，在带入偏度和峰度的公式，发现理论值和样本算出来的值相差甚远，而且$\lambda$算出来时小于零的，这是这个分布不允许的。

所以我就仔细的阅读了[wikipedia关于CIR模型的介绍](https://en.wikipedia.org/wiki/Cox%E2%80%93Ingersoll%E2%80%93Ross_model)，发现

The distribution of future values of a CIR process can be computed in closed form:

$$r_{{t+T}}={\frac  {Y}{2c}}$$中说的是Y满足[non-central Chi-Squared](https://en.wikipedia.org/wiki/Noncentral_chi-squared_distribution) distribution，而不是短期利率，即使c在这里是一个常数。

所以，并不是所有的随机变量乘以一个常数还会满足原来的分布(参数变化不在考虑范围内)。引以为戒，得小心这种陷阱，还是统计学的不够扎实。