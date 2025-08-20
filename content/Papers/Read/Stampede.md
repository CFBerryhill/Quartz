---
Title: Stampede
Authors: " Daniel Rakita, Bilge Mutlu, Michael Gleicher"
Date Published: 2019-05-01
Date found: 2025-08-18
Keywords: 
Link: https://graphics.cs.wisc.edu/Papers/2019/RMG19/
DOI: https://doi.org/10.1109/ICRA.2019.8793617
Read status: Once Over
Draft:
---
---
year: 2019
authors: Daniel Rakita, Bilge Mutlu, Michael Gleicher

--- 

### Stampede
# Data
## Abstract
We present a discrete-optimization technique for finding feasible robot arm trajectories that pass through provided 6-DOF Cartesian-space end-effector paths with high accuracy, a problem called pathwise-inverse kinematics. The output from our method consists of a path function of joint-angles that best follows the provided end-effector path function, given some definition of "best". Our method, called Stampede, casts the robot motion translation problem as a discrete-space graph-search problem where the nodes in the graph are individually solved for using non-linear optimization; framing the problem in such a way gives rise to a well-structured graph that affords an effective best path calculation using an efficient dynamic-programming algorithm. We present techniques for sampling configuration space, such as diversity sampling and adaptive sampling, to construct the search-space in the graph. Through an evaluation, we show that our approach performs well in finding smooth, feasible, collision-free robot motions that match the input end-effector trace with very high accuracy, while alternative approaches, such as a state-of-the-art per-frame inverse kinematics solver and a global non-linear trajectory-optimization approach, performed unfavorably.
## Links

https://graphics.cs.wisc.edu/Papers/2019/RMG19/
https://doi.org/10.1109/ICRA.2019.8793617
## Status: Once Over

# Notes

Pathwise-IK. Take waypoints along the path and solve with no look ahead. 

## Related Papers


