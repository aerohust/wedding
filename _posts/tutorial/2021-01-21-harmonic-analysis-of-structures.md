---
layout: post
title: "Harmonic Analysis of Structures"
subtitle: 
description: Ansys Mechanical
tags: [analysis, harmonic, structure]
img: harmonic-analysis-of-structure.gif
categories: tutorial
math: 1
---
{% include toc.html %}
This post is referred from Ansys document.

## Intro to Harmonic Analysis

Forced Frequency Response or Harmonic Analysis is an important branch of linear dynamics. Linear dynamics solves the equation of motion as a frequency domain problem instead of a time domain problem. 

**Why it is important**
- Most engineered structures will be vibration tested to verify the dynamic response.
- The design may need to avoid resonance with a known excitation.
- Understanding the magnitude of the vibration can prevent fatigue failure.
- This is an effective way to understand the significance of the different modes.
- Harmonic analysis can be used alongside physical testing (such as a shaker table with sine sweep) to correlate the models (natural frequencies and damping).

## Formulation of Harmonic Analysis

Harmonic analyses are used to determine the steady-state response of a structure to loads that vary sinusoidally (harmonically) with time.

Engineers use harmonic analysis to verify a design, providing insight such as:
- Will resonance occur, which could result in excessive motion, stress, noise and vibration?
- Will the cyclically repeating load result in repetitive stress, resulting in fatigue damage and potential failure?

#### Formulation
- Starting with the matrix form of the governing equations of motion, let’s explore a harmonic solution to this equation.
$$
\left [ M \right ]\left \{ \ddot{u} \right \} + \left [ C \right ]\left \{ \dot{u} \right \} + \left [ K \right ]\left \{ u \right \} = \left [ F \right ] \tag{1}\label{eq1}
$$
- The Forcing Function $$\left \{ F \right \}$$ and displacement $$\left \{ u \right \}$$ are of the form shown below. Recall that these can be visualized as sinusoids and simply given a value for time $$\left ( t \right )$$ and circular frequency $$\left ( \Omega \right )$$ we can compute the complex values of the force or displacement at each node, once we have of course solved for the unknown max values and phase shifts for each node in the model.
$$
\left \{ F \right \} = \left \{ F_{max}e^{i\psi} \right \}e^{i \Omega t} \tag{2}\label{eq2}
$$
$$
\left \{ u \right \} = \left \{ u_{max}e^{i\phi} \right \}e^{i \Omega t} \tag{3}\label{eq3}
$$