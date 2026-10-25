# Chặng 4 — Tạo SSH key

**Mục tiêu:** máy bạn được GitHub "tin tưởng" để push code mà không phải nhập mật khẩu mỗi lần.
**Thời lượng:** 15–20 phút.

> 🧠 SSH key gồm **2 file**:
> - `id_ed25519` — **private key**: bí mật, **không bao giờ** gửi cho ai.
> - `id_ed25519.pub` — **public key**: đăng lên GitHub.
>
> 🪟 **Windows:** làm toàn bộ trong **Git Bash** (không dùng `cmd`). Git Bash có sẵn `ssh-keygen` và `ssh`.

---

## Vì sao dùng SSH key?

> 🏠 **Ẩn dụ: ổ khóa và chìa khóa.**
>
> Hãy tưởng tượng GitHub là căn nhà kho chứa code, còn bạn giữ **một chiếc chìa khóa duy nhất**.
>
> - **Public key** giống như **ổ khóa** bạn gắn lên cửa nhà GitHub. Ai nhìn thấy ổ khóa cũng không sao — chỉ nhìn ổ khóa thì không mở được cửa.
> - **Private key** là **chìa khóa** bạn giữ trong túi (máy tính của bạn). Không đưa cho ai, không đăng lên mạng.
>
> Mỗi lần push, GitHub không hỏi mật khẩu. Nó đưa ra một "chiếc hộp đã khóa" bằng ổ khóa của bạn; bạn mở hộp bằng chìa khóa riêng và trả lời đúng. GitHub kiểm tra bằng ổ khóa công khai → biết chắc là bạn. **Chìa khóa riêng không bao giờ rời khỏi máy bạn.**
>
> So với mật khẩu/token:
> - Mật khẩu là **câu thần chú dùng chung**: ai nghe lén hoặc lấy được là dùng được.
> - Private key là **chìa khóa vật lý trong túi**: không gửi qua mạng, nên không thể bị đánh cắp trên đường truyền.
> - Dùng SSH còn giúp push **không phải nhập mật khẩu** mỗi lần.
>
> 💡 Tạo key **một lần**, sau đó dùng lại cho mọi repo trên máy.
>
> ℹ️ GitHub đã bỏ xác thực Git bằng mật khẩu tài khoản từ 2021. Nếu dùng HTTPS, bạn phải tạo **Personal Access Token (PAT)** — token cũng là một "mật khẩu" cần bảo vệ. SSH key tránh được việc phải lưu token trong máy.

---

## Bước 4.1 — Kiểm tra đã có key chưa

```bash
ls -la ~/.ssh
```

👁️ Nếu thấy `id_ed25519` và `id_ed25519.pub` → đã có key, sang Bước 4.3.
👁️ Nếu báo `No such file or directory` → chưa có, làm Bước 4.2.

## Bước 4.2 — Tạo key

```bash
ssh-keygen -t ed25519 -C "email@example.com"
```

- **Enter file in which to save the key**: bấm **Enter** (dùng mặc định `~/.ssh/id_ed25519`).
- **Enter passphrase**: bấm **Enter** (để trống) → **Enter** lần nữa.

> Học viên mới nên để trống passphrase cho đơn giản. Khi quen, có thể tạo lại key có passphrase.

👁️ Kết quả có dạng:

```
Your identification has been saved in /c/Users/ten-ban/.ssh/id_ed25519
Your public key has been saved in /c/Users/ten-ban/.ssh/id_ed25519.pub
```

## Bước 4.3 — Thêm key vào ssh-agent

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

👁️ Thấy `Agent pid ...` và `Identity added: ...`.

> Key không có passphrase thường vẫn dùng được nếu bỏ qua bước này, nhưng cứ chạy — không hại.

## Bước 4.4 — Copy **public key**

**Windows (Git Bash):**

```bash
cat ~/.ssh/id_ed25519.pub | clip
```

**macOS:**

```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

**Linux:**

```bash
xclip -selection clipboard < ~/.ssh/id_ed25519.pub
# Không có xclip: cat ~/.ssh/id_ed25519.pub → bôi đen và copy
```

> ⚠️ Chỉ copy file **`.pub`**. Tuyệt đối không copy `id_ed25519` (private key).
> 👁️ Nội dung key bắt đầu bằng `ssh-ed25519 AAAAC3...` và kết thúc bằng email của bạn.

## Bước 4.5 — Dán key lên GitHub

1. Vào [github.com/settings/keys](https://github.com/settings/keys).
2. Bấm **New SSH key**.
3. **Title**: đặt tên máy, ví dụ `Laptop Windows - Git Bash`.
4. **Key type**: **Authentication Key**.
5. **Key**: dán nội dung vừa copy.
6. Bấm **Add SSH key** (có thể hỏi lại mật khẩu/2FA).

👁️ Danh sách key hiện key vừa thêm.

## Bước 4.6 — Kiểm tra kết nối

```bash
ssh -T git@github.com
```

Lần đầu sẽ hỏi:

```
The authenticity of host 'github.com (...)' can't be established.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

→ Gõ `yes` → Enter.

👁️ Kết quả đúng:

```
Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.
```

> 🎉 Thấy `Hi <username>!` là thành công. Câu "does not provide shell access" là bình thường.

---

## ✅ Checkpoint

- [ ] Trong `~/.ssh` có `id_ed25519` và `id_ed25519.pub`
- [ ] Key đã xuất hiện trên GitHub → Settings → SSH and GPG keys
- [ ] `ssh -T git@github.com` in ra `Hi <username>!`

---

## 🆘 Lỗi thường gặp

| Lỗi / hiện tượng | Nguyên nhân | Cách sửa |
|---|---|---|
| `Permission denied (publickey)` | Key chưa thêm lên GitHub, hoặc dán nhầm private key | Kiểm tra key trên GitHub; copy đúng file `.pub`; chạy `ssh-add ~/.ssh/id_ed25519` |
| `ssh: command not found` (Windows) | Đang dùng `cmd`, hoặc bản Git thiếu OpenSSH | Dùng **Git Bash**; cài lại Git for Windows, chọn **Use bundled OpenSSH** |
| `Host key verification failed` | `known_hosts` cũ hoặc đổi host key | `ssh-keygen -R github.com` rồi thử lại |
| `Warning: unprotected private key file` (macOS/Linux) | Quyền file quá mở | `chmod 600 ~/.ssh/id_ed25519` |
| `Connection timed out` | Mạng/firewall chặn port 22 | Thử `ssh -T -p 443 git@ssh.github.com` |
| Hỏi passphrase mỗi lần | Key có passphrase, agent chưa giữ | `eval "$(ssh-agent -s)"` rồi `ssh-add ~/.ssh/id_ed25519` |

---

## 🏁 Khi nào sang Chặng 5?

- [ ] `ssh -T git@github.com` báo `Hi <username>!`

> 👉 Xong → mở file [chang-5-tao-repo.md](chang-5-tao-repo.md).
