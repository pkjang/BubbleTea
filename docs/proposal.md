---
layout: default
title:  Proposal
---

2.2 Summary of the Project

The idea behind my project is to create an agent that can train itself to maneuver a series of challenging obstacles without failing. 
The plan is to make the course substantially different from a maze for the agent to traverse; it will instead be filled with several
different types of parkour challenges, ranging from 4-block wide jumps to ladder parkour as the standard hurdle. To make it clear as to
what the agent should avoid, the parkour will be hovering above a large area of fire or lava. Therefore the agent will receive a penalty 
whenever it takes damage, or touches those specific blocks. Likewise, it will receive a reward for every other block it touches with a gold block
at the end to indicate the maximum reward for the agent. 



2.3 AI/ML Algorithms

For my project, I will be using reinforcement learning with a linear function approximator, modeling the problem as a Markov Decision Process.



2.4 Evaluation Plan

To quantitatively evaluate the success of my project, I can total up the number of tries and chunk the entire challenge into sections and count the
number of tries it took the agent to complete a section. I can also try to record the amount of time it would take for the agent to finish that section
and use that time to determine if it could finish learning that section under a specified time. Since I plan to make the challenge begin from easy jumps and 
scale to much more difficult jumps, I estimate that the agent would spend at most a few hours trying to learn how to gauge the distance between blocks and angle
to jump. 



Because parkour is mostly straightforward process, where the agent either fails the jump or succeeds in making it, we can qualitatively evaluate the success of the
project by observing how far the agent can complete an ever-increasingly difficult parkour challenge. There will be several jumps focusing on whether a 
specific challenge, like momentum jumps with slime or ice, tight parkour with glass pane or iron bars, or 1 and 2 block "neo" jumps. The goal of the project is to see
how the agent tackles a variety of scenarios in parkour. It would exceed my expectations if the agent were to complete the entire course that I have in mind.



2.5 Appointment with the Instructor

Appointment date and time: Thursday 10/28 at 3:45 PM
