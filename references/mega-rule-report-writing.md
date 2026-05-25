# Mega-rule Report Writing for MDPDTWDD

File này là luật bao quát để agent khác có thể viết, sửa và rà soát báo cáo MDPDTWDD mà không phải đọc lại toàn bộ workspace. Khi có xung đột giữa file này và yêu cầu mới nhất của user, ưu tiên yêu cầu mới nhất nhưng phải ghi rõ điểm thay đổi trong **Điểm cần human duyệt**.

Mục tiêu hợp lệ của mega-rule là tạo văn bản học thuật tiếng Việt tự nhiên, có bằng chứng, có nhịp câu biến thiên, có citation chuẩn IEEE và không bịa dữ kiện. Không biến file này thành hướng dẫn đánh lừa hệ thống phát hiện AI. Nếu user yêu cầu "né detector", diễn giải thành: giảm văn máy bằng cách dùng nguồn thật, số liệu thật, cấu trúc lập luận từ paper thật, và kiểm soát câu chữ ở cấp đoạn.

## 1. Luật kích hoạt và phạm vi

Dùng file này khi:

- Viết hoặc sửa `reports.md`, `beWritten.md`, luận văn, paper draft hoặc từng tiểu mục của báo cáo MDPDTWDD.
- Viết Mở đầu, Tổng quan, Cơ sở lý thuyết, Mô hình, Phương pháp, Thực nghiệm, Kết quả, Thảo luận, Kết luận.
- Chuẩn hóa citation IEEE, tài liệu tham khảo, caption hình/bảng, số liệu thực nghiệm và claim đóng góp.
- Agent được gắn skill nhưng không có ngữ cảnh đầy đủ của workspace.

Không dùng file này để:

- Tự ý thay đổi kết quả thực nghiệm.
- Bịa DOI, venue, bảng, hình, thuật toán hoặc số liệu.
- Viết claim đánh lừa hội đồng, detector hoặc reviewer.
- Viết nhiều tiểu mục liên tiếp khi user chưa duyệt.

## 2. Quy trình không được bỏ qua

Mỗi lượt chỉ viết **một tiểu mục cấp nhỏ nhất**. Nếu user yêu cầu "viết phần trên" nhưng outline chưa rõ, chọn tiểu mục nhỏ nhất hợp lý và ghi heading rõ ràng.

Quy trình bắt buộc:

1. Xác định heading cấp nhỏ nhất đang viết.
2. Xác định loại claim chính: bối cảnh, tổng quan, định nghĩa, mô hình, thuật toán, phương pháp, thực nghiệm, kết quả, thảo luận, hạn chế.
3. Chọn nguồn theo `source-map.md`, `paper-catalog.md`, `references.md` và file này.
4. Lập gói bằng chứng ngắn trước khi viết trong đầu hoặc trong ghi chú:
   - Nguồn/citation key nội bộ.
   - Số IEEE sẽ dùng trong đoạn, ví dụ `[1]`, `[2]`.
   - Claim được phép viết.
   - Vị trí bằng chứng: trang, bảng, hình, section, equation, algorithm hoặc artifact path.
   - Giới hạn của nguồn.
5. Viết nháp trong chatbox, không ghi vào `reports.md`.
6. Ngay dưới nháp phải có **Tài liệu tham khảo**, **Tham chiếu sử dụng**, **Điểm cần human duyệt**.
7. Chỉ khi user duyệt mới ghi phần đó vào `beWritten.md` hoặc file user chỉ định.
8. Dừng sau tiểu mục đó.

Format trả lời:

```markdown
### [Số và tên tiểu mục]

[Nội dung nháp]

**Tài liệu tham khảo**
- [1] ...
- [2] ...

**Tham chiếu sử dụng**
- `[CITE: ...]` -> `[1]`: dùng cho claim ...; vị trí ...
- `[SOURCE: ...]`: dùng cho số liệu ...

**Điểm cần human duyệt**
- ...

**Hình/bảng đề xuất** (nếu có)
- ...
```

## 3. Thứ bậc nguồn chứng cứ

Ưu tiên nguồn theo đúng loại claim:

| Claim | Nguồn ưu tiên | Không dùng |
|---|---|---|
| Bối cảnh logistics Việt Nam, hạ tầng, FTZ, áp lực vận tải | `paper/references/BCT2024_BaoCaoLogisticsVN-FTZ.pdf` | MainPaper hoặc paper thuật toán để suy diễn chính sách Việt Nam |
| Định nghĩa MDPDTWDD, hàm mục tiêu, constraint, dynamic demand | `paper/mainPaper/`, `paper/mainPaper/paper_math_blocks.md` | Báo cáo Logistics Việt Nam |
| Thuật toán gốc, 3DAPANSGA-II, insertion strategy | MainPaper Wang et al. | Báo cáo Logistics Việt Nam |
| Related work VRP/PDPTW/MDVRP/DVRPTW | `paper/references/*.pdf`, theo `paper-catalog.md` | `paper/non-update/` nếu đang viết state-of-the-art chính thức |
| Kết quả repo: TOC/NV cuối | `runs*/solutions/*.sol`, bảng sinh từ `.sol` | Stats CSV nếu xung đột với `.sol` |
| Runtime, convergence, per-generation best | `runs*/stats/*.csv`, logs | `.sol` |
| Protocol, phase, pending work | `docs/EXPERIMENT_LOG.md`, `docs/DEVELOPMENT_PLAN.md`, `reports.md` | Paper citation thay cho artifact |
| Hình/bảng report | `reports/tables*/*.csv`, `reports/figures*/*.png`, script sinh hình | Hình mô tả chung không có nguồn |

