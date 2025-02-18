
18-02-2025 14:47

Status: #child

Tags: [[path planning]] 

---
# A star

In [[Sequential Decision Making]], finding optimal paths through state spaces can be approached through various search algorithms, with the choice depending on available information and the trade-off between optimality and computational efficiency.
Consider a path-planning problem in a geographical zone, where we can represent the environment as a state space $S$ with well-defined transition dynamics $T$ and rewards $R$. Informed search algorithms leverage domain knowledge about the goal state to guide exploration.

**A* search**, a prominent best-first search algorithm, makes decisions by evaluating states using a function
$$ f(s) = g(s) = h(s)$$
where $g(s)$ represents the actual cost (negative reward) accumulated from the initial state to the current state, and $h(s)$ is a heuristic function estimating the cost to reach the goal state [^1]. 

When the algorithm arrives in a node A\* decides to choose the adjacent node with the lowest deterministic value, this can be formalized in our SDM framework $(S, A, T, R, \gamma)$, as a process where A\* selects actions $a \in A$ at each state based on minimizing $f(s')$, where $s'$ represents the next state according to the transition function $T(s'|s,a)$. For geographical pathfinding, a common heuristic is the Euclidean distance to the goal, which maintains consistency properties that guarantee optimality. Going back to the example of pathfinding in a geographical zone, a good choice as an heuristic function $h(s)$ is the Euclidean distance between the reached point in the map and the goal, this because it is considered consistent so it maintains the property $$ h(A) \leq cost(A, B) + h(B) $$[^2].
While A\* excels in single-agent scenarios, its effectiveness diminishes in multi-agent settings where the transition dynamics become more complex due to agent interactions, potentially leading to recurring collisions and replanning cycles.

[[Dijkstra's algorithm]] can be viewed as a special case of A\* where , making it an uninformed search method that doesn't utilize problem-specific information.

## References

[^1]: Russell, S. J., & Norvig, P. (2010). _Artificial Intelligence: a Modern Approach_ (3rd ed., pp. 92–99). Pearson.
[^2]: Magnus Lie Hetland. (2014). _Python algorithms: mastering basic algorithms in the Python language_ (p. 214). Apress.