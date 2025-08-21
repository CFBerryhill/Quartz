Date: 08/21/25

[[Ranged IK]]

An IK solution sampler needs the following properties:
1. Speed
	1. A fast sampler can be used for real-time path-wise solvers
2. Quality
	1. The sampled solutions should be Valid.
	2. The sampled solutions should be Diverse. As in, as Diverse as possible, ideally uniformly sampled.
### 1. Perturbed Starting position 

This is an intuitive option. The idea is that you take some solver like [[Ranged IK]] and have it solve for a given pose $c$ over and over again, changing the inital configuration $q$ each time to try to find different solutions $t$. 

The main problem is that the distance between inital configurations $q_0, q_1$ will not necessarily match the distance between solutions $t_0, t_1$. With sufficiently dense sampling you might end up with practically useful distance between solutions, but it's expensive.  
### 2. [[IK Flow]]

IK Flow uses a neural network trained on many Perturbed starting positions to identify how to sample diverse solutions quickly. Unfortunately, it does not provide any guarantees of diversity. i.e. no missing regions. It does promise speed, though. 