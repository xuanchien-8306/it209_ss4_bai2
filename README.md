# BÁO CÁO GIẢI QUYẾT MERGE CONFLICT

## 1. Mục tiêu

Thực hiện tạo Merge Conflict giữa hai nhánh `main` và `feature-update`, sau đó xử lý xung đột thủ công trong file `README.md`.

## 2. Các bước thực hiện

### Bước 1: Tạo nhánh feature-update

Từ nhánh `main`, tạo nhánh mới:

```bash
git switch -c feature-update
```

Sau đó chỉnh sửa file `README.md` và commit:

```bash
git add README.md
git commit -m "update"
```

### Bước 2: Cập nhật nhánh main

Chuyển về nhánh `main`:

```bash
git switch main
```

Tiếp tục chỉnh sửa cùng dòng trong file `README.md` nhưng sử dụng nội dung khác.

Commit thay đổi:

```bash
git add README.md
git commit -m "update main"
```

### Bước 3: Tạo Merge Conflict

Thực hiện merge nhánh `feature-update` vào `main`:

```bash
git merge feature-update
```

Git phát hiện xung đột trong file `README.md`.

### Bước 4: Giải quyết xung đột thủ công

Mở file `README.md` và tìm các ký hiệu:

```text
<<<<<<< HEAD
=======
>>>>>>> feature-update
```

Xóa các ký hiệu đánh dấu xung đột và chỉnh sửa nội dung thành phiên bản mong muốn.

Sau khi sửa xong, lưu lại file `README.md`.

### Bước 5: Hoàn thành Merge

Đưa file đã giải quyết xung đột vào vùng staging:

```bash
git add README.md
```

Tạo merge commit:

```bash
git commit -m "merge feature-update and resolve conflict"
```

### Bước 6: Kiểm tra lịch sử commit

Sử dụng lệnh:

```bash
git log --graph --oneline --all
```

Kết quả cho thấy nhánh `feature-update` và `main` có các commit riêng, sau đó được gộp lại bằng một merge commit.

## 3. Kết quả

Merge Conflict trong file `README.md` đã được xử lý thủ công thành công. Các ký hiệu `<<<<<<<`, `=======`, `>>>>>>>` đã được xóa và lịch sử commit hiển thị đúng dạng nhánh bằng lệnh `git log --graph --oneline --all`.

