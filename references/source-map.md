# Source Map

Use this file first to choose evidence for a report section.

| Source | Use for |
|---|---|
| `paper/mainPaper/` | 3DAPANSGA-II, original model, equations, scenario definitions, published reference values |
| `paper/references/BCT2024_BaoCaoLogisticsVN-FTZ.pdf` | Bối cảnh logistics Việt Nam, hạ tầng/chính sách/FTZ, dẫn nhập thực tiễn cho Mở đầu và Chương 1 — không dùng làm nguồn thuật toán |
| `paper/references/` | Related work (PDF đã rename) — xem `references/paper-catalog.md` và `references/references.md` |
| `paper/non-update/` | Paper/survey sau mainPaper — **không** trích khi viết đề xuất phương án |
| `file-mapping.md` | Bảng tên gốc → tên chuẩn, phân loại references vs non-update |
| `docs/EXPERIMENT_LOG.md` | Experiment chronology, ablation setup, decisions to keep or remove variants |
| `docs/DEVELOPMENT_PLAN.md` | Current phase, pending work, known limitations |
| `runs/solutions/*.sol` | Final TOC/NV after dynamic insertion; primary result source |
| `runs/stats/*.csv` | Convergence history, elapsed time, iteration-level best values |
| `reports/tables/*.csv` | Generated summary tables after report regeneration |
| `reports/figures/*.png` | Generated figures for result presentation |
| `reports.md` | Main report draft outline |

## Source Rules

- Prefer `.sol` over stats CSV for final TOC/NV.
- Use stats CSV only for iteration history, convergence, and runtime.
- Treat `docs/DEVELOPMENT_PLAN.md` pending phases as plans, not results.
- Treat `reports/tables/summary.csv` as derived output; if it conflicts with `.sol`, fix or flag the report pipeline.
- Use internal key `[CITE: BCT2024_LogisticsVN]` for Vietnamese logistics context and motivation, but final report prose must cite it with IEEE numbering such as `[1]`. Pair it with mainPaper/code artifacts when the paragraph moves from context to MDPDTWDD model or algorithm.
