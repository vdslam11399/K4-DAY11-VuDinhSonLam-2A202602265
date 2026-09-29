# Đối chiếu chất lượng cục bộ — rectangle

Teaching reference, không phải gold set đã phê duyệt; không có điểm đạt tự động.
Nguồn: export r1_craft đã khóa SHA256 `017e1170c3ea8374f68ccf3c85fbd3fa3e3f704d45bfef0e9c4b1e6666c7007d`; slice `B3-dense`.
Ghép hình học greedy một-một theo IoU ≥ 0.50, rồi so class; H ≥ 40 px.
Box trái nằm chủ yếu trong ignore_region reference không tính. Polygon, polyline, track không được chấm.
Đây là phép tính offline của lab, không phải báo cáo hay kết quả tương đương CVAT Premium.

Frame được tính: adasind_145860.jpg, adasind_167700.jpg, adasind_199770.jpg. Frame thiếu trong export: không.
TP=16; FP=4; FN=4; số lần đối chiếu=23; mean IoU của TP=0.769.

| Chỉ số | Micro | Macro | Nhãn thấp nhất |
|---|---:|---:|---:|
| accuracy | 0.696 | 0.930 | 0.870 |
| precision | 0.800 | 0.830 | 0.600 |
| recall | 0.800 | 0.767 | 0.500 |
| jaccard | 0.667 | 0.647 | 0.500 |
| dice | 0.800 | 0.776 | 0.667 |

| Nhãn | TP | FP | FN | Accuracy | Precision | Recall | Jaccard | Dice |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Bike | 5 | 0 | 1 | 0.957 | 1.000 | 0.833 | 0.833 | 0.909 |
| Car | 1 | 0 | 1 | 0.957 | 1.000 | 0.500 | 0.500 | 0.667 |
| Pedestrian | 3 | 1 | 1 | 0.913 | 0.750 | 0.750 | 0.600 | 0.750 |
| ThreeWheeler | 3 | 2 | 1 | 0.870 | 0.600 | 0.750 | 0.500 | 0.667 |
| Truck | 4 | 1 | 0 | 0.957 | 0.800 | 1.000 | 0.800 | 0.889 |

| Frame | TP | FP | FN | Accuracy | Precision | Recall |
|---|---:|---:|---:|---:|---:|---:|
| adasind_145860.jpg | 2 | 0 | 0 | 1.000 | 1.000 | 1.000 |
| adasind_167700.jpg | 7 | 2 | 2 | 0.700 | 0.778 | 0.778 |
| adasind_199770.jpg | 7 | 2 | 2 | 0.636 | 0.778 | 0.778 |

Confusion matrix: hàng = teaching reference; cột = export đã khóa.
`<missing>` là thiếu box; `<extra>` là box thừa. Xem `local_quality_confusion.csv`.

| Reference \ Export | Bike | Car | Pedestrian | ThreeWheeler | Truck | <missing> |
|---|---:|---:|---:|---:|---:|---:|
| Bike | 5 | 0 | 0 | 0 | 0 | 1 |
| Car | 0 | 1 | 0 | 0 | 1 | 0 |
| Pedestrian | 0 | 0 | 3 | 0 | 0 | 1 |
| ThreeWheeler | 0 | 0 | 0 | 3 | 0 | 1 |
| Truck | 0 | 0 | 0 | 0 | 4 | 0 |
| <extra> | 0 | 0 | 1 | 2 | 0 | 0 |

Chi tiết xung đột trong `local_quality_conflicts.csv`; dữ liệu máy đọc trong `local_quality.json`.
Mismatching label đóng góp một FP cho class vẽ và một FN cho class reference; attribute khác được báo riêng.
Micro accuracy đếm mỗi cặp ghép sai class là một lần đối chiếu; Jaccard đếm cả FP và FN.
Macro/worst bỏ nhãn không xuất hiện ở cả hai phía; chỉ số không có mẫu là N/A.
