# References Guide

Mục tiêu của file này là hướng dẫn AI khai thác paper và báo cáo khoa học đúng vai trò khi viết `reports.md`. Không chỉ nêu tên paper; phải biết paper đó đang đỡ claim nào trong đoạn.

## Quy trình bắt buộc trước khi viết đoạn có citation

1. Xác định tiểu mục đang viết và loại claim chính: bối cảnh, tổng quan, mô hình, thuật toán, thực nghiệm, kết quả, hoặc thảo luận.
2. Chọn nguồn từ `source-map.md` và citation key từ `paper-catalog.md`. Citation key chỉ để quản lý nội bộ.
3. Tạo "gói bằng chứng" ngắn trước khi viết:
   - Nguồn/citation key.
   - Số IEEE sẽ xuất hiện trong báo cáo, ví dụ `[1]`, `[2]`, theo thứ tự xuất hiện trong tiểu mục.
   - Claim được phép viết từ nguồn đó.
   - Vị trí bằng chứng: section, trang, bảng, hình, phương trình, hoặc artifact path nếu đã biết.
   - Giới hạn: nguồn không chứng minh điều gì.
4. Viết đoạn sao cho trích dẫn IEEE `[n]` nằm gần câu được đỡ, không gom citation mơ hồ ở cuối đoạn.
5. Ghi block **Tài liệu tham khảo** với entry IEEE đầy đủ ngay dưới đoạn, sau đó ghi block **Tham chiếu sử dụng** để giải thích vai trò nguồn.

Nếu chưa đọc được nội dung paper hoặc chưa biết vị trí bằng chứng, không bịa trang/bảng/hình; dùng trích dẫn IEEE ở mức thận trọng và ghi rõ `[cần kiểm tra trang/bảng/hình]` trong block kiểm duyệt. Không đưa raw key `[CITE: ...]` vào đoạn báo cáo.

## Chuẩn IEEE, DOI và nguồn web

- Paper có DOI: entry IEEE phải có DOI link ở cuối, dạng `doi: https://doi.org/...`.
- Paper không có DOI đã xác minh: không bịa DOI; ghi trong **Điểm cần human duyệt** là `DOI cần xác minh`.
- Nguồn web: entry IEEE phải có URL và `Accessed: yyyy-mm-dd`.
- Sách/báo cáo chính thống không có DOI: ghi cơ quan, tên tài liệu, nơi xuất bản, nhà xuất bản, năm; nếu dùng bản online thì thêm URL và ngày truy cập.
- Nếu cần thêm paper tiếng Việt/tiếng Anh: ưu tiên DOI/trang nhà xuất bản; nếu cần user tải, trả lời bằng link DOI hoặc trang chính thức.
- Ví dụ văn phong trong `vietnamese-academic-style.md` phải lấy từ paper/báo cáo thật trong repo hoặc nguồn đã xác minh. Không tự tạo mẫu nếu chưa chỉ ra paper đã học pattern đó.

## Schema khai thác cho mỗi paper

Khi đọc một paper, trích tối thiểu các trường sau vào ghi chú làm việc hoặc block tham chiếu:

