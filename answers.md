# TP HIL-SERL: report

**Group:** 03

**Students:** BOUDER Chiraz, BRAHIMI Ines, KESSOUAR Abderraouf Tarek

**Date:** 01/10/2026

**Device used (from `check_setup.py`):** cuda / mps / cpu — GPU model if any:

Replace every `...` with your answer. Insert figures from `runs/plots/` with `![caption](runs/plots/<file>.png)`. Keep the report under 6 pages when exported to PDF.

-----------------------------
----------------

## Part 1: Discover the environment

**Human trials (1.2)**

| Operator | Attempt | Success (y/n) | Time (s) | What went wrong |
| --- | --- | --- | --- | --- |
| Ines | 1 | y | 13.1 | Nothing |
| Ines | 2 | y | 27.8| Nothing |
| Ines | 3 | n | 6.1 | The gripper was not correctly aligned |
| Ines | 4 | n | 23.6| The gripper pushed the cube away |
| Ines | 5 | y | 16.4 | Nothing |
| Raouf | 1 | y | 26.7 | Nothing |
| Raouf | 2 | n | 29.9 | Timeout |
| Raouf | 3 | n | 29.9 | Timeout |
| Raouf | 4 | y | 13.0 | Nothing |
| Raouf | 5 | y | 21.0 | Nothing |

**Q1.1** The observation space is a dictionary containing two RGB images, front and wrist, both of size 128×128×3, and an 18-dimensional numerical state vector agent_pos. The normalization ranges suggest that the first values describe the robot end-effector's position and orientation, while the remaining values contain additional robot/environment state variables. The exact semantic meaning of some of these values cannot be determined from the ranges alone.

The raw simulator uses a 7-dimensional continuous action space with values in [-1,1]. However, after the TP's wrappers, the agent sees a 4-dimensional action space: (dx, dy, dz, gripper).where \(dx,dy,dz\) are continuous values in \([-1,1]\) controlling the displacement of the robot's end effector along the three spatial axes. The gripper command ranges from 0 to 2 and controls the gripper.

In contrast, the raw simulator exposes a 7-dimensional continuous action space, with all seven values ranging from \([-1,1]\). The TP wrappers therefore transform the agent's simpler 4-dimensional, end-effector-level commands into the 7-dimensional commands required by the simulator. This gives the RL agent a higher-level control interface instead of requiring it to directly learn the simulator's lower-level 7-dimensional control.

---------------------------------------------------------


**Q1.2** this approach simplifies the RL because simplifies RL because the agent does not need to learn how to move each joint. It directly says: “move the end-effector by (dx, dy, dz).”

Internally, the robot must:

1- Convert (dx, dy, dz) into joint movements.

2- Send those joint commands to the motors.

3- Execute the movement.
----------------------------------------------------------------------------

**Q1.3** We get a reward when we catch the cube, we get 1 when we catch the cube, otherwise we get 0, the reward is sparse 

The problem is that we only tell the robot that it did good when it grabs the cube, we don't tell it that it is doing better if it gets closer to the target. So if it never grabbed the object, it will NEVER learn 

--------------------------------------------------------------------

**Q1.4** 
· Success rate: 60% 

· Mean time to success: 19.7 s 

· Hardest phase: to grab the cube with the gripper

---
-----------------
## Part 2: Record demonstrations

Episodes recorded: ... · Successful: ... · Mean length: ... s

**Q2.1** ...

**Q2.2** ...

**Q2.3** ...

---

## Part 3: RL baseline without interventions

**Q3.1** ...

**Q3.2** ...

**Q3.3** ...

**Q3.4** ...

**Q3.5** γ¹⁰⁰ = ... · Implication: ...

---

## Part 4: HIL-SERL with interventions

![noHIL vs HIL](runs/plots/GROUP_noHIL_vs_HIL.png)

| Run | First success (min) | Min to rolling reward ≥ 0.8 | Interventions | Human effort (s) |
| --- | --- | --- | --- | --- |
| noHIL | | | — | — |
| HIL | | | | |

**Q4.1** ...

**Q4.2** ...

**Q4.3** Metric proposed: ... · Value for our HIL run: ...

**Q4.4** ...

**Q4.5** ...

---

## Part 5: Experiment ___

**Q5.1 Hypothesis (written before the run):** ...

![HIL vs experiment](runs/plots/GROUP_HIL_vs_expX.png)

| Run | First success (min) | Min to rolling reward ≥ 0.8 | Interventions | Human effort (s) |
| --- | --- | --- | --- | --- |
| HIL (first 20 min) | | | | |
| exp ___ | | | | |

**Q5.1 Result:** ...

**Q5.2** ...

---

## Part 6: Class comparison

![Class results](runs/plots/class_results.png)

**Q6.1** ...

**Q6.2** ...

**Q6.3** ...

**Q6.4** ...

**Q6.5** ...
