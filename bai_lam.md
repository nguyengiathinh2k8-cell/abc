# BÀI LÀM –(CHỦ ĐỀ QUẢN LÝ MODEL AI)

- **Mã đề:**
- **Họ tên:Nguyễn Gia Thịnh **
- **Lớp:CNTT1**
- **Link repository:**
- **Hệ điều hành (Windows/macOS):Windows**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
1. pwd
2. get-childitem -force
3. mv tai_lieu_ban_giao.txt docs
4. mkdir bacup
5. cp data/chi_phi_model_thang_11.xlsx bacup
6. rm  model_cache_01.tmp
7. get-childitem -force.
8. cd ".\logs"
9.  Get-Content .\inference.log
10. cd..
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text

    Directory: C:\Users\admin\Downloads\MiniPrjoect\MiniPrjoect\starter-kit\qua
    n-ly-model-ai


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-r---        11/10/2026   2:54 PM                bacup
d-r---        11/10/2026   2:36 PM                data
d-r---        11/10/2026   2:45 PM                docs
d-r---        11/10/2026   2:35 PM                evidence
d-r---        11/10/2026  11:37 PM                logs
d-r---        11/10/2026  12:51 PM                web
-a----        11/10/2026  12:51 PM             96 .env
-a----        11/10/2026  11:38 PM           2852 bai_lam.md


    Directory: C:\Users\admin\Downloads\MiniPrjoect\MiniPrjoect\starter-kit\qua
    n-ly-model-ai\bacup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026  12:51 PM           5815 chi_phi_model_thang_11.xlsx


    Directory: C:\Users\admin\Downloads\MiniPrjoect\MiniPrjoect\starter-kit\qua
    n-ly-model-ai\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026  12:51 PM           5815 chi_phi_model_thang_11.xlsx


    Directory: C:\Users\admin\Downloads\MiniPrjoect\MiniPrjoect\starter-kit\qua
    n-ly-model-ai\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026  12:51 PM            204 tai_lieu_ban_giao.txt


    Directory: C:\Users\admin\Downloads\MiniPrjoect\MiniPrjoect\starter-kit\qua
    n-ly-model-ai\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026  12:51 PM           1234 inference.log
-a----        11/10/2026  11:37 PM            846 loi_model.txt


    Directory: C:\Users\admin\Downloads\MiniPrjoect\MiniPrjoect\starter-kit\qua
    n-ly-model-ai\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-r---        11/10/2026  12:51 PM                images
-a----        11/10/2026  12:51 PM            644 app.js
-a----        11/10/2026  12:51 PM            567 index.html
-a----        11/10/2026  12:51 PM            460 style.css


    Directory: C:\Users\admin\Downloads\MiniPrjoect\MiniPrjoect\starter-kit\qua
    n-ly-model-ai\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026  12:51 PM            339 logo-ai-hub.png

```

## 4.3. Lọc log vận hành Model AI

### a) Lệnh lọc các dòng ERROR

```shell

Get-Content ".\logs\inference.log" | Select-String "ERROR" > ".\logs\loi_model.txt"

```

### 2 dòng đầu tiên trong logs/loi_model.txt

```text
2026-11-10 08:27:45 ERROR POST /v1/chat/completions model=CLAUDE-35
2026-11-10 08:31:12 ERROR POST /v1/audio/transcriptions model=WHISPER-V3


```

### b) Lệnh đếm số dòng WARNING và kết quả

```shell
(Get-Content ".\logs\inference.log" | Select-String "warning").count

```

```text
5

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
 .\tong_hop.ps1

```

### Nội dung file logs/tong_hop.txt

```text
=== BAO CAO VAN HANH MODEL AI ===

2026-11-10 08:09:18 WARNING POST /v1/embeddings model=LLAMA-2-OLD
2026-11-10 08:16:05 WARNING GET /v1/fine-tune/jobs-legacy
2026-11-10 08:38:29 WARNING GET /images/model-card-v1.png
2026-11-10 09:01:44 WARNING POST /v1/completions model=DAVINCI-002
2026-11-10 09:14:02 WARNING GET /v1/quota/expired-key




Count    : 6
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property : 





```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [ ] README.md: Heading 1, hình ảnh (`![Alt](path)`), mô tả có **in đậm**, _in nghiêng_ và `inline code`, bảng, code block, task list, blockquote
- [ ] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [ ] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | -------------------------- | --------------------------- | -------------- |
| 1   |                network            |sai định dạng                             |       sửa lại  cho đúng định dạng         |
| 2   |            console                |hienThiBangModel is not defined                             | sửa lại lỗi ở dòng 18 hienThiBangModel thành hienThiBangModelAI                 |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context: hiện tại tôi chưa học về jv và fix lỗi của ưed bao giờ**
- **Expected: mong muốn có đủ dữ liệu ở bảng**
- **Actual:bảng đnag không hiển thị và vào console đang báo lỗi **
- **Log:hienThiBangModel is not defined  **

### Câu tìm kiếm Google

```text
site:stackoverflow.com "is not defined"

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/chi_phi_model_thang_11.xlsx`, không cần ghi vào đây.
