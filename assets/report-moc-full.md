# MỤC LỤC ĐỀ XUẤT - BÁO CÁO NGHIÊN CỨU KHOA HỌC MDPDTWDD

> Bản MOC này dùng để duyệt cấu trúc báo cáo. Khi viết nội dung, chỉ viết từng tiểu mục lá, có nguồn và citation theo skill `mdpdtwdd-report-writing`.
> Nguyên tắc: không lặp lại cùng một cụm lý thuyết ở nhiều chương; cải tiến của đề tài được phân bổ theo logic lý thuyết -> thiết kế -> thực nghiệm -> thảo luận.

## PHẦN ĐẦU

- Trang bìa
- Lời cảm ơn
- Mục lục
- Danh mục hình ảnh
- Danh mục bảng biểu
- Danh mục từ viết tắt và ký hiệu
- Tóm tắt
- Abstract

## MỞ ĐẦU

0.1. Tính cấp thiết của đề tài

0.2. Mục tiêu nghiên cứu

0.3. Đối tượng và phạm vi nghiên cứu

0.4. Nội dung nghiên cứu

0.5. Phương pháp nghiên cứu

0.6. Kết quả nghiên cứu và đóng góp của đề tài

## CHƯƠNG 1. TỔNG QUAN VỀ ĐỀ TÀI

1.1. Bối cảnh bài toán định tuyến trong logistics

1.2. Tình hình nghiên cứu trong nước và quốc tế

1.2.1. Tình hình nghiên cứu quốc tế về MDPDTWDD và các biến thể gần

1.2.2. Tình hình nghiên cứu trong nước về định tuyến phương tiện và logistics

1.3. Vấn đề đặt ra từ tổng quan nghiên cứu

1.4. Định hướng nghiên cứu của đề tài

1.5. Tổng kết chương

## CHƯƠNG 2. CƠ SỞ LÝ THUYẾT VÀ MÔ HÌNH BÀI TOÁN PHÁT TRIỂN TỪ NGHIÊN CỨU GỐC

2.1. Bài toán MDPDTWDD trong nghiên cứu gốc

2.1.1. Bối cảnh mạng logistics đa kho

2.1.2. Pickup-delivery, cửa sổ thời gian và nhu cầu động

2.1.3. Phương tiện, depot và cơ chế chia sẻ tài nguyên

2.2. Ký hiệu, giả thiết và phạm vi kế thừa từ mainPaper

2.2.1. Tập hợp, tham số và biến quyết định

2.2.2. Giả thiết vận hành và dữ liệu đầu vào

2.2.3. Phạm vi đề tài kế thừa và không kế thừa

2.3. Mô hình toán học của bài toán

2.3.1. Hàm mục tiêu trong nghiên cứu gốc

2.3.2. Các ràng buộc tuyến, tải trọng và thời gian

2.3.3. Ràng buộc phục vụ yêu cầu động

2.4. Thuật toán 3DAPANSGA-II làm baseline

2.4.1. Phân cụm 3D Affinity Propagation

2.4.2. ANSGA-II và cơ chế elite iteration

2.4.3. Chiến lược chèn yêu cầu động trong mainPaper

2.5. Chỉ số đánh giá và cách đối chiếu với mainPaper

2.5.1. TOC, NV và các thành phần chi phí

2.5.2. Runtime, hội tụ và nghiệm Pareto

2.5.3. Mốc Table 22 và quy tắc đọc artifact tái lập

2.6. Định hướng phát triển từ mainPaper trong đề tài

2.6.1. Từ phân cụm 3D AP đến phân cụm có kiểm soát không gian

2.6.2. Từ chèn tuần tự đến chèn có xét regret và urgency

2.6.3. Từ nghiệm sau chèn đến sửa tuyến và tối ưu cục bộ

2.6.4. Chuẩn hóa ngữ nghĩa chi phí và thời điểm xuất phát

2.7. Tổng kết chương

## CHƯƠNG 3. PHƯƠNG PHÁP NGHIÊN CỨU VÀ PIPELINE ĐỀ XUẤT

3.1. Thiết kế nghiên cứu tổng thể

3.1.1. Luồng nghiên cứu từ tái lập đến đánh giá biến thể

3.1.2. Ma trận biến thể và câu hỏi nghiên cứu

3.2. Dữ liệu nghiên cứu và chuẩn bị thực nghiệm

3.2.1. Case study Chongqing

3.2.2. Bộ benchmark Cordeau

3.2.3. Tiền xử lý và kiểm tra instance

3.3. Quy trình tái lập thuật toán gốc

3.3.1. Cấu hình baseline

