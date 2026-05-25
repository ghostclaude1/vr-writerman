# Experiment Reporting

## Research Questions

Use these default RQs unless the user provides a different framing:

| RQ | Question | Required evidence |
|---|---|---|
| RQ1 | Baseline có tái lập được mốc tham chiếu trên Chongqing không? | `docs/EXPERIMENT_LOG.md`, `.sol`, setup |
| RQ2 | Geohash làm thay đổi TOC hoặc độ ổn định qua seed thế nào? | Ablation rows in `docs/EXPERIMENT_LOG.md` |
| RQ3 | Regret-2 và urgency tier ảnh hưởng TOC/NV cuối thế nào? | Only claim independent effect if ablation exists |
| RQ4 | Kết quả có tổng quát sang Cordeau không? | Pending unless `data/process/benchmark` runs exist |

## Protocol Fields

Every experiment paragraph should state:

- Dataset: exact path and instance count when known.
- Variant: baseline, Geohash, current pipeline, or Cordeau batch.
- Seeds: exact seed list.
- Budget: max-gen and runtime cap if present.
- Metrics: TOC, NV, runtime, convergence history.
- Result source: `.sol`, stats CSV, generated table, or log.
- Comparison rule: same dataset, seed/budget where applicable, and reference TOC.

## Current Interpretation

- Phase 0/1/2 have existing artifacts and logs.
- Phase 3 is the report-source synchronization phase: final TOC/NV must come from `.sol`.
- Phase 4 max-gen=150 is pending unless new artifacts are generated.
- Phase 5 Cordeau is pending unless benchmark output exists.

## Result Source Rules

- Final TOC/NV: `runs/solutions/*.sol`.
- Runtime: `runs/stats/*.csv`.
- Convergence: per-iteration `best_toc` in stats CSV.
- Generated summary tables: use after `mdpdtwdd report` has been regenerated from the current code.
