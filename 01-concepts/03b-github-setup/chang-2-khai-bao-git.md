# Chặng 2 — Khai báo tên + email cho Git

**Mục tiêu:** mỗi commit có tên và email — GitHub dùng thông tin này để gắn commit cho tài khoản của bạn.
**Thời lượng:** 5 phút.

> 🪟 **Windows:** mở **Git Bash**. macOS/Linux: mở **Terminal**.

---

## Bước 2.1 — Khai báo tên

```bash
git config --global user.name "Tên của bạn"
```

👁️ Không có thông báo gì = thành công.

> Dùng tên thật hoặc nickname ổn định. Tên này hiện **công khai** trong lịch sử commit.

## Bước 2.2 — Khai báo email

Dùng **đúng email đã đăng ký GitHub** (nếu chưa có tài khoản, làm Chặng 3 rồi quay lại sửa cũng được):

```bash
git config --global user.email "email@example.com"
```

> 🔒 **Muốn giấu email?** GitHub hỗ trợ email ẩn dạng `<username>@users.noreply.github.com` (xem GitHub → Settings → Emails). Commit vẫn được gắn cho tài khoản của bạn.

## Bước 2.3 — Đặt nhánh mặc định là `main`

```bash
git config --global init.defaultBranch main
```

> Bài thực hành dùng nhánh `main`. Cấu hình này giúp repo mới tạo không bị rơi vào `master`.

## Bước 2.4 — Kiểm tra

```bash
git config --list
```

👁️ Thấy các dòng:

```
user.name=Tên của bạn
user.email=email@example.com
init.defaultbranch=main
```

> Xem nhanh từng giá trị: `git config --global user.name`, `git config --global user.email`.

---

## ✅ Checkpoint

- [ ] `git config --global user.name` in đúng tên
- [ ] `git config --global user.email` in đúng email
- [ ] `git config --global init.defaultBranch` in ra `main`

---

## 🆘 Lỗi thường gặp

| Lỗi / hiện tượng | Nguyên nhân | Cách sửa |
|---|---|---|
| Gõ sai tên/email | Đã lưu giá trị cũ | Chạy lại lệnh `git config --global ...` với giá trị đúng — giá trị cũ bị ghi đè |
| `error: key does not contain a section` | Thiếu dấu cách giữa `--global` và `user.name` | Viết đúng: `git config --global user.name "..."` |
| `git config --list` không thấy gì | Chưa cấu hình hoặc gõ thiếu `--global` | Làm lại từ Bước 2.1 |
| Commit hiện sai tài khoản trên GitHub | Email không khớp tài khoản GitHub | Đổi sang email đúng, hoặc dùng email `noreply` của GitHub |

---

## 🏁 Khi nào sang Chặng 3?

- [ ] Đã khai báo đúng tên + email
- [ ] Đã đặt `init.defaultBranch main`

> 👉 Xong → mở file [chang-3-tao-tai-khoan.md](chang-3-tao-tai-khoan.md).
