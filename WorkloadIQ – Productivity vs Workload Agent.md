# 🧭 WorkloadIQ

AI agent for Infosys-style delivery units: why are hours rising while productivity falls? (Synthetic illustrative data – not real Infosys figures.)

## Company trend: hours vs. output per hour (12 weeks)

## Agent: ask

Select a question. The agent reasons over the scores computed below.

## Team analysis (click a row)

## Team detail

## What-if: workload intervention

Cut overtime by **0**% and rebalance tasks for

## Algorithm used by the agent

1. **Ingest** weekly HR + project data per team: hours, overtime, absenteeism, tasks assigned/completed, engagement (1–10), performance (1–5).
2. **Normalize** each metric to 0–100 using min–max across teams.
3. **Workload Pressure Index** `WPI = 0.35·hours + 0.35·overtime + 0.30·tasks per head`.
4. **Output Efficiency** `OE = 0.45·completion + 0.30·performance + 0.25·engagement`.
5. **Burnout Risk** `BR = 0.4·WPI + 0.3·(100−engagement) + 0.3·absenteeism`.
6. **Productivity per hour** `PPH = completion ÷ hours`; compute Pearson correlation of hours vs. PPH over time (negative = diminishing returns).
7. **Bottleneck classification**: overload (WPI high, OE low), under-capacity (tasks/head high, hours moderate), disengagement (engagement low, workload normal), attendance strain (absenteeism high), healthy otherwise.
8. **Recommend** interventions from a rule library, rank by BR, and simulate impact with a regression-style gain: each 10% overtime cut recovers ≈ 3% OE for overloaded teams.