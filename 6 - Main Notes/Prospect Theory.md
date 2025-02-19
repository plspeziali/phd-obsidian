
19-02-2025 16:26

Status: #child

Tags: [[risk sensitive]]

---
# Prospect Theory

To understand why alignment methods work so well, we now frame them through the lens of prospect theory (Tversky & Kahneman, 1992). Prospect theory explains why, when faced with an uncertain event, humans make decisions that do not maximize their expected value. 

For example, because humans are loss-averse, given a gamble that returns $100 with 80% probability and $60 with 20% probability, a person might accept $60 to avoid the gamble, despite their certainty equivalent of $60 being less than the expected value of $80.

In prospect theory, human utility depends on a **value function** and a **weighting function**:

### Definition 3.1: Value Function  
A value function $v: Z \to \mathbb{R}$ maps an outcome $z$, relative to some reference point $z_0$, to its perceived (or subjective) value.  
For example, these functions capture the fact that humans tend to be more sensitive to relative losses than relative gains of the same magnitude.

### Definition 3.2: Weighting Function  
A weighting function $\omega$ is the derivative of a capacity function that maps cumulative probabilities to perceived cumulative probabilities. These functions capture, for example, the fact that humans tend to overestimate the chance of rare events. Let $\omega_z$ denote the weight placed on outcome $z$.

### Definition 3.3: Utility Function  
The utility of a random variable $Z$ is a function of its outcomes:
$$ u(Z) = \sum_{z \in Z} \omega_z v(z - z_0) $$
However, because humans do not see the full probability distribution of an LLM, weighting functions are not salient to this discussion; we will focus only on value functions.  

Using experiments that presented real humans with monetary gambles and asked for their certainty equivalent, Tversky & Kahneman (1992) proposed the following functional form for human value:
$$
v(z; \lambda, \alpha, z_0) =
\begin{cases} 
(z - z_0)^\alpha & \text{if } z \geq z_0 \\
-\lambda(z_0 - z)^\alpha & \text{if } z < z_0
\end{cases}
$$
where the median value of hyperparameters:  
- $\alpha = 0.88$ (controls the curvature of the function, reflecting risk aversion)  
- $\lambda = 2.25$ (controls steepness, reflecting loss aversion)  

While the shape of the median **Kahneman-Tversky value function** is illustrated in the following Figure, it should be noted that it varies across individuals.

![[kto1.png]]

### Salient Qualities of a Value Function  
- The **existence of a reference point** that determines relative gain or loss.  
- **Concavity in relative gains** (i.e. diminishing sensitivity away from $z_0$).  
- **Loss aversion** (i.e. greater sensitivity to losses than gains).  [^1]

---
## References

[^1]: Ethayarajh, K., Xu, W., Muennighoff, N., Jurafsky, D., & Kiela, D. (2024). _[[KTO Model Alignment as Prospect Theoretic Optimization]]_ (No. arXiv:2402.01306). arXiv. [https://doi.org/10.48550/arXiv.2402.01306](https://doi.org/10.48550/arXiv.2402.01306)