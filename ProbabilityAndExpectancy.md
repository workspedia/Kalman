_Chance, too, which seems to rush along with slack reins, is bridled and governed by law._ 
_Anicius Manlius Severinus Boëthius1 (∼480–525 CE)_  
1 Chapter Focus
There are useful properties of certain statistical parameters of probability distributions that are the same for all probability distributions. One does not need to assume that the probability distribution is Gaussian or any other specific distribution. These properties are very useful in Kalman filtering, and this is the essential focus of this chapter.
Probability Density Functions.   
It makes all this  a bit more transparent if we identify probability distributions on real n-dimensional spaces in terms of their probability density functions and then use the ordinary calculus to demonstrate the essential properties of the resulting expectancy operators.
Expectancy, Moments, and Optimal Estimates. 
The key operator needed for developing the essential formulas is what is called the expectancy operator, which turns out to be a linear functional—a very powerful mathematical tool for our purposes. It is used for defining the moments of probability distributions, and the first and second moments of probability distributions on n dimensional real space ℜn can be identified with the essential variables used in Kalman filtering.These formulas lead directly to the identification of the estimator with the least-mean-squared error—independent of the specific probability distribution involved. This unshackles least-mean-squared estimation from dependency on any particular error probability distribution.  
#### 2 Foundations Of Probability Theory  
Probabilities are a way of quantifying uncertainty. Probability theory is about mathematical models for doing just that.  
##### (1) Measure Theory
Probability theory changed in the early twentieth century with the development of measure theory as part of the foundations of the integral calculus. Measures are nonnegative functions defined on the so-called sigma algebras of “measurable sets” in the domain of a potentially integrable function.   
##### (2) Probability Measures
The distinguishing feature of probability measures is that the probability measure of the union of all measurable sets is always equal to 1. There is not much difference between the mathematical properties of probability measures and ordinary measures, other than the fact that probability integrals of the entire domain must equal 1.  
##### (3) Probability Distributions
- Probability Spaces
- Random Variables (RV). 
  > The alternative terms variate, random variable (RV), or stochastic variable are used to denote possible outcomes of a draw from a probability distribution, such as drawing numbered balls in a lottery. These terms do not denote a specific outcome, but the ensemble of possible outcomes and their associated probabilities. 
- Realizations of Variates. 
  > A specific point x ∈ S would be called a realization of a variate, random variable, stochastic variable, or outcome.
- Notation. We will observe the common practice of using an uppercase letter to designate a variate X, representing the ensemble of values that might be drawn from a probability distribution and to use the corresponding lowercase letter x to denote a realization of that draw. The notation x ∈ X would then indicate that x is a realization of the variate X.  
##### (4) Probability Density Functions
Gaussian Cumulative Probability Function  
#### 3 Expectancy
##### (1) Linear Functionals
Linear functionals are powerful devices in mathematical analysis, and one of them—the expectancy operator—is especially useful in estimation theory.  
##### (2) Expectancy Operators  
##### (3) Moments of Distributions  
- Means 
  > If it does exists, the first-order moment of the n-dimensional variate X of a multivariate probability distribution will be a vector of the same dimension, called the mean of the distribution of X.
- Central Moments
- Covariance Matrices
- Moments of Order N > 2
- Cross-Covariance
- Correlation Coefficients
- Statistical Independence and Correlation  
#### 4 Least-Mean-Square Estimate(LMSE)
The word estimate comes from the Latin verb aestimare, meaning “to place a value on (something).” 
In the present context, that “value” will be a real number or real vector and the “something” will be a probability distribution defined over an n-dimensional real space by its mean and covariance.  
Among the more profound discoveries in probability theory are the facts that
- The mean of a probability distribution defined on ℜn is also the estimated value that achieves the least-mean-squared estimation error.
- The trace (sum of diagonal elements) of the associated covariance matrix equals that least (or minimum) mean-squared estimation error. 
##### (1) Squared Estimation Error
- An estimate has also been called an educated guess. 
- Before an archer releases an arrow aimed at a target, her or his best estimate of where it will end up is in the center of the target—or as close thereto as possible.The associated “estimation error” in this case is the miss distance, which is the square root of the sum of the squares of the arrow’s horizontal and vertical displacements from the exact center of the target. Minimizing the miss distance in this case is equivalent to minimizing the sum of the squares of the miss vector components. 
- In practice, the likelihood of making that error zero all the time is negligible, so the long-term goal of most archers is to minimize the expected squared miss distance.
- By using the expectancy operator, that same goal can be put in terms of probability distributions in a way that defines the optimal estimate x̂ of a value drawn from that probability distribution in terms that depend only on the first moment of the distribution, but not otherwise on the shape of the associated probability density function.  
##### (2) Minimization
Optimal estimates are defined by some optimality criterion. 
In the case that criterion is the expected (i.e., mean) squared estimation error, the optimal estimate is the one which minimizes the mean-square estimation error. In that case, it is called the minimum-mean-squared estimate (MMSE), or least-mean-squared estimate (LMSE).  
That is, the LMSE of x is the mean of the distribution—independent of the probability distribution involved.  
#### (3) Least-Mean-Squared Estimation Error
- The covariance of least-mean-squared estimation error is the second central moment of the probability distribution, also known as the covariance of the probability distribution. 
- That is, the mean 𝜇 and covariance Pxx of any probability distribution characterize the LMSE, in terms of its value and its mean-squared error.  
##### (4) Means and Covariances: Moments to Remember
Gamblers and actuaries are rightfully concerned about probability distributions, but distributions are not essential for least-mean-squares estimation. That is fortunate, because it is usually much easier and more efficient to estimate just the mean and covariance of a variate x.  
- Recursive Estimates of Means and Covariances The means and covariances of given data sequences {x[k] | k = 0, 1, 2, … } can be estimated recursively by the formulas.where 𝜇̂[k] is the kth recursive estimate of the mean and P̂xx[k] is the kth recursive estimate of the covariance, using the samples up to the kth element. To start the algorithm off, the value of 𝜇̂[0] can be initialized at x[0], and the value of P̂xx[0] can be initialized as the zero matrix.
##### (5) Alternative Measures of Miss Distance  
#### 5 Transformations Of Variates  
##### (1) Linear Transformations  
##### (2) Transformations by Analytic Functions  
##### (3) Transformation of Probability Density Functions  
#### 6 The Matrix Trace In Statistics
##### (1) Connecting Covariances and Mean-Squared Magnitudes  
If P is the covariance (second central moment) of n-vector variate X, then its trace the mean-squared magnitude of x − 𝜇x
##### (2) A Linear Functional  
##### (3) Matrix Product Commutation Under the Trace  
##### (4) Chi-Squared Test
##### (5) Schweppe Likelihood Ratio Detection  
##### (6) Multihypothesis Detection  
#### 7 Summary
