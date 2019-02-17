#### 5 Unscented Kalman Filters (UKF) (Jeffrey Uhlmann)
##### (0) Abstract
- In the EKF, the state distribution is approximated by a GRV, which is then propagated analytically through the first-order linearization of the nonlinear system. This can introduce large errors in the true posterior mean and covariance of the transformed GRV, which may lead to sub-optimal performance and sometimes divergence of the filter. 
- The UKF addresses this problem by using a deterministic sampling approach. The state distribution is again approximated by a GRV, but is now represented using a minimalset of carefully chosen sample points. These sample points completely capture the true mean and covariance of the GRV, and when propagated through the true nonlinear system, captures the posterior mean and covariance accurately to the 3rd order (Taylor series expansion) for any nonlinearity.  
##### (1) Introduction  
The EKF has been applied extensively to the field of nonlinear estimation. General application areas may be divided into state-estimation and machine learning.  