| Trường | Cần lấy |
|---|---|
| Citation key nội bộ | Theo `paper-catalog.md`, ví dụ `[CITE: WangEtAl2025_MDPDTWDD-mainPaper]`; không xuất hiện trong đoạn báo cáo |
| Trích dẫn trong bài | IEEE numeric, ví dụ `[1]`, `[2]`; đánh số theo thứ tự xuất hiện trong phần đang viết |
| Entry tài liệu tham khảo | IEEE: `[n] Tác giả/Cơ quan, "Tên bài" hoặc *Tên tài liệu*, thông tin xuất bản/tạp chí, vol./no./Art. no./trang, năm.` |
| Loại nguồn | Paper thuật toán, review, case study Việt Nam, báo cáo chính sách, decree, artifact repo |
| Bài toán/biến thể | VRP/VRPTW/PDPTW/MDVRP/MDPDTWDD, dynamic/static, pickup-delivery, time windows, split load, multi-depot |
| Ràng buộc chính | Depot, fleet, time window, demand động, capacity, pickup-delivery pair, precedence, emission/fuel nếu có |
| Phương pháp | Exact, matheuristic, GA, TS, ALNS, VNS, NSGA-II, decomposition, insertion strategy, clustering |
| Dữ liệu/case | Benchmark, thực địa, thành phố, số depot/khách/xe, thời gian mô phỏng |
| Chỉ số | TOC, NV, distance, service level, runtime, Pareto, convergence, cost components |
| Kết quả dùng được | Con số/bảng/hình chính xác; nếu chưa xác minh thì không viết như số liệu cuối |
| Giới hạn | Điều paper không xử lý hoặc chưa phù hợp với MDPDTWDD |
| Vai trò trong report | Dẫn bối cảnh, nhóm related work, định nghĩa mô hình, mốc so sánh, hoặc đối chiếu hạn chế |

## Vai trò nguồn theo loại claim

| Loại claim | Nguồn phù hợp | Không dùng |
|---|---|---|
| Bối cảnh logistics Việt Nam, hạ tầng, chính sách, FTZ | Nội bộ: `[CITE: BCT2024_LogisticsVN]`; trong bài: `[1]` hoặc số IEEE tương ứng | Paper thuật toán để suy diễn chính sách Việt Nam |
| Lý do cần dynamic multi-depot pickup-delivery | MainPaper + Logistics VN nếu nói về bối cảnh Việt Nam | Báo cáo Logistics VN để chứng minh thuật toán |
| Định nghĩa MDPDTWDD, hàm mục tiêu, constraint | MainPaper, `paper_math_blocks.md`, code models/costs | Review hoặc báo cáo chính sách |
| Related work VRP/PDPTW/MDVRP | `paper/references/*.pdf` theo `paper-catalog.md` | `paper/non-update/` khi viết tổng quan chính thức |
| Mốc Chongqing, Table 22 | MainPaper, Table 22: TOC 6736.0, NV 27 | Con số 99374 hoặc stats CSV cuối nếu trái `.sol` |
| Kết quả repo | `.sol`, `runs*/stats/*.csv`, `reports/tables/*.csv`, logs | Paper citation thay cho artifact repo |

## Cách dùng báo cáo Logistics Việt Nam 2024

Nguồn: `paper/references/BCT2024_BaoCaoLogisticsVN-FTZ.pdf`.

- Key nội bộ: `[CITE: BCT2024_LogisticsVN]`
- Trích dẫn trong bài: `[n]`
- Entry tham khảo IEEE: `[n] Bộ Công Thương, *Báo cáo Logistics Việt Nam 2024: Khu thương mại tự do*. Hà Nội, Việt Nam: Nhà xuất bản Công Thương, 2024.`

Dùng bắt buộc khi viết:

- **Mở đầu**: bối cảnh logistics Việt Nam, áp lực tổ chức vận tải, vai trò hạ tầng/kết nối, và lý do bài toán tối ưu tuyến có ý nghĩa thực tiễn.
- **Chương 1** nếu cần cầu nối giữa nghiên cứu VRP quốc tế và bối cảnh triển khai ở Việt Nam.
- **Phần thuật ngữ hoặc dẫn nhập chính sách** khi nhắc khu thương mại tự do, logistics địa phương, chuỗi cung ứng, hoặc định hướng quản lý.

### Dùng số liệu như điểm neo, không liệt kê

Khi dùng báo cáo Logistics VN trong **Mở đầu**, không viết thuần mô tả nhưng cũng không biến đoạn văn thành danh sách thống kê. Chọn **1-2 chỉ báo neo** có liên quan trực tiếp tới luận điểm, rồi dùng chúng để rút ngắn diễn giải và chuyển mạch sang lý do nghiên cứu. Phần Mở đầu chưa đi sâu kỹ thuật chuyên ngành; tránh giải thích dài về thuật toán, hàm mục tiêu, chi phí, benchmark.

