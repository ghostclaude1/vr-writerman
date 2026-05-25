# Vietnamese Academic Style

Mục tiêu: dùng paper/báo cáo tiếng Việt làm chuẩn thuật ngữ, nhịp câu và cách dẫn dắt; dùng paper tiếng Anh làm chuẩn lập luận khoa học, thiết kế mô hình và diễn giải kết quả. Khi hai nguồn xung đột, ưu tiên: tính đúng học thuật -> thuật ngữ đúng chuyên ngành -> văn phong tiếng Việt tự nhiên.

Lưu ý về văn máy: file này bắt buộc sửa các dấu hiệu văn bản đều nhịp, chung chung, thiếu chi tiết và giống mẫu sinh tự động. Không mô tả mục tiêu là đánh lừa hệ thống phát hiện; mục tiêu hợp lệ là văn học thuật tự nhiên, có bằng chứng, có nhịp câu biến thiên và có dấu vết nghiên cứu thật.

## 1. Nguồn chuẩn phong cách

| Nhóm nguồn | File | Vai trò |
|---|---|---|
| Chuẩn văn phong/bối cảnh tiếng Việt | `BCT2024_BaoCaoLogisticsVN-FTZ.pdf` | Cách mở vấn đề bằng số liệu, câu chuyển, cách viết báo cáo chính thống |
| Chuẩn thuật ngữ VRP tiếng Việt | `CaoTran2022_GA-VRP.pdf`, `CaoTran2023_TabuSearch-VRP.pdf` | Thuật ngữ giải thuật, bài toán định tuyến xe, cách định nghĩa khái niệm trong paper VN |
| Chuẩn case study Việt Nam | `NgoEtAl2024_MSW-GIS-ABM-HungYen.pdf`, `NguyenEtAl2016_VRPTW-ICDTienSon.pdf` | Cách gắn bài toán định tuyến với dữ liệu/case thực tế Việt Nam |
| Chuẩn lập luận khoa học tiếng Anh | `paper/mainPaper/`, các Q1/Q2 paper trong `paper/references/` | Gap, mô hình, thuật toán, thí nghiệm, kết quả |

Nếu cần thêm paper để học văn phong/thuật ngữ:

- Tìm nguồn chính thống: DOI, trang tạp chí, cơ sở dữ liệu trường/tạp chí, nhà xuất bản.
- Đưa user DOI/link tải nếu cần user download. Không tự bịa DOI, tác giả, venue, số trang.
- Với nguồn web, reference IEEE phải có `Accessed: yyyy-mm-dd`.

## 2. Mở đầu bài, chương, mục

Câu đầu tiên không bao giờ là câu triết lý chung. Câu mở phải có ít nhất một trong các neo sau: số liệu, tên nghiên cứu/tác giả, sự kiện chính sách, artifact repo, hoặc đối tượng cụ thể.

Sai:

> Logistics đóng vai trò quan trọng trong nền kinh tế hiện đại.

Đúng:

> Kim ngạch xuất nhập khẩu hàng hóa của Việt Nam trong 9 tháng đầu năm 2024 đạt 578,47 tỷ USD, tăng 16,3% so với cùng kỳ [1].

Sau câu mở, không liệt kê dày. Dùng số liệu để rút bớt lời văn và mở ra ý nghĩa:

> Con số này làm nổi rõ áp lực điều phối vận tải và sử dụng phương tiện trong các mạng logistics nhiều điểm, nơi nhu cầu có thể thay đổi theo thời gian.

### Ví dụ học từ paper/báo cáo thật

Các ví dụ dưới đây là pattern rút ra từ nguồn đã có trong repo; khi viết report, bắt chước **cách tổ chức câu và chức năng lập luận**, không sao chép nguyên văn dài.

