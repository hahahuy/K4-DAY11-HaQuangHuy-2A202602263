# Zone table (slice của bạn)

Lệnh `python3 lab11.py model` tự ghi bảng số (cùng cách đếm với `r1_craft/compare.md` và `model_compare.md`); chạy lại lệnh sẽ cập nhật bảng và giữ nguyên phần nhận xét. Bạn chỉ viết mục Nhận xét.

| Zone | n_ref | L missing | L spurious | M missing (`LR_noM` + `R_only`) | M thừa (`LM_noR` + `M_only`) | Lỗi L chính (`what`) |
|---|---:|---:|---:|---:|---:|---|
| center | 4 | 1 | 1 | 1 | 4 | SPURIOUS (1) |
| mid | 13 | 2 | 1 | 3 | 7 | MISSING (2) |
| edge | 0 | 0 | 0 | 0 | 1 | — |

## Nhận xét

- Với người gán nhãn (L), zone `mid` gãy nhiều nhất: 2 missing và 1 spurious, trong khi `center` có 1 missing và 1 spurious, `edge` không có reference. Với model (M), `mid` cũng là zone cần review trước: 3 missing và 7 box thừa, lớn hơn `center` (1 missing, 4 box thừa).
- Các overlay cho thấy một pattern cụ thể thay vì chỉ box lỏng: model thường tách người lái khỏi `Bike` thành `Pedestrian`, hoặc nhầm các `ThreeWheeler` nhỏ thành `Car`/`Truck`; tại `adasind_249480.jpg`, M6 còn nhầm các cục gỗ chở trên nóc `Truck` thành `Pedestrian`. Kết luận này chỉ dựa trên ba frame ADASIND của một camera fisheye; zone trên ảnh không biểu thị khoảng cách thực, IoU sweep không thay đổi kết quả L/R từ 0.30 đến 0.70, và teaching reference là reference học tập chứ chưa phải gold set.
