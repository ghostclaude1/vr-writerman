# Report Structure

Use `reports.md` as the live draft target unless the user specifies another file.

## Recommended Structure

1. Phần đầu: bìa, cảm ơn, mục lục, danh mục hình/bảng/từ viết tắt, tóm tắt, abstract
2. Mở đầu
3. Chương 1 — Tổng quan về đề tài
4. Chương 2 — Cơ sở lý thuyết, mô hình bài toán và định hướng cải tiến
5. Chương 3 — Phương pháp nghiên cứu và pipeline đề xuất
6. Chương 4 — Thực nghiệm, kết quả và phân tích
7. Chương 5 — Thảo luận, đóng góp và kết luận
8. Tài liệu tham khảo
9. Phụ lục

## Outline Rules

- Chương 1 là tổng quan nghiên cứu: nhóm các hướng liên quan và dẫn ra vấn đề đặt ra; không giảng lại VRP/VRPTW/PDPTW/MDVRP như giáo trình.
- Chương 2 là cơ sở và mô hình của đề tài: ký hiệu, phát biểu MDPDTWDD, mô hình toán học, chỉ số đánh giá, thuật toán gốc, và cơ sở hình thành cải tiến.
- Chương 3 là thiết kế phương pháp và pipeline: tái lập baseline, module triển khai, thiết kế G1/G2/G3.
- Chương 4 là bằng chứng thực nghiệm: kết quả, ablation, benchmark, hội tụ, Pareto, cost audit.
- Chương 5 là diễn giải đóng góp: lý thuyết/mô hình hóa, thuật toán/pipeline, thực nghiệm/tái lập, hiệu lực và hạn chế.
- Không dùng heading "Khoảng trống nghiên cứu"; dùng "Vấn đề đặt ra từ tổng quan nghiên cứu".
- Cấp 3 chỉ dùng ở mục có nhiều thành phần thật sự; không tách các mục một đoạn thành heading riêng.

## Section Inputs

| Section | Must answer | Sources |
|---|---|---|
| Mở đầu | Why MDPDTWDD, why dynamic multi-depot routing, repo scope | `paper/mainPaper/`, `BCT2024_BaoCaoLogisticsVN-FTZ.pdf`, `docs/DEVELOPMENT_PLAN.md` |
| Chương 1 | Which research lines matter and what problem this project takes up | `paper/references/` + `references/paper-catalog.md` (không dùng `paper/non-update/`) |
| Chương 2 | Definitions, MDPDTWDD formulation, metrics, original algorithm, theoretical basis for improvements | `paper/mainPaper/`, `src/mdpdtwdd/costs.py`, `src/mdpdtwdd/models.py` |
| Chương 3 | Pipeline, baseline reproduction, G1/G2/G3 design, implementation mapping | `src/mdpdtwdd/pipeline.py`, `clustering.py`, `genetic.py`, `insertion.py`, `routing.py` |
| Chương 4 | Numbers, ablation, benchmark, convergence, Pareto, cost audit evidence | `runs*/solutions/`, `runs*/stats/`, `reports/tables*/`, `reports/figures*/`, logs |
| Chương 5 | Interpretation, contributions, validity threats, limits, future work | Evidence from Chương 4 plus `docs/DEVELOPMENT_PLAN.md` / experiment logs |
