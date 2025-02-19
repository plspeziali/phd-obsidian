---
title: Relatively Rational:Learning Utilities and Rationalities Jointly from Pairwise Preferences
type: paper-note
paper type: journalArticle
author: Yamagata, Taku; Oberkofler, Tobias; Kaufmann, Timo; Bengs, Viktor; Hüllermeier, Eyke; Santos-Rodríguez, Raúl
abstract: Learning utilities from preference feedback has become increasingly important, particularly in fine-tuning language models such as ChatGPT. Traditional methods often assume equal rationality among labellers, leading to inaccurate utility estimates. We propose an algorithm that jointly estimates trainer rationality and item utilities to enhance utility learning and gain additional insights from feedback. Our approach focuses on settings where feedback is received from multiple trainers, using the Boltzmann-rational model to relate choices to latent utilities while accounting for varying levels of rationality. Given shared utilities, our method identifies rationality ratios among trainers from observed choices without extra calibration data or assumptions. We analyse the theoretical impact of assuming equal rationality on utility accuracy and empirically show superior performance in an action-advice setting, where agents construct policies using the learned utilities as rewards. By accurately modelling trainer rationality, we can enhance high-quality feedback collection, potentially leading to better-aligned models and an improved understanding of human preferences.
citekey: yamagataRelativelyRationalLearning
URI: zotero://select/library/items/IJJ8VSRR
Projects: Relative Risk;
---
# Relatively Rational:Learning Utilities and Rationalities Jointly from Pairwise Preferences

> [!Cite]
> Yamagata, T., Oberkofler, T., Kaufmann, T., Bengs, V., Hüllermeier, E., & Santos-Rodríguez, R. (s.d.). _Relatively Rational:Learning Utilities and Rationalities Jointly from Pairwise Preferences_.

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


>[!check] Contribution/Claim
>We propose an algorithm that jointly estimates trainer rationality and item utilities to enhance utility learning and gain additional insights from feedback [(p. 1)](zotero://open-pdf/library/items/USQSAIEQ?page=1&annotation=DJ6ZYTXG)

>[!quote] Quote
>Learning utilities from observed choices requires a model of how the choices are made. The model should relate the choices to utilities, i.e. latent values that represent the intrinsic desirability of the items, while also accounting for other influences on the choices, such as the rationality of the labellers. This is commonly formalised with the Boltzmann-rational model (e.g, Jeon et al., 2020), which models the probability of choosing an item ci from a choice set C = {c1, . . . , cN } as  P (ci) = exp(βui)  PN  j=1 exp(βuj ) ,  where ui is the latent utility of choice ci and β is the labellerspecific rationality coefficient. Higher rationality leads to a more deterministic choice, while lower rationality leads to a more random choice. [(p. 2)](zotero://open-pdf/library/items/USQSAIEQ?page=2&annotation=LKGQ7DXN)
>

>[!check] Contribution/Claim
>Our contributions are the following:  1. Propose an algorithm that jointly learns utilities and rationality coefficients from pairwise preference feedback based on the joint likelihood of the utilities and the rationalities.  2. Theoretically analyse the impact of falsely assuming equal rationality among multiple labellers.  3. Empirically investigate utility learning and resulting downstream task performance in an action-advice setting where the agent learns a policy using the learned utilities as rewards. [(p. 2)](zotero://open-pdf/library/items/USQSAIEQ?page=2&annotation=3JIEJ9K3)

>[!quote] Quote
>Human judgment tuples (a1, a2, s, k, w) are recorded in a database D. Here, a1 and a2 are the pair of actions to compare, s is the state, k is the trainer’s index, and w is an encoding of the judgement, w = (w1, w2) = [1, 0] if the human selects a1 and w = [0, 1] if the human selects a2. [(p. 3)](zotero://open-pdf/library/items/USQSAIEQ?page=3&annotation=IN29QXA9)
>

>[!quote] Quote
>e use the Boltzmann-rational model to represent human preference feedback behaviour. The probability that trainer k indicates action a1 is better than action a2 in state s is given by  P (a1 ≻k,s a2) = 1  1 + e−β ̃(us,a1 −us,a2 ) .  (1)  Here, two groups of parameters need to be estimated:  u = {us,a ∈ R}s∈S,a∈A  are utility parameters for each state/action pair (s, a), where S and A denote the state space and action space, respectively. These parameters indicate how good the action a is in state s, with higher numbers indicating a higher value. The second group,  β = {β ̃ ∈ R}k=1,...,K ,  consists of rationality parameters for the trainers k ∈ {1, . . . , K}. These parameters indicate how rational the different trainers are. Trainers with a higher rationality parameter are more accurate in their feedback.  We employ the following negative log-likelihood function as a loss function and apply the stochastic gradient descent (SGD) algorithm to learn the utility and rationality parameters concurrently:  L(u, β) = −  X  (a1 ,a2 ,s,k,w)∈D  w1 log P (a1 ≻k,s a2)+  w2 log P (a2 ≻k,s a1) [(p. 3)](zotero://open-pdf/library/items/USQSAIEQ?page=3&annotation=RJ4J73KS)
>

>[!quote] Quote
>In order to stabilise the learning process, we implement two constraints. First, we fix the rationality for one of the trainers to one. Here, every trainer may, in principle, serve as a reference, except one that labels completely at random (and hence has rationality β = 0). In practice, such a selection could be facilitated by reviewing a labeller’s history and ensuring to include at least one labeller whom we expect to behave reasonably rationally.  Secondly, we introduce a prior for the utilities. A range of priors have been proposed in the literature (Davidson & Solomon, 1973; Whelan, 2017). Here, we adopt a logistic prior, which can be introduced by having two preferences for each state-action pair against a virtual utility parameter of zero value (Newman, 2023). As a result, the following regularisation term (Lr) is added to the above loss function:  Lr =  X  s∈S ,a∈A  log(1 + e−us,a ) + log(1 + eus,a ) [(p. 3)](zotero://open-pdf/library/items/USQSAIEQ?page=3&annotation=VRWUFK7V)
>

>[!quote] Quote
>To decide which action to take in a given state, we employ greedy action selection based on the learned utility values, i.e. select action  a = arg max  a∈A us,a .  Note that this formulation does not encourage exploration. [(p. 4)](zotero://open-pdf/library/items/USQSAIEQ?page=4&annotation=BASR3FUH)
>


%% Import Date: 2025-02-18T13:42:50.807+01:00 %%