| Nguồn | Quan sát cụ thể | Pattern áp dụng cho report |
|---|---|---|
| `BCT2024_BaoCaoLogisticsVN-FTZ.pdf`, tr. 24 | Báo cáo mở tiểu mục kinh tế Việt Nam bằng số liệu GDP 9 tháng và cơ cấu đóng góp của các khu vực, rồi mới diễn giải điểm sáng công nghiệp chế biến, chế tạo. | Mở bằng số liệu neo -> giải thích ý nghĩa -> chỉ chọn số liên quan trực tiếp tới logistics. |
| `BCT2024_BaoCaoLogisticsVN-FTZ.pdf`, tr. 26 | Phần xuất nhập khẩu nêu kim ngạch 578,47 tỷ USD, tốc độ tăng và cán cân xuất siêu trong cùng một cụm thông tin. | Khi cần tạo sức nặng cho Mở đầu, dùng một cụm số duy nhất rồi chuyển sang áp lực tổ chức vận tải. |
| `BCT2024_BaoCaoLogisticsVN-FTZ.pdf`, tr. 65 | Phần dịch vụ vận tải liên kết nguyên nhân với hệ quả: xuất nhập khẩu và sản xuất tăng kéo theo sản lượng vận tải hàng hóa tăng. | Viết quan hệ nhân quả ngắn: biến động thị trường -> áp lực vận tải -> nhu cầu tối ưu tuyến. |
| `BCT2024_BaoCaoLogisticsVN-FTZ.pdf`, tr. 80 | Phần doanh nghiệp logistics đưa số doanh nghiệp, vốn, lao động, sau đó mới nhận xét về xu thế chuyên nghiệp hóa và chuyển đổi số. | Không liệt kê hết trong Mở đầu; dùng số doanh nghiệp nếu luận điểm là thị trường phân tán/cần điều phối. |

## 3. Gap Statement

Cấu trúc 3 bước:

1. Thừa nhận: `Có nhiều nghiên cứu về X, như [cite]...`
2. Chỉ giới hạn: `Tuy nhiên, trong phạm vi khảo lược chưa tìm thấy...`
3. Khẳng định gap: `Vì vậy, nghiên cứu này được thực hiện nhằm...`

Điều chỉnh cho MDPDTWDD:

- Không viết "khoảng trống nghiên cứu" như heading nếu outline yêu cầu tránh; dùng trong thân đoạn với mức độ vừa phải.
- Không viết quá trực diện rằng đề tài "phát triển từ Wang". Dùng Wang et al. làm nguồn định nghĩa/mốc đối chứng; đóng góp của repo phải neo bằng artifact, pipeline, thí nghiệm.
- Nếu gap chưa đủ tài liệu để khẳng định, dùng `trong phạm vi khảo lược` thay vì khẳng định tuyệt đối.

Mẫu:

```markdown
Có nhiều nghiên cứu về định tuyến xe có cửa sổ thời gian và nhu cầu động, trong đó các hướng gần với MDPDTWDD tập trung vào tái tối ưu tuyến, chiến lược chèn yêu cầu phát sinh và phối hợp nhiều depot [2], [3]. Tuy nhiên, trong phạm vi khảo lược và artifact hiện có, chưa tìm thấy một pipeline tiếng Việt có khả năng tái lập mốc đối chứng, ghi vết từng biến thể và tách rõ tác động của các thành phần xử lý nhu cầu động. Vì vậy, nghiên cứu này được thực hiện nhằm xây dựng và kiểm chứng một quy trình thực nghiệm có thể truy vết cho lớp bài toán MDPDTWDD.
```

## 4. Dẫn vào đề tài hoặc giải pháp

Dùng các cụm đã xuất hiện trong văn phong paper/báo cáo VN:

- `Xuất phát từ thực tiễn đó,`
- `Nhằm lấp đầy khoảng trống đó,`
- `Nhằm giải quyết vấn đề trên,`
- `Trên cơ sở đó,`
- `Từ đó,`

Không dùng lối quảng cáo như `đề tài mang lại giải pháp toàn diện`, `cách tiếp cận vượt trội`, `đột phá`.

Mẫu:

```markdown
Xuất phát từ thực tiễn đó, đề tài lựa chọn MDPDTWDD như một lớp bài toán đại diện cho tình huống nhiều kho, nhiều loại khách hàng và nhu cầu phát sinh trong quá trình vận hành.
```

## 5. Định nghĩa khái niệm và thuật toán

Pattern 3 câu:

1. Vị thế chung của X.
2. Định nghĩa kỹ thuật X + viết tắt lần đầu.
3. Nguyên lý hoạt động hoặc liên hệ ứng dụng.

Mẫu:

