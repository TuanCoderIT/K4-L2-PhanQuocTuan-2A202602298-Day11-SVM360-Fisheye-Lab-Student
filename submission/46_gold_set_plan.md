# Đề xuất gold set theo camera — tình huống giả lập

**Đầu bài:** 50.000 frame từ bốn camera SVM, ngân sách chọn 200 frame để review/gold. Đây là tình huống trên slide, **không phải** 50.000 frame có trong repo. Phân bổ đúng 200 ở `45_sampling_plan.csv` cho bốn camera, mỗi camera có normal và hard slice. “Gold set” ở đây là **kế hoạch tạo** reference sau kiểm chứng, không phải teaching reference ADASIND hoặc nhãn bạn vừa vẽ. Nếu cần, dùng `notebooks/day11-svm360-colab.ipynb` để thử tổng phân bổ; notebook không làm thay phần lý do.

| camera_id | Hard case cần chọn | Vì sao dễ sai | Annotation space / calibration cần giữ | Cách review trước khi gọi là gold |
|---|---|---|---|---|
| front | Đèn pha rọi ngược sáng, bóng râm dải phân cách | Mờ vạch sơn, gán nhãn nhầm bóng râm thành vật cản | Không gian 2D image plane chuẩn hóa theo camera matrix | Cross-check bởi 2 reviewer độc lập và kiểm tra mảng free_space |
| rear | Bám nước mưa/bụi bẩn trên ống kính, chói đèn xe sau | Vật thể bị nhòe nét, sai lệch ranh giới bounding box | Giữ nguyên gốc fisheye distortion parameters | So sánh trùng khớp (IoU > 0.9) giữa các annotator senior |
| left | Xe máy/xe đạp tạt đầu ở mép góc rộng fisheye | Hiện tượng méo hình nặng làm kéo giãn box/polygon | Chuyển đổi tọa độ BEV (Bird's Eye View) để kiểm tra độ cong | Đo đối chiếu hình học trên không gian 3D/BEV |
| right | Vùng giao cắt vỉa hè, vật cản thấp (gờ bê tông, cọc) | Dễ bỏ sót chướng ngại vật thấp nằm sát viền đen ống kính | Tọa độ chuẩn hóa theo khung xe (Ego-frame) | Review thủ công từng frame kết hợp kiểm tra điểm mù |

- Khi nào cần refresh gold set (đổi camera, calibration hoặc rule): Cần refresh khi có sự thay đổi về phần cứng camera (thay ống kính, thay đổi vị trí gá lắp), khi tiến hành re-calibrate thông số intrinsics/extrinsics, hoặc khi quy định gán nhãn (labeling guidelines) có sự điều chỉnh lớn.
- Một ca seam/cross-camera cần policy và evidence trước khi ghép hai box: Cần quy định rõ điểm ghép (overlap region) giữa 2 camera kế tiếp, đối chiếu không gian BEV để đảm bảo vật thể xuất hiện ở điểm giao nhau không bị nhân đôi (duplicate) hoặc ngắt đứt thành 2 ID riêng biệt.
- Vì sao peer agreement hoặc quality report trên ảnh một camera chưa chứng minh gold set đúng cho cả bốn camera: Do mỗi camera có vị trí lắp đặt, mức độ méo fisheye và điều kiện ánh sáng khác nhau; sự đồng thuận trên một camera không phản ánh được sai số căn chỉnh (calibration error) hay hiện tượng lệch không gian khi ghép nối giữa các camera với nhau.