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

*Submitted*, 2025, [[arXiv](https://www.arxiv.org/abs/2505.18327)]

- Constrained stochastic nonlinear optimization problems have attracted significant attention for their ability to model complex real-world scenarios in physics, economics, and biology. As datasets continue to grow, online inference methods have become crucial for enabling real-time decision-making without the need to store historical data. In this work, we develop an online inference procedure for constrained stochastic optimization by leveraging a method called Adaptive Inexact Stochastic Sequential Quadratic Programming (AI-SSQP).

- As a generalization of (sketched) Newton methods to constrained problems, AI-SSQP approximates the objective with a quadratic model and the constraints with a linear model at each step, then applies a randomized sketching solver to inexactly solve the resulting subproblem, along with an adaptive random stepsize to update the primal-dual iterates. Building on this design, we first establish the asymptotic normality guarantee of *averaged* AI-SSQP and observe that the averaged iterates exhibit better statistical efficiency than the last iterates, in terms of a smaller limiting covariance matrix. Furthermore, instead of estimating the limiting covariance matrix directly, we study a new online inference procedure called *random scaling*. Specifically, we construct a test statistic by appropriately rescaling the averaged iterates, such that the limiting distribution of the test statistic is free of any unknown parameters.

- Compared to existing online inference procedures, our approach offers two key advantages: (i) it enables the construction of *asymptotically valid* and *statistically efficient* confidence intervals, while existing procedures based on the last iterates are less efficient and rely on a plug-in covariance estimator that is *inconsistent*; and (ii) it is *matrix-free*, i.e., the computation involves only primal-dual iterates themselves without any matrix inversions, making its computational cost match that of advanced first-order methods for unconstrained problems. We validate our theoretical findings through numerical experiments on nonlinearly constrained regression problems and demonstrate the superior performance of random scaling over existing inference procedures.