Nếu hai nguồn xung đột, không tự hòa giải bằng văn hay. Ghi rõ xung đột trong **Điểm cần human duyệt** và ưu tiên artifact thô gần kết quả nhất.

## 4. Chuẩn IEEE bắt buộc

Trong đoạn báo cáo chỉ dùng số IEEE, ví dụ `[1]`, `[2]`. Không viết raw key `[CITE: ...]` trong nội dung chính. Raw key chỉ được dùng trong block **Tham chiếu sử dụng**.

Luật entry:

- Paper có DOI: phải ghi `doi: https://doi.org/...`.
- Web source: phải có URL và `Accessed: yyyy-mm-dd`.
- Báo cáo/sách không DOI: ghi cơ quan, tên tài liệu, nơi xuất bản, nhà xuất bản, năm; nếu bản online thì thêm URL và ngày truy cập.
- Không bịa DOI, vol., issue, trang, nhà xuất bản.
- Nếu chưa xác minh DOI: ghi `DOI cần human xác minh`.

Entry đã khóa:

```text
[1] Bộ Công Thương, Báo cáo Logistics Việt Nam 2024: Khu thương mại tự do. Hà Nội, Việt Nam: Nhà xuất bản Công Thương, 2024.

[2] Y. Wang, M. Gou, S. Luo, J. Fan, and H. Wang, "The multi-depot pickup and delivery vehicle routing problem with time windows and dynamic demands," Engineering Applications of Artificial Intelligence, vol. 139, Art. no. 109700, 2025, doi: https://doi.org/10.1016/j.engappai.2024.109700.
```

Khi viết một tiểu mục mới, số IEEE đánh theo thứ tự xuất hiện trong chính phần nháp đó. Khi ghép vào bản cuối, có thể cần đánh số lại toàn văn.

## 5. Nguồn chính và vai trò an toàn

### 5.1 Báo cáo Logistics Việt Nam 2024

Nguồn: `paper/references/BCT2024_BaoCaoLogisticsVN-FTZ.pdf`.

Key nội bộ: `[CITE: BCT2024_LogisticsVN]`.

Dùng cho:

- Mở đầu và Chương 1.
- Bối cảnh logistics Việt Nam.
- Tăng trưởng vận tải, xuất nhập khẩu, doanh nghiệp vận tải kho bãi.
- Nhu cầu thực tiễn của tối ưu tuyến và điều phối phương tiện.
- Văn phong báo cáo khoa học/chính sách tiếng Việt.

Không dùng cho:

- Thuật toán.
- Mô hình toán.
- Mốc benchmark.
- Kết quả repo.
- Claim "MDPDTWDD tốt hơn mô hình khác".

Số liệu neo đã xác minh:

| Vị trí | Số liệu | Dùng để viết |
|---|---|---|
| tr. 24 | GDP 9 tháng đầu năm 2024 tăng 6,82%; khu vực dịch vụ tăng 6,95% và đóng góp 48,41% | Nền kinh tế và dịch vụ tạo áp lực logistics |
| tr. 26 | Kim ngạch xuất nhập khẩu 9 tháng đầu năm 2024 đạt 578,47 tỷ USD, tăng 16,3%; xuất khẩu tăng 15,4%, nhập khẩu tăng 17,3%; xuất siêu 20,79 tỷ USD | Quy mô lưu chuyển hàng hóa và nhu cầu điều phối vận tải |
| tr. 65 | Vận tải hàng hóa đạt 1.917,9 triệu tấn, tăng 13,7%; luân chuyển đạt 393,35 tỷ tấn-km, tăng 10,5% | Áp lực vận tải trực tiếp, phù hợp nhất cho Mở đầu |
| tr. 80 | 6.503 doanh nghiệp vận tải, kho bãi đăng ký mới; vốn 36.551 tỷ đồng; 28.898 lao động; số doanh nghiệp tăng 13,5% | Thị trường vận tải kho bãi mở rộng và phân tán |

Quy tắc dùng số liệu trong Mở đầu:

- Mỗi đoạn chỉ dùng 1 số liệu chính, tối đa 2 nếu cùng một luận điểm.
- Sau số liệu phải có câu diễn giải ý nghĩa.
- Không biến Mở đầu thành danh sách thống kê.
- Nếu cần nhiều số, chuyển sang Chương 1 hoặc bảng bối cảnh.

Mẫu đúng về chức năng lập luận:

```markdown
Năm 2024, sản lượng vận tải hàng hóa đạt 1.917,9 triệu tấn, tăng 13,7% so với cùng kỳ [1]. Con số này cho thấy áp lực điều phối phương tiện không chỉ nằm ở quy mô hàng hóa, mà còn ở khả năng tổ chức tuyến khi điểm nhận, điểm giao và thời điểm phục vụ thay đổi theo vận hành.
```

### 5.2 MainPaper Wang et al. 2025

Nguồn:

- `paper/mainPaper/ENG The multi-depot pickup and delivery vehicle routing problem with time windows and dynamic demands.md`
- `paper/mainPaper/paper_math_blocks.md`

