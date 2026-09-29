# Zone table (slice của bạn)

Lệnh `python3 lab11.py model` tự ghi bảng số (cùng cách đếm với `r1_craft/compare.md` và `model_compare.md`); chạy lại lệnh sẽ cập nhật bảng và giữ nguyên phần nhận xét. Bạn chỉ viết mục Nhận xét.

| Zone | n_ref | L missing | L spurious | M missing (`LR_noM` + `R_only`) | M thừa (`LM_noR` + `M_only`) | Lỗi L chính (`what`) |
|---|---:|---:|---:|---:|---:|---|
| center | 6 | 0 | 0 | 4 | 5 | — |
| mid | 7 | 1 | 4 | 3 | 10 | SPURIOUS (3) |
| edge | 7 | 0 | 0 | 1 | 1 | — |

## Nhận xét

- Zone nào người (L) và model (M) gãy nhiều nhất, dẫn số ở bảng trên: Zone **mid** là nơi gãy nhiều nhất. Ở vai người gán nhãn (L), zone mid bị 1 missing và 4 spurious. Model (M) gãy nặng nhất ở zone mid với 3 missing và 10 box thừa (`LM_noR` + `M_only`), kế đó là zone center với 4 missing và 5 box thừa.
- Giả thuyết vì sao (méo fisheye, box lỏng, thiếu `ego_body`, ...) và giới hạn của slice ba frame: do slice `B4-dense` có mật độ phương tiện xe 2 bánh/3 bánh/người đi bộ rất cao ở zone mid và center, các vật nằm chồng lấp lên nhau khiến Model (M) bị nhận diện nhầm/trùng box. Ngoài ra hiệu ứng méo ống kính fisheye ở góc làm bounding box bị lệch IoU khi so với reference. Giới hạn của slice 3 frame là quy mô nhỏ, chưa đủ đánh giá độ ổn định của model trên toàn bộ video 50.000 frame.