3.3.2. Sinh nghiệm và lưu artifact

3.3.3. Đối chiếu với mốc trong paper gốc

3.4. Pipeline triển khai trong project

3.4.1. Phân cụm khách hàng

3.4.2. Tối ưu đa mục tiêu

3.4.3. Chèn yêu cầu động

3.4.4. Tính chi phí và xuất nghiệm cuối

3.5. Thiết kế các biến thể cải tiến GRANITE

3.5.1. G1 - Geohash bucketing cho phân cụm

3.5.2. G2 - Regret-2 và urgency tier cho chèn yêu cầu động

3.5.3. G3 - Route repair và neighborhood search

3.5.4. Các biến thể chưa triển khai hoặc không đưa vào kết luận chính

3.6. Kiểm soát chất lượng thực nghiệm và nguồn số liệu

3.6.1. Nguyên tắc so sánh công bằng

3.6.2. Nguyên tắc đọc artifact và báo cáo số liệu

3.6.3. Các claim bị giới hạn khi chưa có artifact

3.7. Tổng kết chương

## CHƯƠNG 4. THỰC NGHIỆM, KẾT QUẢ VÀ PHÂN TÍCH

4.1. Thiết kế thực nghiệm

4.1.1. Câu hỏi nghiên cứu và thí nghiệm tương ứng

4.1.2. Tiêu chí đánh giá và so sánh

4.2. Cấu hình thực nghiệm

4.2.1. Thiết lập tham số, seed và max-gen

4.2.2. Môi trường chạy thực nghiệm

4.3. Kết quả tái lập trên case Chongqing

4.3.1. Kết quả baseline

4.3.2. So sánh với Table 22 của paper gốc

4.3.3. Phân tích sai khác giữa kết quả tái lập và mốc tham chiếu

4.4. Kết quả đánh giá các biến thể GRANITE

4.4.1. Tác động của G1 đến phân cụm và TOC/NV

4.4.2. Tác động của G2 đến chèn yêu cầu động

4.4.3. Tác động của G3 đến chất lượng tuyến sau chèn

4.4.4. So sánh tổng hợp giữa B0, G1, G2 và G3

4.5. Kết quả benchmark Cordeau

4.5.1. Kết quả pilot

4.5.2. Kết quả full benchmark

4.5.3. Kiểm định thống kê và win-rate

4.6. Phân tích hội tụ và mặt Pareto

4.6.1. Xu hướng hội tụ theo thế hệ

4.6.2. Trade-off giữa TOC và NV

4.6.3. Độ ổn định kết quả theo seed

4.7. Phân tích ngữ nghĩa chi phí và tính khả thi của nghiệm

4.7.1. Ảnh hưởng của departure time đến penalty cost

4.7.2. Vai trò của cost audit trong đọc kết quả

4.7.3. Khả năng tái lập bằng `.sol`, CSV và bảng tổng hợp

4.8. Tổng kết chương

## CHƯƠNG 5. THẢO LUẬN, ĐÓNG GÓP VÀ KẾT LUẬN

5.1. Thảo luận kết quả theo câu hỏi nghiên cứu

5.1.1. Mức độ tái lập được thuật toán gốc

5.1.2. Hiệu quả của các biến thể GRANITE

5.1.3. Khả năng tổng quát hóa qua benchmark Cordeau

5.2. So sánh với nghiên cứu gốc và các hướng liên quan

5.2.1. Điểm tương đồng và khác biệt với 3DAPANSGA-II

5.2.2. Giá trị bổ sung của các cải tiến trong đề tài

5.3. Đóng góp của nghiên cứu

5.3.1. Đóng góp về lý thuyết và mô hình hóa

5.3.2. Đóng góp về thiết kế thuật toán và pipeline

5.3.3. Đóng góp về thực nghiệm và tái lập kết quả

5.4. Đe dọa tính hiệu lực

5.4.1. Hiệu lực nội bộ

5.4.2. Hiệu lực cấu trúc

5.4.3. Hiệu lực ngoại bộ

5.4.4. Hiệu lực kết luận

5.5. Hạn chế của nghiên cứu

5.6. Kết luận và hướng phát triển

## TÀI LIỆU THAM KHẢO

## PHỤ LỤC

Phụ lục A. Danh mục ký hiệu và thuật ngữ

Phụ lục B. Cấu hình thuật toán và lệnh chạy thực nghiệm

Phụ lục C. Bảng kết quả chi tiết theo seed và instance

Phụ lục D. Định dạng file `.sol` và CSV thống kê

Phụ lục E. Cấu trúc mã nguồn liên quan

Phụ lục F. Nhật ký thực nghiệm