Quy tắc:

- Mỗi đoạn Mở đầu chỉ nên có 1 số liệu chính, tối đa 2 nếu hai số cùng phục vụ một luận điểm.
- Sau mỗi số liệu phải có câu diễn giải ý nghĩa; không nối nhiều số liên tiếp.
- Ưu tiên số có khả năng "mở vấn đề": kim ngạch xuất nhập khẩu, sản lượng vận tải, hoặc số doanh nghiệp logistics/vận tải kho bãi.
- Không đưa quá nhiều GDP, LPI, vốn, lao động, xuất siêu, PMI trong cùng một đoạn.
- Các số liệu dày hơn chuyển sang Chương 1 hoặc bảng/hình bối cảnh.

| Nhóm chỉ báo | Ví dụ đã xác minh trong báo cáo | Dùng để nói |
|---|---|---|
| Tăng trưởng kinh tế | GDP 9 tháng đầu năm 2024 tăng 6,82%; khu vực dịch vụ tăng 6,95% và đóng góp 48,41% vào tăng trưởng giá trị tăng thêm | Logistics gắn với tăng trưởng dịch vụ và sản xuất |
| Xuất nhập khẩu | 9 tháng đầu năm 2024, kim ngạch xuất nhập khẩu đạt 578,47 tỷ USD, tăng 16,3%; xuất khẩu tăng 15,4%, nhập khẩu tăng 17,3%; xuất siêu 20,79 tỷ USD | Nhu cầu vận tải, kho bãi, điều phối hàng hóa tăng |
| Vận tải hàng hóa | 9 tháng đầu năm 2024, vận tải hàng hóa đạt 1.917,9 triệu tấn, tăng 13,7%; luân chuyển đạt 393,35 tỷ tấn-km, tăng 10,5% | Áp lực tối ưu hóa tuyến và sử dụng phương tiện |
| Doanh nghiệp logistics/vận tải kho bãi | 9 tháng đầu năm 2024 có 6.503 doanh nghiệp vận tải kho bãi thành lập mới; vốn đăng ký 36.551 tỷ đồng; lao động 28.898 người; số doanh nghiệp tăng 13,5% | Thị trường logistics mở rộng nhưng phân tán, cần năng lực điều phối |
| Năng lực logistics | LPI Việt Nam năm 2023 xếp 43/139; thuộc top 5 ASEAN và top 10/50 thị trường logistics mới nổi | Tiềm năng phát triển còn lớn nhưng cần cải thiện hiệu quả |

Khi đưa số liệu vào đoạn, ghi số liệu đủ đơn vị và mốc thời gian; không dùng các cụm chung như "tăng mạnh", "phát triển nhanh" nếu không có số đi kèm. Trong **Tham chiếu sử dụng**, ghi vị trí: trang/bảng/hình, ví dụ `tr. 26`, `tr. 65`, `tr. 80-81`.

Mẫu tốt:

```markdown
Kim ngạch xuất nhập khẩu 9 tháng đầu năm 2024 đạt 578,47 tỷ USD, tăng 16,3% so với cùng kỳ [1]. Con số này không chỉ phản ánh quy mô lưu chuyển hàng hóa, mà còn cho thấy áp lực điều phối vận tải và sử dụng phương tiện ngày càng lớn trong các mạng logistics nhiều điểm.
```

Mẫu cần tránh:

```markdown
GDP tăng 6,82%, dịch vụ tăng 6,95%, xuất nhập khẩu đạt 578,47 tỷ USD, xuất khẩu tăng 15,4%, nhập khẩu tăng 17,3%, vận tải đạt 1.917,9 triệu tấn, doanh nghiệp vận tải kho bãi tăng 13,5%...
```

Không dùng báo cáo Logistics VN để:

