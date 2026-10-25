# Chặng 5 — Tạo repo trống trên GitHub

**Mục tiêu:** tạo nơi chứa code trên GitHub, sẵn sàng để push.
**Thời lượng:** 5 phút.

> ⚠️ Repo phải **trống hoàn toàn**. Nếu GitHub tạo sẵn `README.md`, lần push đầu sẽ bị lỗi.

---

## Bước 5.1 — Tạo repo

1. Đăng nhập [github.com](https://github.com).
2. Bấm dấu **`+`** góc phải trên → **New repository**.
3. Điền:
   - **Repository name**: `git-from-scratch`
   - **Description** (không bắt buộc): `Phase 0 — học terminal, VS Code, Git/GitHub`
   - **Visibility**: **Public** (ai cũng xem được) hoặc **Private** (chỉ bạn). Có thể đổi sau trong Settings.
4. **KHÔNG tick**:
   - [ ] Add a README file
   - [ ] Add .gitignore
   - [ ] Choose a license
5. Bấm **Create repository**.

👁️ Bạn thấy trang **Quick setup** với 2 tab **HTTPS** / **SSH** và các lệnh gợi ý.
> Trang này nghĩa là repo đang **trống** — đúng yêu cầu.

## Bước 5.2 — Lấy URL SSH

1. Trên trang Quick setup, chọn tab **SSH**.
2. Copy URL dạng:

   ```
   git@github.com:<username>/git-from-scratch.git
   ```

   > ⚠️ Dùng URL **SSH** (`git@github.com:...`), không dùng HTTPS (`https://...`) — vì Chặng 4 đã cấu hình SSH.
3. Lưu URL này lại, Chặng 6 sẽ dùng.

👁️ Thay `<username>` bằng username GitHub của bạn. Ví dụ: `git@github.com:nguyenvana-dev/git-from-scratch.git`.

---

## ✅ Checkpoint

- [ ] Repo đã tạo, đang **trống** (không có README/.gitignore/license)
- [ ] Đã copy URL SSH `git@github.com:...`

---

## 🆘 Lỗi thường gặp

| Lỗi / hiện tượng | Nguyên nhân | Cách sửa |
|---|---|---|
| Lỡ tick "Add a README file" | Repo không còn trống | Cách nhanh: **Settings → Danger Zone → Delete this repository**, tạo lại và **không tick gì**. (Cách khác: xử lý xung đột ở Chặng 6) |
| Tên repo đã tồn tại | Trùng tên trong tài khoản bạn | Đổi tên, ví dụ `git-from-scratch-phase-0` — nhớ dùng đúng URL mới ở Chặng 6 |
| Không thấy tab SSH | Chưa chọn đúng | Ở trang Quick setup bấm tab **SSH** (cạnh HTTPS) |
| Tạo nhầm Private/Public | Chọn sai visibility | **Settings → General → Danger Zone → Change repository visibility** |

---

## 🏁 Khi nào sang Chặng 6?

- [ ] Repo trống đã tạo
- [ ] Đã có URL SSH

> 👉 Xong → mở file [chang-6-push-lan-dau.md](chang-6-push-lan-dau.md).
