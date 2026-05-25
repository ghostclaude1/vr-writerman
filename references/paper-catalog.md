# Paper Catalog (sau rename)

Dùng tên file chuẩn làm key nội bộ `[CITE: AuthorYear_Topic]` để truy vết nguồn. Khi viết báo cáo, **không xuất raw key**; dùng trích dẫn IEEE `[n]` trong đoạn và entry IEEE đầy đủ ở mục **Tài liệu tham khảo**. Chi tiết mapping: `../file-mapping.md`.

## Quy tắc xuất tham chiếu

| Loại | Dùng ở đâu | Ví dụ |
|---|---|---|
| Key nội bộ | `Tham chiếu sử dụng`, ghi chú truy vết | `[CITE: WangEtAl2025_MDPDTWDD-mainPaper]` |
| Trích dẫn trong bài | Đoạn báo cáo đã duyệt | `[2]` |
| Entry tài liệu tham khảo | Ngay dưới phần nháp trong chat và cuối báo cáo | `[2] Y. Wang, ... "..." *Journal*, vol. ..., 2025.` |

## Entry đã khóa cho nguồn chính

| Key nội bộ | Trích dẫn trong bài | Entry tài liệu tham khảo |
|---|---|---|
| `[CITE: BCT2024_LogisticsVN]` | `[1]` | [1] Bộ Công Thương, *Báo cáo Logistics Việt Nam 2024: Khu thương mại tự do*. Hà Nội, Việt Nam: Nhà xuất bản Công Thương, 2024. |
| `[CITE: WangEtAl2025_MDPDTWDD-mainPaper]` | `[2]` | [2] Y. Wang, M. Gou, S. Luo, J. Fan, and H. Wang, "The multi-depot pickup and delivery vehicle routing problem with time windows and dynamic demands," *Engineering Applications of Artificial Intelligence*, vol. 139, Art. no. 109700, 2025, doi: https://doi.org/10.1016/j.engappai.2024.109700. |

## `paper/references/` — được phép trích dẫn

| File | Gợi ý citation key |
|------|-------------------|
| `AhmadiOsman2005_GRAMPS-CCP.pdf` | `[CITE: AhmadiOsman2005_GRAMPS-CCP]` |
| `BCT2024_BaoCaoLogisticsVN-FTZ.pdf` | `[CITE: BCT2024_LogisticsVN]` |
| `CaoTran2022_GA-VRP.pdf` | `[CITE: CaoTran2022_GA-VRP]` |
| `CaoTran2023_TabuSearch-VRP.pdf` | `[CITE: CaoTran2023_TabuSearch-VRP]` |
| `DuEtAl2023_DPDP-LIFO-Hierarchical.pdf` | `[CITE: DuEtAl2023_DPDP-LIFO]` |
| `JeongMoon2024_DPDP-AR-Reassignment-PTM.pdf` | `[CITE: JeongMoon2024_DPDP-AR]` |
| `KaramiEtAl2020_Periodic-DynPDPTW.pdf` | `[CITE: KaramiEtAl2020_Periodic-DynPDPTW]` |
| `KocaturkEtAl2021_MDHFVRPB-VNS-GRAMPS.pdf` | `[CITE: KocaturkEtAl2021_MDHFVRPB]` |
| `LiEtAl2018_MDVRP-SharedDepot-Fuel.pdf` | `[CITE: LiEtAl2018_MDVRP-SharedDepot]` |
| `NgoEtAl2024_MSW-GIS-ABM-HungYen.pdf` | `[CITE: NgoEtAl2024_MSW-GIS]` |
| `NguyenEtAl2016_VRPTW-ICDTienSon.pdf` | `[CITE: NguyenEtAl2016_VRPTW-VN]` |
| `PraxedesEtAl2024_BCP-VRPSPD-Unified.pdf` | `[CITE: PraxedesEtAl2024_BCP-VRPSPD]` |
| `SilvaEtAl2020_MACS-RVND-DVRPTW.pdf` | `[CITE: SilvaEtAl2020_DVRPTW]` |
| `SoeffkerEtAl2022_SDVRP-PrescriptiveAnalytics-Review.pdf` | `[CITE: SoeffkerEtAl2022_SDVRP-Review]` |
| `WangEtAl2018_CMCVRPSDP-HNSGA2-CGA.pdf` | `[CITE: WangEtAl2018_CMCVRPSDP]` |
| `WangEtAl2021_CMDPDLN-SplitLoads-HGA-TS.pdf` | `[CITE: WangEtAl2021_CMDPDLN]` |
| `Xu2024_EVRP-Review.pdf` | `[CITE: Xu2024_EVRP-Review]` |
| `ZhangEtAl2022_HMCVRP-Benders-BBC.pdf` | `[CITE: ZhangEtAl2022_HMCVRP]` |
| `ZhuSheu2018_FSC-SPDPSD-ALNS.pdf` | `[CITE: ZhuSheu2018_SPDPSD]` |
| `VN2229_TTG-Decree.docx` | `[CITE: VN2229_TTG-Decree]` |

## Vai trò đặc biệt

| Citation key | Vai trò đúng | Không dùng cho |
|---|---|---|
| `[CITE: BCT2024_LogisticsVN]` | Bối cảnh logistics Việt Nam, hạ tầng, dịch vụ, địa phương, FTZ, cách dẫn nhập báo cáo khoa học Việt Nam | Thuật toán, mô hình toán, benchmark, kết quả repo |
| `[CITE: VN2229_TTG-Decree]` | Căn cứ chính sách/quyết định nếu báo cáo cần nhắc định hướng quản lý | Kết quả khoa học hoặc hiệu năng thuật toán |

## `paper/mainPaper/`

| File | Gợi ý citation key |
|------|-------------------|
| `ENG The multi-depot pickup and delivery vehicle routing problem with time windows and dynamic demands.md` | `[CITE: WangEtAl2025_MDPDTWDD-mainPaper]` |
| `paper_math_blocks.md` | `[SOURCE: paper/mainPaper/paper_math_blocks.md]` |

## `paper/non-update/` — không cập nhật phương án trong report

| File | Lý do |
|------|-------|
| `Alimoradi2025_BiObj-MDLRPTW-EV.pdf` | 2025, sau mainPaper |
| `WangEtAl2025_MDEVRPTW-DD-IMODE.pdf` | 2025 MDEVRPTW-DD |
| `WangEtAl2025_CMDSDN-TDLC-ANSGAIII.pdf` | 2025 TRE |
| `WangEtAl2025_MDCDVRPMC-EALNS.pdf` | 2025 EALNS |
| `WangEtAl2026_CMDPND-TRCASS-GMC-IMOALNS.pdf` | 2026 |
| `HouEtAl2025_ColdChain-MDSO-FALNS.pdf` | 2025 cold-chain |
| `researching-result/*.md` | Survey nội bộ 2026-05 |