- Khẳng định MDPDTWDD là mô hình tốt hơn mô hình khác.
- Chứng minh thuật toán 3DAPANSGA-II, GA/TS/ALNS, hay pipeline repo đúng/sai.
- Lấy số liệu vận hành cho benchmark Chongqing nếu paper gốc hoặc artifact repo mới là nguồn.

Mẫu diễn giải đúng:

```markdown
Bối cảnh logistics Việt Nam cho thấy nhu cầu tổ chức vận tải có khả năng thích ứng với hạ tầng, mạng lưới dịch vụ và định hướng phát triển logistics địa phương [1]. Từ nền bối cảnh đó, báo cáo lựa chọn lớp bài toán định tuyến đa kho có yêu cầu động như một đối tượng nghiên cứu phù hợp; các khái niệm mô hình hóa và mốc đối chứng thuật toán được đặt trong dòng nghiên cứu MDPDTWDD hiện có [2].
```

## Cách dùng mainPaper

Nguồn chính:

- `paper/mainPaper/ENG The multi-depot pickup and delivery vehicle routing problem with time windows and dynamic demands.md`
- `paper/mainPaper/paper_math_blocks.md`
- Key nội bộ: `[CITE: WangEtAl2025_MDPDTWDD-mainPaper]`
- Trích dẫn trong bài: `[n]`
- Entry tham khảo IEEE: `[n] Y. Wang, M. Gou, S. Luo, J. Fan, and H. Wang, "The multi-depot pickup and delivery vehicle routing problem with time windows and dynamic demands," *Engineering Applications of Artificial Intelligence*, vol. 139, Art. no. 109700, 2025, doi: https://doi.org/10.1016/j.engappai.2024.109700.`

Dùng cho:

- Định nghĩa bài toán MDPDTWDD.
- Thành phần chi phí, ràng buộc, dynamic demand, time windows.
- Thuật toán gốc 3DAPANSGA-II và insertion strategy.
- Mốc so sánh Table 22: TOC 6736.0, NV 27.

Khi trích mainPaper, ưu tiên ghi vị trí cụ thể: section, equation, algorithm, table, hoặc figure. Nếu chưa xác minh vị trí, ghi `[cần kiểm tra vị trí trong mainPaper]`.

### Định vị đóng góp khi dùng mainPaper

- Không viết: "đề tài phát triển từ nghiên cứu của Wang", "dựa trên Wang để phát triển", hoặc câu khiến đóng góp của đề tài trông như chỉ thay Wang phát biểu.
- Nên viết: "đề tài lựa chọn lớp bài toán MDPDTWDD", "báo cáo sử dụng các khái niệm và mốc đối chứng đã được công bố", "trọng tâm của đề tài là tái lập, kiểm chứng và đánh giá pipeline/biến thể trong môi trường thực nghiệm của repo".
- Khi câu mô tả định nghĩa, mô hình, thuật toán 3DAPANSGA-II, insertion strategy, Table 22 hoặc case Chongqing từ mainPaper, phải cite IEEE `[n]` gần câu đó.
- Khi câu mô tả đóng góp của repo như harness, biến thể, sửa pipeline, artifact, số liệu thực nghiệm, dùng `[SOURCE: ...]` hoặc artifact repo thay cho paper.

## Cách dùng paper related work

Khi viết Chương 1, nhóm paper theo vai trò thay vì liệt kê tuần tự:

