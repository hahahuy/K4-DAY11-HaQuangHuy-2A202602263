# Error analysis card

## Zone × block

| zone | block | what | count |
|---|---|---|---:|
| center | B4 | MISSING | 3 |
| center | B4 | SPURIOUS | 6 |
| center | C0 | SPURIOUS | 2 |
| edge | B4 | SPURIOUS | 1 |
| edge | C0 | SPURIOUS | 1 |
| mid | B4 | MISSING | 6 |
| mid | B4 | SPURIOUS | 9 |

## Top defects
- SPURIOUS: 19 (ví dụ frame adasind_019560.jpg)
- MISSING: 9 (ví dụ frame adasind_265065.jpg)

## Phân tích của bạn

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`; chạy lại lệnh sẽ cập nhật bảng và giữ nguyên mục này. Viết cho lỗi nổi bật nhất, dẫn frame/`object_ref`.

- Nguyên nhân khả dĩ (`why`) và vì sao bạn nghĩ vậy: lỗi `SPURIOUS` nổi bật phần lớn là `E4_model_domain`, không phải chỉ box lỏng. Ở `adasind_249480.jpg` M2/M4 tách người lái ra khỏi `Bike` thành `Pedestrian`; M6 nhầm các cục gỗ chở trên nóc `Truck` thành `Pedestrian`. Tại `adasind_261480.jpg`, model lặp lại việc tách người khỏi `Bike` và nhầm `ThreeWheeler` thành `Car` hoặc `Truck`. Một ca `M8` ở `adasind_265065.jpg` giữ là `E5_unresolved` vì ảnh không đủ rõ để kết luận bên nào sai.
- Cách sửa và ai nhận việc (`owner`): `ai_team` cần review dữ liệu/huấn luyện cho quy ước R03 (người lái được gộp trong `Bike`) và phân biệt `ThreeWheeler`/hàng chở với người. `annotator` đã thêm lại R4 `Bike` bị bỏ sót ở `adasind_265065.jpg`; delta xác nhận center tăng từ 3 lên 4 matched, missing giảm từ 1 xuống 0. Các ca reference không đủ bằng chứng được giữ theo ảnh gốc hoặc escalated, không sửa chỉ để tăng chỉ số.
- Bằng chứng (ảnh trong `screenshots/`, dòng findings, rule): `screenshots/model-bike-pedestrian.png`, `screenshots/model-truck-wood.png`; findings `r3_diag` M2/M4/M6 ở `adasind_249480.jpg`, M2/M5/M6/M8/M10/M12 ở `adasind_261480.jpg`; R03, R04 và `rework/delta.md`.
