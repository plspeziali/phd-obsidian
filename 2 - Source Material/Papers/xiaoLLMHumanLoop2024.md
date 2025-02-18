---
title: "LLM A*: Human in the Loop Large Language Models Enabled A* Search for Robotics"
type: paper-note
year: 2024
paper type: preprint
author: Xiao, Hengjia; Wang, Peng
abstract: "This research focuses on how Large Language Models (LLMs) can help with (path) planning for mobile embodied agents such as robots, in a human-in-the-loop and interactive manner. A novel framework named LLM A*, aims to leverage the commonsense of LLMs, and the utility-optimal A* is proposed to facilitate few-shot near-optimal path planning. Prompts are used for two main purposes: 1) to provide LLMs with essential information like environments, costs, heuristics, etc.; 2) to communicate human feedback on intermediate planning results to LLMs. This approach takes human feedback on board and renders the entire planning process transparent (akin to a ‘white box’) to humans. Moreover, it facilitates code-free path planning, thereby fostering the accessibility and inclusiveness of artificial intelligence techniques to communities less proficient in coding. Comparative analysis against A* and RL demonstrates that LLM A* exhibits greater efficiency in terms of search space and achieves paths comparable to A* while outperforming RL. The interactive nature of LLM A* also makes it a promising tool for deployment in collaborative human-robot tasks. Codes and Supplemental Materials can be found at GitHub: https://github.com/speedhawk/LLM-A-."
citekey: xiaoLLMHumanLoop2024
URI: zotero://select/library/items/PNF689KH
Projects: Deliverable;
tags:
  - Computer
  - Science
  - Artificial
  - Intelligence
  - Computer
  - Science
  - Human-Computer
  - Interaction
  - Computer
  - Science
  - Robotics
---
# LLM A*: Human in the Loop Large Language Models Enabled A* Search for Robotics

> [!Cite]
> Xiao, H., & Wang, P. (2024). _LLM A\*: Human in the Loop Large Language Models Enabled A\* Search for Robotics_ (No. arXiv:2312.01797). arXiv. [https://doi.org/10.48550/arXiv.2312.01797](https://doi.org/10.48550/arXiv.2312.01797)

---
## Summary
%% begin summary %%
%% end summary %%

## Key Contributions
%% begin key contributions %%
%% end key contributions %%

## Relevance to Projects
- [Deliverable](Deliverable.md)  


## Annotations
These are automatically sourced from Zotero.


>[!quote] Quote
>This paper harnesses the advantages of A\* being able to find an optimal path and LLMs being able to consider commonsense knowledge when interacting with humans (agents) and proposes the LLM A\*, a human-in-the-loop solution for robot path planning. [(p. 2)](zotero://open-pdf/library/items/LJJE4FN7?page=2&annotation=ZTZT498Y)
>

>[!quote] Quote
>Briefly, LLM A\* can be summarised into three pivotal stages. The first stage is to set up the environment where a robot performs path planning, and communicates the information to LLMs. The second stage entails the definition of the initial state, the goal state, and the heuristics to be used. We have adopted a generic form of heuristic that considers obstacles, distances, and actions the robot can perform in the environment. It is worth mentioning that the heuristic can be tailored to specific setups based on the applications. Subsequently, LLMs identify feasible moves for path planning, evaluated against a cost function combining path cost and current-state heuristic, akin to A*. The best ‘move’ with the minimum cost will be selected and communicated to humans upon request, who may accept or decline it. The decision will be communicated back to LLMs to carry on completing or terminating the planning. One benefit of human guidance and assessments is to minimise the use of tokens, which remains a challenge to use LLMs such as ChatGPT [(p. 2)](zotero://open-pdf/library/items/LJJE4FN7?page=2&annotation=WHKTRFXA)
>

>[!check] Contribution/Claim
>The contributions of this paper include: 1). a first-of-its-kind LLM-based A\* is proposed for robotic path planning and a set of metrics are defined to evaluate the performance; 2). the interactive and code-free nature of LLM A\* makes it appealing to non-expert robotic users; 3). enhanced safety assurance in comparison to A* and RL as humans are involved in the planning and loop and have full control of the planning process. [(p. 2)](zotero://open-pdf/library/items/LJJE4FN7?page=2&annotation=3XXLZJY6)

>[!quote] Quote
>constructing an LLM A\* model primarily involves two stages. The first stage entails ‘teaching/tuning’ an LLM to comprehend the environment in which [(p. 4)](zotero://open-pdf/library/items/LJJE4FN7?page=4&annotation=EG37EMJQ)
>the agent operates, along with the available actions it can perform. [(p. 5)](zotero://open-pdf/library/items/LJJE4FN7?page=5&annotation=FSYAX2ZL)
>

>[!quote] Quote
>The second stage involves the path-planning process. Equipped with the requisite information, the LLM endeavors to devise a path between the initial state ss and the goal state sg. As prompts are employed to interact with the LLM, human intervention may be necessary during the planning phase for two purposes: 1) guiding the LLM to only convey essential information back to humans, thereby conserving valuable tokens; 2) offering guidance or heuristics when required to expedite the planning process. The prompts also empower humans to inquire about the planning process as needed, rendering the entire planning process transparent to humans. [(p. 5)](zotero://open-pdf/library/items/LJJE4FN7?page=5&annotation=SHU7DV3R)
>


%% Import Date: 2025-02-18T14:36:44.164+01:00 %%
