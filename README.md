# VietQR Salary Batch

Mini app static để tạo nhiều mã VietQR chi lương/thưởng trong một batch.

## Chạy nhanh

1. Giải nén file zip.
2. Mở `index.html` bằng Chrome/Edge/Safari.
3. Paste nội dung lương hoặc import file Excel theo template.
4. Kiểm tra từng dòng: tên, số tài khoản, ngân hàng, số tiền, nội dung.
5. Bấm **Tạo QR**.
6. Mở app ngân hàng, quét từng QR, kiểm tra lại thông tin rồi xác nhận chuyển khoản.

## Lưu ý quan trọng

- App không tự chuyển tiền và không kết nối tài khoản ngân hàng của bạn.
- App dùng VietQR Quick Link dạng:
  `https://img.vietqr.io/image/<BANK_ID>-<ACCOUNT_NO>-<TEMPLATE>.png?amount=<AMOUNT>&addInfo=<DESCRIPTION>&accountName=<ACCOUNT_NAME>`
- Cần internet để tải danh sách ngân hàng mới nhất từ `https://api.vietqr.io/v2/banks` và hiển thị ảnh QR từ `img.vietqr.io`.
- Nếu không tải được danh sách bank, app có fallback cho các ngân hàng phổ biến như Sacombank, Techcombank, MBBank, Vietcombank, BIDV, ACB...
- Luôn kiểm tra lại người thụ hưởng, số tiền, số tài khoản, ngân hàng và nội dung trên app ngân hàng trước khi xác nhận.

## Excel template

Dùng file:

`templates/vietqr_salary_batch_template.xlsx`

Header chính:

- Name
- Bank
- Account No
- Amount
- Transfer Content
- Note

`Amount` có thể nhập dạng:

- `5368k` = 5,368,000
- `4370k` = 4,370,000
- `10tr` = 10,000,000
- `10000000` = 10,000,000

## CSV template

Dùng file:

`samples/transfer_template.csv`

## Log local

Nút **Lưu log batch** lưu lịch sử trong `localStorage` của trình duyệt hiện tại. Xóa cache/browser profile có thể mất log.

## Chỉnh sửa code

Toàn bộ app nằm trong `index.html`, không cần build, không cần cài Node.js.
