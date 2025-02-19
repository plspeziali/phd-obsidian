---
%% cssclass: research-note %%


title: "KTO: Model Alignment as Prospect Theoretic Optimization"


type: "paper-note"


year: 2024


paper type: "preprint"

author: "Ethayarajh, Kawin; Xu, Winnie; Muennighoff, Niklas; Jurafsky, Dan; Kiela, Douwe"


abstract: "Kahneman & Tversky’s prospect theory tells us that humans perceive random variables in a biased but well-defined manner (1992); for example, humans are famously loss-averse. We show that objectives for aligning LLMs with human feedback implicitly incorporate many of these biases—the success of these objectives (e.g., DPO) over crossentropy minimization can partly be ascribed to them belonging to a family of loss functions that we call human-aware losses (HALOs). However, the utility functions these methods attribute to humans still differ from those in the prospect theory literature. Using a Kahneman-Tversky model of human utility, we propose a HALO that directly maximizes the utility of generations instead of maximizing the log-likelihood of preferences, as current methods do. We call this approach KTO, and it matches or exceeds the performance of preference-based methods at scales from 1B to 30B, despite only learning from a binary signal of whether an output is desirable. More broadly, our work suggests that there is no one HALO that is universally superior; the best loss depends on the inductive biases most appropriate for a given setting, an oft-overlooked consideration."



citekey: ethayarajhKTOModelAlignment2024


URI: zotero://select/library/items/6DCZK4PC



Projects: Relative Risk; 



Tags: Computer Science - Artificial Intelligence Computer Science - Machine Learning 

---
# KTO: Model Alignment as Prospect Theoretic Optimization

> [!Cite]
> Ethayarajh, K., Xu, W., Muennighoff, N., Jurafsky, D., & Kiela, D. (2024). _KTO: Model Alignment as Prospect Theoretic Optimization_ (No. arXiv:2402.01306). arXiv. [https://doi.org/10.48550/arXiv.2402.01306](https://doi.org/10.48550/arXiv.2402.01306)

---
## Summary
%% begin summary %%
%% end summary %%

## Key Contributions
%% begin key contributions %%
%% end key contributions %%

## Relevance to Projects
- [Relative Risk](Relative Risk.md)  


## Annotations
These are automatically sourced from Zotero.


>[!quote] Quote
>In prospect theory, human utility depends on a value function and a weighting function:3  Definition 3.1. A value function v : Z → R maps an outcome z, relative to some reference point z0, to its perceived (or subjective) value. For example, these functions capture the fact that humans tend to be more sensitive to relative losses than relative gains of the same magnitude.  Definition 3.2. A weighting function ω is the derivative of a capacity function that maps cumulative probabilities to perceived cumulative probabilities. These functions capture, for example, the fact that humans tend to overestimate the chance of rare events. Let ωz denote the weight placed on outcome z.  Definition 3.3. The utility of a random variable Z is a function of its outcomes: u(Z) ≜ P  z∈Z ωzv(z − z0).  However, because humans do not see the full probability distribution of an LLM, weighting functions are not salient to this discussion; we will focus only on value functions. Using experiments that presented real humans with monetary gambles and asked for their certainty equivalent, Tversky & Kahneman (1992) proposed the following functional form for human value:  v(z; λ, α, z0) =  (  (z − z0)α if z ≥ z0  −λ(z0 − z)α if z < z0  (4)  where the median value of hyperparameter α = 0.88 and λ = 2.25 across individuals. α controls the curvature of the function, which reflects risk aversion; λ controls its steepness, which reflects loss aversion. While the shape of the median Kahneman-Tversky value function is illustrated in Figure 1, it should be noted that it varies across individuals [(p. 3)](zotero://open-pdf/library/items/3IECIQB7?page=3&annotation=V5TTEKY8)
>

>[!quote] Quote
>The salient qualities of a value function are: the existence of a reference point that is used to get the relative gain or loss; concavity in relative gains (i.e., diminishing sensitivity away from z0); and loss aversion (i.e., greater sensitivity to losses). [(p. 3)](zotero://open-pdf/library/items/3IECIQB7?page=3&annotation=XEV25ABG)

%% Import Date: 2025-02-19T16:24:28.386+01:00 %%