| Nhóm | Citation gợi ý | Dùng để nói |
|---|---|---|
| Case study/VRP Việt Nam | `[CITE: NguyenEtAl2016_VRPTW-VN]`, `[CITE: NgoEtAl2024_MSW-GIS]`, `[CITE: CaoTran2022_GA-VRP]`, `[CITE: CaoTran2023_TabuSearch-VRP]` | Bài toán định tuyến đã được áp dụng trong bối cảnh Việt Nam nhưng thường chưa bao phủ đầy đủ multi-depot + pickup-delivery + demand động |
| Dynamic / periodic PDPTW | `[CITE: KaramiEtAl2020_Periodic-DynPDPTW]`, `[CITE: SilvaEtAl2020_DVRPTW]`, `[CITE: JeongMoon2024_DPDP-AR]`, `[CITE: DuEtAl2023_DPDP-LIFO]` | Demand động, tái gán, ràng buộc pickup-delivery, cập nhật trong thời gian vận hành |
| Multi-depot / collaboration / shared resources | `[CITE: LiEtAl2018_MDVRP-SharedDepot]`, `[CITE: KocaturkEtAl2021_MDHFVRPB]`, `[CITE: WangEtAl2021_CMDPDLN]`, `[CITE: ZhangEtAl2022_HMCVRP]` | Nhiều depot, chia sẻ depot/fleet, hợp tác logistics, split load |
| Metaheuristic / exact / review | `[CITE: AhmadiOsman2005_GRAMPS-CCP]`, `[CITE: PraxedesEtAl2024_BCP-VRPSPD]`, `[CITE: SoeffkerEtAl2022_SDVRP-Review]`, `[CITE: Xu2024_EVRP-Review]` | Nền thuật toán, cách phân loại phương pháp, điểm mạnh/yếu của heuristic và exact |
| Pickup-delivery / simultaneous pickup-delivery | `[CITE: WangEtAl2018_CMCVRPSDP]`, `[CITE: ZhuSheu2018_SPDPSD]` | Pickup-delivery, simultaneous delivery-pickup, chi phí/chuỗi cung ứng liên quan |

Không viết kiểu "nhiều nghiên cứu đã..." nếu không gắn ít nhất một nhóm citation cụ thể.

## Chuẩn block Tài liệu tham khảo và Tham chiếu sử dụng

Mỗi đoạn có citation phải có block:

```markdown
**Tài liệu tham khảo**
- [1] Bộ Công Thương, *Báo cáo Logistics Việt Nam 2024: Khu thương mại tự do*. Hà Nội, Việt Nam: Nhà xuất bản Công Thương, 2024.
- [2] Y. Wang, M. Gou, S. Luo, J. Fan, and H. Wang, "The multi-depot pickup and delivery vehicle routing problem with time windows and dynamic demands," *Engineering Applications of Artificial Intelligence*, vol. 139, Art. no. 109700, 2025, doi: https://doi.org/10.1016/j.engappai.2024.109700.

**Tham chiếu sử dụng**
- `[CITE: BCT2024_LogisticsVN]` → `[1]`: neo bối cảnh logistics Việt Nam và nhu cầu thực tiễn; cần kiểm tra trang/bảng nếu lấy số liệu cụ thể.
- `[CITE: WangEtAl2025_MDPDTWDD-mainPaper]` → `[2]`: định nghĩa MDPDTWDD và vai trò demand động/time windows; vị trí: [section/equation/table nếu biết].
- `[SOURCE: runs/.../*.sol]`: số liệu TOC/NV của thực nghiệm repo.
```

## Các lỗi phải tránh

- Dùng báo cáo Logistics VN như nguồn thuật toán.
- Dùng mainPaper để nói về chính sách Việt Nam nếu claim đó thuộc báo cáo Logistics VN.
- Đưa raw key như `[CITE: BCT2024_LogisticsVN]` vào đoạn báo cáo thay cho trích dẫn IEEE `[n]`.
- Viết quá trực diện rằng đề tài "phát triển từ Wang"; chỉ dùng mainPaper như nguồn học thuật/mốc đối chứng cho claim tương ứng, còn đóng góp repo phải nêu bằng artifact và thiết kế thực nghiệm riêng.
- Trích paper non-update để làm state-of-the-art chính thức của báo cáo, trừ khi user yêu cầu phần đọc thêm riêng.
- Viết số liệu, DOI, venue, trang, bảng, hoặc tên thuật toán khi chưa thấy trong nguồn.
- Gom 5 citation ở cuối đoạn mà không rõ citation nào đỡ claim nào.
- Dịch quá tay tên bài toán làm mất thuật ngữ chuẩn; dùng glossary khi cần.
