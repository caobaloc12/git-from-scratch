# Chặng 1 — Cài Git trên máy

**Mục tiêu:** cài Git và mở được **Git Bash** (Windows) / **Terminal** (macOS, Linux).
**Thời lượng:** 10–15 phút.

> 🧠 Chỉ cần cài **một lần**. Cài xong, `git --version` phải chạy được.
> 🪟 **Windows:** cài **Git for Windows** — bộ cài này kèm luôn **Git Bash**, terminal dùng xuyên suốt khóa học.

---

## Windows

### Bước 1.1 — Tải bộ cài

1. Mở trình duyệt → vào [git-scm.com/download/win](https://git-scm.com/download/win).
2. Bấm **Click here to download** (bản 64-bit).

👁️ File tải về có dạng `Git-2.xx.x-64-bit.exe`.

> ⚠️ Chỉ tải từ `git-scm.com`. Không tải từ trang lạ.

### Bước 1.2 — Chạy bộ cài

1. Mở file vừa tải → bấm **Yes** nếu Windows hỏi quyền.
2. Bấm **Next** qua các bước, **giữ nguyên lựa chọn mặc định**.
   - Riêng bước **Default editor**: nếu đã có VS Code, có thể chọn **Use Visual Studio Code as Git's default editor**. Chưa có thì để mặc định (Vim) — không sao.
3. Bước **Adjusting your PATH**: giữ **Git from the command line and also from 3rd-party software**.
4. Bấm **Install** → **Finish**.

👁️ Sau khi cài, menu Start có thư mục **Git** chứa **Git Bash**.

### Bước 1.3 — Mở Git Bash và kiểm tra

1. Start → gõ `Git Bash` → Enter.
2. Gõ:

```bash
git --version
```

👁️ In ra `git version 2.xx.x.windows.x` → đúng.

### Bước 1.4 — Chọn Git Bash làm terminal mặc định trong VS Code

> Làm sau khi đã cài VS Code (đọc `02-vscode.md`). Chưa cài thì bỏ qua bước này.

1. Mở VS Code → `` Ctrl + ` `` để mở terminal.
2. Bấm dấu `∨` cạnh nút `+` → **Select Default Profile** → chọn **Git Bash**.
3. Đóng terminal và mở lại → terminal mới là Git Bash.

---

## macOS

### Bước 1.1 — Kiểm tra Git có sẵn chưa

Mở **Terminal** → gõ:

```bash
git --version
```

👁️ Nếu thấy `git version 2.xx.x` → đã có Git, sang Chặng 2.
👁️ Nếu macOS hiện hộp thoại cài **Command Line Tools** → bấm **Install**, đợi cài xong rồi chạy lại `git --version`.

### Bước 1.2 — (Nếu cần) Cài bằng Homebrew

```bash
brew install git
git --version
```

> 🆘 Chưa có Homebrew? Xem [brew.sh](https://brew.sh) hoặc dùng cách cài Command Line Tools ở trên.

---

## Linux (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install git -y
git --version
```

> Fedora/CentOS: `sudo dnf install git -y`.

---

## ✅ Checkpoint

- [ ] `git --version` in ra số phiên bản, không báo lỗi
- [ ] Windows: mở được **Git Bash** từ Start

---

## 🆘 Lỗi thường gặp

| Lỗi / hiện tượng | Nguyên nhân | Cách sửa |
|---|---|---|
| `git: command not found` | Chưa cài Git, hoặc terminal mở trước khi cài | Cài Git → **đóng hết terminal** → mở lại Git Bash |
| Windows không thấy Git Bash | Bộ cài thiếu thành phần | Chạy lại bộ cài Git for Windows, giữ lựa chọn mặc định |
| macOS báo `xcrun: error: invalid active developer path` | Thiếu Command Line Tools | `xcode-select --install` |
| `Permission denied` khi cài trên Linux | Thiếu `sudo` | Thêm `sudo` trước lệnh cài |
| Cài xong nhưng VS Code vẫn mở PowerShell | Chưa đổi default profile | Làm Bước 1.4 |

---

## 🏁 Khi nào sang Chặng 2?

- [ ] `git --version` chạy được
- [ ] Windows: đã mở được Git Bash

> 👉 Xong → mở file [chang-2-khai-bao-git.md](chang-2-khai-bao-git.md).
