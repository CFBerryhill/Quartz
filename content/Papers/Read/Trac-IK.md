---
Title: Trac-IK
Authors: Patrick Beeson, Barrett Ames
Date Published: 2015-11-01
Date found: 2025-08-12
Keywords: 
Link: https://dl.acm.org/doi/10.1109/HUMANOIDS.2015.7363472
DOI: "{{DOI}}"
Read status: 
Draft:
---
---
year: 2015
authors: Patrick Beeson, Barrett Ames

--- 

### Trac-IK
# Data
## Abstract
The Inverse Kinematics (IK) algorithms implemented in the open-source Orocos Kinematics and Dynamics Library (KDL) are arguably the most widely-used generic IK solvers worldwide. However, KDL's only joint-limit-constrained IK implementation, a pseudoinverse Jacobian IK solver, repeatedly exhibits false-negative failures on various humanoid platforms. In order to find a better IK solver for generic manipulator chains, a variety of open-source, drop-in alternatives have been implemented and evaluated for this paper. This article provides quantitative comparisons, using multiple humanoid platforms, between an improved implementation of the KDL inverse Jacobian algorithm, a set of sequential quadratic programming (SQP) IK algorithms that use a variety of quadratic error metrics, and a combined algorithm that concurrently runs the best performing SQP algorithm and the improved inverse Jacobian implementation. The best alternative IK implementation finds solutions much more often than KDL, is faster on average than KDL for typical manipulation chains, and (when desired) allows tolerances on each Cartesian dimension, further improving speed and convergence when an exact Cartesian pose is not possible and/or necessary.
## Links
https://dl.acm.org/doi/10.1109/HUMANOIDS.2015.7363472
## Status: Read

# Notes

Standard IK stuff, but with the power of analytical solving we can get better and faster solutions than numerical solvers.

## Related Papers

