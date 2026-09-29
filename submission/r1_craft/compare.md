# So sánh L với R

Chỉ số L/R là thứ tự box cao ≥ H=40 trong từng frame, theo thứ tự XML; bắt đầu từ 1.
Box L trong ignore_region được báo IGNORE_SCOPE, không tính SPURIOUS.

## adasind_258420.jpg
- L5+R5 mid BOX_GEOMETRY
- L7 mid SPURIOUS
- L9 mid SPURIOUS
- L11 mid SPURIOUS
## adasind_270517.jpg
- L3 mid IGNORE_SCOPE
## adasind_310008.jpg

## Theo zone
| zone | n_ref | matched | missing | spurious |
|---|---|---|---|---|
| center | 6 | 6 | 0 | 0 |
| mid | 7 | 6 | 1 | 4 |
| edge | 7 | 7 | 0 | 0 |
