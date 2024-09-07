---
layout:     post
title:      Integration Using Excel
subtitle:   an easy and small try
author:     "Li Yinan"
header-img: "img/post-integration-excel.jpg"
catalog: true
mathjax: true
onTop: true
tags:
    - Excel
    - Math
---

## Problem Setup
This first project is not too difficult. Here Excel may seem like an unwise choice, but it helps us understand algorithms better than other calculators. In fact, using Excel to try out simple problems first helps us better deal with complex problems using high-level programming language.

The first example is to solve an easy integral.
$$
\int_{0}^{\frac{\pi}{2}} \frac{1}{1+sint} dt
$$

Analytically, we can substitute $x=tan\frac{t}{2}$ to solve the problem.

## Preperations
Before the probem can be put into Excel, boundary values should be defined first. As given by problem, $t_{0}=0$, and $t_{f}=\pi/2$. Substitue $t=0$ into the expression leads to $\frac{1}{1+sint}=1$

[picture](img\in-post\post-integration-excel\initial-value.png)

Then, discretization of the small element is needed, which means the value of time step$dt$ should be chosen. Smaller $dt$ will result in slow convergence while larger $dt$ constitutes to error in final value. Here the eqaution is discretized by choosing $ dt=0.01$.

[discretization](img\in-post\post-integration-excel\discretization.png)

## Accumulation to get the answer
Accumulation is used to simulate integration operation. In Excel, it can be realized by adding the new value to the current value.

In the integration case, after finding the initial value, increment in each time step needs to be determined. It is the part inside of integration symbol.  $\Delta y=\Delta f(t)dt$. 

[accumulation1](img\in-post\post-integration-excel\accumulation1.png)

Accumulate for each step(including the first step). Since $0 \leq t \leq \frac{\pi}{2}$, hence the termial value of $t$ is about 1.57. Scroll down to corresponding row and the result is: 

[result](img\in-post\post-integration-excel\result.png)

Curve represents the integral value at each time steps:
[curve](img\in-post\post-integration-excel\curve.jpg)

Using online calculator, the analytical result is 1, consider the size oftime step $\Dealta t=0.01$, this is an acceptable result. 