Key nội bộ: `[CITE: WangEtAl2025_MDPDTWDD-mainPaper]`.

Dùng cho:

- Định nghĩa MDPDTWDD.
- Multi-depot, pickup-delivery, time windows, dynamic demands.
- Cost components, objective, constraints.
- 3DAPANSGA-II, adaptive non-dominated sorting, insertion strategy.
- Mốc Table 22: TOC 6736.0, NV 27.

Không dùng như:

- Căn cứ chính sách Việt Nam.
- Bằng chứng cho kết quả repo.
- Cách nói làm người đọc hiểu toàn bộ đề tài chỉ "phát triển từ Wang".

Cách định vị đóng góp:

- Không viết: "Đề tài phát triển từ Wang et al."
- Không viết như thay Wang phát biểu nhưng không cite.
- Nên viết: "Đề tài lựa chọn lớp bài toán MDPDTWDD đã được mô tả trong tài liệu, sử dụng các khái niệm và mốc đối chứng cần thiết để thiết kế quy trình tái lập, kiểm chứng và đánh giá biến thể."
- Câu nào lấy định nghĩa/mô hình/thuật toán từ Wang phải cite `[n]` gần câu đó.
- Câu nào nói kết quả của đề tài phải cite artifact repo.

### 5.3 Related work được phép

Dùng `paper/references/` theo nhóm, không liệt kê tuần tự:

| Nhóm | Key gợi ý | Vai trò |
|---|---|---|
| Case study/VRP Việt Nam | `[CITE: NguyenEtAl2016_VRPTW-VN]`, `[CITE: NgoEtAl2024_MSW-GIS]`, `[CITE: CaoTran2022_GA-VRP]`, `[CITE: CaoTran2023_TabuSearch-VRP]` | Thuật ngữ, lối hành văn, ứng dụng định tuyến trong bối cảnh Việt Nam |
| Dynamic/periodic PDPTW | `[CITE: KaramiEtAl2020_Periodic-DynPDPTW]`, `[CITE: SilvaEtAl2020_DVRPTW]`, `[CITE: JeongMoon2024_DPDP-AR]`, `[CITE: DuEtAl2023_DPDP-LIFO]` | Nhu cầu động, tái gán, cập nhật trong vận hành |
| Multi-depot/collaboration/shared resources | `[CITE: LiEtAl2018_MDVRP-SharedDepot]`, `[CITE: KocaturkEtAl2021_MDHFVRPB]`, `[CITE: WangEtAl2021_CMDPDLN]`, `[CITE: ZhangEtAl2022_HMCVRP]` | Nhiều depot, hợp tác logistics, chia sẻ nguồn lực |
| Metaheuristic/exact/review | `[CITE: AhmadiOsman2005_GRAMPS-CCP]`, `[CITE: PraxedesEtAl2024_BCP-VRPSPD]`, `[CITE: SoeffkerEtAl2022_SDVRP-Review]`, `[CITE: Xu2024_EVRP-Review]` | Nền phương pháp và phân loại thuật toán |
| Pickup-delivery/simultaneous pickup-delivery | `[CITE: WangEtAl2018_CMCVRPSDP]`, `[CITE: ZhuSheu2018_SPDPSD]` | Pickup-delivery, simultaneous delivery-pickup, chi phí chuỗi cung ứng |

### 5.4 Nguồn không dùng để cập nhật phương án

`paper/non-update/` gồm các paper/survey sau mainPaper hoặc ngoài phạm vi cập nhật chính thức. Chỉ dùng nếu user yêu cầu phần đọc thêm riêng. Không dùng để viết "phương án mới" hoặc state-of-the-art chính thức của report.

## 6. Văn phong học thuật tiếng Việt

Luật chung: paper Việt Nam làm chuẩn thuật ngữ và nhịp câu; paper tiếng Anh làm chuẩn lập luận khoa học. Khi viết tiếng Việt, không dịch sát câu tiếng Anh.

### 6.1 Câu mở bài/chương/mục

Câu đầu tiên không bắt đầu bằng triết lý chung. Phải là một phát biểu thực tế có thể trích dẫn hoặc kiểm chứng.

Sai:

```text
Logistics đóng vai trò quan trọng trong nền kinh tế hiện đại.
```

Đúng:

```text
Sản lượng vận tải hàng hóa năm 2024 đạt 1.917,9 triệu tấn, tăng 13,7% so với cùng kỳ [1].
```

Sau câu mở, câu thứ hai giải thích ý nghĩa. Câu thứ ba mới nối sang bài toán nghiên cứu.

### 6.2 Gap statement

Cấu trúc 3 bước:

1. Thừa nhận: "Có nhiều nghiên cứu về X, như [cite]..."
2. Chỉ giới hạn: "Tuy nhiên, trong phạm vi khảo lược chưa tìm thấy..."
3. Khẳng định gap: "Vì vậy, nghiên cứu này được thực hiện nhằm..."

Điều chỉnh cho report này:

- Không nói tuyệt đối nếu chưa khảo lược đủ.
- Dùng "trong phạm vi khảo lược" để giữ độ an toàn.
- Không dùng heading "Khoảng trống nghiên cứu" nếu outline cần giọng tự nhiên hơn; dùng "Vấn đề đặt ra từ tổng quan nghiên cứu".

### 6.3 Dẫn vào đề tài/giải pháp

