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
_In the meantime, the method of least squares had been discovered independently and published by Andrien-Marie in France and Robert Adrian in the United States. Such Jungian synchronicity (i.e., the phenomenon of multiple, near-simultaneous discovery) was to be repeated for other breakthroughs in estimation theory, as well—for the Wiener–Kolmogorov filter and the Kalman filter._  
##### (2) Method of Least Squares
Gauss discovered that if he wrote a system of equations in matrix form, as  Hx = z , then he could consider the problem of solving for that value of an estimate x̂ (pronounced “x-hat”) that minimizes the “estimated measurement error” Hx̂ − z. 
He could characterize that estimation error in terms of its Euclidean vector norm |Hx̂ − z|, or, equivalently, its square.
Consequently, it will achieve its minimum value where all its derivatives with respect to the x̂k are zero.  
For the examples considered above, observability does not depend upon the measurable data (z). It depends only on the nonsingularity of the Gramian matrix, which depends only on the linear constraint matrix (H) between the unknowns and knowns.  
Observability of a set of unknown variables is the issue of whether or not their values are uniquely determinable from a given set of constraints, expressed as equations involving functions of the unknown variables.   
##### (3) Mathematical Modeling of Uncertainty
Probabilities represent the state of knowledge about physical phenomena by providing something more useful than “I don’t know” to questions involving uncertainty.
- The Italian Cardano performed an accurate analysis of probabilities for games involving dice. He assumed that successive tosses of the dice were statistically independent events. 
  > Cardano stated without proof that the accuracies of empirical statistics tend to improve with the number of trials. This would later be formalized as a Law of Large Numbers.
- More general treatments of probabilities were developed by Blaise Pascal, Pierre de Fermat , and Christiaan Huygens.
  - Fermat’s work on combinations was taken up by Bernoulli, who is considered by some historians to be the founder of probability theory. He gave the first rigorous proof of the Law of Large Numbers for repeated independent trials (now called Bernoulli trials). 
  - Bayes derived his famous rule for statistical inference sometime after Bernoulli.
- Abraham de Moivre, Laplace, and Gauss continued this development into the nineteenth century.
  - The idea that the laws of nature embrace random phenomena and that these are treatable by probabilistic models began to emerge in the nineteenth century. The development and application of probabilistic models for the physical world expanded rapidly in that period.
  - The work of James Clerk Maxwell (1831–1879) in statistical mechanics established the probabilistic treatment of natural phenomena as a scientific (and successful) discipline.  
  - Andrei Andreyevich Markov (1856–1922) would develop much of the theory of what is today called a Markov process (in continuous time) or Markov chain (in discrete time), a random process with the property that the evolution over time of its probability distribution can be treated as an initial-value problem. 
    - That is, the instantaneous variation with time of the probability distribution of possible states of the process is determined by the current distribution, which includes the effects of all past history of the process.  
- An important figure in probability theory and the theory of random processes in the twentieth century was the Russian academician Andrei Nikolayevich Kolmogorov (1903–1987). 
  - Starting around 1925, working with Aleksandr Yakovlevich Khinchin and others, he reestablished the foundations of probability theory on measure theory, which had originated as the basis for integration theory and became the accepted mathematical basis of probability and random processes. 
  - Along with Norbert Wiener, he is credited with founding much of the theory of prediction, smoothing and filtering of Markov processes, and the general theory of ergodic processes. 
  - His theory was the first formal theory of optimal estimation for systems involving random processes.
##### (4) The Wiener–Kolmogorov Filter
In the popular scientific press, Wiener is probably more famous for naming and promoting cybernetics than for developing the Wiener–Kolmogorov filter.
Some of his greatest mathematical achievements were in generalized harmonic analysis, in which he extended the Fourier transform to functions of finite power. 
Previous results were restricted to functions of finite energy, which is an unreasonable constraint for signals on the real line. 
Another of his many achievements involving the generalized Fourier transform was proving that the transform of white noise is also white noise.
In his derivation of an optimal estimator, Wiener would use probability measures on function spaces to represent uncertain dynamics. 
He derived the solution for the least-mean-squared prediction error in terms of the autocorrelation functions of the signal and the noise. 
The solution is in the form of an integral operator that can be synthesized with analog circuits, given certain constraints on the regularity of the autocorrelation functions or, equivalently, their Fourier transforms.
##### (5) The Kalman Filter
- Discovery
  - In 1958, Why not apply the notion of state variables to the Wiener–Kolmogorov filtering problem. The Kalman filter is the culmination of a progression of models and associated optimal estimation methods for dynamic processes.
  - Wiener–Kolmogorov models use the PSD in the frequency domain to characterize the dynamic and statistical properties of a dynamic process. Optimal Wiener–Kolmogorov estimators are derivable from the PSD, which can be estimated from measured system outputs. This assumes the dynamic process model is time invariant.
  - Control theorists use linear differential equations as dynamic system models.This led to the development of mixed models, in which the dynamic system functions as a “shaping filter” excited by white noise. Coefficients of the linear differential equations determine the shape of the output PSD, and the shape of the PSD defines the Wiener–Kolmogorov estimator. This approach allows the dynamic system model to be time varying. These linear differential equations can be modeled as a system of first-order differential equations in what has come to be called state space.
   -The next step in this progression would be to develop the equivalent estimation methods right from a time-varying state space model—and that is what Kalman did.One of the more remarkable achievements of Kalman and Bucy in that period was proving that the Riccati equation can have a stable (steady-state) solution even if the dynamic system is unstable provided that the system is observable and controllable.With the additional assumption of finite dimensionality, Kalman was able to derive the Wiener–Kolmogorov filter as what we now call the Kalman filter. 
