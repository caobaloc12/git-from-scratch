# Chặng 7 — Kiểm tra kết quả cuối

**Mục tiêu:** xác nhận code đã lên GitHub và luyện push lần 2.
**Thời lượng:** 5 phút.

---

## Bước 7.1 — Kiểm tra trên GitHub

1. Mở repo trên trình duyệt → bấm **F5**.
2. 👁️ Thấy:
   - Danh sách file `README.md`, `CHECKLIST.md`, `01-concepts/`, `02-practice/`
   - Nhánh **main**
   - Số commit (ít nhất `1 commit`)
3. Bấm vào `README.md` → 👁️ nội dung hiển thị đúng tiếng Việt.
4. Bấm **Commits** → 👁️ thấy commit `chore: khởi tạo repo phase 0`.

## Bước 7.2 — Kiểm tra từ máy

```bash
cd ~/Workspace/github/git-from-scratch
git status
git remote -v
git log --oneline
```

👁️ Lần lượt:
- `Your branch is up to date with 'origin/main'.`
- 2 dòng remote trỏ `git@github.com:<username>/git-from-scratch.git`
- Ít nhất 1 commit

## Bước 7.3 — Push lần 2

1. Mở `02-practice/03-sandbox/hello.txt` (VS Code hoặc Notepad) → thêm 1 dòng, ví dụ:

   ```
   Dòng này được thêm từ máy của tôi.
   ```

2. Trong Git Bash, xem thay đổi:

   ```bash
   git diff
   ```

   👁️ Thấy dòng vừa thêm với dấu `+`.

3. Commit & push:

   ```bash
   git add .
   git commit -m "docs: cập nhật hello.txt từ máy local"
   git push
   ```

   👁️ Push xong không báo lỗi.

4. Refresh trang GitHub → 👁️ thấy `2 commits`, nội dung `hello.txt` đã đổi.

## Bước 7.4 — Hoàn thành checklist

1. Mở `CHECKLIST.md` → đánh dấu `[x]` các mục bạn đã làm.
2. Commit + push:

   ```bash
   git add CHECKLIST.md
   git commit -m "docs: cập nhật checklist phase 0"
   git push
   ```

---

## ✅ Checkpoint cuối

- [ ] Repo trên GitHub có ≥ 2 commit
- [ ] `hello.txt` trên GitHub có nội dung mới
- [ ] `git status` báo up to date
- [ ] `CHECKLIST.md` đã được cập nhật

> 🎉 Chúc mừng! Bạn đã hoàn thành Phase 0 phần GitHub.
> Tiếp theo: làm các bài trong `02-practice/` và tick dần `CHECKLIST.md`.

---

## 🆘 Lỗi thường gặp

| Lỗi / hiện tượng | Nguyên nhân | Cách sửa |
|---|---|---|
| Push báo `rejected` / `fetch first` | Trên GitHub có thay đổi chưa kéo về | `git pull --rebase` rồi `git push` |
| GitHub không thấy commit mới | Chưa push, hoặc nhìn nhầm nhánh | Chạy `git push`; kiểm tra đang ở nhánh `main`; refresh trang |
| `git diff` không thấy gì | File chưa được lưu | Lưu file (`Ctrl + S`) rồi kiểm tra lại |
| Commit xong nhưng `git status` vẫn còn file | File nằm trong `.gitignore` | Bình thường với `node_modules/`, `.env`... |
| Không đăng nhập được GitHub trên web | Quên mật khẩu / mất 2FA | Dùng recovery codes hoặc khôi phục qua email |

---

## 🏁 Hoàn thành

- [ ] Đã push lần 2 thành công
- [ ] Đã cập nhật `CHECKLIST.md`

> 👉 Quay lại [README.md](../../README.md) để tiếp tục lộ trình.
