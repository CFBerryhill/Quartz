---
Title: IK Link
Authors: Yeping Wang, Carter Sifferman, Micheal Gleicher
Date Published: 2024-06-01
Date found: 2025-08-21
Keywords:
Link: https://arxiv.org/abs/2402.16154
DOI: "{{DOI}}"
Read status:
Draft:
---
---
year: 2024
authors: Yeping Wang, Carter Sifferman, Micheal Gleicher

--- 
# Data
## Abstract
Many applications require a robot to accurately track reference end-effector trajectories. Certain trajectories may not be tracked as single, continuous paths due to the robot's kinematic constraints or obstacles elsewhere in the environment. In this situation, it becomes necessary to divide the trajectory into shorter segments. Each such division introduces a reconfiguration, in which the robot deviates from the reference trajectory, repositions itself in configuration space, and then resumes task execution. The occurrence of reconfigurations should be minimized because they increase the time and energy usage. In this paper, we present IKLink, a method for finding joint motions to track reference end-effector trajectories while executing minimal reconfigurations. Our graph-based method generates a diverse set of Inverse Kinematics (IK) solutions for every waypoint on the reference trajectory and utilizes a dynamic programming algorithm to find the globally optimal motion by linking the IK solutions. We demonstrate the effectiveness of IKLink through a simulation experiment and an illustrative demonstration using a physical robot.

## Links
https://arxiv.org/abs/2402.16154
## Status: Read

# Notes

Pathwise-IK

Motivation: Reconfigurations suck and we want to minimize the number of times we do them

generate a diverse set of solutions, then use dynamic programming to compute the best arrangement of the sampled solutions from each waypoint that produces the path with the fewest configurations. 


## Related Papers

- [[Relaxed IK]]
- [[Stampede]]
- [[Ranged IK]]
