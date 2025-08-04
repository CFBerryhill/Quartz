---
Title: "Semantic Belief Behavior Graph: Enabling Autonomous Robot Inspection in Unknown Environments"
Authors: Muhammad Fadhil Ginting; David D. Fan; Sung-Kyun Kim; Mykel J. Kochenderfer; Ali-Akbar Agha-Mohammadi
Date Published: 2024-07-01
Date found: 2025-06-16
Keywords: Planning, Robotics, Inspection
Link: https://arxiv.org/abs/2401.17191
DOI: 
Read status: Read
---
# Data
## Abstract
This paper addresses the problem of autonomous robotic inspection in complex and unknown environments. This capability is crucial for efficient and precise inspections in various real-world scenarios, even when faced with perceptual uncertainty and lack of prior knowledge of the environment. Existing methods for real-world autonomous inspections typically rely on predefined targets and waypoints and often fail to adapt to dynamic or unknown settings. In this paper, we introduce the Semantic Belief Behavior Graph (SB2G) framework as a new approach to semantic-aware autonomous robot inspection. SB2G generates a control policy for the robot, using behavior nodes that encapsulate various semantic-based policies designed for inspecting different classes of objects. We design an active semantic search behavior to guide the robot in locating objects for inspection while reducing semantic information uncertainty. The edges in the SB2G encode transitions between these behaviors. We validate our approach through simulation and real-world urban inspections using a legged robotic platform. Our results show that SB2G enables a more efficient object inspection policy, exhibiting similar behaviors comparable to human-operated inspections.

## Links
https://arxiv.org/abs/2401.17191

## Status: Read


## Notes

### Summary

SB2G utilizes off the shelf object detecting CV work like YOLO and a finite-state machine to achieve faster and more in-depth inspection of target objects within an environment than a baseline like Geometric coverage. 
### Breakdown

- Introduction
	- planning using semantic information 
		- looks like some useful references might exist here
	- planning and decision-making using semantic information for autonomous robot inspection
		- Seems super relevant!
	- must address:
		- perceptual uncertainty from semantic detection
		- locating the semantic objects with absence or limited prior knowledge
		- integrating semantic information into planning/control
	- SB2G
		- geometric and semantic information of objects of interest
		- semantic search behavior to acquire better semantic information
		- Graph governs transitions between behavior nodes, triggered by attaining sufficient belief confidence
	- Results
		- can autonomously preform inspections in real world environments without prior knowledge of the map or object locations. 
- Related work
	- Planning
	- Semantic Active Mapping
	- Semantic-based task planning
- Problem Formulation
	- Robot and geo-semantic st
		- robot state: $x_k \in X$
			- $x_k = (x^p, x^q, x^a)$
				- $x^p \in R^3$ is position 
				- $x^q \in SO(3)$ is orientation
				- $x^a$ internal state
		- objects geo-semantic state: $y_k \in Y$
			- $y_k$ represents $N$ objects $y_k = {y_{1k}, y_{2k},..., y_{Nk}}$
			- $y_{ik} = (y^p, y^q, y^l, y^a)$ where 
				- $y^p$ is position
				- $y^q$ is orientation
				- $y^l$ is its class
				- $y^a$ is the affordance status
					- some metadata including its status such as "to be inspected" or "to be ascended"
		- time: $k$
	- Robot control and transition model
		- Control input: $u_k \in U$ 
		- Process noise: $w_k$
		- State evolution model: ($x_{k+1} + y_{k+1} = f(x_k, y_k, u_k, w_k)$)
	- Geo-semantic observation variable and model
		- the state of $y_k$ is only partially observable. If an object $y_{ik}$ is observable then an observation can be obtained
		- $z_k \in Z$ is an observation
			- $z_k = (z^p, z^q, z^l, z^s)$
				- $z^p$ is measured position
				- $z^q$ is measured orientation
				- $z^l$ is detected class
				- $z^s$ is confidence score
		- The observation model therefore is $z_k=h(x_k, y_k, v_k)$ where $v_k$ is observation noise.
	- Belief
		- a belief state $b_k \in B$ is a conditional probability distribution $b_k = p(x_k, y_l | H_k)$ over the history of observations and control inputs up to time $k$. $b_k$ is the basis for decision making
		- Belief model: $b_{k+1}= \tau(b_k, u_k, z_{k+1})$
	- Policy, reward, and cost
		- Policy: $u_k = \pi(b_k)$
		- To find an optimal policy, there are semantic task rewards and costs
		- The robot gets a reward when it successfully inspects objects, climbs stairs or enters doors, and cost includes distance traveled by the robot. 
	- **Problem 1:** find the optimal inspection policy $\pi$
- Semantic Belief Behavior Graph
	- nodes represent distinct robot behaviors, edges denote transition conditions similar to a finite state machine
	- Belief representation and prediction
		- A belief spans over the robots position, and all objects identification (is the object there?) and classification (what is it?)
		- Observation model
		- state transition model
		- belief prediction model
	- Semantic based behavior
		- Object inspection
			- behavior for close-range inspection, defined on a per-object basis. $pi^{inspect-door}$, for instance
		- Stair climbing
			- crucial for being able to inspect urban environments
	- Active semantic search behavior
		- achieving high-confidence estimates of object state is challenging due to perceptual uncertainties. active semantic search guides the robot to perform actions to increase confidence in a belief. 
		- **Problem 2:** finding a policy to increase belief about the state of a target object 
		- 2 simplifying assumptions
			- the transition model is deterministic (noise is 0)
			- sparse sampling to reduce the search branching factor
	- Behavior transition
		- Trigger conditions
			- Consider edges that transition from
			- 1.  From active semantic search behaviors to semantic-based behaviors $\pi^{i-l}$ Trigger condition occurs when $b_k$ is in the set of beliefs $B^l$ that ensures the robot will  complete the semantic-based behaviors correctly
			- 2. From Active semantic search to geometric coverage. Trigger condition occurs when $b_k \in B^a$
			- 3. From geometric coverage to active semantic search. Trigger condition occurs when it detects an uninspected object $y_i$ and the current belief is in $B^{search-l}$. the set $B^{search-l}$ consists of beliefs having low-confidence object probabilities such that active semantic search would effectively reduce uncertainty. 
			- 4. From semantic-based behaviors to geometric coverage. Triggered when the robot has successfully completed the semantic task. 
		- Planning
			- There is a nice little algorithm included in the paper (Algorithm 1) that I won't bother copying here. 
- Experimental results
	- Simulation
		- Gazebo sim with BD Spot. 10 semantic objects
		- compared with geometric coverage and geometric coverage + inspection
		- SB2G looks to have a much smoother path, and a lot less wasted time. as well as more inspected objects at closer range. 
	- Field tests
		- Human vs. SB2G
		- Human took a very similar path for search and inspection.
		- Humans had less travel distance and inspected more quickly, because they can identify targets more quickly. 



## Related Papers

- Possible references to look at:
	- 1: Automatic inspection data collection of building surface based on BIM and UAV
	- 14: Adaptive coverage path planning for efficient exploration of unknown environments
	- 20:Autonomous exploration and simultaneous object search using aerial robots
	- 21:Semantics-aware receding horizon planner for object-centric active mapping
	- 22:Semantics-aware exploration and inspection path planning