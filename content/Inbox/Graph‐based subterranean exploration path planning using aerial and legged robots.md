---
Title: Graph‐based subterranean exploration path planning using aerial and legged robots
Authors: Tung Dang, Marco Tranzatto, Shehryar Khattak, Frank Mascarich, K. Alexis, Marco Hutter
Date Published: 2020-11-01
Date found: 2025-06-16
Keywords: Robotics, Path Planning, Aerial Robotcs, legged robots
Link: https://www.semanticscholar.org/paper/Graph%E2%80%90based-subterranean-exploration-path-planning-Dang-Tranzatto/77ecb3756ae32b9615e196bf27668051072b9fbb
DOI: 10.1002/rob.21993
Read status: Read
---

# Data
## Abstract
Autonomous exploration of subterranean environments remains a major challenge for robotic systems. In response, this paper contributes a novel graph‐based subterranean exploration path planning method that is attuned to key topological properties of subterranean settings, such as large‐scale tunnel‐like networks and complex multibranched topologies. Designed both for aerial and legged robots, the proposed method is structured around a bifurcated local‐ and global‐planner architecture. The local planner utilizes a rapidly exploring random graph to reliably and efficiently identify paths that optimize an exploration gain within a local subspace, while simultaneously avoiding obstacles, respecting applicable traversability constraints and honoring dynamic limitations of the robots. Reflecting the fact that multibranched and tunnel‐like networks of underground environments can often lead to dead‐ends and accounting for the robot endurance, the global planning layer works in conjunction with the local planner to incrementally build a sparse global graph and is engaged when the system must be repositioned to a previously identified frontier of the exploration space, or commanded to return‐to‐home. The designed planner is detailed with respect to its computational complexity and compared against state‐of‐the‐art approaches. Emphasizing field experimentation, the method is evaluated within multiple real‐life deployments using aerial robots and the ANYmal legged system inside both long‐wall and room‐and‐pillar underground mines in the United States and in Switzerland, as well as inside an underground bunker. The presented results further include missions conducted within the Defense Advanced Research Projects Agency (DARPA) Subterranean Challenge, a relevant competition on underground exploration.
## Links
https://www.semanticscholar.org/paper/Graph%E2%80%90based-subterranean-exploration-path-planning-Dang-Tranzatto/77ecb3756ae32b9615e196bf27668051072b9fbb

10.1002/rob.21993

framework: file:///home/cbford/Downloads/JFR_GBPlanner.pdf
## Status: Abstract

# Notes

- Introduction
	- exploring subterranean spaces is tough because these spaces are often complex, self similar, sensing degraded, and communication deprived. The terrain is often rough and dynamic. 
	- Still, we want robots in these spaces for things like cave rescue, repair, inspection of infrastructure (subways and sewers), and exploratory/scientific missions on both earth and in space. 
	- Investigation of legged vs. Ariel exploration of these spaces
	- "New Graph-based exploration planner building on bifurcated local and global planning architecture tailed to the underground domain." 
- Related work
	- general problem of exploration path planning is well studied, but focused on outdoor or small interior environments. 
	- Niche community investigating custom solutions to the problem of subterranean exploration
- Problem Statement
	- (copying a lot of this verbatim to look at while I read)
	- Scale necessitates that the planning be hierarchical in nature (global planner vs. local planner)
	- $M$ is a 3D occupancy map of the environment which is incrementally built from measurements of depth sensor $S$, as well as robot poses from localization system $O$
		- the map consists of voxels $m$ of 3 categories. $m \in M_{free}$, $m \in M_{occupied}$, and $m \in M_{unknown}$
		- $M_{NG}$ rare no-go zones including traversability constraints or other imposed limits. 
		- $d_{max}$ is the effective range
		- \[$F_{H}, F_{V}$\] be horizontal and vertical FoV of $S$
		- Robot's configuration at time $t, \xi_t = [x_t, y_t, z_t, \psi_t]$. 
		- $M_{*, res} \subset M_{unknown}$ - residual map with volume $V_{*, res}$ which is infeasible to explore. 
		- Given volume $V_*$, potential explorable volume is $V_{*, explore} = V_* / V_{*, res}$
	- Definition 1: Local Completion
		- Given map $M$ , within a local sub-space $M_L$ of dimensions $D_L$ centered around the current robot configuration, the planner reports "local completion" if $V_{D_L, explored} = V_{D_L} / V_{D_L, res}$ 
	- Definition 2: Global Completion
		- Given the full occupancy map of $M$ of the environment with dimensions $D_G$ and volume $V_{D_G}$, the planner considers "global completion" if $V_{D_G, explored}=V_{D_G} / V_{D_G, res}$ 
		- in practice it is unrealistic to identify $V_{res}$, but you can approximate it
	- Problem 1: Local Exploration Planner
		- Given occupancy map $M$ and a local subset of it $M_L$ and robot config $\xi_0$, find a collision-free and traversability-aware path $\sigma_L={\xi_i}$ to guide the robot towards unmapped areas and maximize an exploration gain defined as the volume which is expected to be mapped when the robot traverses along the path $\sigma_L$ with sensor $S$. A path is admissible if it is collision-free and not going through "no-go" zones that may encode traversability constraints. when "local completion" is reported by this planner, the global planner is to be engaged. 
	- Problem 2: Global Exploration Planner
		- Given the explored and unknown subsets of an occupancy map $M$ of the environment and the current robot configuration $\xi_0$, find a collision-free path $\sigma_G$ leading the robot towards the frontiers of the unmapped areas. Feasible paths of this planning problem must take into account the remaining endurance of the robot. When the environment is explored completely or battery limits are approaching find a path to return to the home location $\xi_{home}$
- Proposed approach
	- local planner
		- balance volumetric gain vs. exploration gain. volumetric gain is exactly what it sounds like- how much new volume is being added to the map. Exploration gain isn't explained well at all. 
	- global planner
		- balance global exploration vs. volumetric gain (including an estimate of new potential frontier)
	- Traversability aware planning with a depth map
	- refine the path to stay further away from obstacles as possible
- Results
	- Simulation
		- included environments believed to be adversarial to SOA exploration planners, like big km long mines - and 15 minutes.
		- GBPlanner outperforms NBVP (should look into that) and Frontier Planning. Frontier planning does not have a comparable performance compared to GBPlanner and NBVP
	- Experimental
		- utilizing a variety of legged and ariel robots
		- planner is robost to a variety of environments and robot forms!
### Summary



## Related Papers
