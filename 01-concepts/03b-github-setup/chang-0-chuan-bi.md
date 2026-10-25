# Chặng 0 — Chuẩn bị trước khi cài Git

**Mục tiêu:** chuẩn bị môi trường và nắm đường đi, tránh bỡ ngỡ khi bắt đầu.
**Thời lượng:** 10–15 phút.

> 🧠 Chặng 0 **không cài gì cả**. Chỉ kiểm tra bạn đã "sẵn sàng" chưa.

---

## Bước 0.1 — Xác định hệ điều hành

| Bạn thấy | OS của bạn |
|---|---|
| Thanh Start góc trái dưới, có logo 4 ô vuông | **Windows** |
| Logo quả táo ở góc trái trên menu | **macOS** |
| Logo chim cánh cụt hoặc giao diện lạ | **Linux** |

Ghi nhớ OS vì các chặng sau sẽ có nhánh riêng cho từng OS.

---

## Bước 0.2 — Mở Terminal

**Windows:** Start → gõ `Git Bash`.
👁️ **Nếu thấy** Git Bash → mở nó (sẽ dùng suốt Chặng 1–7).
👁️ **Nếu KHÔNG thấy** → chưa có Git, tạm dùng **Command Prompt** (Start → `cmd`).

**macOS:** `Cmd + Space` → gõ `Terminal` → Enter.

**Ubuntu/Linux:** `Ctrl + Alt + T`.

---

## Bước 0.3 — Nắm 4 lệnh terminal cơ bản

```bash
pwd              # Xem đang đứng ở thư mục nào
ls               # Xem trong thư mục có gì
cd <tên thư mục> # Đi vào một thư mục
cd ..            # Lùi lên 1 cấp
```

### Bài tập nhỏ

Trong terminal, gõ **lần lượt** từng dòng (mỗi dòng Enter một lần):

```bash
pwd
```
👁️ In ra `.../Users/ten-ban` hoặc `/home/ten-ban` → đó là **thư mục nhà** (home). Đúng.

```bash
ls
```
👁️ Thấy danh sách `Desktop`, `Documents`, `Downloads`... → đúng.

```bash
cd Desktop
pwd
```
👁️ `pwd` bây giờ in ra đường dẫn **kết thúc bằng** `/Desktop`.

```bash
cd ..
pwd
```
👁️ Về lại home.

---

## ✅ Checkpoint A

Bạn đã dùng được `pwd`, `ls`, `cd`, `cd ..` mà **không phải nhờ ai**.

Chưa làm được → dừng lại, nhờ giảng viên / bạn bè hướng dẫn trực tiếp **trước khi sang Bước 0.4**.

---

## Bước 0.4 — Chuẩn bị thư mục dự án Phase 0

Chúng ta sẽ làm việc trong 1 thư mục tên `git-from-scratch`, đặt ở **Workspace** cho dễ tìm.

### Kiểm tra đã có chưa

```bash
ls ~/Workspace/github
```

👁️ Tìm tên `git-from-scratch` trong danh sách:
- ✅ **Đã có** → sang **Bước 0.5**.
- ⚠️ **Chưa có** → xem mục dưới.

### Nếu chưa có thư mục

**Cách 1 — Bạn được gửi file .zip:**
1. Giải nén file zip → được thư mục `git-from-scratch`.
2. Kéo thả thư mục đó vào `~/Workspace/github/`.

**Cách 2 — Bạn được gửi link GitHub:**
1. Mở link dạng `https://github.com/<username-giao-vien>/git-from-scratch`.
2. Bấm nút xanh **`<> Code`** (góc phải trên danh sách file).
3. Chọn **`Download ZIP`**.
4. Giải nén file vừa tải → kéo thả thư mục vào `~/Workspace/github/`.

> 🆘 **Không có file zip, cũng không có link?** → Liên hệ giảng viên/người phụ trách. **Không tự tạo thư mục trống** — vì sẽ thiếu các file hướng dẫn.

### Kiểm tra nội dung thư mục

```bash
ls ~/Workspace/github/git-from-scratch
```

👁️ Bạn **phải thấy**: `README.md`, `CHECKLIST.md`, `01-concepts`, `02-practice`. (File `.gitignore` là file ẩn — không hiện với `ls`, bình thường.)

---

## Bước 0.5 — Đứng đúng thư mục dự án

Từ Chặng 1 đến hết Chặng 7, terminal **phải đứng trong** thư mục này:

```bash
cd ~/Workspace/github/git-from-scratch
pwd
```

👁️ `pwd` phải in đường dẫn **kết thúc bằng** `/git-from-scratch`. Nếu không → `cd` lại.

```bash
ls
```

👁️ Phải thấy `README.md`, `01-concepts`, `02-practice`...

---

## ✅ Checkpoint B

Terminal đang đứng trong `git-from-scratch`. Đường dẫn `pwd` **kết thúc bằng** `/git-from-scratch`.

> ⚠️ Mỗi lần **mở terminal mới**, bạn phải `cd ~/Workspace/github/git-from-scratch` lại — Git chỉ làm việc khi đứng trong thư mục dự án.

---

## Bước 0.6 — Biết đường đi sắp tới

Bạn sẽ đi qua **7 chặng**, mỗi chặng có checkpoint riêng:

| Chặng | Việc chính | Kết quả kiểm tra được |
|---|---|---|
| 1 | Cài Git | `git --version` chạy được |
| 2 | Khai báo tên + email | `git config --list` có tên + email |
| 3 | Tạo tài khoản GitHub | Đăng nhập được `github.com` |
| 4 | Tạo SSH key | `ssh -T git@github.com` báo `Hi <username>!` |
| 5 | Tạo repo trống | Có URL `git@github.com:...` |
| 6 | Push lần đầu | Code lên GitHub |
| 7 | Kiểm tra | Thấy file trên trang GitHub + push lần 2 |

---

## 🏁 Khi nào sang Chặng 1?

Đạt **cả 2 checkpoint**:
- [ ] Checkpoint A — dùng được `pwd`, `ls`, `cd`
- [ ] Checkpoint B — terminal đang đứng trong `git-from-scratch`

> 👉 Xong → mở file [chang-1-cai-git.md](chang-1-cai-git.md).
