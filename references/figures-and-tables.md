# Figures And Tables

## Naming (bắt buộc)

| Loại | Vị trí caption | Ví dụ |
|------|----------------|-------|
| Bảng | **Trên** bảng | `Bảng 4.2. TOC trung bình theo biến thể (max-gen=15, Chongqing)` |
| Hình | **Dưới** hình | `Hình 4.1. Hội tụ TOC theo thế hệ (seed 42)` |

## Hình — hai cách đưa cho user

### A — Mã Python (ưu tiên khi có artifact)

```python
# Ví dụ: boxplot TOC từ summary CSV
import pandas as pd
import matplotlib.pyplot as plt
from pathlib import Path

summary = Path("reports/tables_phaseB_harness/G3/summary.csv")
df = pd.read_csv(summary)
fig, ax = plt.subplots(figsize=(6, 4))
# ... plot ...
out = Path("reports/figures/toc_boxplot_g3.png")
fig.savefig(out, dpi=150, bbox_inches="tight")
plt.close()
```

Hoặc: `mdpdtwdd report --runs-dir runs_phaseB_harness/G3 --reference-toc 6736`

Kèm caption **dưới hình** trong block trả lời.

### B — Mô tả tìm ảnh trên internet

- **Caption (dưới hình):** `Hình 2.1. Sơ đồ mạng logistics đa kho (minh họa)`
- **Từ khóa EN:** `multi-depot vehicle routing network diagram`
- **Từ khóa VN:** `sơ đồ mạng logistics đa kho`
- **Loại:** sơ đồ khối / bản đồ case study
- **Gợi ý nguồn:** Fig. 1 mainPaper — không bịa URL
- **Bản quyền:** trích nguồn nếu dùng ảnh từ paper

## Bảng

- Caption **trên** bảng.
- Số từ `.sol` hoặc CSV đã xác nhận; ghi `[SOURCE: path]` trong **Tham chiếu sử dụng**.
- Mốc paper Chongqing: TOC **6736.0**, NV **27**.
