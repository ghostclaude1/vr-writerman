# Evidence And Citation Rules

## Claim Classes

| Class | Definition | Required handling |
|---|---|---|
| Evidence | Directly supported by repo files or paper text | Cite file path or paper placeholder |
| Inference | Interpretation from evidence | Use cautious language and cite the evidence |
| Plan | Pending work or proposed experiment | Mark as pending; do not write as result |

## Citation Rules

- Literature-review claims need citations or `[CITE: title/file]` placeholders.
- Repo-status claims need source paths such as `[SOURCE: docs/EXPERIMENT_LOG.md]`.
- Numeric result claims need artifact paths, preferably `.sol` for final TOC/NV.
- Do not fabricate DOI, author, year, venue, or citation numbers.
- When bibliography is not locked, use descriptive placeholders instead of fake numbered citations.
- For paper citations, record what the paper supports: bối cảnh, mô hình, thuật toán, dữ liệu, kết quả, or limitation. See `references/references.md`.
- `[CITE: BCT2024_LogisticsVN]` supports Vietnamese logistics context and policy motivation only; it does not support algorithmic or benchmark claims.
- Raw `[CITE: ...]` keys are internal trace keys only. Final report prose must use IEEE numeric citations such as `[1]` and `[2]`, plus a **Tài liệu tham khảo** block with full IEEE bibliographic entries.
- Do not over-frame the work as "developed from Wang et al."; cite Wang et al. for definitions/model/baseline/reference values, but describe this repo's work as implementation, reproduction, pipeline design, variants, artifacts, and experiments supported by repo sources.

## Forbidden Claims

- Cordeau benchmark is complete without Cordeau run artifacts.
- max-gen=150 has been run without corresponding artifacts.
- Regret-2 or urgency tier has independent measured impact without ablation.
- Generated tables are authoritative when they conflict with `.sol`.
- The current pipeline is "statistically superior" without enough instances and an appropriate test.

## Citation Density Gate

Before returning literature-review text:

- Count sentences with academic claims.
- Attach a citation, repo source, or `[cần dẫn nguồn]` marker to each claim.
- Avoid citation-free overview paragraphs.
