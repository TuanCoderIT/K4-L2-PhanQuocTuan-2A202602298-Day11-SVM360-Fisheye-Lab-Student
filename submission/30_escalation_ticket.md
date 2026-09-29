# Escalation ticket

## Ticket 1

- **Frame:** adasind_258420.jpg
- **Ảnh chụp:** `submission/screenshots/adasind_258420_edge_defect.jpg`
- **Expected impact:** Giảm 15% false negative (MISSING) của Model YOLO ở vùng biên ảnh fisheye đối với xe 3 bánh.
- **Owner:** `ai_team`
- **Recommendation:** Bổ sung augmentations méo fisheye góc rộng và fine-tune YOLO model trên tập dữ liệu ống kính fisheye ở biên ảnh.

## Ticket 2

- **Frame:** adasind_270517.jpg
- **Ảnh chụp:** `submission/screenshots/adasind_270517_occlusion.jpg`
- **Expected impact:** Chuẩn hóa quy định gán nhãn cho các trường hợp phương tiện che khuất nhiều đối tượng ở khoảng cách xa.
- **Owner:** `guideline`
- **Recommendation:** Thêm ví dụ minh họa chi tiết cho Rule R06/R09 khi gán `ignore_region` `unreadable` cho vật bị che khuất >70%.
