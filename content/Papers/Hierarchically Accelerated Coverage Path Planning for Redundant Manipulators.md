---
Title: Hierarchically Accelerated Coverage Path Planning for Redundant Manipulators
Authors: Yeping Wang, Micheal Gleicher
Date Published: 2025-02-26
Date found: 2025-06-16
Keywords: Coverage Path Planning, Manipulators, Gleicher, GTSP, TSP, IK, Inverse Kinematics
Abstract: Many robotic applications, such as sanding, polishing, wiping and sensor scanning, require a manipulator to dexterously cover a surface using its end-effector. In this paper, we provide an efficient and effective coverage path planning approach that leverages a manipulator's redundancy and task tolerances to minimize costs in joint space. We formulate the problem as a Generalized Traveling Salesman Problem and hierarchically streamline the graph size. Our strategy is to identify guide paths that roughly cover the surface and accelerate the computation by solving a sequence of smaller problems. We demonstrate the effectiveness of our method through a simulation experiment and an illustrative demonstration using a physical robot.
Link: https://scholar.google.com/citations?view_op=view_citation&hl=en&user=kDkH9UkAAAAJ&sortby=pubdate&citation_for_view=kDkH9UkAAAAJ:TlpoogIpr_IC
DOI: https://doi.org/10.48550/arXiv.2502.19591
Read status: Read
---
## Notes

- Introduction
	- aim: solve coverage while minimizing cost in joint space
	- 'redundant robot manipulator systems'?
		- ans: the robot has more degrees of freedom than the task requires
	- Formulated as GTSP (generalized traveling salesman problem)
	- Contribution: effective and efficient approach compared against two baselines
- Related work
	- Might be worth looking into task sequencing papers
	- and viewpoint coverage path planning
	- Other work plans in cartesian space as opposed to joint space, leaving a lot of cost reduction on the table
- Technical Overview
	- Problem Formulation
		- given a surface defined by a triangle mesh, visit each vertice with the end effector having the same normal as the point on the surface.
	- Baselines
		- Construct a Cartesian graph -> solve
			- doesn't account for joint-space reconfiguring
		- Construct a [[RangedIK]] Joint space graph -> solve
			- doesn't scale well
	- H-Joint-GTSP
		- improves on joint space graph by first constructing a "guide path" to reduce the search space and sampling IK solutions near it. 
		- Step 1: Extract End-Effector Target Exemplars
			- make clusters of end-effector poses
		- Step 2:
			- sample $m$ IK solutions from each of the clusters
		- Step 3:
			- Solve  upper-level TSP for a guide path
		- Step 4:
			- sample IK solutions near the guide path
		- Step 5: 
			- solve lower-level GTSP
	- Evaluation
		- Proposed solution betters or matches computation time, number of recongifurations, and joint movements 

Figure 2 really does a good job of visually explaining the baselines vs the proposed approach better than the text
### Summary

Aim: Solve coverage path planning while minimizing cost in joint space, and do so efficiently

Baselines included a fast method with clunky results re: joint space (solved the path in Cartesian space, not joint space), and a joint-space solver that took a long time. Proposed solution computed a "guide path" first, then sampled nearby to resolve the rest of the path. Much faster than the joint space solution, matching the Cartesian solution while still beating the Cartesian solution in join movements. 

## Related Papers

- [[RangedIK]]