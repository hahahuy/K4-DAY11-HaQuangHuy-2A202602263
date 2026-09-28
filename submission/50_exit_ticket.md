# Exit ticket

Đọc `docs/10-svm360-reading-vi.md` trước khi trả lời câu 1–2. Các câu về zone, `why`, rework, parking và sampling
đã nằm trong file tương ứng nên không hỏi lại ở đây.

1. Một vật ở vùng seam giữa hai camera thật xuất hiện với hai box khác nhau: đây không tự động là `DUPLICATE`; cần quy tắc cross-camera riêng. Hai ảnh fisheye có thể cùng thấy một vật ở seam với hai box khác nhau. Chỉ sau khi có timestamp đồng bộ, calibration và policy output (giữ, hợp nhất hay chọn một box) mới quyết định cách đánh giá hoặc nối identity.
2. Một vật đi qua nhiều frame trên cùng camera: giữ cùng track ID khi có bằng chứng là cùng vật còn quan sát được; thêm keyframe khi hình học thay đổi đáng kể; đặt Outside khi vật rời trường nhìn. Trước khi nối qua hai camera cần timestamp đồng bộ, calibration, bằng chứng vị trí/thời gian liên tục và policy output; không nối chỉ vì box trông giống nhau.
3. Ở `adasind_265065.jpg`, `R4` là Bike tôi bỏ sót nhưng reference có. Tôi đối chiếu ảnh gốc và `compare.html`, ghi finding `E1_annotator_error`, rồi thêm lại đúng ca đó trong rework; `delta.md` cho thấy center missing giảm 1 xuống 0. Nếu làm lại, tôi sẽ quét từng vùng center/mid theo H=40 trước khi vẽ và kiểm riêng các xe nhỏ/đỗ ven đường trước khi khóa.
