---
name: mdpdtwdd-report-writing
description: >-
  Viết, sửa và rà soát báo cáo nghiên cứu tiếng Việt cho MDPDTWDD theo từng tiểu mục
  nhỏ nhất, có tham chiếu dưới mỗi đoạn, chuẩn hóa cách khai thác paper/báo cáo
  Logistics Việt Nam, quy tắc hình/bảng, và lọc tài liệu non-update sau mainPaper.
  Dùng khi viết reports.md, luận văn, paper draft, tổng quan tài liệu, kết quả
  thực nghiệm, hoặc khi user nhắc mdpdtwdd-report-writing.
---

# MDPDTWDD Report Writing

Skill viết báo cáo nghiên cứu khoa học tiếng Việt cho project MDPDTWDD. Mục tiêu: văn phong học thuật tự nhiên, thuật ngữ nhất quán, số liệu neo vào artifact repo, không bịa citation.

Nếu agent chỉ nhận package skill mà không có toàn bộ ngữ cảnh workspace, đọc `references/mega-rule-report-writing.md` trước. File này là mega-rule vận hành, gồm quy trình viết, thứ bậc nguồn, chuẩn IEEE, snapshot kết quả an toàn, lỗi cấm và các vòng xác thực.

## Khi nào dùng skill

- Viết hoặc sửa `reports.md`, draft luận văn, hoặc từng chương/mục báo cáo.
- Soạn tổng quan tài liệu, phương pháp, thiết kế thực nghiệm, kết quả, thảo luận.
- Chuẩn bị hình/bảng để user chèn vào Word/LaTeX.
- Rà soát claim, citation, và nguồn số liệu trước khi nộp hội đồng.

## Workflow bắt buộc (human-in-the-loop)

**Chỉ viết một tiểu mục cấp nhỏ nhất mỗi lượt** (ví dụ `1.2.3`, không viết cả `1.2` nếu `1.2` còn nhiều tiểu mục con).

Quy trình mỗi lượt:

1. Xác nhận tiểu mục đích (heading cấp nhỏ nhất trong outline).
2. Liệt kê nguồn sẽ dùng: `references/source-map.md`, `references/references.md`, `references/vietnamese-academic-style.md`, `references/literature-policy.md`, `references/paper-catalog.md`, `file-mapping.md`.
3. Lập nhanh "gói bằng chứng" cho tiểu mục: paper nào dùng cho claim nào, số liệu/bảng/hình/trang nào nếu đã biết, và claim nào còn thiếu nguồn. `[CITE: ...]` chỉ là key nội bộ, **không được xuất hiện trong đoạn báo cáo cuối**.
4. Viết nháp **chỉ** tiểu mục đó.
5. Nếu có tham chiếu paper/tài liệu trong nội dung → dùng trích dẫn IEEE trong đoạn, ví dụ `[1]`, `[2]`, rồi ghi block **Tài liệu tham khảo** theo chuẩn IEEE và **Tham chiếu sử dụng** ngay **phía dưới** đoạn vừa viết.
6. Ghi **Điểm cần human duyệt**.
7. Khi user duyệt, mới được ghi nội dung vào `beWritten.md` hoặc file user chỉ định; không tự ghi draft chưa duyệt vào `reports.md`.
8. **Dừng.** Không viết tiểu mục kế tiếp cho đến khi user duyệt hoặc yêu cầu chỉnh.

### Format trả lời bắt buộc

```markdown
### [Số và tên tiểu mục — cấp nhỏ nhất]

[Nội dung nháp tiếng Việt học thuật]

**Tài liệu tham khảo**
- [n] Tác giả/Cơ quan, "Tên bài" hoặc *Tên tài liệu*, thông tin xuất bản/tạp chí, vol./no./Art. no./trang, năm.

**Tham chiếu sử dụng**
- Key nội bộ `[CITE: ...]` → trích dẫn IEEE trong bài `[n]`: dùng cho ...; vai trò: bối cảnh / mô hình / thuật toán / dữ liệu / kết quả; vị trí: trang/bảng/hình nếu biết
- `[SOURCE: path]`: dùng cho số liệu/kết quả ...

**Điểm cần human duyệt**
- Claim/citation/số liệu cần xác nhận
- Thuật ngữ cần khóa
- Có được viết tiểu mục tiếp theo không

**Hình/bảng đề xuất** (nếu có — xem mục Hình và bảng)
```

