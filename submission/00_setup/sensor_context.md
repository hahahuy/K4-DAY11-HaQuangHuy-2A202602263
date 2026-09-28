# Sensor context

- Rig theo quan sát: ảnh được quay từ camera fisheye gắn về phía bên phải xe máy, nhìn cảnh đường phố. Trong ảnh có xe máy với người điều khiển và một người ngồi sau đang cầm điện thoại; đây là nhận định từ ảnh, không phải thông số rig được dataset xác nhận.
- `ego_body` nhìn thấy ở góc trái dưới frame: phần thân xe, tay lái/tay phải của người điều khiển, chân người lái và chân người ngồi sau.
- Vòng kính xuất hiện ở phần trên và dưới của ảnh; phần vùng cong/viền của lens chiếm ước khoảng 40-60% khung hình. Cần soát theo vòng kính nhìn thấy ở từng frame, không suy nội suy từ ảnh khác.
