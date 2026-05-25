# Literature Policy

## Mốc thời gian

- **Paper gốc đề tài:** `paper/mainPaper/` — Wang et al., *Engineering Applications of Artificial Intelligence* 139 (2025) 109700.
- **Phạm vi viết báo cáo:** chỉ dùng tài liệu trong `paper/references/` + mainPaper + artifact repo (`runs/`, `docs/`, `reports/`).
- **Cấm làm “cập nhật state-of-the-art”:** không trích `paper/non-update/` để đề xuất phương án mới hơn mainPaper hoặc thay thế pipeline GRANITE.

## Quy tắc thư mục

| Path | Vai trò |
|------|---------|
| `paper/references/*.pdf` | Related work được phép — đã rename theo `file-mapping.md` |
| `paper/non-update/*.pdf` | Paper 2025–2026 mở rộng sau mainPaper |
| `paper/non-update/researching-result/` | Khảo sát repo 2026 — không đưa vào tổng quan chính thức |

## Khi viết tổng quan tài liệu

1. Nhóm theo `references/paper-catalog.md` (dynamic, multi-depot, collaboration, metaheuristic).
2. Mỗi claim học thuật → `[CITE: tên file chuẩn]` hoặc `[cần dẫn nguồn]`.
3. So sánh với mainPaper: nêu gap mà **đề tài này** lấp, không so với Wang 2025/2026 trong non-update.
4. Nếu user hỏi “paper mới nhất” → trả lời tách: phần report vs phần đọc thêm trong `non-update/`.

## Mốc thí nghiệm Chongqing

- Table 22 mainPaper: TOC **6736.0**, NV **27** (insertion strategy).
- Không dùng **99374** (sai, không có trong paper).
