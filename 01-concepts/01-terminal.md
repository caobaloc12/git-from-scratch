# Terminal / Command Line

## Vì sao?

90% công cụ lập trình (git, npm, build...) chạy bằng CLI. Biết terminal = không sợ môi trường.

> 🪟 **Windows:** mở **Git Bash** (cài kèm [Git for Windows](https://git-scm.com/download/win)) để dùng đúng các lệnh bên dưới.
> Command Prompt (`cmd`) **không hiểu** `~`, `ls`, `touch`...; PowerShell hiểu `~` nhưng không có `touch`.

## Khái niệm cần hiểu

- **Working directory**: thư mục hiện tại terminal đang đứng.
- **Absolute path** vs **relative path**:
  - macOS/Linux: `/Users/ten/du-an` hoặc `/home/ten/du-an` (tuyệt đối)
  - Windows (Git Bash): `/c/Users/ten/du-an`, ứng với `C:\Users\ten\du-an`
  - `./du-an` hoặc `../` (tương đối)
- **Root** `/`, **home** `~`.
  - Windows (Git Bash): `~` = `C:\Users\<tên-bạn>`

## Lệnh cần thuộc

| Lệnh | Ý nghĩa |
|---|---|
| `pwd` | Xem đang đứng ở thư mục nào |
| `ls` / `ls -la` | Liệt kê file (kể cả file ẩn) |
| `cd <path>` | Di chuyển |
| `cd ..` | Lên 1 cấp |
| `mkdir <name>` | Tạo thư mục |
| `touch <file>` | Tạo file rỗng |
| `rm <file>` | Xóa file (⚠️ không có thùng rác) |
| `mv <a> <b>` | Di chuyển / đổi tên |
| `cp <a> <b>` | Sao chép |
| `cat <file>` | Xem nội dung file |
| `clear` | Xóa màn hình |
| `history` | Xem lệnh đã gõ |

> 💡 Mẹo: nhấn `Tab` để tự động hoàn thành tên file/thư mục. Dùng `↑` để lấy lại lệnh trước.