Dùng các cụm đã phù hợp văn phong học thuật Việt Nam:

- `Xuất phát từ thực tiễn đó,`
- `Nhằm lấp đầy khoảng trống đó,`
- `Nhằm giải quyết vấn đề trên,`
- `Trên cơ sở đó,`
- `Từ đó,`

Không dùng quảng cáo:

- `giải pháp toàn diện`
- `đột phá`
- `vượt trội`
- `hiệu quả rõ rệt` nếu không có số liệu.

### 6.4 Định nghĩa khái niệm/thuật toán

Pattern 3 câu:

1. Vị thế chung của khái niệm.
2. Định nghĩa kỹ thuật và viết tắt lần đầu.
3. Nguyên lý hoạt động hoặc liên hệ ứng dụng.

Nếu chưa có bản dịch tiếng Việt học thuật, giữ thuật ngữ gốc và thêm `(tạm dịch: ...)` ở lần đầu. Tên riêng/framework không dịch nếu dịch làm mất nhận diện.

### 6.5 Mô tả phương pháp

Viết theo văn xuôi có liên kết bước:

- `Sau khi [X], nghiên cứu thực hiện...`
- `Tiếp đến là...`
- `Cụ thể,`
- `Trong đó,`
- `Theo đó,`
- `Từ đó,`

Không liệt kê như checklist nếu đang viết nội dung chính của báo cáo.

### 6.6 Trình bày kết quả

Thứ tự bắt buộc:

```text
Dẫn vào bảng/hình -> số liệu cụ thể -> so sánh/đánh giá -> lập luận suy diễn -> nhận xét giới hạn
```

Không mở bằng "Nhìn chung". Không nói "hiệu quả" nếu không có số liệu đi kèm.

### 6.7 Kết luận có hạn chế

Kết luận bắt đầu bằng dữ liệu cụ thể, artifact hoặc claim đã chứng minh. Có thể dùng "Tóm lại" ở cuối đoạn, nhưng không dùng làm câu mở nếu trước đó chưa có số liệu.

## 7. Pattern học từ paper thật trong repo

Các pattern này dùng để bắt chước chức năng lập luận, không sao chép nguyên văn dài.

| Nguồn | Quan sát đã khóa | Cách áp dụng |
|---|---|---|
| `BCT2024_BaoCaoLogisticsVN-FTZ.pdf`, tr. 24 | Mở tiểu mục bằng số liệu GDP rồi diễn giải theo khu vực kinh tế | Mở chương bằng số liệu neo, sau đó giải thích tác động tới logistics |
| `BCT2024_BaoCaoLogisticsVN-FTZ.pdf`, tr. 26 | Gộp kim ngạch, tốc độ tăng và xuất siêu thành một cụm thông tin | Mở Mở đầu bằng một cụm số đủ mạnh, không rải nhiều số |
| `BCT2024_BaoCaoLogisticsVN-FTZ.pdf`, tr. 65 | Liên kết xuất nhập khẩu/sản xuất với sản lượng vận tải | Viết quan hệ nhân quả: lưu chuyển hàng hóa tăng -> áp lực điều phối tuyến |
| `BCT2024_BaoCaoLogisticsVN-FTZ.pdf`, tr. 80 | Đưa số doanh nghiệp, vốn, lao động rồi mới nhận xét xu thế | Khi nói thị trường logistics phân tán, dùng số doanh nghiệp làm điểm neo |
| `CaoTran2022_GA-VRP.pdf`, tr. 36 | Tóm tắt nêu mục tiêu nghiên cứu, sau đó định nghĩa VRP và độ khó | Khi định nghĩa MDPDTWDD: nêu mục tiêu -> tên bài toán -> đặc tính tối ưu tổ hợp |
| `CaoTran2022_GA-VRP.pdf`, tr. 37 | Phân nhóm phương pháp trước khi nói giải thuật di truyền | Tổng quan phải nhóm hướng nghiên cứu, không liệt kê paper tuần tự |
| `CaoTran2023_TabuSearch-VRP.pdf`, tr. 38-39 | Giải thích Tabu Search theo lời giải ban đầu, lân cận, bước chuyển, danh sách cấm | Mô tả thuật toán theo trình tự vận hành, không chỉ nêu khái niệm |
| `NgoEtAl2024_MSW-GIS-ABM-HungYen.pdf`, tr. 3-4 | Mô tả địa bàn, dữ liệu thứ cấp, khảo sát, phỏng vấn, đo tải trước mô hình | Phần thực nghiệm phải nêu dataset, xử lý, mô hình, kịch bản theo thứ tự |
| `NgoEtAl2024_MSW-GIS-ABM-HungYen.pdf`, tr. 17 | Kết luận nêu kịch bản, tỷ lệ, điểm trung chuyển và giới hạn | Kết quả tốt phải kèm điều kiện và hạn chế |

## 8. Thuật ngữ bắt buộc

Dùng `domain-glossary.md` nếu cần chi tiết. Các thuật ngữ ưu tiên:

