# Domain Glossary

## Problem Terms

| Term | Vietnamese use |
|---|---|
| MDPDTWDD | Bài toán định tuyến đa kho có lấy-giao hàng, cửa sổ thời gian và nhu cầu động |
| Multi-Depot | Đa kho; có nhiều depot giao hoặc nhận |
| Pickup-Delivery | Lấy-giao hàng; cần phân biệt điểm giao và điểm nhận |
| Time Window | Cửa sổ thời gian phục vụ |
| Dynamic Demand | Nhu cầu phát sinh sau pha tĩnh |

## Metrics

| Term | Meaning |
|---|---|
| TOC | Total Operating Cost; chỉ số chính, lấy kết quả cuối từ `.sol` |
| NV | Number of Vehicles; lấy kết quả cuối từ `.sol` |
| Runtime | Thời gian chạy; lấy từ CSV thống kê |
| max-gen | Số thế hệ của ANSGA-II |
| seed | Hạt ngẫu nhiên để tái lập |
| Pareto front | Tập nghiệm không bị trội trong không gian TOC/NV |

## Algorithm Terms

| Term | Usage |
|---|---|
| 3DAPANSGA-II | Tên thuật toán, giữ nguyên tiếng Anh |
| 3D Affinity Propagation | Phân cụm theo không gian và thời gian |
| ANSGA-II | Bộ tiến hóa đa mục tiêu |
| Geohash bucketing | Chia khách theo ô không gian trước khi chạy AP |
| Regret-2 ordering | Thứ tự chèn theo chênh lệch hai lựa chọn gần nhất |
| Urgency tier | Phân nhóm URGENT / SEMI / NON theo slack thời gian |

## Translation Policy

### Group A — Có bản dịch tiếng Việt dùng được

| English | Vietnamese use |
|---|---|
| Vehicle routing problem (VRP) | Bài toán định tuyến xe / bài toán định tuyến phương tiện |
| Time windows | Cửa sổ thời gian |
| Pickup and delivery | Lấy và giao hàng / lấy-giao hàng |
| Dynamic demand | Nhu cầu động / nhu cầu phát sinh |
| Multi-depot | Đa kho |
| Total operating cost | Tổng chi phí vận hành |
| Number of vehicles | Số lượng phương tiện |
| Genetic algorithm | Giải thuật di truyền |
| Tabu Search | Thuật toán tìm kiếm Tabu |

### Group B — Chưa có bản dịch VN học thuật chắc chắn

Giữ nguyên thuật ngữ gốc và định nghĩa một lần; nếu cần, thêm `(tạm dịch: ...)`.

| Term | First-use pattern |
|---|---|
| Affinity Propagation | Affinity Propagation (tạm dịch: lan truyền ái lực), một phương pháp phân cụm dựa trên độ tương đồng giữa các điểm dữ liệu |
| ANSGA-II | Adaptive Non-dominated Sorting Genetic Algorithm II (ANSGA-II, tạm dịch: giải thuật di truyền sắp xếp không trội thích nghi thế hệ II) |
| Geohash bucketing | Geohash bucketing (tạm dịch: chia ô không gian bằng Geohash) |
| Regret-2 | Regret-2 (tạm dịch: chèn theo độ tiếc nuối bậc hai) |
| Elite archive | Elite archive (tạm dịch: kho nghiệm ưu tú) |
| Deep route repair | Deep route repair (tạm dịch: sửa tuyến nhiều lượt) |

Tên riêng/framework không dịch nếu dịch làm mất nhận diện thuật toán.

## Wording Rules

- Prefer "thành phần pipeline", "biến thể pipeline", "mốc tham chiếu".
- Avoid unsupported claims such as "vượt trội", "tốt hơn đáng kể", or "tối ưu hơn" without statistical evidence.
- Keep algorithm names in English and explain their role in Vietnamese.
