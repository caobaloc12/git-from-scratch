# Bài thực hành: Terminal

Làm tay từng bước trong terminal. Gõ lệnh, không dùng chuột.

> 🪟 **Windows:** làm toàn bộ bài trong **Git Bash** (cài kèm Git for Windows). Không dùng Command Prompt (`cmd`).

## Bài 1 — Điều hướng
1. Mở terminal, gõ `pwd` → ghi lại đường dẫn.
2. `cd ~` → `ls -la`.
3. Tạo thư mục `drill` trong Workspace: `mkdir -p ~/Workspace/drill`.
4. `cd ~/Workspace/drill` → `pwd` xác nhận.

> 🪟 **Windows:** `~` = `C:\Users\<tên-bạn>` → thư mục thật là `C:\Users\<tên-bạn>\Workspace\drill`.
> (Dùng Workspace thay vì Desktop để tránh trường hợp OneDrive đã chuyển hướng thư mục Desktop.)

## Bài 2 — Tạo / xóa file
1. `touch note.txt`
2. `echo "xin chao" > note.txt`
3. `cat note.txt`
4. `mv note.txt note2.txt`
5. `cp note2.txt note3.txt`
6. `ls`
7. `rm note3.txt` → `ls` lại xác nhận.

## Bài 3 — Đường dẫn tương đối
1. Trong `drill`, tạo `mkdir sub && cd sub`.
2. `touch a.txt` → quay lại bằng `cd ..`.
3. Xem file bằng đường dẫn: `cat sub/a.txt`.
4. Xóa cả thư mục: `rm -r sub`.

## Bài 4 — Thử phá (an toàn)
1. Cố `cd` vào thư mục không tồn tại → đọc lỗi.
2. Cố `cat` file không tồn tại → đọc lỗi.
3. Không tồn tại = đọc lỗi. Hiểu lỗi = không sợ lỗi.

> ✅ Xong: ghi lại 5 lệnh bạn thấy dùng nhiều nhất vào đây rồi commit.