| English | Cách viết tiếng Việt |
|---|---|
| Vehicle Routing Problem (VRP) | bài toán định tuyến xe (VRP) |
| Vehicle Routing Problem with Time Windows (VRPTW) | bài toán định tuyến xe có cửa sổ thời gian (VRPTW) |
| Pickup and Delivery Problem with Time Windows (PDPTW) | bài toán lấy và giao hàng có cửa sổ thời gian (PDPTW) |
| Multi-depot Pickup and Delivery Vehicle Routing Problem with Time Windows and Dynamic Demands | bài toán định tuyến xe lấy và giao hàng đa kho có cửa sổ thời gian và nhu cầu động (MDPDTWDD) |
| Time window | cửa sổ thời gian |
| Dynamic demand | nhu cầu động hoặc yêu cầu phát sinh động |
| Depot | kho hoặc depot; chọn một cách gọi và giữ nhất quán |
| Total operating cost (TOC) | tổng chi phí vận hành (TOC) |
| Number of vehicles (NV) | số lượng phương tiện (NV) |
| Penalty cost (PC) | chi phí phạt (PC) |
| Fixed cost (FC) | chi phí cố định (FC) |
| Maintenance cost (MC) | chi phí bảo trì (MC) |
| Transportation cost (TC) | chi phí vận chuyển (TC) |
| Inventory cost (IC) | chi phí tồn trữ (IC) |
| Adaptive Non-dominated Sorting Genetic Algorithm II | Adaptive Non-dominated Sorting Genetic Algorithm II (ANSGA-II, tạm dịch: giải thuật di truyền sắp xếp không trội thích nghi thế hệ II) |
| 3D allocation problem | 3D allocation problem (3D AP, tạm dịch: bài toán phân bổ ba chiều) |

Không dịch quá tay tên thuật toán. Nếu thuật ngữ không có bản dịch chuẩn, giữ tiếng Anh và thêm `(tạm dịch: ...)` ở lần đầu.

## 9. Cấu trúc chương và logic dẫn chuyển

Mỗi chương phải có một đoạn mở chương 3-5 câu trước heading cấp 2 đầu tiên. Đoạn mở chương không tóm tắt mục lục; nó phải tạo sợi chỉ logic.

| Chương | Vai trò | Đoạn mở nên theo kiểu |
|---|---|---|
| Mở đầu | Bối cảnh, vấn đề, mục tiêu, phạm vi, đóng góp | Số liệu -> áp lực thực tiễn -> lớp bài toán |
| Chương 1 - Tổng quan | Người khác đã làm gì, nhóm hướng liên quan, vấn đề đặt ra | Số liệu/nhu cầu -> các hướng nghiên cứu -> giới hạn khảo lược |
| Chương 2 - Cơ sở và mô hình | Định nghĩa, ký hiệu, MDPDTWDD, objective, constraints, chỉ số | Kế thừa vấn đề từ Chương 1 -> cần mô hình hóa -> phạm vi chương |
| Chương 3 - Phương pháp/pipeline | Cách đề tài tái lập, thiết kế biến thể, chạy thí nghiệm | Từ mô hình -> cần pipeline -> mô tả biến thể |
| Chương 4 - Thực nghiệm và kết quả | Protocol, artifact, bảng, hình, so sánh, kiểm định | Hệ thống đã cài đặt -> kết quả đo -> giới hạn đọc kết quả |
| Chương 5 - Thảo luận/kết luận | Đóng góp, giới hạn, hướng phát triển | Số liệu chính -> ý nghĩa -> hạn chế |

Chống lặp ý:

- Chương 1 không giảng VRP như giáo trình.
- Chương 2 không viết lại tổng quan nghiên cứu.
- Chương 3 không ôm hết đóng góp lý thuyết và kết quả.
- Chương 4 không nhắc lại thuật toán quá dài.
- Chương 5 không lặp bảng kết quả, chỉ diễn giải.

Phân bổ cải tiến:

- Lý do hình thành cải tiến: Chương 2.
- Thiết kế thuật toán/pipeline: Chương 3.
- Kết quả ablation và benchmark: Chương 4.
- Ý nghĩa, giới hạn, đóng góp: Chương 5.

## 10. Snapshot kết quả repo được phép dùng

Các số dưới đây là snapshot an toàn tại thời điểm đóng gói skill. Nếu workspace có artifact mới hơn, phải ưu tiên artifact mới và ghi nguồn.

### 10.1 Phase B official rerun, Chongqing, code hiện tại

Điều kiện:

- Dataset: `case_chongqing`, `data/process/case/case.csv`.
- Seeds: `42,43,44`.
- Budget: `max-gen=15`.
- Nguồn: `runs_phaseB_harness/*/solutions/*.sol`, `runs_gfull_phaseB/*/solutions/*.sol`, `reports/tables_phaseB_harness/*.csv`, `reports/tables_gfull_phaseB/*.csv`.

Kết quả:

| Variant | TOC mean | NV mean | PC mean | Runtime mean |
|---|---:|---:|---:|---:|
| B0 | 6345.2133 | 26.6667 | 0.0000 | `2.7601s` trong bảng 6.1 của `reports.md`; không khóa claim runtime nếu chưa kiểm tra lại artifact vì `reports.md` có ghi chú runtime B0 không thống nhất |
| G2-current | 6345.4167 | 26.6667 | 0.0000 | kiểm tra bảng trước khi viết |
| G3-route-repair | 6335.4200 | 26.6667 | 0.0000 | kiểm tra bảng trước khi viết |
| G4-elite-archive | 6334.5300 | 26.6667 | 0.0000 | kiểm tra bảng trước khi viết |
| G5-deep-repair | 6327.2567 | 26.6667 | 0.0000 | kiểm tra bảng trước khi viết |
| GRANITE-STAP-NSGA / G-full | 6326.4667 | 26.6667 | 0.0000 | 4.1479s |

