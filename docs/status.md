---
layout: default
title: Status
---

Project Summary:
The goal of the project is still to navigate a series of jumps to reach a diamond block at the end of the challenge 
using environment observers. The agent should be able to control its own speed, direction, and jump inputs to safely
land on every subsequent iron block.



Approach:
My current approach to implementing a parkour agent requires using a rectangular box drawn around the agent to detect nearby blocks that
it is able to jump to. For the sake of simplicity and to avoid getting stuck moving between two blocks infinitely, I only allowed the agent 
to move forward toward whatever blocks were in the view of the agent before every jump. To achieve this, I drew a 4x8x3 rectangular
box in front of the agent to detect iron blocks. The agent would then pick the closest one out of all the blocks it detects to attempt the jump.
This would also mean that the test cases I create for the agent needed to be handpicked in that I could not allow wide angles in between jumps.

The 3D rectangle drawn in front of the agent is returned as a single dimensional array, mainly due to the nature of loading observations into a
JSON file. We can map each cell in the one-dimensional array to each position in the rectangular box by dividing and modding the array length by
the box's dimension. Rather than computing the exact Euclidean distance to each block, I "flatten" the box so that the agent only considers the
block distance using its x and z coordinates.



Evaluation:
While this approach does work for the purpose of getting the agent across the parkour challenge safely, it fails to provide any useful representations
of the agent "learning" to overcome challenges that it faces. Using a direct mapping of observations gives the agent sight and knowledge that it should
not have had to begin with. With my current approach it would mean that the agent would determine the kind of input required to make the jump using a set
of hard-coded movements. It also means that the agent actually does not make errors in its jumps because it eliminates all chances of errors occurring from
the grid JSON.



Remaining Goals and Challenges:
For the following weeks, I will be trying to implement a proper reinforcement learning approach to the agent. Currently
the agent is able to navigate through the parkour course mainly due to using the observation grid feature from the xml file.
This sort of approach does not actually allow the agent to learn through trial and error and instead will preprocess nearby
blocks before attempting a jump. However, I expect that it will be challenging since the agent will have to be able to gauge
jumps by its distances and determine the kind of input required to make the jump. The agent might also fail to finish the parkour
challenge before Minecraft runs out of memory, an error that I have already encountered by letting the agent run for too long.

Another challenge that I hopefully would like to reach is adding more complex obstacles like ladders, slime blocks, and glass panes
or iron bars for the agent to overcome. I would assume it would be difficult to train the agent to learn how to maneuvor such obstacles
mainly because it would require a different technique than normal block-to-block jumps. 



Resources Used:
Malmo depth_maze_runner.py example
Malmo block_type_test.py example
