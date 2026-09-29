# Sensor context

- **Rig:** Theo quan sát từ ảnh, camera (có thể là camera hành trình hoặc GoPro/điện thoại gắn tản nhiệt) được gắn phía trước của một chiếc xe máy (scooter/xe số). Góc quay hướng về phía trước theo chiều di chuyển của xe. Camera được gắn khá thấp, gần với ghi-đông hoặc mặt đồng hồ xe, cho góc nhìn từ phía người lái (đôi khi nhìn thấy một phần tay/vai người lái ở góc dưới).

- **`ego_body`:** Một phần thân xe của chính người lái (ego vehicle) xuất hiện rõ ở các góc dưới của khung hình:
  - Ở góc dưới bên trái: Thường nhìn thấy tay áo và găng tay/tay nắm ghi-đông của người lái (rõ nhất ở ảnh 1 và 2).
  - Ở góc dưới bên phải: Đôi khi nhìn thấy một phần nhỏ của gương chiếu hậu hoặc ốp đầu xe.

- **Vòng kính (lens circle):** Vì đây là loại ống kính mắt cá (fisheye lens) góc cực rộng, vòng tròn giới hạn kính (lens vignette/black border) xuất hiện rất rõ ràng:
  - Vòng tròn đen này bao trọn toàn bộ bốn góc và các cạnh của ảnh.
  - Vùng hình ảnh hữu ích (scene content) nằm gọn bên trong một vòng tròn lớn ở trung tâm.
  - Diện tích vùng ảnh hữu ích chiếm khoảng 80-85% tổng diện tích khung hình chữ nhật; phần còn lại là viền đen bezel của ống kính.