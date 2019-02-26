[wiki](https://en.wikipedia.org/wiki/Unscented_transform)
#### Unscented transform
The unscented transform (UT) is a mathematical function used to estimate the result of applying a given nonlinear transformation to a probability distribution that is characterized only in terms of a finite set of statistics.   
#### Background
- Many filtering and control methods represent _estimates of the state_ of a system in the form of a __mean vector__ and an __associated error covariance matrix__. 
  - As an example, the estimated 2-dimensional position of an object of interest might be represented by a _mean position vector_, [x,y], with an _uncertainty given in the form of a 2x2 covariance matrix_ giving the variance in x, the variance in y, and the cross covariance between the two. 
  - A covariance that is zero implies that there is no uncertainty or error and that the position of the object is exactly what is specified by the mean vector.  
- The mean and covariance representation only gives the first two moments of an underlying, but otherwise unknown, probability distribution. 
  - In the case of a moving object, the unknown probability distribution might represent the uncertainty of the object's position at a given time. 
  - The mean and covariance representation of uncertainty is mathematically convenient because any linear transformation {\displaystyle T} T can be applied to a mean vector m and covariance matrix M as Tm and TMT^. 
  - This linearity property does not hold for moments beyond the first raw moment (the mean) and the second central moment (the covariance), so _it is not generally possible to determine the mean and covariance resulting from a nonlinear transformation_ because the result depends on all the moments, and only the first two are given.  
- Although the covariance matrix is often treated as being the expected squared error associated with the mean, in practice the matrix is maintained as an upper bound on the actual squared error. Specifically, a mean and covariance estimate  (m,M) is conservatively maintained so that the covariance matrix  M is greater than or equal to the actual squared error associated with  m.Mathematically this means that the result of subtracting the expected squared error (which is not usually known) from M is a semi-definite or positive-definite matrix.   
  - The reason for maintaining a conservative covariance estimate is that most filtering and control algorithms will tend to diverge (fail) if the covariance is underestimated.  This is because a spuriously small covariance implies less uncertainty and leads the filter to place more weight (confidence) than is justified in the accuracy of the mean.  
- Returning to the example above, when the covariance is zero it is trivial to determine the location of the object after it moves according to an arbitrary nonlinear function f(x,y): just apply the function to the mean vector. When the covariance is not zero the transformed mean will not generally be equal to f(x,y) and it is not even possible to determine the mean of the transformed probability distribution from only its prior mean and covariance. 
  - Given this indeterminacy, the nonlinearly transformed mean and covariance can only be approximated. The earliest approximation was to linearize the nonlinear function and apply the resulting Jacobian matrix to the given mean and covariance. This is the basis of the extended Kalman Filter (EKF), and although it was known to yield poor results in many circumstances, there was no practical alternative for many decades.  
#### Motivation for the unscented transform
- Consider the following intuition: With a fixed number of parameters it should be easier to approximate a given distribution than it is to approximate an arbitrary nonlinear function/transformation.  
  - Following this intuition, the goal is to find a parameterization that captures the mean and covariance information while at the same time permitting the direct propagation of the information through an arbitrary set of nonlinear equations.  
  - This can be accomplished by generating a discrete distribution having the same first and second (and possibly higher) moments, where each point in the discrete approximation can be directly transformed. 
  - The mean and covariance of the transformed ensemble can then be computed as the estimate of the nonlinear transformation of the original distribution. 
  - More generally, the application of a given nonlinear transformation to a discrete distribution of points, computed so as to capture a set of known statistics of an unknown distribution, is referred to as an unscented transformation.  
- In other words, the given mean and covariance information can be exactly encoded in a set of points, referred to as sigma points, which if treated as elements of a discrete probability distribution has mean and covariance equal to the given mean and covariance. 
  - This distribution can be propagated exactly by applying the nonlinear function to each point. The mean and covariance of the transformed set of points then represents the desired transformed estimate. 
  - The principal advantage of the approach is that the nonlinear function is fully exploited, as opposed to the EKF which replaces it with a linear one. 

- Eliminating the need for linearization also provides advantages independent of any improvement in estimation quality. 
  - One immediate advantage is that the UT can be applied with any given function whereas linearization may not be possible for functions that are not differentiable. 
  - A practical advantage is that the UT can be easier to implement because it avoids the need to derive and implement a linearizing Jacobian matrix.  
#### Sigma points  
- To compute the unscented transform, one first has to choose a set of sigma points. 
  - In general, n+1 sigma points are necessary and sufficient to define a discrete distribution having a given mean and covariance in  n dimensions.
