#### 1 Chapter Focus
##### (1) Estimation Problem
This is the problem of estimating the state of a linear stochastic system by using measurements that are linear functions of the state.  The measurement and plant noise 𝑣k and 𝑤k are assumed to be zero-mean random processes, and the initial value x0 is a variate with known mean x0 and known covariance matrix P0. 
The objective will be to find an estimate of the n state vector xk represented by __x̂k, a linear function of the measurements zi, … ,zk,__ that minimizes the weighted mean-squared error.
##### (2) Main Points to Be Covered
- Linear Least-Mean-Squared Estimation Problem 
  > We are now prepared to derive the mathematical forms of optimal linear estimators for the states of linear stochastic systems defined in the previous chapters. This is called the linear quadratic (LQ) estimation problem. The dynamic systems are linear and the performance cost functions are quadratic (least-mean-squared estimation error).  
- Filtering, Prediction, and Smoothing 
There are three general types of estimators for the LQ problem:
  - Predictors use observations strictly prior to the time that the state of the dynamic system is to be estimated:  
  - Filters use observations up to and including the time that the state of the dynamic system is to be estimated:
  - Smoothers use observations beyond the time that the state of the dynamic system is to be estimated.  
- Kalman gain 
  - A straightforward and simple approach using the orthogonality principle is used in the derivation of estimators. 
  - These estimators will have minimum variance and be unbiased and consistent.
  - Two easier derivations of the Kalman gain formula are also provided, one starting with the Gaussian maximum-likelihood (ML) estimator and the other starting with the linear least-mean-square (LMS) estimator.
- Unbiased Estimators 
  - The Kalman filter can be characterized as an algorithm for computing the conditional mean and covariance of the probability distribution of the state of a linear stochastic system with uncorrelated random process and measurement noise. 
  - The conditional mean is the unique unbiased estimate.
  - It is propagated in feedback form by a system of linear differential equations or by the corresponding discrete-time equations. 
  - The conditional covariance is propagated by a nonlinear differential equation or its discrete-time equivalent. 
  - This implementation automatically minimizes the expected risk associated with any quadratic loss function of the estimation error.
- Performance Properties of Optimal Estimators  
#### 2 Kalman Filter  
##### (1) Observational Update Problem for System State Estimator  
##### (2) Estimator in Linear Form  
The optimal linear estimate is equivalent to the general (nonlinear) optimal estimator if the variates x and z are jointly Gaussian.  
Therefore, it suffices to seek an updated estimate x̂k(+)—based on the observation zk—that is a linear function of the a priori estimate and the measurement z.x̂k(+) = K1k x̂k(−) + Kkzk, (5.7)where x̂k(−) is the a priori estimate of xk and x̂k(+) is the a posteriori value of the estimate.  
##### (3) Solving for the Kalman Gain  
##### (4) Kalman Gain from Gaussian Maximum Likelihood  
##### (5) Kalman Gain from Recursive Linear LMS Estimator
This is another low stress derivation of the Kalman gain, starting from the linear LMS estimator in recursive form. It makes fewer assumptions than the derivation from Gaussian ML estimation and uses just a bit of matrix arithmetic.  
##### (6) Summary of Equations for the Discrete-Time Kalman Estimator  
#### 3 Kalman–Bucy Filter  
#### 4 Optimal Linear Predictors  

#### 6 Relation between  Kalman Filter and Wiener Filter

