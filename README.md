# Tiền điện nước phòng 1003

Trang web một file (`index.html`) để chia tiền điện, nước KTX cho 6 người theo **số ngày ở thực tế** của từng người, từ tháng 6 đến tháng 12/2026.

## Cách dùng

Mở `index.html` bằng trình duyệt (hoặc qua GitHub Pages). Không cần cài đặt hay build gì.

1. Chọn tab tháng.
2. Dán tin nhắn hóa đơn vào ô **Dán hóa đơn** để tự nhận diện ngày và số tiền, hoặc nhập tay ngày bắt đầu/kết thúc, tổng tiền điện, tổng tiền nước.
3. Sửa số ngày ở của người nào vắng; để trống (nút **Đủ**) nghĩa là ở đủ cả đợt.
4. Bấm **📱 QR** để hiện mã VietQR chuyển khoản đúng số tiền; đánh dấu cột **Đã đóng** khi đã nhận tiền.
5. Tab **Tổng kết** xem tổng cả các tháng.

Quy ước: ngày kết thúc đợt trước là ngày bắt đầu đợt sau.

## Cách chia tiền

Tiền của mỗi người = tổng tiền × số ngày ở của người đó ÷ tổng số ngày ở của cả phòng. Phần lẻ do làm tròn được dồn sao cho tổng các phần bằng đúng hóa đơn.

## Dữ liệu và đồng bộ

- Dữ liệu lưu trong `localStorage` của trình duyệt và đồng bộ lên Firebase Realtime Database (`/rooms/1003`), kiểm tra bản mới mỗi 10 giây. Mọi máy mở trang đều thấy cùng số liệu.
- **Mã quản lý**: đặt mã để chỉ máy nào nhập đúng mã mới sửa được, các máy khác chỉ xem. Lưu ý: mã nằm trong dữ liệu trên Firebase, nên chỉ chống sửa nhầm, không phải bảo mật thật.
- Có thể **xuất/nhập file JSON** để sao lưu, hoặc **xoá toàn bộ dữ liệu**.

## Thay đổi cho phòng khác

Sửa các hằng số trong `index.html`:

- `MONTHS` — danh sách tháng,
- `NUM_PEOPLE` — số người,
- `syncCfg` — URL Firebase và tên phòng.
