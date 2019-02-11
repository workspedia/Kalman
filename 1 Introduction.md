#### 1 On Kalman Filtering
##### (1) First of All: What Is a Kalman Filter?
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

##### (2) How It Came to Be Called a Filter  
It might seem strange that the term filter would apply to an estimator.  
- More commonly, a filter is a physical __device__ for __removing unwanted fractions of mixtures__.  
- In the era of crystal radios and vacuum tubes, the term was applied to analog circuits that __“filter” electronic signals__.
- This concept was extended in the 1930s and 1940s to the __separation of “signals” from “noise__,” both of which were characterized by their __power spectral densities__.
  > _Kolmogorov and Wiener used this statistical characterization of their probability distributions in forming an optimal estimate of the signal, given the sum of the signal and noise_.
- With Kalman filtering, the term assumed a meaning that is well beyond the original idea of separation of the components of a mixture. 
  > _It has also come to include the solution of an inversion problem, in which one knows how to represent the measurable variables as functions of the variables of principal interest._  
  > _In essence, it inverts this functional relationship and estimates the independent variables as inverted functions of the dependent (measurable) variables._  
  > _These variables of interest are also allowed to be dynamic, with dynamics that are only partially predictable._
  
##### (3) Its Mathematical Foundations
![Foundational concepts in Kalman filtering](https://github.com/workspedia/Kalman/blob/master/Foundational%20concepts%20in%20Kalman%20filtering.PNG)
##### (4) What It Is Used for
The applications of Kalman filtering encompass many fields, but its use as a tool is almost exclusively for two purposes:   
__estimation__ and __performance analysis__ of estimators.  
- Estimating the State of Dynamic Systems.
  > _Nearly all physical systems are dynamic to some degree._
  > _If one wants very precise estimates of their characteristics over time, then one has to take their dynamics into consideration._
  > _The problem is that one does not always know their dynamics very precisely either. _
  > _Given this state of partial ignorance, the best one can do is expressing our ignorance more precisely—using probabilities._ 
  > _The Kalman filter allows us to estimate the state of dynamic systems with certain types of random behavior by using such statistical information. 
| Application      | Dynamic System | Sensor Types   |  
|      -----       |     ------     |     ------     |  
| Process control  | Chemical plant | Pressure       |
|                  |                | Gas analyzer   |
| Flood prediction | River system   | Water level    |
|                  |                | Weather radar  |
| Tracking         | Spacecraft     | Radar          |
|                  |                | Imaging system |
| Navigation       | Ship           | Sextant        |
|                  |                | Accelerometer  |
|                  |                | GNSSa receiver |

The Global Positioning System (GPS),   
  > _a satellite-based radionavigation system owned by the __United States__ government and operated by the United States Air Force._  
  
A satellite navigation system with global coverage may be termed a global navigation satellite system (GNSS).   
  > _As of October 2018, the United States' Global Positioning System (GPS) and Russia's GLONASS are fully operational GNSSs, with China's BeiDou Navigation Satellite System (BDS) and the European Union's Galileo scheduled to be fully operational by 2020._
- Performance Analysis of Estimation Systems.
The Kalman filter uses a parametric characterization of the probability distribution of its estimation errors in determining the optimal filtering gains, and these parameters may be used in assessing its performance as a function of the “design parameters” of an estimation system, such as
#### 2 On Optimal Estimation Methods
##### (1) Beginnings of Optimal Estimation Theory
The first method for forming an optimal estimate from noisy data is the method of __least squares__. 
The __inevitability of measurement errors__ had been recognized since the time of Galileo.
It was the first optimal estimation method, and it provided an important connection between the experimental and theoretical sciences: _it gave experimentalists a practical method for estimating the unknown parameters of theoretical models_.
##### (2) Method of Least Squares
Gauss discovered that if he wrote a system of equations in matrix form, as  
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{300}&space;\tiny&space;Hx&space;=&space;z" target="_blank"><img src="https://latex.codecogs.com/png.latex?\dpi{300}&space;\tiny&space;Hx&space;=&space;z" title="\tiny Hx = z" /></a>

then he could consider the problem of solving for that value of an estimate x̂ (pronounced
“x-hat”) that minimizes the “estimated measurement error” Hx̂ − z. He could
characterize that estimation error in terms of its Euclidean vector norm |Hx̂ − z|, or,
equivalently, its square:
