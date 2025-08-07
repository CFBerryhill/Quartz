---
Title: Ranged IK
Authors: Yeping Wang, Pragathi Praveena, Daniel Rakita, Micheal Gleicher
Date Published: 2023-02-27
Date found: 2025-08-07
Keywords: Robotics, Planning
Link: https://arxiv.org/abs/2302.13935
DOI: 
Read status: Read
Draft:
---
# Data
## Abstract
Generating feasible robot motions in real-time
requires achieving multiple tasks (i.e., kinematic requirements)
simultaneously. These tasks can have a specific goal, a range
of equally valid goals, or a range of acceptable goals with
a preference toward a specific goal. To satisfy multiple and
potentially competing tasks simultaneously, it is important
to exploit the flexibility afforded by tasks with a range of
goals. In this paper, we propose a real-time motion generation
method that accommodates all three categories of tasks within
a single, unified framework and leverages the flexibility of
tasks with a range of goals to accommodate other tasks. Our
method incorporates tasks in a weighted-sum multiple-objective
optimization structure and uses barrier methods with novel loss
functions to encode the valid range of a task. We demonstrate
the effectiveness of our method through a simulation experiment
that compares it to state-of-the-art alternative approaches, and
by demonstrating it on a physical camera-in-hand robot that
shows that our method enables the robot to achieve smooth and
feasible camera motions.
## Links
https://arxiv.org/abs/2302.13935

## Status: Read


# Notes

### Summary

The primary contribution seems to be the variety of Loss functions associated with the tasks. (groove, swamp, swamp-groove, etc.). These loss functions allow for more flexible planning, leading to lower overall joint wear and smoother more feasible motion. 

## Related Papers

- IK Link
- Relaxed IK
- Trac IK
- IK Flow