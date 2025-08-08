---
Title: IK Flow
Authors: Barrett Ames, Jeremy Morgan, George Konidaris
Date Published: 2021-11-17
Date found: 2025-08-08
Keywords: Inverse Kinematics, Robotics
Link: https://arxiv.org/abs/2111.08933
DOI: arXiv:2111.08933
Read status: Read
Draft:
---
# Data
## Abstract
Inverse kinematics - finding joint poses that reach a given Cartesian-space end-effector pose - is a common operation in robotics, since goals and waypoints are typically defined in Cartesian space, but robots must be controlled in joint space. However, existing inverse kinematics solvers return a single solution pose, where systems with more than 6 degrees of freedom support infinitely many such solutions, which can be useful in the presence of constraints, pose preferences, or obstacles. We introduce a method that uses a deep neural network to learn to generate a diverse set of samples from the solution space of such kinematic chains. The resulting samples can be generated quickly (2000 solutions in under 10ms) and accurately (to within 10 millimeters and 2 degrees of an exact solution) and can be rapidly refined by classical methods if necessary.
## Links

https://arxiv.org/abs/2111.08933
## Status:  Read

# Notes

TLDR;  Utilize a particular kind of neural network to generate a large number of samples of the solution space to an IK problem for a redundant robot.

I have a lot of lingering questions about some of the intuition behind things like the shape of the manifolds this paper suggests are true about IK solution spaces, and also understanding 90% of the neural network stuff. 

## Related Papers

- TRAC-IK ?
