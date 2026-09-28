# Guideline patch

- **Rule mới đề xuất:** Bổ sung ví dụ trực quan cho R03: nếu người có tư thế ngồi/điều khiển trên xe hai bánh thì vẽ một `Bike`, không thêm `Pedestrian` cho phần người. Nếu người đứng tách khỏi xe và đẩy/dắt xe thì vẽ hai box `Pedestrian` và `Bike`.
- **Áp dụng cho:** `Bike`, `Pedestrian`, rule rider R03; ưu tiên review các ca chồng box người/xe ở zone center và mid.
- **Vì sao luật hiện tại (`docs/02-rules-vi.md`) không đủ:** R03 đã nêu nguyên tắc chữ, nhưng các box model M2/M4 ở `adasind_249480.jpg` và M2/M5 ở `adasind_261480.jpg` cho thấy cần một ví dụ ảnh có cả người lái lẫn người dắt xe để giảm diễn giải khác nhau khi review/huấn luyện.
- **`rules_version` mới:** v1.0.0 → v1.1.0.
- **Hiệu lực từ:** các task gán nhãn và review mới sau khi guideline được phát hành; không hồi tố âm thầm export đã khóa.
