# Error analysis card

## Zone × block

| zone | block | what | count |
|---|---|---|---:|
| center | B4 | MISSING | 4 |
| center | B4 | SPURIOUS | 5 |
| center | C0 | MISSING | 1 |
| center | C0 | SPURIOUS | 3 |
| edge | B4 | ATTRIBUTE | 1 |
| edge | B4 | MISSING | 1 |
| edge | B4 | SPURIOUS | 1 |
| edge | C0 | WRONG_CLASS | 1 |
| mid | B4 | ATTRIBUTE | 1 |
| mid | B4 | BOX_GEOMETRY | 1 |
| mid | B4 | IGNORE_SCOPE | 2 |
| mid | B4 | MISSING | 3 |
| mid | B4 | SPURIOUS | 16 |
| mid | B4 | STRUCTURE | 1 |

## Top defects
- SPURIOUS: 25 (ví dụ frame adasind_019560.jpg)
- MISSING: 9 (ví dụ frame adasind_019560.jpg)
- IGNORE_SCOPE: 2 (ví dụ frame adasind_270517.jpg)

## Phân tích của bạn

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`; chạy lại lệnh sẽ cập nhật bảng và giữ nguyên mục này. Viết cho lỗi nổi bật nhất, dẫn frame/`object_ref`.

- Nguyên nhân khả dĩ (`why`) và vì sao bạn nghĩ vậy: Lỗi nổi bật nhất là `SPURIOUS` (25 ca) và `MISSING` (9 ca) tập trung nhiều nhất ở zone `mid` thuộc slice `B4-dense`. Nguyên nhân chủ yếu do `E4_model_domain` (Model YOLO bị ảnh hưởng bởi độ biến dạng ống kính fisheye ở khoảng cách tầm trung và vùng viền kính) cùng lỗi gán nhãn `E1_annotator_error` khi xử lý phương tiện xe hai bánh/xe ba bánh chen chúc nhau.
- Cách sửa và ai nhận việc (`owner`): `ai_team` xử lý các ca lỗi model bằng cách bổ sung dữ liệu huấn luyện fisheye augmentation (`action=escalate`); `annotator` thực hiện rework loại bỏ các box thừa `SPURIOUS` dựa trên checklist 9 mục (`action=rework`).
- Bằng chứng (ảnh trong `screenshots/`, dòng findings, rule): Screenshots `submission/screenshots/adasind_258420_edge_defect.jpg` và `adasind_270517_occlusion.jpg`, các dòng findings `r3_diag` (ví dụ `adasind_258420.jpg` `L1+R1` và `L7`), tuân thủ luật `R01`, `R03`, `R04`, `R05`.
