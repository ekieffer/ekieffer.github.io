---
classes: wide
title: "CoevolutionAry HybRid Bi-level OptimizatioN (CARBON)"
permalink: /carbon/
date: 2020-11-05T14:53:00+00:00
author_profile: true
author: Emmanuel Kieffer

---

<style>
figcaption {
    text-align:center;
}
</style>

Multi-level optimization stems from the need to tackle complex problems involving multiple decision makers. Two-level optimization, referred as "Bi-level optimization", occurs when two decision makers only control a part of the decision variables but impact each other (e.g., objective value, feasibility). Bi-level problems are sequential by nature and can be represented as nested optimization problems in which one problem (<em>upper-level</em>) is constrained by another one (<em>lower-level</em>). The nested structure is a real obstacle that can be highly time consuming when the lower-level is $\mathcal{NP}-hard$ even when considering metaheuristics. Consequently, classical nested optimization should be avoided. Some surrogate-based approaches have been proposed to approximate the lower-level objective value function (or variables) to reduce the number the lower-level is globally optimized. Unfortunately, such a methodology is not applicable for large-scale and combinatorial bi-level problems. 
{: style="text-align: justify;"}


<figure style="width: 500px" class="align-center">
  <a id="model"><img src="/assets/images/model.png" alt=""></a>
  <figcaption>A Bi-level optimization problem and its general mathematical formulation</figcaption>
</figure>

In this work, we investigated new methodologies to address these  limitations.  After a deep study of theoretical properties and a survey of the existing applications being bi-level by nature, we turned our attention to an hybrid strategy relying on machine learning and co-evolution.  Using the principle employed in GP hyper-heuristics, we decided to train heuristics in order to tackle efficiently the  $\mathcal{NP}-hard$ lower-level of bi-level problems.  This automatic generation of heuristics allowed us to break the nested structure into two separated phases: **training lower-level heuristics** and **solving the upper-level problem with the new heuristics**.
{: style="text-align: justify;"}


<figure style="width: 500px" class="align-center">
$$\begin{aligned}
 \min\limits\_{x \in \mathbf{X}, y \in \mathbf{Y}}   &\quad F(x,y) & \\\\\\
 \text{s.t.} & \quad G(x,y) \leq 0&\\\\\\
 			&\quad  \min\limits\_{y \in \mathbf{Y}} \quad f(x,y) && \\\\\\
 			&\quad  \text{s.t. } \quad g(x,y) \leq 0 &\\\\\\
 \end{aligned}
 $$
 <a id="mf"><figcaption>General mathematical formulation</figcaption></a>
</figure>


Although we were able to **break the nested structure**, we still had to solve the problem in two phases. We noticed that the training of heuristics could be performed during the optimization of the upper-level using competitive co-evolution. Instead of adopting the classical decomposition scheme which suffers from the strong epistatic links between lower-level and upper-level variables, we show that co-evolving the solution and the mean to get to it could cope with these link issues. 
{: style="text-align: justify;"}

In order to validate our work, we designed numerical experiments and compared our results against state-of-the-art algorithms.  The results demonstrate that the new hybrid strategy permits to address  nested optimization efficiently. 
In addition to the resolution approaches, we proposed two real application cases that benefit from a bi-level reformulation: **The Bi-level Clustering Optimization Problem** and **The Bi-level Cloud Pricing Optimization Problem**.
{: style="text-align: justify;"}







