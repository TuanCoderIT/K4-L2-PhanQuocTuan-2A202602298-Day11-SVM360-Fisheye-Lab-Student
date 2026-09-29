# QA review · B4-dense

Mã khóa: 8B4D-C84C

| frame | object_ref | rule_id | nhận xét |
|---|---|---|---|
| adasind_258420.jpg | L5 | R05 | Kiểm tra attribute occluded của Car L5 do bị xe phía trước che khuất một phần. |
| adasind_258420.jpg | L7 | R03 | Kiểm tra Bike L7 và L8 có thuộc cùng một người lái hay hai người hai xe riêng biệt. |
| adasind_270517.jpg | L1 | R05 | Bike L1 chạm mép phải khung hình (xbr=1080), xác nhận attribute truncated đã đặt đúng. |
| adasind_270517.jpg | L3 | R06 | Xe ThreeWheeler L3 bị che gần hết ở xa, kiểm tra xem có thuộc ignore_region reason=unreadable không. |

Ghi finding r2_qa: cell=L_only, rule_id có giá trị, why để trống.

