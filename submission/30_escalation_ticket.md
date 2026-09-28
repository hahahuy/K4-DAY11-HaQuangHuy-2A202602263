# Escalation ticket

## Ticket 1

- **Frame:** `adasind_249480.jpg` và `adasind_261480.jpg`.
- **Ảnh chụp:** `submission/screenshots/model-bike-pedestrian.png` và `submission/screenshots/model-truck-wood.png`.
- **Expected impact:** model tạo `Pedestrian` thừa khi người thuộc một `Bike` (M2/M4 ở `adasind_249480.jpg`, M2/M5 ở `adasind_261480.jpg`), đồng thời M6 ở `adasind_249480.jpg` nhầm hàng chở trên nóc `Truck` thành `Pedestrian`. Điều này làm tăng SPURIOUS và làm sai class trong các cảnh đông vật thể.
- **Owner:** `ai_team`.
- **Recommendation:** rà mẫu train/eval có người lái xe hai bánh theo R03, hard-negative cho hàng chở trên `Truck`, và đánh giá riêng các nhầm lẫn `ThreeWheeler` với `Car`/`Truck`; không thay nhãn đã khóa chỉ để khớp model.
