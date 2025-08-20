---
Title: Relaxed-IK
Authors: Daniel Rakita, Bilge Mutlu, Michael Gleicher
Date Published:
Date found: 2025-08-20
Keywords:
Link: https://graphics.cs.wisc.edu/Papers/2018/RMG18a/p43.pd
DOI: "{{DOI}}"
Read status:
Draft:
---
---
year: 2018
authors: Daniel Rakita, Bilge Mutlu, Michael Gleicher

--- 
# Data
## Abstract
We present a real-time motion-synthesis method forrobot manipulators, called RelaxedIK, that is able to not only accurately match end-effector pose goals as done by traditional IK solvers, but also create smooth, feasible motions that avoid joint-space discontinuities, self-collisions, and kinematic singularities. To achieve these objectives on-the-fly, we cast the standard IK formulation as a weighted-sum non-linear optimization problem,such that motion goals in addition to end-effector pose matching can be encoded as terms in the sum. We present a normalization procedure such that our method is able to effectively make trade-offs to simultaneously reconcile many, and potentially competing, objectives. Using these trade-offs, our formulation allows features to be relaxed when in conflict with other features deemed more important at a given time. We compare performance against a state-of-the-art IK solver and a real-time motion-planning approach in several geometric and real-world tasks on seven robot platforms ranging from 5-DOF to 8-DOF. We show that our method achieves motions that effectively follow position and orientation end-effector goals without sacrificing motion feasibility, resulting in more successful execution of tasks compared to the baseline approaches.
## Links
https://graphics.cs.wisc.edu/Papers/2018/RMG18a/p43.pdf
## Status: 

# Notes

Goal: achieve smooth feasible motions. Done with weighted-sum non-linear optimization problem.

- Problem Formulation
	- Match the end-effector pose goal corresponding to goal positon $P_g$ and goal orientation $q_g$ as precisely and quickly as possible without sacrificing robot configuration feasibility
	- feasibility defined by not breaking velocity limits upon consecutive solutions (no joint space discontinuities), no self collisions, and no singularities. 
	- Expectation: solving discrete IK problems at each update with this goal, will yield continuous and feasible motions in a sequence. 
		- Not sure why I should believe this without look ahead, but maybe there is lookahead?
	- the end-effector constraint is not a hard constraint, pose goals can be relaxed in favor of feasibility or other important properties. 
	- you can statically or dynamically weight each term to determine how important each feature is relative to each other.
- Optimization
	- I get the gist, but I lack the mathematical optimization context to really grok this.
		- good reason to read more textbooks :)
	- A NN estimates some important quantity - but I once again did not really grok it on the once over. I want to read some more optimization/kinematics content and return to this paper. and 


## Related Papers

- [ 3 ] reference looks like something that might be good for IK. 
- [[Stampede]]
- [[Relaxed-IK]]