Thiếu nguồn → `[cần dẫn nguồn]` hoặc hỏi user; **không** tự điền số liệu/citation.

## Luật tham chiếu paper và báo cáo Logistics VN

Chi tiết: `references/references.md`.

- Trước khi viết đoạn có citation, phân loại claim: bối cảnh thực tiễn, định nghĩa/mô hình, thuật toán, dữ liệu thực nghiệm, kết quả, hoặc nhận xét hạn chế.
- Với mỗi paper được trích, phải biết tối thiểu: paper đang đỡ claim nào, lấy từ phần/bảng/hình nào nếu đã biết, và vì sao paper đó liên quan tới MDPDTWDD.
- Báo cáo Logistics Việt Nam 2024 dùng key nội bộ `[CITE: BCT2024_LogisticsVN]`, nhưng khi viết đoạn báo cáo phải hiện bằng số IEEE như `[1]`. Đây là nguồn bắt buộc khi viết **Mở đầu**, bối cảnh Việt Nam, logistics/FTZ/hạ tầng/chính sách. Không dùng nguồn này để chứng minh tính đúng của thuật toán, mô hình toán hoặc kết quả benchmark.
- Khi dùng Báo cáo Logistics Việt Nam trong **Mở đầu**, chỉ chọn 1-2 số liệu neo thật đắt để rút bớt lời văn và mở ra ý nghĩa; không liệt kê dày như phần tình hình. Sau mỗi số liệu phải có câu diễn giải "vì sao số này làm đề tài cần thiết". Các số liệu chi tiết hơn để sang Chương 1 hoặc mục bối cảnh chuyên sâu. Ghi trang/bảng/hình trong **Tham chiếu sử dụng**.
- Paper thuật toán/VRP dùng để đỡ claim khoa học; báo cáo Logistics VN dùng để neo vấn đề thực tiễn và giọng văn báo cáo khoa học Việt Nam.
- Không để paragraph học thuật chỉ có citation ở cuối đoạn nhưng không rõ citation đỡ câu nào. Không xuất raw key như `[CITE: ...]` trong đoạn báo cáo. Nếu không chắc, ghi `[cần dẫn nguồn: paper nào/trang nào?]`.
- Khi dùng mainPaper của Wang et al., không viết như "đề tài phát triển từ Wang" hoặc "thay Wang phát biểu". Viết trung tính: đề tài lựa chọn lớp bài toán MDPDTWDD trong tài liệu, kế thừa khái niệm/mốc đối chứng cần thiết, rồi nhấn mạnh phần việc của repo là tái lập, kiểm chứng, thiết kế pipeline/biến thể và đánh giá thực nghiệm. Vẫn phải cite `[n]` ở claim lấy từ paper.

## Văn phong học thuật tiếng Việt

Chi tiết: `references/vietnamese-academic-style.md`.

- Paper/báo cáo **tiếng Việt** trong repo là chuẩn chính cho thuật ngữ, nhịp câu, câu chuyển và cách mở đoạn: `BCT2024_BaoCaoLogisticsVN-FTZ.pdf`, `CaoTran2022_GA-VRP.pdf`, `CaoTran2023_TabuSearch-VRP.pdf`.
- Paper tiếng Anh dùng để học cách lập luận khoa học, cấu trúc gap, định nghĩa bài toán, thiết kế phương pháp và diễn giải kết quả; khi viết tiếng Việt phải chuyển hóa theo lối văn học thuật Việt Nam, không dịch sát từng câu.
- Câu mở bài/chương/mục không bắt đầu bằng triết lý chung. Phải là một phát biểu thực tế có nguồn, số liệu, tên nghiên cứu, artifact, hoặc sự kiện cụ thể.
- Khi cần thêm paper để chuẩn hóa thuật ngữ/lập luận, dùng tài liệu đã có trước; nếu thiếu thì tìm DOI/link nguồn chính thống và đề xuất user tải, không bịa nguồn.
- Đọc `references/project-specific-errors.md` trước khi sửa hoặc viết lại các phần đã từng bị góp ý.

