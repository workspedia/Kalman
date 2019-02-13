#### 1 Chapter Focus
##### (1) The Bigger Picture
schematic, Charts, (especially) schematic circuits;
The schematic shows the following three dynamic models.
- The one labeled “System Dynamics” models the real-world dynamics in the intended application of the Kalman filter. This model may contain state variables for representing time-correlated random processes .
- The one labeled “State Dynamics” in the Kalman filter should contain a fairly faithful replication of the true system dynamics, except that it does not know the values of the random inputs 𝑤 in the real-world model. 
- The one labeled “covariance dynamics,” is a dynamic model for the second moment (covariance matrix P) of estimation errors.   
##### (2) Models for Dynamic Systems
Differential Equations and State Variables Since their introduction by Isaac Newton and Gottfried Leibniz in the seventeenth century, differential equations have provided concise and faithful mathematical models for many dynamic systems of importance to humans.  
 > i.e. & e.g.
  > _i.e. is the abbreviation of __id est__ in Latin, meaning "that is to say, in other words", which is equivalent to that is / in other words, and is used to further explain the point made earlier. For example:I like citrus fruits, i.e., the juicy._
  > _e.g. is the abbreviation of Latin __exempli gratia__, which means "for example". It is equivalent to for example, for the sake of example, for example, as. The purpose of using e.g. is to illustrate the previous point with several examples. For example:I like citrus fruits, e.g., tangerines, lemons and limes._  
##### (3) Main Points to Be Covered
The objective in this chapter is to characterize the measurable outputs of dynamic systems as functions of the internal states and inputs of the system. The treatment here is deterministic, in order to define functional relationships between inputs and outputs. In Chapter 4, the inputs are allowed to be nondeterministic (i.e., random), and the focus of the Chapter 5 is on how to estimate the state variables of a dynamic system in this context.  
Dynamic Systems and Differential Equations.   
In the context of Kalman filtering, a dynamic system has come to be synonymous with a system of ordinary differential equations describing the evolution over time of the state of a physical system.  
#### 2 Deterministic Dynamic System Models   
##### (1) Dynamic Systems Modeled by Differential Equations  
A system is an assemblage of interrelated entities that can be considered as a whole.  If the attributes of interest of a system are changing with time, then it is called a dynamic system.  A process is the evolution over time of a dynamic system. From the time of Newton, engineers and scientists have learned to define dynamic systems in terms of the differential equations that govern their behavior.  They have also learned how to solve many of these differential equations to obtain formulas for predicting the future behavior of dynamic systems.  
Not all dynamic systems can be modeled by differential equations There are other types of dynamic system models, such as Petri nets, inference nets or tables of experimental data.  
one can reduce the form of any system of higher order differential equations to an equivalent system of first-order differential equations.
In that sense, the initial value of each
state variable represents an independent degree of freedom of the dynamic system.  
#### 3 Continuous Linear Dynamic Systems And Their Solutions  
##### (1) Input–Output Models of Linear Dynamic Systems  
##### (2) Dynamic Coefficient Matrices and Input Coupling Matrices  
̇ẋ (t) = F(t)x(t) + C(t)u(t), The matrix F(t) is called the dynamic coefficient matrix, or simply the dynamic matrix. Its elements are called the dynamic coefficients. The matrix C(t) is called the input coupling matrix, and its elements are called input coupling coefficients. The r-vector u is called the input vector.
##### (3) Companion Form for Higher Order Derivatives  
In general, the nth-order linear differential equation can be rewritten as a system of n first-order differential equations. 
Although the state variable representation as a first-order system is not unique, there is a unique way of representing it called the companion form.   
##### (4) Outputs and Measurement Sensitivity Matrices
Measurable Outputs and Measurement Sensitivities Only the inputs and outputs of the system can be measured, and it is usual practice to consider the variables zi as the measured values. For linear problems, they are related to the state variables and the inputs by a system of linear equations that can be represented in vector form as z(t) = H(t)x(t) + D(t)u(t),
The 𝓁-vector z(t) is called the measurement vector or the output vector of the system.
The coefficient hij(t) represents the sensitivity (measurement sensor scale factor) of the ith measured output to the jth internal state. 
The matrix H(t) of these values is called the measurement sensitivity matrix, and D(t) is called the input–output coupling matrix. The measurement sensitivities hij(t) and input/output coupling coefficients dij(t), 1 ≤ i ≤ 𝓁, 1 ≤ j ≤ r, are known functions of time. 
The state equation 2.13 and the output equation 2.17 together form the dynamic equations of the system shown in Table 2.1.
##### (5) Difference Equations and State-Transition Matrices (STMs)
Difference equations are the discrete-time versions of differential equations. They are usually written in terms of forward differences x(tk+1) − x(tk) of the state variable (the dependent variable), expressed as a function 𝜓 of all independent variables or of the forward value x(tk+1) as a function 𝜙 of all independent variables (including the previous value as an independent variable):For linear dynamic systems, the functional dependence of x(tk+1) on x(tk) and u(tk) can be represented by matrices: where the matrices Ψ and Φ replace the functions 𝜓 and 𝜙, respectively. The matrix Φ is called the state-transition matrix (STM). The matrix C is called the discrete-time input coupling matrix or simply the input coupling matrix—if the discrete-time context is already established.
##### (6) Solving Differential Equations for STMs  
Fundamental Solutions of Homogeneous Equations An n × n matrix-valued function Φ(t) is called a fundamental solution of the homogeneous
equation ẋ (t) = F(t)x(t) on the interval t ∈ [0, T] if Φ(̇ t) = F(t)Φ(t) and Φ(0) = In, the n × n identity matrix. Note that for any possible initial vector x(0), the vector x(t) = Φ(t)x(0) satisfies the equation That is, x(t) = Φ(t)x(0) is the solution of the homogeneous equation ẋ = Fx with initial value x(0).
##### (7) Solution of Nonhomogeneous Equations  
##### (8) Closed-Form Solutions of Time-Invariant Systems  
##### (9) Time-Varying Systems
#### 4 Discrete Linear System And Their Solutions  
##### (1) Discretized Linear Systems  
##### (2) Discrete-Time Solution for Time-Invariant Systems  
#### 5 Observability of Linear Dynamic System Models  
#### 6 Summary
