---
Title: A novel robot co-worker system for paint factories without the need of existing robotic infrastructure
Authors: Rafael Rey, J. A. Cobano, Marco Corzetto, L. Merino, P. Alvito, F. Caballero
Abstract: This paper presents a human–robot co-working system to be applied to industrial tasks such as the production line of a paint factory. The aim is to optimize the picking task with respect to manual operation in a paint factory. The use of an agile autonomous robot co-worker reduces the time in the picking process of materials, and the reduction of the exposure time to raw materials of the worker improves the human safety. Moreover, the process supervision is also improved thanks to a better traceability of the whole process. The whole system consists of a manufacturing process management system, an autonomous navigation system, and a people detection and tracking system. The localization module does not require the installation of reflectors or visual markers for robot operation, significantly simplifying the system deployment in a factory. The robot is able to respond to changing environmental conditions such as people, moving forklifts or unmapped static obstacles like pallets or boxes. The system is not tied to specific manufacturing orders. It is fully integrated with the manufacturing process management system and it can process all possible orders as long as their components are placed into the warehouse. Real experiments to validate the system have been performed in a paint factory by a real holonomic platform and a worker. The results are promising from the evaluation of performance indicators such as exposure time of the worker to raw materials, automation of the process, robust and safe navigation, and the assessment of the end-user.
Date Published: 2020-09-01
Date found: 2025-06-16
Keywords: 
Link: https://www.sciencedirect.com/science/article/abs/pii/S0736584521000089?via%3Dihub
DOI: 10.1016/J.RCIM.2021.102122
Read status: Abstract
---
## Notes

- Introduction
	- "one of the most important challenges of the smart factories is the deployment of robots that operate alongside workers"
	- Most modern factories have "fences" between robots and workers - a serious limitation
	- check out references [3], [4], [5].

Contributions:

> 1. Implementation of a robot co-worker system in a paint factory, fully integrated into the business process.
> 2. Implementation of an autonomous AGV navigation system able to operate in a factory without the need of cables, line-painting or RFID installation in the floor.
> 3. Implementation of an Ultra Wide Band (UWB) localization system for people detection that provides new capabilities for robot situation awareness and, together with robot onboard sensors, avoids the separation of robot and human workers.
> 4. Improvement of the original Lazy Theta* path planning algorithm in order to foster safety instead of the classical optimal-length path.
> 5. Low computation time of the algorithms implemented in order to ensure safety when obstacles or unexpected events take place.
> 6. Experimental validation with the real platform performed in a real paint factory involving actual operators/workers.

- State of the art
	- Wow this section is chalk full of really useful references - post processing work is adding all these references to the "pile"

- The Robot
	- Some technical mechanical details - upshot is that its omnidirectional
	- Software - ROS
		- Path planning, sensing and tracking, multiple sesnors. Fig 3 shows the outline
		- Fig 4 - Human machine interaction

- Tons of useful technical information I'm skipping over in favor of finding the upshot

- The upshot:
	- It does the thing to great effect, seemingly

Paper focuses very heavily on technical details of the implementation - very little on the Human/Robot interaction and the actual working relationship

### Summary


## References to add to the pile

- Human-Robot Similarity and Willingness to Work with a Robotic Co-worker
	- https://dl.acm.org/doi/abs/10.1145/3171221.3171281
- Evaluation of automatic guided vehicle systems
	- ancient, but probably worth a once over for building my own knowledge / context
	- https://www.sciencedirect.com/science/article/pii/S073658450800029X
- A novel scheduling method for automated guided vehicles in workshop environments
	- https://journals.sagepub.com/doi/10.1177/1729881419844152
- TIREBOT: A collaborative robot for the tire workshop
	- https://www.sciencedirect.com/science/article/pii/S073658451830320X
- A Visualization of Human Physical Risks in Manufacturing Processes Using BPMN
	- https://link.springer.com/chapter/10.1007/978-3-319-74030-0_58
- MIT: Probablistic Robotics (Ancient, but good for building my knowledge)
## Related Papers
