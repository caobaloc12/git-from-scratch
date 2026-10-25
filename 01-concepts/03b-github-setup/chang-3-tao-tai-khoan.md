# Chặng 3 — Tạo tài khoản GitHub

**Mục tiêu:** có tài khoản GitHub và đăng nhập được.
**Thời lượng:** 10 phút.

> 🧠 Đã có tài khoản thì bỏ qua chặng này — nhưng nhớ dùng **đúng email** đã khai báo ở Chặng 2.

---

## Bước 3.1 — Đăng ký

1. Mở [github.com](https://github.com) → bấm **Sign up** (góc phải trên).
2. Nhập **email** (dùng email bạn hay kiểm tra).
3. Tạo **password** mạnh (≥ 15 ký tự hoặc dùng trình quản lý mật khẩu).
4. Nhập **username** — tên này sẽ xuất hiện trong URL repo:
   👁️ `github.com/<username>/git-from-scratch`
   > Chọn tên ngắn, dễ nhớ, không chứa thông tin nhạy cảm. Ví dụ: `nguyenvana-dev`.
5. Xác nhận bạn không phải robot → **Create account**.
6. Nhập mã **6 chữ số** GitHub gửi qua email.

👁️ Đăng nhập thành công → thấy trang **Home / Dashboard**.

## Bước 3.2 — Xác minh email

1. Mở hộp thư → tìm mail từ GitHub → bấm **Verify email address**.
2. Trong GitHub: **Settings → Emails** → thấy email có nhãn **Verified**.

> ⚠️ Chưa xác minh email có thể bị chặn ở một số bước, kể cả push code.

## Bước 3.3 — Bật 2FA (bắt buộc với tài khoản mới)

GitHub yêu cầu xác thực 2 lớp (2FA). Làm ngay để tránh bị khóa:

1. **Settings → Password and authentication → Two-factor authentication → Enable**.
2. Chọn **Authenticator app** (Google Authenticator, Microsoft Authenticator, Authy...).
3. Quét QR bằng app → nhập mã 6 số.
4. **Lưu recovery codes** vào nơi an toàn (in ra hoặc lưu trong password manager).

> 🆘 Mất điện thoại + mất recovery codes = có thể mất tài khoản. Đừng bỏ qua bước lưu mã.

---

## ✅ Checkpoint

- [ ] Đăng nhập được github.com
- [ ] Email đã **Verified**
- [ ] Đã bật 2FA và lưu recovery codes

---

## 🆘 Lỗi thường gặp

| Lỗi / hiện tượng | Nguyên nhân | Cách sửa |
|---|---|---|
| Không nhận được mail xác minh | Mail vào Spam/Quảng cáo | Kiểm tra Spam, chờ vài phút, bấm **Resend** |
| Username đã có người dùng | Trùng tên | Thêm hậu tố: `nguyenvana-dev`, `nguyenvana-01`... |
| Không qua được bước xác minh robot | Trình duyệt/VPN chặn | Tắt VPN, thử trình duyệt khác, làm lại chậm hơn |
| Mất recovery codes | Chưa lưu | Vào Settings → Password and authentication để tạo lại (khi còn đăng nhập được) |

---

## 🏁 Khi nào sang Chặng 4?

- [ ] Đã đăng nhập được GitHub
- [ ] Email đã xác minh

> 👉 Xong → mở file [chang-4-tao-ssh-key.md](chang-4-tao-ssh-key.md).
