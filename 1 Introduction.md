#### 1 On Kalman Filtering
##### 1 First of All: What Is a Kalman Filter?
It has been called 
  - the linear least mean squares estimator (LLSME) 
    - because it minimizes the mean-squared estimation error for a linear stochastic system using noisy linear sensors
  - linear quadratic estimator(LQE)  
    - because it minimizes a quadratic function of estimation error for a linear dynamic system with white measurement and disturbance noise.

It is the only practical finite-dimensional solution to the __real-time optimal estimation problem for stochastic systems__,  
and it makes very few assumptions about the underlying probability distributions except that they have finite means and second central moments (covariances).

It is not always possible or desirable to measure every variable that you want to control, and the Kalman filter
provides the mathematical framework for __inferring__ the unmeasured variables from indirect and noisy measurements.

The Kalman filter is also used for __predicting__ the likely future courses of dynamic systems that people are not likely to control,   
such as the flow of rivers during flood, the trajectories of celestial bodies, or the prices of traded commodities and securities. 

It is not a physical tool, but a mathematical one.  
_1. It is only a mathematical tool. It is important to understand its use and function._  
_2. It is a computer program._
_3. It is a consistent statistical characterization of an estimation problem._

#### 2 How It Came to Be Called a Filter  
It might seem strange that the term filter would apply to an estimator.  
- More commonly, a filter is a physical __device__ for __removing unwanted fractions of mixtures__.  
- In the era of crystal radios and vacuum tubes, the term was applied to analog circuits that __“filter” electronic signals__.
- This concept was extended in the 1930s and 1940s to the __separation of “signals” from “noise__,” both of which were characterized by their __power spectral densities__.
  > _Kolmogorov and Wiener used this statistical characterization of their probability distributions in forming an optimal estimate of the signal, given the sum of the signal and noise_.
- With Kalman filtering, the term assumed a meaning that is well beyond the original idea of separation of the components of a mixture. 
  > _It has also come to include the solution of an inversion problem, in which one knows how to represent the measurable variables as functions of the variables of principal interest._  
  > _In essence, it inverts this functional relationship and estimates the independent variables as inverted functions of the dependent (measurable) variables._  
  > _These variables of interest are also allowed to be dynamic, with dynamics that are only partially predictable._
  
#### 3 Its Mathematical Foundations
