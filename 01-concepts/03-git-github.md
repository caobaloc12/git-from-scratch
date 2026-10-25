# Git & GitHub

## Git là gì? GitHub là gì?

- **Git**: hệ thống quản lý phiên bản — lưu lại mọi thay đổi của code **ở máy bạn**.
- **GitHub**: nơi lưu repo Git **trên cloud**, để backup, chia sẻ, làm việc nhóm, làm "CV" cho dev.

## Mô hình 3 vùng

```
Working Directory  →  Staging Area  →  Repository (commit)
   (sửa file)         (git add)        (git commit)
```

Hiểu 3 vùng này là hiểu 80% Git.

## Lệnh cần thuộc

```bash
# Cấu hình 1 lần
git config --global user.name "Ten"
git config --global user.email "email@example.com"

# Khởi tạo & lưu
git init
git status                 # xem trạng thái
git add <file>             # đưa vào staging (git add . = tất cả)
git commit -m "message"    # lưu lại 1 mốc

# Làm việc với remote
git remote add origin <url>
git push -u origin main
git pull

# Branch
git branch                 # liệt kê
git switch -c ten-branch   # tạo & chuyển branch
git switch main
git merge ten-branch
```

## Quy tắc thực hành

1. **Commit nhỏ, message rõ**: `feat: thêm trang login` > `update`.
2. **Commit thường xuyên** — mỗi lần làm xong 1 việc nhỏ.
3. **Không commit file `.env`, `node_modules`** (đã có `.gitignore`).
4. **Luôn `git status` trước khi commit** để biết mình đang làm gì.

## Conflict là gì?

Khi 2 branch sửa cùng 1 dòng → Git không biết chọn cái nào → báo conflict.
Giải quyết: mở file, chọn phần giữ lại, xóa dấu `<<<<<<<`, `=======`, `>>>>>>>`, rồi `add` + `commit`.

> 📌 **Chưa có tài khoản GitHub hoặc chưa từng push code?**
> → Mở thư mục `03b-github-setup/`, đọc `README.md` trước, rồi làm theo từng chặng.
