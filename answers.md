# TP HIL-SERL: report

**Group:** 03

**Students:** BOUDER Chiraz, BRAHIMI Ines, KESSOUAR Abderraouf Tarek

**Date:** 01/10/2026

**Device used (from `check_setup.py`):** cuda / mps / cpu — GPU model if any:

Replace every `...` with your answer. Insert figures from `runs/plots/` with `![caption](runs/plots/<file>.png)`. Keep the report under 6 pages when exported to PDF.

---

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

**Q1.1** ...

**Q1.2** ...

**Q1.3** ...

**Q1.4** Success rate: ... · Mean time to success: ... s · Hardest phase: ...

---

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
