# Experiment 1: virus_antibody - parameter sweep: endemic corridors

Prompt 1 - 21 March 2026, 4:25 PM

```
grab github.com/mesa/mesa-examples;

for the virus_antibody model, perform a parameter sweep, we are looking for a meta-stable / endemic path, test parameters, combinations; hypothesize relationships between parameters that lead to endemic paths, test those. Keep a log of all experiments in case of timeouts. Write a markdown report, including suggestions for further research
```

[report](/virus_antibody_sweep_report.md)

Output

```
Now let me write a comprehensive parameter sweep script:Excellent! Full sweep complete. Now let me analyze the results and build the report:Now let me write the full markdown report:Here's a summary of what was done and found.

---

## What was run

**1,899 total simulation runs** across two phases:

- **Phase 1 (broad sweep):** 576 parameter combinations × 3 replicates (1,728 runs). Grid over 5 parameters: `antibody_duplication_rate`, `virus_duplication_rate`, `virus_mutation_rate`, `initial_antibody`, `initial_viruses`
- **Phases 2A–D (focused hypotheses):** 4 targeted experiments testing specific relationships (57 combos × 3 reps)

---

## Key findings

**Endemic runs are rare but real** — only ~5.6% of Phase 1 combos produced any endemic outcome. The space is dominated by immune victory (~64%) or population explosion (~28%).

**The endemic corridor requires three conditions simultaneously:**

1. **Low absolute duplication rates** (≤ 0.010 for both)
2. **Virus duplication ≈ 1–2× antibody duplication** — viruses need a mild replication edge, but not a runaway one
3. **High mutation rate (μ ≥ 0.10)** — this is the decisive factor; it continuously generates novel DNA variants that outpace antibody memory propagation

**Most robust single configuration:** `(ab_dup=0.010, v_dup=0.010, μ=0.20, A₀=10, V₀=20)` — the only one achieving **3/3 replicates endemic_stable**.

**Surprise:** perfectly balanced rates (Hypothesis A) and an antibody advantage (Hypothesis B) both failed to produce endemicity — the model's memory system is effective enough that any antibody edge resolves the infection. The virus needs a *slight* duplication edge, combined with mutation fast enough to stay ahead of memory sharing.

The full 1,899-run experiment log (with complete time series) is attached for further analysis.
```

