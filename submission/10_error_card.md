# Error analysis card

## Zone × block

| zone | block | what | count |
|---|---|---|---:|
| center | B3 | MISSING | 3 |
| center | B3 | SPURIOUS | 6 |
| center | B3 | WRONG_CLASS | 1 |
| center | C0 | SPURIOUS | 1 |
| edge | B3 | MISSING | 4 |
| edge | B3 | SPURIOUS | 3 |
| mid | B3 | IGNORE_SCOPE | 4 |
| mid | B3 | MISSING | 8 |
| mid | B3 | SPURIOUS | 7 |
| mid | C0 | MISSING | 1 |

## Top defects
- SPURIOUS: 17 (ví dụ frame adasind_019560.jpg)
- MISSING: 16 (ví dụ frame adasind_019560.jpg)
- IGNORE_SCOPE: 4 (ví dụ frame adasind_145860.jpg)

## Phân tích của bạn

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`; chạy lại lệnh sẽ cập nhật bảng và giữ nguyên mục này. Viết cho lỗi nổi bật nhất, dẫn frame/`object_ref`.

- Nguyên nhân khả dĩ (`why`) và vì sao bạn nghĩ vậy: Ảnh bị mờ, dẫn đến các chi tiết trong ảnh bị bỏ sót.
- Cách sửa và ai nhận việc (`owner`): Sửa lại bằng cách rà soát lại các object.
- Bằng chứng (ảnh trong `screenshots/`, dòng findings, rule): 