## Nguyên tắc cấu trúc MOC / outline

Khi soạn hoặc sửa mục lục báo cáo, ưu tiên cấu trúc gọn như BCKH Việt Nam nhưng giữ chất của paper thuật toán. Không biến MOC thành danh sách quá vụn các đoạn sẽ viết; cấp 3 chỉ dùng khi mục đó có nhiều thành phần thật sự.

### Chống lặp ý giữa các chương

- **Chương 1 — Tổng quan:** trả lời người khác đã nghiên cứu gì, các hướng liên quan nhóm ra sao, và vấn đề nào đặt ra cho đề tài. Không giảng lại VRP/VRPTW/PDPTW/MDVRP như giáo trình.
- **Chương 2 — Cơ sở và mô hình:** định nghĩa ký hiệu, phát biểu MDPDTWDD, mô hình toán học, chỉ số đánh giá, thuật toán gốc, và cơ sở hình thành cải tiến. Không viết lại tình hình nghiên cứu.
- **Chương 3 — Phương pháp / pipeline:** mô tả cách đề tài triển khai, tái lập và thiết kế các biến thể. Không để toàn bộ đóng góp lý thuyết và thực nghiệm chỉ nằm ở chương này.
- **Chương 4 — Thực nghiệm:** chứng minh tác động của cải tiến bằng artifact, bảng, hình, benchmark, kiểm định.
- **Chương 5 — Thảo luận:** gom đóng góp theo ba lớp: lý thuyết/mô hình hóa, thiết kế thuật toán/pipeline, thực nghiệm/tái lập.

### Phân bổ cải tiến của đề tài

Các cải tiến không được dồn hết vào "Các biến thể cải tiến" trong Chương 3:

- Nền tảng lý thuyết / lý do hình thành cải tiến đặt ở Chương 2.
- Thiết kế thuật toán cụ thể đặt ở Chương 3.
- Kết quả và ablation đặt ở Chương 4.
- Diễn giải đóng góp, giới hạn, và ý nghĩa đặt ở Chương 5.

Tránh heading kiểu nội bộ như "Khoảng trống nghiên cứu"; dùng "Vấn đề đặt ra từ tổng quan nghiên cứu" hoặc "Định hướng nghiên cứu của đề tài".

## Hình và bảng (để user chèn vào report)

Chi tiết: `references/figures-and-tables.md`.

### Quy tắc đặt tên (bắt buộc)

| Loại | Vị trí tên | Ví dụ |
|------|------------|-------|
| **Bảng** | **Trên** bảng | `Bảng 4.2. TOC trung bình theo biến thể (max-gen=15)` |
| **Hình** | **Dưới** hình | `Hình 4.1. Hội tụ TOC theo thế hệ (seed 42)` |

### Cách đưa hình cho user

Khi cần hình minh họa, **không** chỉ mô tả chung. Chọn **một trong hai**:

**A — Mã vẽ sẵn (ưu tiên nếu có số liệu trong repo)**

- Cung cấp script Python đầy đủ (matplotlib / seaborn / repo `mdpdtwdd report`).
- Ghi rõ input: path CSV, `.sol`, hoặc lệnh CLI.
- Ghi output: `reports/figures/...png` và kích thước đề xuất.
- Kèm caption **dưới hình** theo quy tắc trên.

**B — Mô tả để user tìm ảnh trên internet**

- Tiêu đề hình (caption dưới hình).
- Từ khóa tìm kiếm tiếng Anh + tiếng Việt.
- Loại hình (sơ đồ khối, bản đồ case study, biểu đồ cột, …).
- Nguồn gợi ý (paper Fig. X, trang benchmark, …) — **không** bịa URL.
- Ghi chú bản quyền / cần trích nguồn.

Không gửi file ảnh nhị phân trừ khi user yêu cầu; ưu tiên mã hoặc mô tả tìm kiếm.

