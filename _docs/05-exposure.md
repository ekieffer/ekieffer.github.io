---
title: "Investors exposure to private equity responsible investment"
permalink: /docs/exposure/
excerpt: "Exposure"
last_modified_at: 2020-10-30
toc: false
---

An element of major importance to measure the exposure to private equity is the Investment Degree (ID) defined as follows:
{: style="text-align: justify;"}

$$ID_t=\frac{NAV_t}{NAV_t+Cash_t}$$

$NAV_t$ is the total net asset value of the underlying investment funds and $Cash_t$ is the uninvested cash in the portfolio. Investor’s objective consists in keeping the $ID_t$ as close as possible to **1** by minimizing $Cash_t$.
{: style="text-align: justify;"}

The investment degree as described above does not take into account the investment in sustainable funds. Therefore, we propose to decompose  and compute it depending on whether the invested funds are the targeted ones or if there are only eligible, i.e. with less priorities.
{: style="text-align: justify;"}

$$ID_t(\alpha) = \alpha \frac{\mathit{NAV}_t^{\,target}}{ \mathit{NAV}_t + Cash_t} + (1-\alpha) \frac{\mathit{NAV}_t^{\,eligible}}{\mathit{NAV}_t + Cash_t}$$


<br />
With $\mathit{NAV}T_t = \alpha \mathit{NAV}_t^{\,targeted} + (1-\alpha)\mathit{NAVT}_t^{\,eligible}$, the decomposition of the net asset value of the underlying targeted funds and  eligible ones. $\alpha$ is the coefficient denoting the importance allocated to targeted ESG investments. Note that in this project, our main incentive is to determine the maximal $\alpha$-exposure knowing that the investment degree should be kept as close as possible to 1. For this purpose, a maxmin objectivefunction is considered:
{: style="text-align: justify;"}


$$\max\limits_\alpha\min\limits_{C_t}E_t\left[(1-ID_{t+1}(\alpha))^2\right]$$

with $E_t$ denoting the conditional expectation at the end of the period t. Note also that commitments at period t will have consequences on the Investment Degree on period t+1. Although being underinvesting may lead to opportunity costs, an investor is looking to avoid cash shortages, i.e. $Cash_t<0$ and thus $ID_t(\alpha)>1$for all $\alpha$. The latter happens only if the call requirements exceed the investor resource capacities.
{: style="text-align: justify;"}

Being fully invested is a complicated task for an investor. The committed capital is drawn down gradually while distributions may already occur before the entirety of the capital is called. Furthermore, the capital is generally not completely invested. Investors also face a multi-period dynamic portfolio optimisation problem. In order to take into account its dynamicity, an equivalent multi-level single-period portfolio optimisation is solved at each period to determine the optimal commitment $C_t$ with the best $\alpha$-exposure.
{: style="text-align: justify;"}

In order to compute the global optimal solution of this problem, investors will have to determine the distributions as well as the capital called at the period t+1.In order to solve this pitfall, two approaches have been applied in the literature so far:
{: style="text-align: justify;"}

- Cash flow predictions ([Takeshi and Alexander 2002](https://doi.org/10.3905/jpm.2002.319836), [de Malherbe 2004](Modeling Private Equity Funds and Private Equity Collateralised Fund Obligations))
- Recommitment engineering using strategies ([de Zwart 2012](https://doi.org/10.2469/faj.v68.n3.1)), [Oberli 2015](https://www.jstor.org/stable/43503837))

Cash flow predictions rely on **direct** forecasts of the cash in and out flows that are directly injected into the solution to obtain the recommitment solution. The quality of the solution depends directly on the quality of the prediction. The advantage of cash-flow predictions is the direct access to the analytical optimal solution. Its main drawback lies in the fact that prediction accuracy only occurs towards the end of the life cycle of the funds.
{: style="text-align: justify;"}

The second approach based on strategies is an **indirect** approach replacing the analytical solution by approximation rules which do not **rely** on cash flow predictions. This last point is clearly an advantage when cash flow predictions cannot be accurate when funds are still at their infancy. Although bypassing the need of cash flow prediction has a certain utility, it might be also a drawback when reaching the end of the life cycle of the funds.
{: style="text-align: justify;"}

In this project, we will combine both approaches as they turn to be complementary. Although no one in the literature relied on cash flow forecasts inside recommitment strategies, we claim that the conjunction of both methods would provide an efficient procedure to keep a maximum exposure to private equity in diverse situations.
{: style="text-align: justify;"}

For this purpose, the generation of recommitment strategies become a real challenge with an increasing search space that limits manual search. In this particular context, an AI-assisted algorithm would take on its full meaning. As described in the previous section, **STAIRS** will be an AI-assisted algorithm in charge of the evolution and the evaluation of advanced recommitment strategies. In the next section, **STAIRS**’s characteristics are described.
{: style="text-align: justify;"}