The Kalman filter solved the data fusion problem associated with combining radar data with inertial sensor data to arrive at an overall estimate of the aircraft trajectory and the data rejection problem associated with detecting exogenous errors in measurement data. It has been an integral part of nearly every onboard trajectory estimation and control system designed since that time.
  - Impact of Kalman Filtering on Technology From the standpoint of those involved in estimation and control problems, at least, this has to be considered the greatest achievement in estimation theory of the twentieth century. The principal uses of Kalman filtering have been in “modern” control systems, in the tracking and navigation of all sorts of vehicles, and in predictive design of estimation and control systems. These technical activities were made possible by the introduction of the Kalman filter.  
######  Relative Advantages of Kalman and Wiener–Kolmogorov Filtering
1. The Wiener–Kolmogorov filter implementation in analog electronics can operate at much higher effective throughput than the (digital) Kalman filter.

2. The Kalman filter is implementable in the form of an algorithm for a digital computer, which was replacing analog circuitry for estimation and control at the time when the Kalman filter was introduced. This implementation may be slower, but it is capable of much greater accuracy than had been achievable with analog filters.

3. The Wiener–Kolmogorov filter does not require finite dimensional stochastic process models for the signal and noise.

4. The Kalman filter does not require that the deterministic dynamics or the random processes have stationary properties, and many applications of importance include nonstationary stochastic processes.

5. The Kalman filter is compatible with the state-space formulation of optimal controllers for dynamic systems, and Kalman was able to prove useful dual properties of estimation and control for these systems.

6. For the modern controls engineering student, the Kalman filter requires less additional mathematical preparation to learn and use than the Wiener–Kolmogorov filter. As a result, the Kalman filter can be taught at the undergraduate level in engineering curricula.

7. The Kalman filter provides the necessary information for mathematically sound, statistically based decision methods for detecting and rejecting anomalous measurements
##### (6) Implementation Methods
##### (7) Nonlinear Approximations
Those experienced with Kalman filtering often find themselves morphing problems to resemble the Kalman filtering model.

This is especially so with nonlinear problems, for which there is no practical and mathematically correct approach comparable to the Kalman filter. 

Although it was originally derived for linear problems, the Kalman filter is habitually applied to nonlinear problems by using various approximation methods. This approach has worked remarkably well for a number of nonlinear problems, but there will always be limits to how far it can be pushed.

We mention here some approaches that have been used to extend the applicability of Kalman filtering methodologies to nonlinearly problems. 


###### Extended Kalman Filtering (EKF) for Quasilinear Problems 
EKF was used in the very first application of Kalman filtering: the space navigation problem for the Apollo missions to the moon and back. 
_The name refers to the Monaco Monte Carlo gambling casino, which uses pseudorandom methods to transform the distribution of wealth among its players._
##### (8) Truly Nonlinear Estimation
Problems involving nonlinear and random dynamic systems have been studied for some time in statistical mechanics.   
##### (9) The Detection Problem for Surveillance
Surveillance problems include the detection, identification, and tracking of objects within a certain region of space. 
However, the detection problem must usually be solved before identification and tracking can begin. The Kalman filter requires an initial state estimate for each object, and that initial estimate must be obtained by detecting it. 
Those initial states are distributed according to some “point process,” but there are no technically mature methods (comparable to the Kalman filter) for estimating the state of a point process.
#### 4 Common Notation
> _The fundamental problem of symbolic notation, in almost any context, is that there are never enough symbols to go around. There are not enough letters in the Roman alphabet to represent the basic phonetic elements of standard spoken English, let alone all the variables in Kalman filtering and its applications. As a result, some symbols must play multiple roles. In such cases, their roles will be defined as they are introduced. It is sometimes confusing but unavoidable._  
##### (1) “Dot” Notation for Derivatives
Newton’s notation using ̇f(t), ̈f(t) for the first two derivatives of f with respect to t is used where convenient to save ink.
##### (2) Standard Symbols for Kalman Filter Variables
There appear to be two “standard” conventions in technical publications for the symbols used in Kalman filtering. 
- The one used in this book is similar to the original notation of Kalman. 
- The other standard notation is sometimes associated with applications of Kalman filtering in control theory.
- The state vector wears a “hat” as the estimated value, x̂, and subscripting to denote the sequence of values that the estimate assumes over time. The problem is that it has two values at the same time: the a prior value (before the measurement at the current time has been used in refining the estimate) and the a posteriori value (after the current measurement has been used in refining the estimate). These distinctions are indicated by the signum.  The negative sign (−) indicates the a priori value, and the positive sign (+) indicates the a posteriori value. 
##### (3) Common Notation for Array Dimensions  
#### Summary
The Kalman filter is an estimator used to estimate the state of a linear dynamic system perturbed by white noise using measurements that are linear functions of the system state but corrupted by additive white noise. 

The Kalman filter was derived as the solution to the Wiener filtering problem using the state-space model for dynamic and random processes. 

The result is easier to derive (and to use) than the Wiener–Kolmogorov filter. 

Square-root filtering is a reformulation of the Kalman filter for better numerical stability in finite-precision arithmetic. 

Sequential Monte Carlo methods and particle filtering can be used to extend Kalman filtering beyond the quasilinear estimation problems that are solvable by extended Kalman filtering.

The Unscented Kalman Filter has about the same computational complexity as the extended Kalman filter and essentially the same numerical stability as square-root filtering but with potentially greater robustness against nonlinear effects.


