# Exit ticket

Đọc `docs/10-svm360-reading-vi.md` trước khi trả lời câu 1–2. Các câu về zone, `why`, rework, parking và sampling đã nằm trong file tương ứng nên không hỏi lại ở đây.

1. Một vật ở vùng seam giữa hai camera thật xuất hiện với hai box khác nhau: đó là lỗi `DUPLICATE` hay cần một quy tắc riêng? Vì sao?
   Cần một quy tắc riêng (cross-camera matching policy) chứ không đơn thuần gán là lỗi `DUPLICATE`. Vì vùng seam là vùng phủ chồng góc nhìn giữa 2 camera fisheye vật lý độc lập; việc cùng một vật thể xuất hiện trên 2 ống kính là hiện tượng quang học tự nhiên, cần có quy tắc ghép nối hình học/không gian 3D thay vì quy trách nhiệm trùng lặp trên 2D single-camera.

2. Một vật đi qua nhiều frame trên cùng camera: khi nào giữ cùng track ID, khi nào thêm keyframe hoặc trạng thái Outside? Nêu bằng chứng sẽ cần trước khi nối track qua hai camera.
   Giữ cùng track ID khi vật thể di chuyển liên tục và còn xuất hiện rõ trong tầm nhìn. Thêm keyframe khi đối tượng thay đổi hướng/hình dạng đáng kể hoặc bị che khuất một phần. Đặt trạng thái Outside khi đối tượng ra khỏi tầm nhìn ống kính. Bằng chứng cần thiết trước khi nối track qua 2 camera bao gồm: thời gian (timestamp đồng bộ), quỹ đạo di chuyển (trajectory), ma trận hiệu chuẩn camera (extrinsic calibration parameters) và đặc trưng ngoại hình (re-ID features).

3. Nhìn lại cả buổi: một chỗ bạn tin nhãn mình đúng nhưng reference hoặc người soát nghĩ khác (dẫn frame/`object_ref`), bạn đã xử lý thế nào, và nếu làm lại slice này bạn sẽ đổi gì trong cách làm?
   Tại frame `adasind_258420.jpg`, đối tượng `L5` (`Car`), tôi tin nhãn gán đúng nhưng reference không có box. Tôi đã giữ quyết định và ghi lý do `keep_with_reason` với `why=E0_reference_defect` trong `findings.csv` cùng `decision_log.csv`. Nếu làm lại slice này, tôi sẽ kiểm tra kỹ hơn bằng checklist 9 bước self-QC trước khi khóa bản cuối để tránh các lỗi `SPURIOUS` nhỏ.
