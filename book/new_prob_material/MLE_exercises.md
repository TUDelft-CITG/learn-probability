# Exercises Maximum Likelihood Estimator

## Exercise 1

Find the MLE of $\theta$ based on $n$ independent observables $x_i$ with PDF
$$
f\left(x_i \mid \theta\right)=(1+\theta) x_i^\theta
$$

$\theta > 0$ and $0 < x_i < 1$.

### *Solution:*

First note that the PDF of the individual $x_i$ are given, these are independent, so the joint PDF (or likelihood function) of vector $x$ follows as:

$$
\begin{aligned}
L(\theta \mid \mathbf{x})=\prod_{i=1}^n f\left(x_i \mid \theta\right) & =\prod_{i=1}^n\left((1+\theta) x_i^\theta\right)=(1+\theta)^n \prod_{i=1}^n\left(x_i^\theta\right) \\
\ln (L(\theta \mid \mathbf{x})) & =n \ln (1+\theta)+\ln \left(\prod_{i=1}^n x_i^\theta\right) \\
& =n \ln (1+\theta)+\theta \sum_{i=1}^n \ln \left(x_i\right) \\
\frac{\partial \ln (L(\theta \mid \mathbf{x}))}{\partial \theta} & =\frac{n}{1+\theta}+\sum_{i=1}^n \ln \left(x_i\right)=0 \\
\hat{\theta} & =-\frac{n}{\sum_{i=1}^n \ln \left(x_i\right)}-1
\end{aligned}
$$

## Exercise 2

Find the MLE of $\theta$ based on $n$ independent observables $x_i$ with PDF

$$
f\left(x_i \mid \theta\right)=\sqrt{\frac{2}{\pi}} \theta^{-\frac{3}{2}} x_i^2 \exp -\frac{1 x_i^2}{2 \theta}
$$

$x_i > 0$ and $\theta > 0$.

### *Solution:*

First note that the PDF of the individual $x_i$ are given, these are independent, so the joint PDF (or likelihood function) of vector $x$ follows as:

$$
\begin{aligned}
L(\theta \mid \mathbf{x})=\prod_{i=1}^n f\left(x_i \mid \theta\right)&=\sqrt{\frac{2}{\pi}}^n \theta^{-\frac{3 n}{2}} \prod_{i=1}^n x_i^2 \exp \left(-\frac{1}{2} \frac{x_i^2}{\theta}\right) \\
\ln (L(\theta \mid \mathbf{x}))&=n \ln \sqrt{\frac{2}{\pi}}-\frac{3 n}{2} \ln \theta+\sum_{i=1}^n \ln x_i^2-\frac{1}{2} \sum_{i=1}^n \frac{x_i^2}{\theta} \\
\frac{\partial \ln (L(\theta \mid \mathbf{x}))}{\partial \theta}&=0-\frac{3 n}{2 \theta}+0+\frac{1}{2} \sum_{i=1}^n \frac{x_i^2}{\theta^2}=0 \\
\hat{\theta}&=\frac{\sum_{i=1}^n x_i^2}{3 n} \\
\end{aligned}
$$

## Exercise 3

The amplitude (signal-strength) of a received radar signal is measured once: observation $x$. The observable has a Rayleigh distribution with unknown parameter $\theta$:

$$
f(x \mid \theta)=\frac{x}{\theta^2} e^{-\frac{x^2}{2 \theta^2}}
$$

with $x > 0$ and $\theta > 0$. Determine the Maximum Likelihood Estimator for the parameter $\theta$.

### *Solution:*

Note that since there is only one observation, so there is no product:

$$
\begin{aligned}
L(\theta \mid \mathbf{x})=f(x \mid \theta) & =\frac{x}{\theta^2} e^{-\frac{x^2}{2 \theta^2}} \\
\ln (L(\theta \mid \mathbf{x})) & =-\ln x+\ln \theta^{-2}-\frac{x^2}{2 \theta^2} \\
\frac{\partial \ln (L(\theta \mid \mathbf{x}))}{\partial \theta} & =-\frac{2}{\theta}+\frac{2 x^2}{2 \theta^3}=0 \\
\hat{\theta} & =\frac{1}{2} \sqrt{2} x
\end{aligned}
$$