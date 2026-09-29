# So sánh L với R

Chỉ số L/R là thứ tự box cao ≥ H=40 trong từng frame, theo thứ tự XML; bắt đầu từ 1.
Box L trong ignore_region được báo IGNORE_SCOPE, không tính SPURIOUS.

## adasind_145860.jpg
- L3 mid IGNORE_SCOPE
## adasind_167700.jpg
- L3 mid IGNORE_SCOPE
- L4 mid IGNORE_SCOPE
- L5+R4 center WRONG_CLASS
- L7 mid SPURIOUS
- R2 mid MISSING
## adasind_199770.jpg
- L2 mid IGNORE_SCOPE
- L3 center SPURIOUS
- L10 mid SPURIOUS
- R3 mid MISSING
- R4 mid MISSING

## Theo zone
| zone | n_ref | matched | missing | spurious |
|---|---|---|---|---|
| center | 9 | 8 | 1 | 2 |
| mid | 7 | 4 | 3 | 2 |
| edge | 4 | 4 | 0 | 0 |
