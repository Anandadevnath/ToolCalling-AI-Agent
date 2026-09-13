TOOLBENCH FINAL MASTER RESEARCH BACKUP
======================================

Backup name:
ToolBench_FINAL_MASTER_BACKUP_THROUGH_STEP10_20260912_194408

Created:
2026-09-12T19:44:17.149692+06:00

Timezone:
Asia/Dhaka

Research status:
STEPS 1–10 COMPLETE

Primary research:
How Tool-Calling Agents Fail as Reasoning Chains Grow:
A Large-Scale Taxonomy and Scaling Analysis of Multi-Hop Failure Propagation

PRIMARY DATASET
---------------
ToolBench-v1

Cleaned dataset:
186,597 trajectories

80% research/training split:
149,277 trajectories

Original untouched 20% validation split:
37,320 trajectories

STEP 3
------
23 engineered structural features.

STEP 4
------
Final GPT-OSS taxonomy annotations:
4,000 trajectories

Human Gold:
300 trajectories

Human/LLM exact agreement:
40.67%

Cohen Kappa:
0.2545

Final 4K taxonomy:
Intent Misunderstanding      943
Wrong Tool Selection         834
Parameter Hallucination      745
Execution/Cascading Error    927
No Failure                   551

Overall ToolBench failure rate:
86.22%

STEP 5
------
Sequential pattern mining / association analysis / clustering experiments.

STEP 6
------
XGBoost failure prediction.
Human Gold excluded from development.
Train / validation / test:
2590 / 555 / 555
Human Gold audit:
300

STEP 7
------
Failure rate vs trajectory depth with bootstrap 95% confidence intervals.

ToolBench depth range:
2–14

Best scaling model:
Power Law

Power Law AIC:
216.084564

Power Law BIC:
228.672663

Delta AIC vs Exponential:
72.448383

STEP 8
------
Failure propagation modeling.

First-order Markov Chain:
Macro-F1 = 0.8822

LSTM + MiniLM:
Macro-F1 = 0.4609

IMPORTANT:
Step8 uses an onset-persistence proxy constructed from trajectory-level failure annotations.
These are NOT independently human-annotated per-turn failure states.

STEP 9
------
Cross-benchmark validation using ToolHop.

ToolHop trajectories:
300

Failures:
221

No Failure:
79

Failure rate:
73.67%

ToolHop best scaling model:
Power Law

Cross-benchmark curve similarity:
0.882596

Pearson r:
0.85066

Pearson p:
0.003651

Spearman rho:
0.800757

Spearman p:
0.009508

Failure-depth KS statistic:
0.399533

Failure-depth KS p:
2.295111e-30

IMPORTANT:
ToolBench depth = ToolBench trajectory step_depth.
ToolHop depth = actual generated tool-call count.
These depth definitions are NOT exactly equivalent.

STEP 10
-------
Final results synthesis and publication visualizations complete.

Safeguards:
- Original ToolBench 37,320-row validation split remains untouched.
- Low human/LLM agreement is retained transparently.
- ToolHop automated labels are not represented as human labels.
- Step8 proxy-state limitation is documented.
- ToolBench and ToolHop depth definitions are not treated as identical.

BACKUP CONTENT
--------------
SOURCE_MASTER_BACKUP/
    Immutable Master_backup copied from Kaggle New_backup.

CURRENT_RESEARCH/
    Complete current /kaggle/working/toolbench_research directory.

BACKUP_METADATA/
    README
    validation report
    file manifest
    important-file audit
    backup summary

This backup was created after successful completion of Step 10.