```markdown
Giải thuật di truyền là một nhóm phương pháp tìm kiếm thường được dùng cho các bài toán tối ưu tổ hợp có không gian nghiệm lớn. Trong nghiên cứu này, Adaptive Non-dominated Sorting Genetic Algorithm II (ANSGA-II, tạm dịch: giải thuật di truyền sắp xếp không trội thích nghi thế hệ II) được hiểu là thành phần tiến hóa đa mục tiêu dùng để tìm các nghiệm cân bằng giữa tổng chi phí vận hành và số lượng phương tiện. Thành phần này không được trình bày như đóng góp thuật toán mới nếu repo chỉ tái lập hoặc điều chỉnh pipeline.
```

Nếu chưa có bản dịch tiếng Việt học thuật đã xác minh, giữ nguyên thuật ngữ gốc và thêm `(tạm dịch: ...)` ở lần đầu. Không dịch tên riêng/framework nếu việc dịch làm mất nhận diện thuật toán.

### Ví dụ học từ paper VRP tiếng Việt

| Nguồn | Quan sát cụ thể | Pattern áp dụng |
|---|---|---|
| `CaoTran2022_GA-VRP.pdf`, tr. 36 | Tóm tắt đặt mục tiêu nghiên cứu trước, sau đó định nghĩa VRP và nêu tính NP-đầy đủ. | Khi định nghĩa bài toán, viết theo thứ tự: mục tiêu nghiên cứu -> tên bài toán và viết tắt -> đặc tính độ khó. |
| `CaoTran2022_GA-VRP.pdf`, tr. 37 | Paper chia nhóm phương pháp: chính xác, gần đúng, heuristic, tìm kiếm cục bộ, metaheuristic; dùng `Tuy nhiên` để chỉ giới hạn phương pháp chính xác. | Khi viết tổng quan, dùng cấu trúc phân nhóm phương pháp trước khi chọn hướng thuật toán; không nhảy thẳng vào tên thuật toán. |
| `CaoTran2022_GA-VRP.pdf`, tr. 37 | Đoạn giải thuật di truyền đi từ vị thế chung tới nguyên lý quần thể, chọn lọc, lai ghép, đột biến. | Định nghĩa thuật toán theo chuỗi: vị thế -> cơ chế biểu diễn nghiệm -> các toán tử chính. |
| `CaoTran2023_TabuSearch-VRP.pdf`, tr. 38-39 | Tabu Search được giải thích bằng lời giải ban đầu, miền lân cận, bước chuyển và cơ chế cấm quay lại. | Khi định nghĩa thuật toán, đưa các thành phần vận hành theo thứ tự thời gian, tránh chỉ liệt kê khái niệm. |

## 6. Mô tả phương pháp nghiên cứu

Liên kết các bước bằng văn xuôi, không liệt kê cơ học:

- `Tiếp đến là`
- `Sau khi [X], nghiên cứu thực hiện...`
- `Cụ thể,`
- `Trong đó,`
- `Theo đó,`
- `Từ đó,`

Mẫu:

```markdown
Sau khi chuẩn hóa dữ liệu đầu vào thành cấu trúc instance thống nhất, nghiên cứu thực hiện phân cụm khách hàng theo thông tin không gian và thời gian. Tiếp đến là bước tối ưu đa mục tiêu, trong đó mỗi nghiệm được đánh giá theo tổng chi phí vận hành và số lượng phương tiện. Từ đó, các yêu cầu động được chèn vào tuyến hiện có và ghi vết bằng file `.sol` để phục vụ kiểm chứng.
```

### Ví dụ học từ paper/case study thật

| Nguồn | Quan sát cụ thể | Pattern áp dụng |
|---|---|---|
| `CaoTran2022_GA-VRP.pdf`, tr. 39-40 | Paper mô tả thuật toán bằng chuỗi bước: phân cụm, khởi tạo quần thể, đánh giá thích nghi, chọn lọc/lai ghép/đột biến, tạo thế hệ mới. | Dùng câu chuyển `Sau khi...`, `Tiếp đến là...`, `Từ đó...` để viết thành văn xuôi thay vì bullet cứng. |
| `CaoTran2023_TabuSearch-VRP.pdf`, tr. 40 | Paper dẫn vào hình bằng câu "Các tham số chính..." rồi giải thích không gian tìm kiếm và cấu trúc lân cận. | Trước bảng/hình thuật toán phải có câu dẫn nêu vai trò hình/bảng, không thả hình độc lập. |
| `NgoEtAl2024_MSW-GIS-ABM-HungYen.pdf`, tr. 3-4 | Case study Hưng Yên mô tả địa bàn, dữ liệu thứ cấp, khảo sát thực địa, phỏng vấn hộ và đo tải rác trước khi mô hình hóa. | Với phương pháp thực nghiệm, viết theo logic: địa bàn/dữ liệu -> thu thập -> tiền xử lý -> mô hình/thuật toán -> kịch bản đánh giá. |

