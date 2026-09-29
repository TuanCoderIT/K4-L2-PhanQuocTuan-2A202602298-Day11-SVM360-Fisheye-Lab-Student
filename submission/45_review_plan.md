# Kế hoạch review từ lỗi quan sát được

Từ `findings.csv` và `zone_table.md`, chọn **hai lát cắt của bài ADASIND một camera** cần review trước. Bảng này giải thích dữ liệu thật bạn vừa làm; nó không thay cho kế hoạch bốn camera giả lập ở `45_sampling_plan.csv`.

| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| adasind_258420.jpg (zone mid & edge) | 4 ca MISSING (Model), 3 ca SPURIOUS (Annotator) | Mật độ xe hai bánh và xe ba bánh cao, biến dạng méo ống kính fisheye dẫn đến lỗi thiếu/thừa box | Bảng so sánh IoU sweep và screenshot `adasind_258420_edge_defect.jpg` |
| adasind_270517.jpg (zone mid) | 2 ca MISSING (Model), 1 ca SPURIOUS (L3) | Nhiều vật thể bị che khuất một phần (occluded) ở khoảng cách xa | Báo cáo compare HTML và screenshot `adasind_270517_occlusion.jpg` |

Giới hạn của kết luận từ ba frame ADASIND: Quy mô mẫu chỉ 3 frame không đủ đại diện cho toàn bộ các điều kiện môi trường, ánh sáng và thời tiết khác nhau trong tập 50.000 frame.

## Chuyển sang kế hoạch bốn camera giả lập

Cách soát độ phủ của 200 frame ở `45_sampling_plan.csv` (kể cả tránh đếm nhiều frame liền nhau trong cùng cảnh như nhiều ca độc lập), và vì sao kế hoạch đó chỉ giúp tìm ca cần soi, chưa đo được tỷ lệ lỗi: Cần thực hiện lấy mẫu cách khoảng (stride sampling) ví dụ mỗi 5-10 giây chọn 1 frame để đảm bảo tính đa dạng ngữ cảnh và độc lập giữa các ca. Kế hoạch này giúp khoanh vùng các trường hợp khó (hard cases) cần kiểm tra trực quan bằng mắt, nhưng chưa đủ đại diện thống kê để tính tỷ lệ lỗi toàn hệ thống.
