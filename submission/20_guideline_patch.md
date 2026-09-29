# Guideline patch

- **Rule mới đề xuất:** R12 — Quy định ngưỡng khoảng cách và tiêu chuẩn gán nhãn cho xe ba bánh (ThreeWheeler) bị che khuất ở vùng biến dạng fisheye.
- **Áp dụng cho:** Class `ThreeWheeler`, zone `mid` và `edge`.
- **Vì sao luật hiện tại (`docs/02-rules-vi.md`) không đủ:** Luật v1.0.0 chưa chi tiết hóa quy tắc xử lý với xe ba bánh chở hàng/chở người ở khoảng cách xa bị che một phần trong vùng biến dạng fisheye, gây ra sự không thống nhất giữa Annotator và Reference.
- **`rules_version` mới:** v1.1.0
- **Hiệu lực từ:** Round Rework (P5) trở đi.