## 7. Trình bày kết quả nghiên cứu

Thứ tự bắt buộc:

`Dẫn vào bảng/hình -> số liệu cụ thể -> so sánh/đánh giá -> lập luận suy diễn -> nhận xét giới hạn`

Không bắt đầu kết quả bằng `Nhìn chung`. Bắt đầu bằng thiết lập hoặc số liệu:

```markdown
Với case Chongqing, thiết lập 3 seed và max-gen=15 cho thấy biến thể G-full đạt TOC trung bình ... từ các file `.sol`. So với B0, mức chênh ... cho thấy tác động của sửa tuyến là có nhưng chưa đủ để kết luận ưu thế tổng quát. Kết quả này cần được đọc trong giới hạn của một case và budget thế hệ thấp.
```

### Ví dụ học từ phần kết quả thật

| Nguồn | Quan sát cụ thể | Pattern áp dụng |
|---|---|---|
| `CaoTran2022_GA-VRP.pdf`, tr. 40 | Trước bảng so sánh, paper nêu cấu hình thuật toán, sau đó dẫn vào hình và bảng kết quả. | Khi trình bày kết quả MDPDTWDD: nêu thiết lập run -> dẫn bảng/hình -> đọc số liệu chính -> nhận xét. |
| `CaoTran2023_TabuSearch-VRP.pdf`, tr. 42 | Paper nêu tham số, kết quả với `Imax = 10`, nguồn benchmark rồi mới kết luận thuật toán tốt hơn ở nhóm dữ liệu nhất định. | Không nói "tốt hơn" chung chung; gắn kết luận với nhóm dữ liệu, thiết lập và nguồn so sánh. |
| `NgoEtAl2024_MSW-GIS-ABM-HungYen.pdf`, tr. 17 | Kết luận nêu các kịch bản, tỷ lệ giảm chất thải còn lại, số điểm trung chuyển bổ sung và giới hạn còn hộ ngoài vùng thu gom. | Kết quả tốt phải đi kèm điều kiện và hạn chế; không chỉ nêu số thắng. |

## 8. Kết luận có hạn chế

Kết luận bắt đầu bằng dữ liệu cụ thể, artifact, hoặc claim đã chứng minh; không mở bằng `Nhìn chung`, `Tóm lại` nếu chưa có số neo.

Mẫu:

```markdown
Trên 3 seed của case Chongqing, G-full giảm TOC trung bình ... so với B0 nhưng chưa tạo chênh lệch đủ lớn để thay thế benchmark đa instance. Kết quả này xác nhận pipeline có khả năng ghi vết và so sánh biến thể, đồng thời chỉ ra nhu cầu mở rộng thí nghiệm sang Cordeau dưới cùng cost semantics.
```

## 9. Từ nối chuyển đoạn

Chỉ dùng các nhóm sau, trừ khi văn cảnh bắt buộc:

| Nhóm | Từ nối |
|---|---|
| Đối lập | `Tuy nhiên,`, `Tuy vậy,`, `Mặc dù vậy,`, `Trong khi đó,`, `Song,` |
| Bổ sung | `Bên cạnh đó,`, `Ngoài ra,`, `Hơn nữa,`, `Đặc biệt là,`, `Cùng với đó,` |
| Hệ quả | `Do đó,`, `Vì vậy,`, `Từ đó,`, `Trên cơ sở đó,`, `Điều này cho thấy`, `Điều này phản ánh` |
| Dẫn vào đề tài | `Xuất phát từ thực tiễn đó,`, `Nhằm lấp đầy khoảng trống đó,`, `Nhằm giải quyết vấn đề trên,` |
| Kết thúc | `Kết quả cho thấy`, `Có thể thấy,`, `Như vậy,`, `Tóm lại,` |
| Liên kết bước | `Tiếp đến là`, `Sau khi [X], nghiên cứu thực hiện...`, `Cụ thể,`, `Trong đó,`, `Theo đó,` |

