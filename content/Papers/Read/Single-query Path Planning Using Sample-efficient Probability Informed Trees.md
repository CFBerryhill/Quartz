---
Title: Single-query Path Planning Using Sample-efficient Probability Informed Trees
Authors: Daniel Rakita, Bilge Mutlu, Michael Gleicher
Date Published: 
Date found: 2025-07-10
Keywords: 
Link: https://graphics.cs.wisc.edu/Papers/2021/RMG21/
DOI: 
Read status: Once Over
Draft:
---
# Data
## Abstract
In this work, we present a novel sampling-based path planning method, called SPRINT. The method finds solutions for high dimensional path planning problems quickly and robustly. Its efficiency comes from minimizing the number of collision check samples. This reduction in sampling relies on heuristics that predict the likelihood that samples will be useful in the search process. Specifically, heuristics (1) prioritize more promising search regions; (2) cull samples from local minima regions; and (3) steer the search away from previously observed collision states. Empirical evaluations show that our method finds shorter or comparable-length solution paths in significantly less time than commonly used methods. We demonstrate that these performance gains can be largely attributed to our approach to achieve sample efficiency.
## Links
https://graphics.cs.wisc.edu/Papers/2021/RMG21/
## Status: Abstract


# Notes

- Introduction 
	- dd
- Related work
	- Other planners like RRT, PRM, EST
- Goal: Target searching through useful space by trimming search space unlikely to yield useful results because of collision / applying a probability factor to more likely space and a probability penalty to unlikely space
- As planning occurs, do a mix of exploration/exploitation. When exploiting, push nodes that have been shown to be making progress towards the final goal. When exploring, push nodes that have gotten further from the root. 
- Use a number of checkpoints (~50 seems good enough for the circumstances the authors attempted) between the goal and the start. (how do you actually determine these checkpoints?)
- Faster on all benchmarks, on a variety of tasks and robot shapes. 
### Summary

## Related Papers
