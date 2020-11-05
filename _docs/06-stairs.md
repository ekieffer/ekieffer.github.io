---
title: "STAIRS: an AI-assisted approach"
permalink: /docs/stairs/
excerpt: "STAIRS"
last_modified_at: 2020-10-30
toc: true
---

## Description

Artificial Intelligence augments the capabilities of decision makers to deal with complex problems by exploring more efficiently the space of possibilities. Far more than a simple expert system, AI provides Knowledge Discovery which is a key of major importance, especially in Private Equity. This is the reason why it has a growing impact in FinTech services. From Quantitative Trading ([Ganesh et al. 2018](https://arxiv.org/abs/1809.01506)) to Fraud detection ([Roy et al. 2018](https://ieeexplore.ieee.org/document/8374722)), the number of AI-based algorithms escalated especially with the rise of Deep Learning.
{: style="text-align: justify;"}


<style>
figcaption {
    text-align:center;
}
</style>

<figure style="width: 500px" class="align-center">
  <a id="trend"><img src="/assets/images/AI.png" alt=""></a>
  <figcaption>Figure 3.: Percentage of Guardian Technology Headlines with AI in the title </figcaption>
</figure>

Although Deep Learning Revolution changed the AI landscape towards Deep Neural Network due to their efficiency, some aspects in AI remain very challenging. Indeed, the main superiority of Deep Neural Networks is also the main shortcoming. Due to their large size, it is very complex to understand the decision rules of the networks. By decision rules, we mean the combination of the numerous weights constituting the networks (see <a href="#trend">Figure 4</a>).
{: style="text-align: justify;"}


<figure style="width: 500px" class="align-center">
  <a id="trend"><img src="/assets/images/NN.png" alt=""></a>
  <figcaption>Figure 4.: Deep Neural network architecture </figcaption>
</figure>


Recently, some concerns have been raised on safety and trustworthiness of Deep Neural Networks ([Huang et al. 2018](https://doi.org/10.1016/j.cosrev.2020.100270)). These concerns have followed fatal incident withautonomous/self-driving cars in which the AI behaviour analysis is constrained by the complexity of the underlying Deep Neural Network.
{: style="text-align: justify;"}

To ensure trustworthiness, **STAIRS** will be conceived as a white box in such a manner that non-AI specialists will be able to understand and challenge the decision rules yield by the algorithm. For this purpose, **STAIRS** will directly generate recommitment strategies and validate them using numerical simulations. **STAIRS** will rely on the following sub-components depicted in <a href="#stairs"> Figure. 5</a>:
{: style="text-align: justify;"}


1. A Feature selection from the field of knowledge
2. An encoding mechanism for recommitment strategies
3. A core procedure to generate and adapt encoded strategies 
4. A simulation kernel to evaluate encoded strategies and Investment Degrees
5. A decoding mechanism to return Intelligible strategies for decision makers

<figure style="width: 500px" class="align-center">
  <a id="trend"><img src="/assets/images/stairs.png" alt=""></a>
  <figcaption>Figure 5.: STAIRS's components </figcaption>
</figure>

The main advantage of **STAIRS** will be its modularity and the entire control over the learning process. Its main advantage relies on the place taken by the decision maker as well as the direct interaction with the system. The following sections list the components composing **STAIRS**: 
{: style="text-align: justify;"}

### Features
Features are essential to ensure an efficient learning process. **STAIRS** will rely on features stemming from the field of Knowledge, i.e., private equity indicators. Since trustworthiness is one of our main concerns, it is natural to build on a sturdy foundation and rely on features that experts in private equity uses on a daily basis.
{: style="text-align: justify;"}

This approach does not mean that **STAIRS** will always rely on the same set of features. One very interesting aspect and characteristics of **STAIRS** will be the so-called **"Automatically Defined Functions"**. **STAIRS** will generate strategies/rules/functions that can be re-injected as features to produce more sophisticated strategies.
{: style="text-align: justify;"}

### Encoding

Discovering the right encoding is a key of major importance, especially when using randomized search optimisation algorithms. First, it translates human concepts (e.g. strategies, solutions, ...) into a digital structure that an AI-algorithm can modify and improve at will. 
{: style="text-align: justify;"}

The choice of an encoding is strongly dependent on the AI algorithm that will handling it. In this project, several existing alternatives could be potentially sufficient:
{: style="text-align: justify;"}

- Grammar-based encoding
- Tree-based encoding
- Vector-based encoding

Just as importantly, encoding should be able to represent and target any possible strategies to offer a non-ambiguous search space. The resulting digital structure, after encoding, should have reasonable size to avoid prohibitive computation times.
{: style="text-align: justify;"}

### Core procedure

The core procedure is the main component providing the Intelligence required to identify efficient recommitment strategies encoded as digital structures. This procedure is typically a global optimisation algorithm searching for recommitment strategies improvement according to an objective function, i.e. Investment Degree over funds lifetime.
{: style="text-align: justify;"}

Among the class of global optimisation algorithms that are well-suited for this task, one can find metaheuristics. They are randomized search algorithms which have the important property to escape local optima. They have been successfully applied on very complex problems such as NP-hard problems (e.g. combinatorial, non-convex problems).
{: style="text-align: justify;"}

In this project, we will focus on recent algorithms belonging to the “Genetic programming” category. It has been shown that genetic programming algorithms have the capabilities to generate artificial software code ([Langdon et al. 2015](https://doi.org/10.1109/TEVC.2013.2281544)), symbolic expression ([Zhong et al. 2018](https://doi.org/10.1109/TSMC.2018.2853719)) as well as heuristics ([Kieffer et al. 2019](https://doi.org/10.1109/TEVC.2019.2906581)). Recommitment strategies fall in this last case as they can be assimilated to heuristics for the private equity portfolio management problem.
{: style="text-align: justify;"}


### Evaluation of strategies through simulations

In order to evaluate recommitment strategies generated by the core procedure, portfolio simulations should be performed. Every time the core procedure needs to validate the quality of a strategy, the latter will be sent to a virtual portfolio of private equity funds. A management scenario will be then started using the recommitment strategy as input. At each period of the simulation (e.g. quarter), the experimental Investment Degree will be recorded. Once the simulation has been performed, a postprocessing step will measure the deviation between the experimental Investment Degree and the expected one. 
{: style="text-align: justify;"}


The total deviation is finally returned to the core procedure and serves as a score for the optimisation search. Due to the stochasticity of the simulations, multiple runs will be performed to obtain a good statistical confidence.
{: style="text-align: justify;"}

### Decoding

Once the best strategy has been identified by the core procedure after multiple runs, the digital representation of this same strategy is decoded into an Intelligible recommitment formula for the decision maker, i.e. investors. This step is the reverse operation done during encoding except that the returned strategy is the one that obtained the best score.
{: style="text-align: justify;"}

To conclude this part on **STAIRS**’s characteristics, one should also note that manually designed strategies as discussed in [de Zwart 2012](https://doi.org/10.2469/faj.v68.n3.1) can be provided to **STAIRS** in order to guide the AI search. Such an approach can be described as a “warm” start situation in which **STAIRS** will build new recommitment strategy on an existing knowledge. For this purpose, existing recommitment strategies can be added as new features or new “Automated Defined Function”.
{: style="text-align: justify;"}


## Risk Management

The model described in the previous sections treats equally opportunity costs and cash shortage situations. In practice, this approach may be undesirable. For example, large institutions may be less sensible to cash shortage and prefer to mitigate opportunity costs more. On the contrary, some investors have more risk aversion.
In this project, we will also introduce a more flexible objective with customizable weights depending on the investor’s profile such as risk aversion, exposure to ESG/Sustainability, etc …
{: style="text-align: justify;"}


<figure style="width: 500px" class="align-center">
  <a id="ID"><img src="/assets/images/ID.png" alt=""></a>
  <figcaption>Figure 6.: Investment degrees  </figcaption>
</figure>

These weights will influence the search for recommitment strategies. For example, large weights in the Overinvestment area will guide STAIRS to consider strategies with limited overcommitments. The primary purpose of this weighting approach is to control the deviation to the expected Investment Degree (see <a href="#ID">Figure 6)</a>.
{: style="text-align: justify;"}
