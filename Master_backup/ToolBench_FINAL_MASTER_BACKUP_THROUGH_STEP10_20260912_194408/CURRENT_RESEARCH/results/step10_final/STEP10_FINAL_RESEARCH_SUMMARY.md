# Final Research Results Synthesis

## Failure Taxonomy

The final ToolBench annotation set contains **4,000 trajectories**. Overall failure prevalence is **86.22%**.

- Intent Misunderstanding: 943 (23.57%)
- Wrong Tool Selection: 834 (20.85%)
- Parameter Hallucination: 745 (18.62%)
- Execution/Cascading Error: 927 (23.18%)
- No Failure: 551 (13.78%)

## Human Validation

The blind human audit matched **300 trajectories**. Exact human–LLM agreement was **40.67%** with **Cohen's κ = 0.2545**.

The low agreement is retained as an explicit methodological limitation; the automated labels are not presented as human ground truth.

## Failure Scaling

ToolBench failure rate changes from **55.99%** at depth **2** to **94.12%** at depth **14**.

The preferred scaling model is **Power Law**, with ΔAIC = **72.4484** relative to the alternative model.

## Failure Propagation

The first-order Markov model achieved **Macro-F1 = 0.8822**, while the LSTM achieved **Macro-F1 = 0.4609**.

The Markov result must be interpreted with the Step-8 onset-persistence proxy limitation: the per-turn states were derived from trajectory-level failure annotations rather than independently annotated at every turn.

## Cross-Benchmark Validation

ToolHop contains **300 annotated trajectories**, with a failure rate of **73.67%**.

ToolBench favored **Power Law** scaling and ToolHop favored **Power Law** scaling.

The overlapping-depth curves have similarity **0.8826**, Pearson **r = 0.8507 (p = 0.003651)**, and Spearman **ρ = 0.8008 (p = 0.009508)**.

The failure-depth distributions differ significantly (KS D = **0.3995**, p = **2.29511e-30**), indicating that benchmark depth distributions differ even though failure-depth scaling patterns are strongly associated.

## Main Conclusion

The experiments support the conclusion that tool-calling failure probability generally increases with trajectory depth. The preferred power-law relationship observed in ToolBench also appears in ToolHop, providing cross-benchmark evidence that the scaling pattern is not unique to one benchmark. The conclusion remains bounded by automated taxonomy labeling, low human–LLM agreement, different depth definitions across benchmarks, and the Step-8 proxy-state construction.

## Safeguards and Limitations

- Final ToolBench analysis uses the 4,000 Step-4 annotations.
- ToolHop analysis uses the 300 Step-9C annotations.
- ToolHop gold answers were hidden from the failure judge.
- Bootstrap confidence intervals are used for failure-rate estimates.
- Power-law and exponential models are compared by AIC/BIC.
- Cross-benchmark curve comparison is restricted to overlapping observed depths.
- KS tests are interpreted as depth-distribution comparisons, not equality tests of scaling functions.
- ToolBench and ToolHop trajectory-depth definitions are not treated as exactly equivalent.
- Step-8 Markov/LSTM states use the documented onset-persistence proxy.
- The original ToolBench 37,320-row validation split remains untouched.