Hạn chế `Có thể thấy,` nếu câu sau chỉ là nhận xét chung. Dùng khi sau đó có kết luận được neo bằng số liệu.

## 10. Tránh văn máy, giữ nhịp tự nhiên

Mục tiêu bắt buộc khi sửa là giảm dấu hiệu văn máy: câu mở chung, nhịp câu đều, kết luận không có chứng cứ, liệt kê máy móc, cụm từ sáo rỗng. Cách sửa phải dựa trên bằng chứng và pattern học từ paper thật, không chỉ thay từ đồng nghĩa.

| Lỗi | Dấu hiệu | Cách sửa |
|---|---|---|
| Mở đầu bằng `Trong bối cảnh...` | Câu mở chung | Thay bằng số liệu/sự kiện/tên nghiên cứu |
| `Có thể thấy rằng...` | Hedge phrase | Viết thẳng kết luận hoặc bỏ |
| `Đây là một vấn đề quan trọng` | Nhận định chung | Thay bằng hệ quả cụ thể |
| Liệt kê `Thứ nhất... Thứ hai...` | Cứng nhắc | Viết văn xuôi, nhóm theo chức năng |
| 3 câu liên tiếp cùng cấu trúc | Nhịp đều | Gộp/tách câu, đổi vị trí mệnh đề |
| Dấu `--` hoặc em dash để giải thích | Văn dịch | Viết trong ngoặc: `pipeline (chuỗi xử lý)` |
| Liệt kê tên công cụ dài | Inventory listing | Nhóm theo chức năng |
| Đoạn nào cũng 4-5 câu | Uniform paragraph | Xen đoạn 2-3 câu với đoạn 5-6 câu |
| Dùng `:` trước giải thích dài | Dạng list trá hình | Chuyển thành văn xuôi |
| `Về A... Về B...` | Song song máy móc | Đổi cấu trúc câu |

Từ cần hạn chế nếu không có dữ liệu đi kèm: `quan trọng`, `toàn diện`, `đáng kể`, `hiệu quả`, `vượt trội`, `tối ưu`.

## 11. Checklist trước khi nộp

```text
[ ] Câu đầu tiên có số liệu, tên nghiên cứu, sự kiện, artifact hoặc đối tượng cụ thể?
[ ] Mỗi số liệu đều có IEEE citation [n] hoặc ghi "(thực đo ngày yyyy-mm-dd)"?
[ ] Không có 3 câu liên tiếp bắt đầu giống nhau?
[ ] Không có câu mở vô nghĩa như "Trong phần này chúng tôi sẽ..."?
[ ] Độ dài câu có biến thiên: có câu ngắn dưới 15 từ xen câu dài hơn 35 từ?
[ ] Ít nhất một pattern văn phong được neo vào paper VN cụ thể trong ghi chú/Tham chiếu sử dụng?
[ ] Thuật ngữ chưa có bản dịch chuẩn có ghi "(tạm dịch: ...)" ở lần đầu?
[ ] Không viết "phát triển từ Wang" như thể toàn bộ đóng góp lệ thuộc mainPaper?
[ ] Đóng góp repo được neo bằng artifact, `.sol`, CSV, logs hoặc docs?
[ ] Đọc to nghe tự nhiên, không giống bản dịch máy?
```

## 12. ARS Revision Prompt Cho MDPDTWDD

Khi dùng ARS `revision` mode, dùng prompt mẫu:

```text
Revise this Vietnamese academic draft section for the MDPDTWDD report:
1. Check the first sentence: it must be a concrete fact, source, number, artifact, or named study, not a generic statement.
2. Convert citations to IEEE numeric style and include DOI links when available; web sources need Accessed date.
3. Remove generic phrases such as "Có thể thấy rằng", "đây là một vấn đề quan trọng", "đáng kể" without evidence.
4. Follow Vietnamese academic paper style: evidence -> interpretation -> limitation.
5. Use Vietnamese sources for terminology and sentence rhythm; use English papers for scientific argument structure.
6. Avoid saying the work is simply "developed from Wang"; cite Wang et al. for model/baseline claims and use repo artifacts for this project's contributions.
7. Vary sentence length and avoid inventory-style listing.
8. Identify at least one concrete Vietnamese-paper pattern used in the revision, with source file/page.
[DRAFT TEXT]
```
