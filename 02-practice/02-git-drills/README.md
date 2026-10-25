# Bài thực hành: Git

Làm trên chính repo `git-from-scratch` này.

> 🪟 **Windows:** dùng **Git Bash** cho mọi lệnh trong bài. Không dùng Command Prompt (`cmd`).

## Bài 1 — Commit đầu tiên
1. `git status` → xem có gì chưa tracked.
2. `git add .`
3. `git commit -m "chore: khởi tạo repo phase 0"`
4. `git log --oneline` → xem lịch sử.

## Bài 2 — Sửa & commit
1. Mở `02-practice/03-sandbox/hello.txt`, sửa nội dung.
2. `git diff` → xem thay đổi.
3. `git add` + commit với message rõ ràng.

## Bài 3 — Branch & merge
1. `git switch -c practice-branch`
2. Thêm 1 file mới (bất kỳ), commit.
3. `git switch main`
4. `git merge practice-branch`
5. Xóa branch: `git branch -d practice-branch`.

## Bài 4 — Push lên GitHub
1. Tạo repo trống trên GitHub (không tick README).
2. `git remote add origin <url>`
3. `git push -u origin main`
4. Lên GitHub xác nhận code đã lên.

## Bài 5 — Thử conflict (nâng cao)
1. Trên `main`, sửa dòng 1 của `hello.txt`, commit.
2. Tạo branch mới từ commit trước đó, sửa **cùng dòng 1**, commit.
3. Merge → Git báo conflict.
4. Giải quyết conflict, `add`, `commit`.

> ✅ Xong: repo này trên GitHub phải có ≥ 5 commit + ≥ 1 branch đã merge.
