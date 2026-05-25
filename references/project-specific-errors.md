# Project-Specific Report Errors

File này ghi các lỗi đặc thù đã xảy ra khi viết report MDPDTWDD. Đọc file này trước khi viết lại phần đã bị góp ý.

## 1. Citation và reference

| Lỗi | Vì sao sai | Cách sửa |
|---|---|---|
| Đưa raw key `[CITE: ...]` vào đoạn báo cáo | Key chỉ để truy vết nội bộ | Dùng IEEE `[n]` trong đoạn; block tham chiếu mới ghi key nội bộ |
| Reference IEEE thiếu DOI/link khi có DOI | Không đủ chuẩn paper | Thêm `doi: https://doi.org/...`; nếu chưa xác minh, ghi điểm cần human duyệt |
| Web source không ghi ngày truy cập | Không đạt chuẩn IEEE cho web | Thêm `Accessed: yyyy-mm-dd` |
| Bịa DOI, venue, trang | Vi phạm integrity | Tra nguồn chính thống hoặc yêu cầu user cung cấp/tải paper |

## 2. Dùng Báo cáo Logistics Việt Nam

| Lỗi | Vì sao sai | Cách sửa |
|---|---|---|
| Viết toàn lời văn, không có số liệu | Thiếu chất báo cáo khoa học | Dùng 1-2 số liệu neo thật đắt |
| Liệt kê quá nhiều số liệu liên tiếp | Biến mở đầu thành bảng thống kê | Mỗi đoạn 1 số chính, sau đó diễn giải ý nghĩa |
| Dùng báo cáo logistics để chứng minh thuật toán | Sai vai trò nguồn | Chỉ dùng cho bối cảnh/thực tiễn/chính sách |
| Nhồi tình hình kinh tế vĩ mô vào Mở đầu | Lệch khỏi đề tài | Chọn số gắn trực tiếp với vận tải, kho bãi, lưu chuyển hàng hóa |

## 3. Quan hệ với mainPaper Wang et al.

| Lỗi | Vì sao sai | Cách sửa |
|---|---|---|
| Viết "đề tài phát triển từ Wang" quá trực diện | Làm mờ đóng góp riêng của report | Viết "đề tài lựa chọn lớp bài toán MDPDTWDD", "sử dụng mốc đối chứng đã công bố" |
| Dùng mainPaper cho mọi claim | Lẫn nguồn nền tảng với nguồn artifact | Paper cho mô hình/mốc; repo artifacts cho kết quả và đóng góp |
| Viết như thay Wang phát biểu mà không nhận là Wang | Không minh bạch học thuật | Cite `[n]` gần câu định nghĩa/mô hình/algorithm từ paper |

## 4. Văn phong Mở đầu

| Lỗi | Vì sao sai | Cách sửa |
|---|---|---|
| Mở đầu bằng `Trong bối cảnh...` | Câu chung, nghe máy | Mở bằng số liệu/sự kiện/tên nghiên cứu |
| `Logistics rất quan trọng` | Triết lý chung | Thay bằng số liệu và hệ quả cụ thể |
| Giải thích kỹ thuật quá sớm | Mở đầu chưa phải chương chuyên môn | Chỉ nêu lớp bài toán và lý do chọn, để chi tiết sang Chương 2/3 |
| Mọi đoạn cùng nhịp 4 câu | Văn đều, thiếu tự nhiên | Xen câu ngắn, câu dài; gộp/tách theo ý |
| Tự viết mẫu chung mà không học từ paper | Skill không tận dụng nguồn VN đã cung cấp | Khi thêm quy tắc văn phong, ghi pattern cụ thể từ `BCT2024`, `CaoTran2022/2023`, `NgoEtAl2024` hoặc paper liên quan |
| Biến "tránh văn máy" thành thay từ đồng nghĩa | Không sửa được cấu trúc | Sửa ở cấp câu/đoạn trước: câu mở, nhịp câu, vị trí số liệu, dẫn chứng, giới hạn |

## 5. Kết quả và artifact

| Lỗi | Vì sao sai | Cách sửa |
|---|---|---|
| Lấy TOC/NV cuối từ stats CSV | Có thể lệch với solution sau insertion | Lấy final TOC/NV từ `.sol` |
| Claim Cordeau hoàn tất khi thiếu artifact | Sai trạng thái nghiên cứu | Chỉ claim khi có đủ runs/tables/logs |
| Claim max-gen=150 nếu chưa có run | Sai bằng chứng | Ghi là kế hoạch hoặc pending |
| Viết `hiệu quả hơn`, `vượt trội` không kiểm định | Quá mức | Dùng `cho tín hiệu`, `giảm trong thiết lập...`, kèm test nếu có |

## 6. Cấu trúc chương và dẫn chuyển

Mỗi chương phải có một đoạn mở chương 3-5 câu trước heading cấp 2 đầu tiên. Đoạn này nêu bối cảnh, sợi chỉ logic từ chương trước và phạm vi chương; không tóm tắt mục lục.

| Kiểu | Khi dùng | Cấu trúc |
|---|---|---|
| Số liệu -> vấn đề | Chương 1 | Câu số liệu cụ thể -> câu chỉ vấn đề/gap -> câu liên hệ chương |
| Kế thừa -> mở rộng | Chương 2, 3 | Câu nhắc kết quả/chốt vấn đề chương trước -> `Để [X], cần...` -> câu phạm vi chương |
| Kết quả -> đánh giá | Chương 4 | Câu mô tả hệ thống/thí nghiệm -> câu trình bày kết quả -> câu số liệu chính |

Câu kết mục không viết kiểu:

> Như vậy, phần này đã trình bày ba phương pháp chính. Phần tiếp theo sẽ...

Viết kiểu neo điểm hoặc mở tự nhiên:

> Song, để cơ chế chèn yêu cầu động phát huy tác dụng trong điều kiện cửa sổ thời gian hẹp, cần kiểm tra thêm chất lượng tuyến sau bước repair; nội dung này được đặt trong thiết kế pipeline ở chương sau.

## 7. Cách cập nhật file này

Khi user góp ý một lỗi mới:

1. Ghi lỗi thành một dòng trong bảng phù hợp.
2. Ghi vì sao sai theo ngữ cảnh MDPDTWDD.
3. Ghi cách sửa dưới dạng thao tác cụ thể.
4. Nếu lỗi lặp lại nhiều lần, bổ sung rule ngắn vào `SKILL.md`.
