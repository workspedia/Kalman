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



