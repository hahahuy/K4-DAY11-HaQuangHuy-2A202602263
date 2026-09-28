# So sánh L với R

Chỉ số L/R là thứ tự box cao ≥ H=40 trong từng frame, theo thứ tự XML; bắt đầu từ 1.
Box L trong ignore_region được báo IGNORE_SCOPE, không tính SPURIOUS.

## adasind_019560.jpg
- L3 center SPURIOUS
- L5 edge SPURIOUS
- L6 center SPURIOUS

## Theo zone
| zone | n_ref | matched | missing | spurious |
|---|---|---|---|---|
| center | 3 | 3 | 0 | 2 |
| mid | 2 | 2 | 0 | 0 |
| edge | 1 | 1 | 0 | 1 |

## Nhận xét ba ca cần giải thích

- `adasind_019560.jpg` — `L6 Pedestrian` (center, `SPURIOUS` so với R): giữ nhãn này. Người đứng ngoài xe hai bánh và đang dắt xe, không ngồi lên để điều khiển. Theo R03, người dắt xe phải có một box `Pedestrian` riêng cùng với box `Bike`; vì vậy đây là bất đồng với teaching reference cần được nêu rõ, không phải một rider gộp vào `Bike`.
- `adasind_019560.jpg` — `L3 Bike` (center, `SPURIOUS` so với R): giữ nhãn này. Đây là một xe hai bánh riêng ở phía sau, bị xe hai bánh ở giữa đường che một phần, không phải box trùng. Phần thấy được cao khoảng 57 px, vượt H=40 của R01; box bám phần nhìn thấy theo R02 và có `occluded=true` theo R05.
- `adasind_019560.jpg` — `L5 Bike` (edge, `SPURIOUS` so với R): nhãn này là lỗi cần sửa. Vật ở góc trái là một phần thân xe gắn camera, không phải xe hai bánh độc lập; xoá box `Bike` và đánh dấu phần thân xe nhìn thấy bằng `ignore_region` với `reason=ego_body` theo R06-R07. Trạng thái `truncated=true` hiện có không biến ego body thành đối tượng `Bike`.

Teaching reference là tín hiệu để soát lại sau khoá, không tự động là chân lý. Hai ca `L3` và `L6` được giữ vì có bằng chứng từ ảnh và rule; `L5` được sửa vì sai phạm vi đối tượng.
