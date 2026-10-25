# Chặng 6 — Push code lần đầu

**Mục tiêu:** đưa thư mục `git-from-scratch` từ máy lên GitHub.
**Thời lượng:** 10 phút.

> 🪟 **Windows:** dùng **Git Bash**. macOS/Linux: Terminal.
> 🧠 Làm đúng thứ tự: `init` → `add` → `commit` → `remote` → `push`.

---

## Bước 6.1 — Đứng trong thư mục dự án

```bash
cd ~/Workspace/github/git-from-scratch
pwd
```

👁️ Đường dẫn **kết thúc bằng** `/git-from-scratch`.
> Không thấy thư mục? Quay lại Chặng 0 — Bước 0.4.

## Bước 6.2 — Khởi tạo Git (nếu chưa có)

```bash
git status
```

- 👁️ Nếu thấy `not a git repository` → chạy:

  ```bash
  git init
  ```

  👁️ Thấy `Initialized empty Git repository in ...`.

- 👁️ Nếu thấy danh sách file → repo đã có Git, sang Bước 6.3.

> ℹ️ Tải ZIP từ GitHub thì **không có** thư mục `.git`, nên phải `git init`.

## Bước 6.3 — Commit đầu tiên

```bash
git add .
git commit -m "chore: khởi tạo repo phase 0"
```

👁️ Thấy danh sách file và dòng `... files changed`.

> 🆘 Nếu báo thiếu `user.name` / `user.email` → quay lại Chặng 2.

## Bước 6.4 — Nối repo local với GitHub

Dùng URL SSH đã copy ở Chặng 5:

```bash
git remote add origin git@github.com:<username>/git-from-scratch.git
git remote -v
```

👁️ Thấy 2 dòng `origin  git@github.com:... (fetch)` và `(push)`.

- Nếu báo `remote origin already exists`:

  ```bash
  git remote set-url origin git@github.com:<username>/git-from-scratch.git
  ```

## Bước 6.5 — Đảm bảo nhánh tên `main`

```bash
git branch --show-current
```

👁️ Nếu in ra `main` → bỏ qua.
👁️ Nếu in ra `master` (hoặc tên khác) → đổi tên:

```bash
git branch -M main
```

## Bước 6.6 — Push

```bash
git push -u origin main
```

Lần đầu có thể hỏi:

```
The authenticity of host 'github.com (...)' can't be established.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

→ Gõ `yes`.

👁️ Kết quả đúng có dạng:

```
Enumerating objects: ...
Writing objects: 100% ...
To github.com:<username>/git-from-scratch.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
```

## Bước 6.7 — Kiểm tra trên GitHub

1. Mở lại trang repo → bấm **F5**.
2. 👁️ Thấy đủ file: `README.md`, `CHECKLIST.md`, `01-concepts`, `02-practice`.
3. 👁️ Thấy dòng `1 commit` và nhánh `main`.

```bash
git status
```

👁️ `Your branch is up to date with 'origin/main'.` và `nothing to commit, working tree clean`.

---

## ✅ Checkpoint

- [ ] Repo trên GitHub có file
- [ ] Có ít nhất 1 commit
- [ ] `git status` báo up to date với `origin/main`

---

## 🆘 Lỗi thường gặp

| Lỗi / hiện tượng | Nguyên nhân | Cách sửa |
|---|---|---|
| `not a git repository` | Chưa `git init` | Chạy `git init` (Bước 6.2) |
| `Author identity unknown` | Chưa cấu hình tên/email | Làm Chặng 2 |
| `Permission denied (publickey)` | SSH chưa đúng | Làm lại Chặng 4; kiểm tra `ssh -T git@github.com` |
| `remote origin already exists` | Đã add remote trước đó | `git remote set-url origin <url-ssh>` |
| `src refspec main does not match any` | Chưa có commit, hoặc nhánh chưa tên `main` | Kiểm tra `git log --oneline`; chạy `git branch -M main` rồi push lại |
| `Updates were rejected... fetch first` | Repo trên GitHub có file (thường do tick README) | Cách sạch nhất: xóa repo, tạo lại **trống** (Chặng 5) rồi push lại |
| `Repository not found` | Sai URL/username, hoặc chưa có quyền | `git remote -v` kiểm tra URL; sửa bằng `git remote set-url` |
| `Could not read from remote repository` | Sai URL hoặc SSH lỗi | Kiểm tra URL; chạy `ssh -T git@github.com` |

---

## 🏁 Khi nào sang Chặng 7?

- [ ] Code đã lên GitHub
- [ ] `git status` sạch và up to date

> 👉 Xong → mở file [chang-7-kiem-tra.md](chang-7-kiem-tra.md).
