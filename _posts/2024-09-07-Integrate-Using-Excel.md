---
layout:     post
title:      Integration Using Excel
subtitle:   an easy and small try
author:     "Li Yinan"
header-img: "img/post-integration-excel.jpg"
catalog: true
mathjax: true
tags:
    - Excel
    - Math
---

## Problem Setup
let's try to solve an easy integral.
$
\int_{0}^{\frac{\pi}{2}} \frac{1}{1+sint} dt
$
The traditional method is to substitute $x=tan\frac{t}{2}$ to solve the problem.

## Preperations
Before the probem can be put into Excel, boundary values should be determined first. As given by problem, $t_{0}=0$, and $t_{f}=\pi/2$. Substitue $t=0$ gives $\frac{1}{1+sint_{0}}=1$

![](https://raw.githubusercontent.com/mgt-lya/mgt-lya.github.io/master/img/in-post/post-integration-excel/initial-value.png)

Then, discretization of the equation into small element is required, which means the value of time step $\Delta t$ (or $dt$ in continuous time) needs to be chosen. Smaller $\Delta t$ will result in slow convergence while larger $\Delta t$ constitutes to error in final value. Here I choose $ \Delta t=0.01$.

![](https://raw.githubusercontent.com/mgt-lya/mgt-lya.github.io/master/img/in-post/post-integration-excel/discretization.png)

## Accumulation & Get The Answer
Accumulation is used to simulate integration operation. In Excel, it can be realized by $\textbf{adding the new value to the current value.}$

Initial value of the integral can be found by current value $int=0$ plus new value $f(x)dt=\frac{1}{sint_{0}} \times \Delta t=1\times 0.01=0.01$, which is the increment of first step.

After finding the initial value, we can add increment at differnet steps to current value. For example the C3 cell is the summation of C2 and increment $B3 \times \Delta t$ 

![](https://raw.githubusercontent.com/mgt-lya/mgt-lya.github.io/master/img/in-post/post-integration-excel/accumulation1.png)

For each time step, the increment is the same. Since $0 \leq t \leq \frac{\pi}{2}$, the termial value of $t$ is about 1.57. Scroll down to corresponding row and the result is: 

![](https://raw.githubusercontent.com/mgt-lya/mgt-lya.github.io/master/img/in-post/post-integration-excel/result.png)

The curve representing the integral value at each time step is:

![](https://raw.githubusercontent.com/mgt-lya/mgt-lya.github.io/master/img/in-post/post-integration-excel/curve.jpg)

By using online calculator, we can get the correct, analytical result, which is 1. Consider the size of time step $\Delta t$ is 0.01, the numerical result is acceptable.

## EXCEL Download
The Excel table used in this example can be downloaded from [here](https://github.com/mgt-lya/mgt-lya.github.io/blob/master/Assets/Integration_Excel.xlsx)