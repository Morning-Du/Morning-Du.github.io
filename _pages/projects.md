---
layout: page
title: Research
permalink: /projects/
description: 
nav: true
nav_order: 1
display_categories: [work, fun]
horizontal: false
---

#### 1. Online Statistical Inference of Constrained Stochastic Optimization via Random Scaling

**Xinchen Du**, [Wanrong Zhu](https://zhuwr0423.github.io/), [Wei Biao Wu](https://stat.uchicago.edu/people/profile/wei-biao-wu/), and [Sen Na](https://senna1128.github.io/)  

*To appear, Journal of Machine Learning Research, 2026, [[arXiv version](https://www.arxiv.org/abs/2505.18327)].*  **A short version has been accepted in [NeurIPS 2025 ML×OR Workshop](https://mlxor-workshop.github.io/)**

- Constrained stochastic nonlinear optimization problems have attracted significant attention for their ability to model complex real-world scenarios in physics, economics, and biology. As datasets continue to grow, online inference methods have become crucial for enabling real-time decision-making without the need to store historical data. In this work, we develop an online inference procedure for constrained stochastic optimization by leveraging a method called Adaptive Inexact Stochastic Sequential Quadratic Programming (AI-SSQP).

- As a generalization of (sketched) Newton methods to constrained problems, AI-SSQP approximates the objective with a quadratic model and the constraints with a linear model at each step, then applies a randomized sketching solver to inexactly solve the resulting subproblem, along with an adaptive random stepsize to update the primal-dual iterates. Building on this design, we first establish the asymptotic normality guarantee of *averaged* AI-SSQP and observe that the averaged iterates exhibit better statistical efficiency than the last iterates, in terms of a smaller limiting covariance matrix. Furthermore, instead of estimating the limiting covariance matrix directly, we study a new online inference procedure called *random scaling*. Specifically, we construct a test statistic by appropriately rescaling the averaged iterates, such that the limiting distribution of the test statistic is free of any unknown parameters.

- Compared to existing online inference procedures, our approach offers two key advantages: (i) it enables the construction of *asymptotically valid* and *statistically efficient* confidence intervals, while existing procedures based on the last iterates are less efficient and rely on a plug-in covariance estimator that is *inconsistent*; and (ii) it is *matrix-free*, i.e., the computation involves only primal-dual iterates themselves without any matrix inversions, making its computational cost match that of advanced first-order methods for unconstrained problems. We validate our theoretical findings through numerical experiments on nonlinearly constrained regression problems and demonstrate the superior performance of random scaling over existing inference procedures.





#### 2. Online Statistical Inference for Proximal Stochastic Gradient Descent under Markovian Sampling

**Xinchen Du**, and [Sen Na](https://senna1128.github.io/) 

Draft available upon request.  **A short version has been accepted in [NeurIPS 2025 COML Workshop](https://constrained-opt-ml.github.io/)**

- Nonsmooth stochastic optimization has emerged as a fundamental framework for modeling complex machine learning phenomena, particularly those involving constraints. Proximal stochastic gradient descent (proximal SGD) serves as the predominant algorithm to solve it. While existing research focuses on the *i.i.d.* data setting, nonsmooth optimization under *Markovian sampling* remains largely unexplored. 
 

- This work proposes an online statistical inference procedure for nonsmooth optimization under *Markovian sampling* using proximal SGD. We establish asymptotic normality of *averaged* proximal SGD iterates and introduce a random scaling inference method that constructs parameter-free pivotal statistics through appropriate normalization. Our approach enables *asymptotically valid* confidence intervals, and the entire inference procedure is *fully online*.




#### 3. Inference of Online Newton Methods with Nesterov’s Accelerated Sketching

Haoxuan Wang, **Xinchen Du**, and [Sen Na](https://senna1128.github.io/) 

  *ICML 2026, [[arXiv version](https://arxiv.org/abs/2604.23436)].*

- Reliable decision-making with streaming data requires principled uncertainty quantification of online methods. While first-order methods enable efficient iterate updates, their inference procedures still require updating proper (covariance) matrices, incurring $O(d^2)$ time and memory complexity, and are sensitive to ill-conditioning and noise heterogeneity of the problem. This costly inference task offers an opportunity for more robust second-order methods, which are, however, bottlenecked by solving Newton systems with $O(d^3)$ complexity. 

- In this paper, we address this gap by studying an online Newton method with Hessian averaging, where the Newton direction at each step is approximately computed using a *sketch-and-project solver with Nesterov's acceleration*, matching $O(d^2)$ complexity of first-order methods. For the proposed method, we quantify its uncertainty arising from both random data and randomized computation. 

- Under standard smoothness and moment conditions, we establish global almost-sure convergence, prove asymptotic normality of the last iterate with a limiting covariance characterized by a Lyapunov equation, and develop a fully online covariance estimator with non-asymptotic convergence guarantees. 
We also connect the resulting uncertainty quantification to that of exact and sketched Newton methods without Nesterov's acceleration. Extensive experiments on regression models demonstrate the superiority of the proposed method for online inference.

