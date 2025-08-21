### Jacobian Matrix

A matrix that describes how the robot moves with time. Used in Optimization based IK Solvers. 
### Degrees of Freedom
An object in the physical world has up to 6 *cartesian* Degrees of Freedom (DoF). \[x, y, z] and \[pitch, yaw, roll].

A mechanical DoF refers to the number of points of actuation a robot has. A robot arm with 3 joints and 2 extenders has 5 degrees of freedom, for instance.

Carteisan DoF are easily limited - the end effector must exist only within this plane (limiting to just 5 degrees of freedom). 
### Redundancy

given:
$n$ - the number of [[2.3 Degrees of Freedom|DoF]] in joint space 
$m$ - the number of [[2.3 Degrees of Freedom|DoF]] in task space 

- $n<m$ - The Robot is *under-actuated* and the problem is kinematically deficient. The Jacobian $J$ is "wide" and the only way to solve the inverse kinematics problem is through the pseudo inverse $J^+$
- $n=m$ - The Robot is *fully actuated*. The Jacobian $J$ is square and full rank meaning that the forward kinematics equation is directly invertible. The world is great!
- $n>m$ - The Robot is *over-actuated* and the problem is kinematically redundant. the only way to solve the problem is through the psuedo-inverse. The redundancy is a benefit though -  it means there are more solutions for each desired pose. The human arm, for example, is over-actuated with 7 DoF (3 in the shoulder and wrist, 1 in the elbow) in a 6 DoF task space (3d real space)

### Task Space
The Robot's work space. A robot arm's task space might be a hemisphere around its base, whereas a mobile robot's task space might be a room or building or world.
### Configuration/Joint Space
The space of all valid robot configurations. A robot configuration is defined as a vector of joint positions.
### Null Space

The set of all possible solutions for some IK task. A redundant robot with 7 DoF which has 6 DoF in task space will have infinite solutions for a given end effector Pose. 


