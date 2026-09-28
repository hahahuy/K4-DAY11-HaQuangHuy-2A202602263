# Kế hoạch review từ lỗi quan sát được

Từ `findings.csv` và `zone_table.md`, chọn **hai lát cắt của bài ADASIND một camera** cần review trước. Bảng này
giải thích dữ liệu thật bạn vừa làm; nó không thay cho kế hoạch bốn camera giả lập ở `45_sampling_plan.csv`.

| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| `adasind_261480.jpg`, zone mid | 3 `ThreeWheeler` model missing và nhiều model SPURIOUS do tách/nhầm class | Zone mid có 3 model missing và 7 model thừa; cần kiểm R03/R04 trước vì lỗi lặp lại trong cảnh đông vật thể | `model_compare.html`, `screenshots/model-bike-pedestrian.png`, findings L2+R6, L6+R4, L3+R5, M2/M5/M6/M8/M10/M12 |
| `adasind_265065.jpg`, center và mid | 1 Bike annotator missing đã rework; 1 Bike và 1 Pedestrian reference có thể sai; 1 ca model/reference chưa rõ | Frame có accuracy cục bộ 0.556 trước rework và chứa cả lỗi annotator, bất đồng reference lẫn ca cần reviewer độc lập | `compare.html`, `rework/delta.md`, findings R4, R5, R7, M8 |

Giới hạn của kết luận từ ba frame ADASIND: chỉ là ba frame của một camera fisheye; zone ảnh không là khoảng cách thực và không đại diện bốn camera SVM. Teaching reference là tín hiệu học tập, chưa phải gold set; các tỷ lệ từ đây không suy rộng thành tỷ lệ lỗi dataset.

## Chuyển sang kế hoạch bốn camera giả lập

Cách soát độ phủ của 200 frame ở `45_sampling_plan.csv` (kể cả tránh đếm nhiều frame liền nhau trong cùng cảnh
như nhiều ca độc lập), và vì sao kế hoạch đó chỉ giúp tìm ca cần soi, chưa đo được tỷ lệ lỗi: kiểm đủ front/rear/left/right × normal/hard, kiểm tổng từng ô và lấy mẫu theo scene/timestamp cách nhau để tránh đếm nhiều frame liền nhau là các ca độc lập. Bổ sung hard case rider, ThreeWheeler, ego body, vật ở seam và che khuất cho từng camera. Đây chỉ là kế hoạch tìm ca cần soi trong tình huống 50.000 frame giả lập; không phải mẫu ngẫu nhiên đủ để ước lượng tỷ lệ lỗi hay chất lượng hệ thống.
