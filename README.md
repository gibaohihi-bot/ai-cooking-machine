# CHEF / Máy nấu tự động — 3D Lab

Mô hình tương tác cho ý tưởng máy nấu tự động: người dùng sơ chế, chia sẵn từng khẩu phần, khai báo ngăn rồi chọn món và khẩu vị. Giao diện tiếng Việt.

## Chạy bản thử

[Mở mô phỏng trực tiếp](https://gibaohihi-bot.github.io/ai-cooking-machine/) trên GitHub Pages.

Hoặc tải `index.html`, mở bằng Chrome, Edge hoặc Safari. Bản tải về không cần cài đặt, API key, thư viện ngoài hay kết nối mạng.

## Xem máy

- Kéo để xoay 360°, cuộn hoặc chụm hai ngón để zoom.
- Chọn phối cảnh, mặt trước, mặt sau hoặc từ trên.
- Mở, đóng, làm trong suốt vỏ máy; kéo thanh tách bộ phận.
- Bấm mô hình hoặc chọn một trong 14 cụm: vỏ, lạnh, ngăn, cửa thả, máng dẫn, nồi, cánh đảo, bếp, bình nước/dầu, bơm, gia vị, điều khiển, quạt/làm lạnh và cảm biến.
- Cấu tạo, chức năng và giới hạn từng cụm hiển thị ở bảng chi tiết.

## Chạy mẻ

1. Khai báo nguyên liệu và khối lượng cho 6 ngăn; mỗi ngăn dùng hết một khẩu phần.
2. Chọn xào, kho hoặc canh; chỉnh mức mặn/cay và nhập mô tả.
3. Tạo kế hoạch. Bộ lập kế hoạch kiểm tra thịt, rau, khối lượng và một số từ khóa trong yêu cầu.
4. Chạy mẻ: cửa mở, nguyên liệu rơi, bơm cấp, cánh đảo quay và trạng thái nhiệt thay đổi.
5. Tạm dừng tắt gia nhiệt/cánh đảo; tiếp tục không thả lại ngăn đã dùng.
6. Dừng máy hoặc lỗi sẽ ngắt mô phỏng; nạp lại để tạo mẻ mới.
7. Đánh giá khẩu vị được lưu trên trình duyệt nếu localStorage khả dụng.

Thử lỗi kẹt ngăn thịt, quá nhiệt; thử chặn khi khoang lạnh chưa đạt hoặc nồi chưa lắp.

## Giới hạn

Đây là mô hình ý tưởng, không phải CAD để sản xuất hay mô phỏng vật lý/điện/nhiệt đã kiểm chứng. Kích thước, vật liệu, thời gian, nhiệt và cảm biến đều minh họa. Phần mềm không điều khiển máy thật, không chứng minh món ăn đã chín an toàn. Món được lập từ quy tắc cho ba cách nấu; chưa gọi AI thật. Các chi tiết cơ khí nhỏ, dây điện, van và tính toán tải chưa được thiết kế để chế tạo.

Mô hình dùng Canvas 2D để chiếu các khối 3D theo phối cảnh, sắp xếp độ sâu và chọn mặt bằng chuột. Không phụ thuộc WebGL hay CDN; hình học được định nghĩa trong `index.html`.

## Kiểm tra

`node --check simulator.js` kiểm tra cú pháp. `node verify.cjs` chạy kiểm tra logic mô phỏng bằng DOM/canvas giả lập: hoàn tất, giữ lại ngăn không dùng, tạm dừng, kẹt ngăn, quá nhiệt, điều kiện đầu vào và phản hồi. Giao diện đã được mở và chạy thử một mẻ trên website GitHub Pages bằng Chrome.

`simulator.js` là bản tách script từ HTML phục vụ kiểm tra; mã chạy độc lập nằm đầy đủ trong `index.html`.
