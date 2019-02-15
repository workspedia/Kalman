#### 1 Chapter Focus  
- In this chapter, some of the basic notions and mathematical models of statistical and deterministic mechanics are combined into a stochastic system model, which represents the evolution over time of key statistical parameters in systems with uncertain dynamics.
- These stochastic system models are used to define random processes (RPs) in continuous time and in discrete time (also called random sequences). 
- They represent the state of knowledge about a dynamic system—including its state of uncertainty. 
- They represent what we know about a dynamic system, including a quantitative model for what we do not know.
#### 2 Random Variables, Processes, And Sequences  
##### (1) Historical Background
- Random Processes 
  > An early impetus for the development of a mathematical theory of stochastic systems was the 1828 publication of “A brief account of microscopical observations made on the particles contained in the pollen of plants and on the general existence of active molecules in organic and inorganic bodies” by the British botanist Robert Brown. This phenomenon came to be called Brownian movement or Brownian motion. 
  > Mathematical models for RPs were derived in terms of what has come to be called stochastic differential equations. French scientist Paul Langevin1 (1872–1946) modeled the velocity 𝑣 of a particle in Brownian motion in terms of a differential equation of the form     d𝑣/dt = −𝛽𝑣 + a(t), where 𝑣 is the velocity of a particle, 𝛽 is a damping coefficient (due to the viscosity of the suspending medium), and a(t) is called a random force. The accelerations applied could be ascribed to van der Waals forces, which are sufficiently smooth that the velocity changes would not be instantaneous.
  > However, the random forcing function a(t) of the Langevin equation  has been idealized in three ways from the physically motivated example of Brownian motion. This new process model for a(t) transcends the ordinary  calculus, because the resulting “white-noise” process a(t) is not integrable in the ordinary calculus.
  > At about the time that the Kalman filter was introduced, however, a special calculus was developed (stochastic calculus) for this model.
  > Another mathematical characterization of white noise was provided by Norbert Weiner, using his generalized harmonic analysis. Wiener preferred to focus on the mathematical properties of 𝑣(t)  with 𝛽 = 0, a process now called a Wiener process.  
##### (2) Definitions
For the purposes of this book, the values of RVs will almost always be n-dimensional real vectors.An RP assigns a RV X(t) to every time t on some interval. A random sequence (RS) assigns a RV Xk to every integer k in some range of integers. A random sequence may also be denoted by curly brackets as {xk}, in which case the lowercase letter might be used.In Kalman filtering, the statistical properties of interest for RPs and sequences include how their statistics and joint statistics are related across time or between components of vectors. 
#### 3 Statistical Properties
##### (1) Independent Identically Distributed (i.i.d.) Processes
For identically distributed (i.d.) processes and sequences, the RV distribution is identical for all values of time (t) or index (k). their joint probability density is equal to the product of their individual probability densities.Discrete and continuous i.i.d. processes play a significant role in Kalman filtering.  
##### (2) Process Means
For non-i.d. processes and sequences, the mean 𝜇x of an RP X(t) or random sequence {Xk} may be a function of time. For n-vector-valued RPs or RSs, the means are defined by the individual expected value taken at each time (continuous or discrete) respectively.  
##### (3) Time Correlation and Covariance  
The time correlation of the n-vector-valued process X(t) between any two times t1 and t2 is defined as the n × n matrix. 
##### (4) Uncorrelated and Orthogonal Random Processes 
A random process X(t) is called uncorrelated if its time covariance.
The processes X(t) and Y(t) are called orthogonal if their correlation matrix is identically zero.
##### (5) Strict-Sense and Wide-Sense Stationarity
##### (6) Ergodic Random Processes  
Following Maxwell’s hypothesis, an RP is considered ergodic if all of its statistical parameters (mean, variance, and so on) can be determined from arbitrarily chosen member functions. A sampled function X(t) is ergodic if its time-averaged statistics equal its ensemble averages.
##### (7) Markov Processes and Sequences  
An RP X(t) is called a Markov process if its future state distribution, conditioned on knowledge of its present state, is not improved by knowledge of previous states.
##### (8) Gaussian Random Processes  
##### (9) Simulating Multivariate Gaussian Processes  
##### (10) Power Spectral Densities  
#### 4 Linear Random Process Models  
##### (1) Stochastic Differential Equations for RPs
Differential equations involving RPs are called stochastic differential equations. Introducing RPs as inhomogeneous terms in ordinary differential equations has ramifications beyond the level of rigor that will be followed here, and the reader should be aware of them. 
The problem is that RPs are not integrable functions in the conventional (Riemann) calculus. The resolution of this problem requires foundational modifications of the calculus to obtain many of the results presented. The Riemann integral of the “ordinary” calculus must be modified to what is called the Itô calculus.  
Linear Stochastic Differential Equations A linear stochastic differential
equation as a model of an RP with initial conditions has the general form
ẋ (t) = F(t)x(t) + G(t)𝑤(t) + C(t)u(t), (4.63)
z(t) = H(t)x(t) + 𝑣(t) + D(t)u(t), (4.64)
where the variables are defined as
x(t) is an n × 1 state vector,
z(t) is an l × 1 measurement vector,
u(t) is an r × 1 deterministic input vector,
F(t) is an n × n time-varying dynamic coefficient matrix,
C(t) is an n × r time-varying input coupling matrix,
H(t) is an l × n time-varying measurement sensitivity matrix,
D(t) is an l × r time-varying output coupling matrix,
G(t) is an n × r time-varying process noise coupling matrix,
𝑤(t) is an r × 1 zero-mean uncorrelated “plant noise” process,
𝑣(t) is an l × 1 zero-mean uncorrelated “measurement noise” process  
##### (2) Discrete-Time Models for Random Sequences (RS)
RPs in discrete time are also called random sequences. A vector-valued discrete-time recursive equation for modeling an RS with initial conditions can be given in the form  
##### (3) Autoregressive Processes and Linear Predictive Models  
#### 5 Shaping Filters And State Augmentation
The focus of this section is on the use of shaping filters to model nonwhite-noise models for stationary RPs, using white-noise processes as inputs. It can be useful to generate an autocorrelation function or PSD from real data and then develop an appropriate noise model using differential or difference equations.  
##### (1) Correlated Process Noise Models  
##### (2) Correlated Measurement Noise Models  
#### 7 Relationships Between Model Parameters  
#### 8 Orthogonality Principle  

#### 6 Mean And Covariance Propagation  