Claim được phép:

- G-full thắng B0 `3/3` seed, mean delta `-18.7467` (`-0.2961%`) trong thiết lập Chongqing max-gen=15.
- PC bằng `0` cho B0/G2/G3/G4/G5/G-full trong official rerun hiện tại.
- Khác biệt TOC trên Chongqing là nhỏ; không dùng riêng kết quả này để claim hiệu quả lớn.

Claim cấm:

- "G-full vượt trội" nếu không kèm giới hạn.
- "Penalty bị tắt" hoặc "làm phẳng PC"; PC bằng 0 do route/departure-time hợp lệ.
- Dùng số legacy `97k/102k` làm paper-comparable.

### 10.2 So sánh Table 22 mainPaper

Mốc mainPaper Table 22:

- Insertion strategy/S3-SA: TOC `6736.0`, NV `27`, PC `0`.

G-full Chongqing max-gen=15:

| Cách đọc | TOC mean | So với Table 22 |
|---|---:|---:|
| Raw repo output | 6326.4667 | `-6.0798%` |
| FC normalized to 3216 | 6714.4667 | `-0.3197%` |
| FC+MC normalized to Table 22 | 6751.0628 | `+0.2236%` |

Claim được phép:

- Raw output của repo thấp hơn Table 22 insertion strategy `6.0798%`.
- Nếu chỉ chuẩn hóa FC, G-full vẫn thấp hơn `0.3197%`.
- Nếu chuẩn hóa cả FC và MC, G-full cao hơn `0.2236%`; vì vậy không claim "vượt Table 22" một cách tuyệt đối.

Claim cấm:

- Dùng `99374` làm mốc Table 22.
- Nói đã reproduce hoàn toàn Table 22 nếu chưa kiểm tra provenance dữ liệu và cost component.

### 10.3 Paper-ready full run

Trạng thái:

- `285/285` jobs PASS, `0` FAIL.
- Nguồn: `runs_paper_full`, `reports/tables_paper_full`, `logs/paper_full_progress.csv`.
- Gồm benchmark 30 instance x 3 seed cho B0/G3/G-full và case Chongqing x 3 seed cho B0/G3/G4/G5/G-full.

Benchmark paper-ready:

- G-full vs B0: TOC mean delta `-12832.9680` (`-14.7373%`), wins `85/90`, NV mean delta `0`.
- G3 vs B0: TOC mean delta `-8030.7862` (`-11.1352%`).

Case Chongqing paper-ready:

- G-full vs B0: TOC mean delta `-14.8667` (`-0.2393%`), delta NV `0`, wins `3/3`.

Claim được phép:

- Full run hiện có đủ artifact để nói về tín hiệu cải thiện trên benchmark paper-ready.
- Phải ghi rõ dataset, seed, budget và bảng nguồn.

### 10.4 Paper-budget benchmark G-full, max-gen=150

Điều kiện:

- Dataset: `data/process/benchmark/*.csv`.
- Variant: `GRANITE-STAP-NSGA / G-full`.
- Seeds: `42,43,44`.
- Budget: `max-gen=150`.
- Jobs: `90/90` PASS.
- Nguồn: `reports/tables_paper_benchmark_gen150`, `runs_paper_benchmark_gen150` nếu có.

Kết quả:

- TOC mean `22910.1780`.
- NV mean `10.2222`.
- PC mean `17832.5007`.
- Runtime mean `6.2226s`.
- So với G-full max-gen=15: TOC giảm `47.5679%`, NV giảm `1.1444`, PC giảm `20403.4595`.

Claim được phép:

- Tăng budget giúp G-full cải thiện TOC/PC rõ trong benchmark local.
- Chưa đủ để claim reproduce Table 16.

Claim cấm:

- "Đã khớp Table 16".
- So sánh công bằng với B0/G3 cùng budget 150 nếu B0/G3 max-gen=150 chưa có artifact paired.

### 10.5 XY-grid bucketing probe

Điều kiện:

- Thay Geohash bằng XY-grid bucket cho benchmark Euclidean.
- Jobs: `90/90` PASS.

Kết quả:

- TOC/NV/PC không đổi so với G-full max-gen=150 trước đó.
- Runtime mean thay đổi nhẹ: `6.2226s` vs `6.1432s` theo bảng trong `reports.md`.

Claim được phép:

- Giả thuyết "Geohash làm benchmark tệ" bị bác bỏ trong cấu hình hiện tại.

Claim cấm:

- Nói XY-grid tốt hơn về chất lượng nghiệm.

### 10.6 B_v fix và repair probe cho benchmark PC cao

Điều kiện:

- Subset 5 instance có PC cao.
- So sánh trước/sau sửa chọn departure time `B_v`.

Kết quả chính:

- TOC mean trước `75670.7733`, sau `62802.9887`.
- PC mean trước `66790.9113`, sau `54021.4703`.
- NV mean trước `15.3333`, sau `15.0667`.
- Wins `13/15`.

Claim được phép:

- `B_v` fix là cải tiến có bằng chứng trên subset PC cao vì giảm TOC/PC mà không làm tăng NV trung bình.

Claim cấm:

