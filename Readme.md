**MLCAD23-FPGA-Macro-Placement-Contest**

**Evaluation & Ranking:**

-	There are 176 public benchmark designs provided (downloadable from https://www.kaggle.com/datasets/ismailbustany/mlcad2023-fpga-macroplacement-contest/settings)
- There are 60 hidden benchmark designs that will be shared after the conclusion of the contest.
- For each design in the benchmark suite (public or hidden), the macro placers will be ranked based on the contest evaluation metric. The final rank for a placer will be the sum of the individual ranks on all the circuits. The macro placer with the smallest total rank wins the contest.
- The macro placement runtime must 10 minutes or less
- The macro placement must be legal.  That is, macros must be placed on their respective legal sites.
- The placement must be routed by the Vivado© router.  The router must complete the job within 5 hours. The routing is considered failed if the router takes more than 5 hours to finish.
- Score = Routed-WL * (1 + Runtime_Factor)
o	The Vivado© router reports total routed wirelength. This is the base of the score.
o	Total placement (macros and standard cells) and routing runtime will be used in computing P&R_Runtime_Factor;
o	Runtime_Factor = - (Runtime - Median_Runtime) / 10.0 There is 1% scaling factor for every 10% runtime reduction/addition against the median runtime of all place+route solutions;
o	Runtime factor is between -10% and +10%
o	We would like to stress that although runtime is a part of the contest metric, the "Total Routed Wirelength" will be the dominant component. In other words, a placer will not get a significant advantage if it is extremely fast compared to the median runtime of all the placers participating in the contest.
- The run corresponding to a failed place/route task will be assigned the lowest rank on this design. 
- In the presence of multiple failures, the break-tie factors are the following: Placer failure or router failure, router runtime, number of unrouted nets, number of illegal placements
