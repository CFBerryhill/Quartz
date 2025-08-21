
## Pose-Wise

[[Ranged IK]]
[[Relaxed IK]]

Solving for a single end effector pose. 

Input: A Robot $F$ and a goal $c$
Output: A set of joint configurations $q$ such that

$$F(q) = c$$
Typically done using optimization. 
## Path-Wise

[[Stampede]]

Solving for a path. 

Input: A path in Task Space $T$ with elements $t_i$
Output: A path in Configuration Space $Q$ such that each configuration $q_i$ maps to $t_i$ and is feasible.
### Sampling

[[IK Flow]]
[[Stampede]]

A useful tool for Path-Wise IK to find better solutions. Stampede, for instance, selects waypoints along the path and samples many possible point-wise solutions. 