- Dùng subset này để claim tổng quát toàn benchmark nếu chưa có full rerun.
- Claim split repair sâu là phương án chính nếu NV tăng quá cao.

### 10.7 Cordeau evidence

Trước audit `B_v`:

- Pilot 4 instance x 3 seed, max-gen=6: G3 thắng B0 `12/12`, mean percent delta `-16.8169%`.
- Full seed42, 30 instance, max-gen=6: G3 thắng B0 `30/30`, mean percent delta `-18.9826%`, Wilcoxon p=`9.31323e-10`.

Sau re-evaluate với `B_v`:

- G3 vs B0: thắng `26/30`, paired mean percent delta `-9.7318%`, Wilcoxon p=`4.16301e-07`.
- G3 vs G2: thắng `27/30`, paired mean percent delta `-9.4337%`, Wilcoxon p=`5.12227e-08`.

Claim được phép:

- Cordeau cũ là evidence truy vết hoặc evidence trước audit.
- Sau audit, tín hiệu vẫn còn nhưng effect nhỏ hơn.

Claim cấm:

- Nói Cordeau full current-code multi-seed đã hoàn tất nếu chưa có artifact mới.

### 10.8 Kiểm chứng code

Các mốc đã xuất hiện trong `reports.md`:

- `pytest tests -q`: từng có `34 passed`, sau đó `36 passed`, sau B_v/repair có `39 passed`.
- `ruff check src tests scripts/run_paper_full_experiment.py`: passed ở thời điểm ghi report.

Khi viết báo cáo hiện tại, nếu cần claim test mới nhất, phải chạy lại hoặc ghi là "theo log trong `reports.md`".

## 11. Các claim tuyệt đối cấm

Không viết:

- "Đề tài phát triển từ Wang et al." như một câu định vị chính.
- "G-full vượt trội" nếu không có dataset, seed, budget, số liệu và kiểm định.
- "Đã reproduce Table 16" nếu PC benchmark còn cao và chưa khớp.
- "Đã reproduce Table 22 hoàn toàn" nếu chưa kiểm tra provenance và normalized cost.
- "Geohash là nguyên nhân benchmark tệ" sau khi XY-grid cho kết quả không đổi.
- "Time-dependent routing đúng nghĩa" vì chưa có dữ liệu tốc độ theo thời điểm.
- "Regret-2/urgency tier có tác động độc lập" nếu chưa có ablation riêng.
- "Penalty bị tắt" khi PC=0.
- "Cordeau current-code full multi-seed đã xong" nếu chưa có artifact.
- "Hiệu quả", "tối ưu", "vượt trội", "đáng kể" nếu không có số liệu ngay gần đó.

## 12. Hình và bảng

Quy tắc caption:

| Loại | Vị trí tên | Ví dụ |
|---|---|---|
| Bảng | Trên bảng | `Bảng 4.2. TOC trung bình theo biến thể (max-gen=15)` |
| Hình | Dưới hình | `Hình 4.1. Hội tụ TOC theo thế hệ (seed 42)` |

Trước bảng/hình phải có câu dẫn:

- Thiết lập dữ liệu.
- Mục đích bảng/hình.
- Chỉ số đọc chính.

Sau bảng/hình phải có đoạn đọc kết quả:

- Nêu 1-3 số liệu chính.
- So sánh.
- Diễn giải.
- Giới hạn.

Không thả bảng/hình độc lập. Không dùng hình minh họa chung nếu cần hình từ artifact.

## 13. Vòng xác thực bắt buộc

Agent phải đi qua các vòng dưới đây trước khi gửi nháp cho user.

### Vòng 1 - Section gate

```text
[ ] Đã xác định đúng tiểu mục cấp nhỏ nhất?
[ ] Không viết lan sang tiểu mục sau?
[ ] Có đoạn mở nếu đây là chương mới?
[ ] Không tự ghi vào reports.md?
```

### Vòng 2 - Evidence gate

```text
[ ] Mỗi claim số liệu có citation IEEE hoặc artifact path?
[ ] Bối cảnh Việt Nam dùng BCT2024, không dùng mainPaper?
[ ] Mô hình/thuật toán dùng mainPaper hoặc code, không dùng BCT2024?
[ ] Kết quả repo dùng .sol/CSV/log, không dùng paper thay artifact?
[ ] Nếu là inference, ngôn ngữ đã thận trọng?
```

### Vòng 3 - Citation gate

```text
[ ] Nội dung chính chỉ có IEEE [n], không có raw [CITE: ...]?
[ ] Block Tài liệu tham khảo có entry IEEE đầy đủ?
[ ] DOI đã có link nếu biết?
[ ] Web source có Accessed date?
[ ] Tham chiếu sử dụng ghi rõ key -> [n] -> claim -> vị trí?
```

### Vòng 4 - Style gate

```text
[ ] Câu đầu tiên có số liệu, sự kiện, nguồn, artifact hoặc tên nghiên cứu?
[ ] Không mở bằng triết lý chung?
[ ] Không liệt kê số liệu dày như thống kê?
[ ] Có câu diễn giải sau số liệu?
[ ] Không có 3 câu liên tiếp cùng cấu trúc?
[ ] Có câu ngắn xen câu dài?
[ ] Không có cụm "quan trọng", "toàn diện", "đáng kể", "hiệu quả" nếu không có dữ liệu?
```

### Vòng 5 - Result gate