### Bảng

- Tên bảng **phía trên**.
- Số liệu từ `.sol` / CSV đã xác nhận; ghi `[SOURCE: ...]` trong block tham chiếu.
- Mốc paper Chongqing: TOC **6736.0**, NV **27** (Table 22 mainPaper) — **không** dùng 99374.

## Tài liệu được phép / non-update

Chi tiết: `references/literature-policy.md`.

- **Được dùng khi viết report:** `paper/mainPaper/`, `paper/references/` (tài liệu ≤ mốc thời gian mainPaper).
- **Không dùng để cập nhật phương án mới hơn mainPaper:** `paper/non-update/` (survey 2026, paper ≥2025 sau mainPaper, v.v.).
- Mốc tham chiếu thí nghiệm Chongqing: **6736.0** (insertion strategy), không phải 99374.

## Luật chất lượng (tóm tắt)

- Không bịa paper, tác giả, DOI, số liệu, bảng, hình, kết quả.
- TOC/NV cuối: `runs*/solutions/*.sol`; runtime/hội tụ: `runs*/stats/*.csv`.
- Không claim Cordeau / max-gen=150 / ablation độc lập nếu chưa có artifact.
- Văn phong: xem `references/writing-style.md`, thuật ngữ `references/domain-glossary.md`.

## Tài liệu tham chiếu trong skill

| File | Nội dung |
|------|----------|
| `references/mega-rule-report-writing.md` | Mega-rule đầy đủ để agent khác viết report mà không cần đọc lại toàn bộ workspace: workflow, evidence hierarchy, IEEE, văn phong, số liệu an toàn, claim cấm, verification gates |
| `references/report-structure.md` | Khung chương, nguồn theo section |
| `references/source-map.md` | Bảng map path → vai trò |
| `references/references.md` | Quy tắc khai thác paper, báo cáo Logistics VN, và format gói bằng chứng |
| `references/vietnamese-academic-style.md` | Chuẩn văn phong học thuật tiếng Việt, câu chuyển, gap, định nghĩa, phương pháp, kết quả |
| `references/project-specific-errors.md` | Lỗi đặc thù của report MDPDTWDD và cách sửa |
| `references/evidence-and-citation-rules.md` | Claim classes, citation gate |
| `references/experiment-reporting.md` | RQ, protocol, nguồn số liệu |
| `references/figures-and-tables.md` | Mẫu mã hình, mô tả tìm ảnh, bảng |
| `references/literature-policy.md` | mainPaper vs non-update |
| `references/paper-catalog.md` | Tên file chuẩn + `[CITE: ...]` key |
| `file-mapping.md` | Rename PDF, nhóm theo chương, lệnh `scripts/rename-paper-references.ps1` |
| `references/domain-glossary.md` | Thuật ngữ MDPDTWDD |
| `references/writing-style.md` | Nhịp đoạn, mẫu câu rút gọn; xem bản đầy đủ ở `vietnamese-academic-style.md` |
| `assets/report-outline.md` | Outline mặc định (9 phần ngắn) |
| `assets/report-moc-full.md` | **MOC đầy đủ** NCKH Việt Nam — mục lục triển khai chính |

## Phong cách học thuật (rút gọn)

Học từ báo cáo Logistics VN, paper UNETI, luận văn Ontario Tech — nhưng khi viết phải dùng `references/references.md` để biến nguồn thành claim/citation cụ thể. Không import ngữ cảnh VN30/chứng khoán từ skill cũ.

Cấu trúc journal / báo cáo VN / luận văn: giữ nguyên trong bản gốc `temp/mdpdtwdd-report-writing/SKILL.md` (mục 1–9 thuật ngữ VRP, mẫu lập luận); khi viết thực tế ưu tiên workflow và file `references/` ở trên.

## Codex

- **Local project:** `.codex/skills/mdpdtwdd-report-writing/`
- **Global:** `~/.codex/skills/mdpdtwdd-report-writing/`
- Gọi skill: `mdpdtwdd-report-writing` hoặc `$mdpdtwdd-report-writing` (Codex agent).
