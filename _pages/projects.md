---
layout: page
title: Research
permalink: /projects/
description: 
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
---

## 1. Online Statistical Inference of Constrained Stochastic Optimization via Random Scaling
\textbf{Xinchen Du}, Wanrong Zhu, Wei Biao Wu, and Sen Na
\textit{Submitted}, 2025 [[arXiv]](https://www.arxiv.org/abs/2505.18327)

- Constrained stochastic nonlinear optimization problems have attracted significant attention for their ability to model complex real-world scenarios in physics, economics, and biology. As datasets continue to grow, online inference methods have become crucial for enabling real-time decision-making without the need to store historical data. 
In this work, we develop an online inference procedure for constrained stochastic optimization by leveraging a method called Adaptive Inexact Stochastic Sequential Quadratic Programming (AI-SSQP). As a generalization of (sketched) Newton methods to constrained problems, AI-SSQP approximates the objective with a quadratic model and the constraints with a linear model at each step, then applies a randomized sketching solver to inexactly solve the resulting subproblem, along with an adaptive random stepsize to update the primal-dual iterates.
Building on this design, we first establish the asymptotic normality guarantee of \textit{averaged} AI-SSQP and observe that the averaged iterates exhibit better statistical efficiency than the last iterates, in terms of a smaller limiting covariance matrix. Furthermore, instead of estimating the limiting covariance matrix directly, we study a new online inference procedure called \textit{random scaling}. 
Specifically, we construct a test statistic by appropriately rescaling the averaged iterates, such that the limiting distribution of the test statistic is free of any unknown parameters. Compared to existing online inference procedures, our approach offers two key advantages: (i) it enables the construction of \textit{asymptotically valid} and \textit{statistically efficient} confidence intervals, while existing procedures based on the last iterates are less efficient and rely on a plug-in covariance estimator that is \mbox{inconsistent}; and (ii) it is \textit{matrix-free}, i.e., the computation involves only primal-dual iterates themselves without any matrix inversions, making its computational cost match that of advanced first-order methods for unconstrained problems. We validate our theoretical findings through numerical experiments on nonlinearly constrained regression problems and demonstrate the superior performance of random scaling over existing inference procedures.


<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