```text
[ ] Nếu nhắc TOC/NV cuối, nguồn là .sol hoặc bảng sinh từ .sol?
[ ] Nếu nhắc runtime/convergence, nguồn là stats CSV/log?
[ ] Nếu nhắc Table 22, dùng TOC 6736.0, NV 27?
[ ] Không dùng số legacy 97k/102k cho paper-comparable?
[ ] Không claim Table 16/Table 22 quá mức?
```

### Vòng 6 - Project-error gate

```text
[ ] Không viết "phát triển từ Wang" quá trực diện?
[ ] Không thay Wang phát biểu mà thiếu cite?
[ ] Không nói G-full là TDVRP đúng nghĩa?
[ ] Không claim Cordeau current-code nếu artifact chưa có?
[ ] Không biến Mở đầu thành văn kỹ thuật quá sâu?
```

### Vòng 7 - Human approval gate

```text
[ ] Có block Điểm cần human duyệt?
[ ] Có hỏi user duyệt trước khi ghi vào beWritten.md?
[ ] Không viết tiếp tiểu mục mới khi user chưa yêu cầu?
```

## 14. Công thức viết nhanh theo từng phần

### 14.1 Mở đầu

Cấu trúc:

1. Câu số liệu logistics Việt Nam.
2. Câu diễn giải áp lực điều phối.
3. Câu nối sang lớp bài toán định tuyến.
4. Câu giới thiệu MDPDTWDD với citation mainPaper.
5. Câu định vị đề tài: tái lập, kiểm chứng, thiết kế pipeline/biến thể, đánh giá artifact.

Không làm:

- Không giải thích chi tiết equation.
- Không liệt kê 5 số liệu BCT.
- Không nói "Logistics rất quan trọng".

### 14.2 Tổng quan nghiên cứu

Cấu trúc:

1. Nhóm nghiên cứu theo hướng.
2. Mỗi nhóm nêu 1-2 paper đại diện.
3. Chỉ ra giới hạn theo phạm vi khảo lược.
4. Dẫn sang vấn đề của đề tài.

Không làm:

- Không liệt kê từng paper như danh bạ.
- Không dùng `paper/non-update/` để cập nhật state-of-the-art chính thức.

### 14.3 Cơ sở và mô hình

Cấu trúc:

1. Định nghĩa lớp bài toán.
2. Ký hiệu/tập/chỉ số.
3. Objective và cost components.
4. Constraints.
5. Mối liên hệ với chỉ số đánh giá repo.

Nguồn chính: Wang et al., `paper_math_blocks.md`, code nếu cần.

### 14.4 Phương pháp

Cấu trúc:

1. Pipeline dữ liệu.
2. Baseline.
3. Biến thể G1-G5/G-full.
4. Cách ghi artifact.
5. Protocol so sánh.

Viết các bước bằng văn xuôi, không thành manual chạy lệnh trừ khi user yêu cầu.

### 14.5 Kết quả

Cấu trúc:

1. Dẫn vào bảng.
2. Nêu thiết lập.
3. Đọc số liệu chính.
4. So sánh cùng seed/budget.
5. Nhận xét giới hạn.

Luôn kèm artifact path.

### 14.6 Thảo luận/kết luận

Cấu trúc:

1. Bắt đầu bằng số liệu đã chứng minh.
2. Diễn giải đóng góp theo ba lớp: mô hình hóa, pipeline/thuật toán, thực nghiệm.
3. Nêu hạn chế.
4. Nêu hướng phát triển.

Không dùng "Nhìn chung" làm câu đầu.

## 15. Quy tắc ghi vào beWritten.md

Trong chatbox:

- Luôn đưa nháp và tài liệu tham khảo tương ứng.
- Không dùng `reports.md` làm nơi lưu tạm.
- Không tự cập nhật `beWritten.md` nếu user chưa duyệt.

Khi user duyệt:

- Tạo `beWritten.md` nếu chưa có.
- Ghi đúng phần đã duyệt.
- Không sửa nội dung đã duyệt nếu user không yêu cầu.
- Nếu có chỉnh nhỏ để đồng bộ numbering/citation, ghi rõ trong phản hồi.

## 16. Mini checklist trước khi agent kết thúc lượt

```text
[ ] Tôi đã viết đúng một tiểu mục cấp nhỏ nhất.
[ ] Tôi đã dùng IEEE [n], không dùng raw key trong đoạn.
[ ] Tôi đã có Tài liệu tham khảo ngay dưới nháp.
[ ] Tôi đã có Tham chiếu sử dụng giải thích nguồn đỡ claim nào.
[ ] Tôi đã ghi Điểm cần human duyệt.
[ ] Tôi không ghi vào reports.md.
[ ] Tôi không ghi vào beWritten.md nếu user chưa duyệt.
[ ] Tôi không claim quá mức so với artifact.
[ ] Tôi không biến văn phong tự nhiên thành mẹo né detector.
```

## 17. Checklist cho người chỉnh skill/package

Khi sửa skill hoặc đóng gói lại:

```text
[ ] `SKILL.md` có link tới file mega-rule này.
[ ] `references/mega-rule-report-writing.md` nằm trong package skill.
[ ] `quick_validate.py` báo skill hợp lệ.
[ ] `rg "mega-rule-report-writing"` tìm thấy ít nhất trong SKILL.md.
[ ] Nếu tạo zip, zip đã được refresh sau khi sửa.
```
