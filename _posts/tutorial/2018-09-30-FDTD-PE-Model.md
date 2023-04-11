---
layout: post
title: "Finite-Difference Time-Domain Method"
subtitle:
description:
tags: [math]
img: fdtd-method.png
categories: tutorial
math: 1
---
<div class="alert alert-warning" role="alert" markdown="1">
I'm not a native English speaker, please ignore my bad expressions. This post is not complete, it will be improved later. 
</div>
{% include toc.html %}

In this post, I will show you the basic hybrid model: FDTD-PE.

You can also see details in the artical of [Timothy Van Renterghem](https://www.ingentaconnect.com/content/dav/aaua/2005/00000091/00000004/art00006). 

An efficient hybrid model is presented for sound propagation in situations with several reflecting obstacles near the source. A Finite-Difference Time-Domain (FDTD) model is used in the complex source region, while a Parabolic Equation (PE) model is used for propagation to a distant receiver. The models are coupled by transformation of FDTD results at the boundary of the source region from the time domain to the frequency domain. The FDTD-PE model takes into account multiple reflections of sound waves in the source region, and interaction of sound waves with complex wind fields near the obstacles. It is shown that the FDTD-PE model is accurate, and requires considerably smaller computer times and memory than FDTD does.

## FDTD Method

**1.1. Linearized Euler Equations (LEEs)**

Set of 2 coupled equations to solve:

$$\begin{align}\tag{1}\label{eq1}
\begin{cases}
\left( \frac { \partial  }{ \partial t } +\underline { { v }_{ 0 } } .\nabla  \right) \underline { v } +\left( \underline { v } .\nabla  \right) \underline { { v }_{ 0 } } +\frac { \nabla p }{ { \rho  }_{ 0 } } =0\\
\left( \frac { \partial  }{ \partial t } +\underline { { v }_{ 0 } } .\nabla  \right) p+{ \rho  }_{ 0 }{ c }_{ 0 }^{ 2 }\nabla .\underline { v } =0
\end{cases}
\end{align}
$$

**1.2. Conservative form of the LEEs in 2D with source terms**
$$\tag{2}\label{eq2}\frac { \partial U }{ \partial t } +\frac { \partial E }{ \partial x } +\frac { \partial G }{ \partial z } +H=S$$

**1.3. Discretization in time and space**
- Set the initial conditions $$U\left( t=0 \right)$$
- Compute the spatial derivatives of the Eulerian fluxes to evaluate $$K\left( U \right)$$
- Advance the solution in time to obtain $$U\left( t=\Delta t \right)$$
- Repeat the previous steps until we obtain $$U\left( t= N \Delta t \right)$$

To solve the LEEs we need to choose a numerical differentiation method (Finite Differences) and a time-integration method (Runge-Kutta algorithms). We call these methods FDTD for “Finite-Difference Time-Domain”.

## PE Method

We use a 2D version of the FDTD model, based on the 2D Euler equations.

You can read the book “Computational atmospheric acoustics” of Salomons to know more details

## FDTD-PE Method
Coupling: the Finite-Difference Time-Domain (FDTD) method and the Parabolic Equation (PE) method.

