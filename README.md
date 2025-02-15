# Github Automated-Commit


Kho lưu trữ này chứa một quy trình GitHub Actions tự động cập nhật tệp có tên `TIMESTAMP.txt` với ngày và giờ hiện tại sau mỗi 12 giờ. 
README này cung cấp cái nhìn tổng quan chi tiết về cách hoạt động của quy trình và hướng dẫn bạn tùy chỉnh và sử dụng nó.
Đặc biệt nếu bạn mới làm quen với GitHub hoặc GitHub Actions.

## Tổng quan  

Quy trình `Automated-Commit` minh họa khả năng của GitHub Actions trong việc tự động hóa các tác vụ định kỳ trong kho lưu trữ. 

Cụ thể, quy trình này:  
- Lấy mã nguồn mới nhất từ nhánh `master`.  
- Cập nhật tệp `TIMESTAMP.txt` với ngày và giờ hiện tại.  
- Thực hiện commit thay đổi vào kho lưu trữ nếu phát hiện có sự chỉnh sửa.  
- Đẩy các thay đổi lên nhánh `master`.  

## Cấu trúc quy trình  
Quy trình này được định nghĩa trong tệp `.github/workflows/master.yml` và bao gồm:  
- **Trigger**: Được cấu hình để chạy mỗi 12 giờ và có thể kích hoạt thủ công qua giao diện GitHub bằng sự kiện `workflow_dispatch`.  
- **Công việc và các bước**: Chứa một công việc `update_commit` chạy trên môi trường Ubuntu mới nhất, thực hiện các tác vụ như thiết lập Git, cập nhật `TIMESTAMP.txt`, commit và đẩy thay đổi.  
- **Quyền hạn**: Được cấp quyền ghi vào nội dung kho lưu trữ.  

## Hướng dẫn sử dụng  

### Tạo phiên bản của riêng bạn  

Để tạo phiên bản riêng của kho lưu trữ và quy trình này:

Truy cập link: https://github.com/dante4rt/automated-commit  

1. Nhấn vào nút "Use this template" trên trang kho lưu trữ GitHub (Góc trên bên phải).  
2. Chọn "Create new repository".  
3. Tick chọn "Include all branches"
4. Đặt tên cho Repository name
5. Chọn Private > Create Repository

### Tùy chỉnh quy trình  

Trước khi sử dụng quy trình, bạn cần tùy chỉnh email và tên người dùng GitHub của mình:  

1. Điều hướng đến tệp `.github/workflows/master.yml` trong kho lưu trữ của vừa clone về.  
2. Chỉnh sửa tệp, thay `"rxmxdhxni@gmail.com"` bằng email của bạn và `"dante4rt"` bằng tên người dùng GitHub của bạn trong bước `Setup Git Configuration`.  
3. Commit các thay đổi.  


### Xem lịch sử chạy quy trình  

Để xem lịch sử chạy của quy trình:  

1. Điều hướng đến tab `Actions` trong kho lưu trữ của bạn.  
2. Chọn quy trình `Automated-Commit` để xem chi tiết từng lần chạy.  


### Kích hoạt quy trình thủ công  

Bạn có thể kích hoạt quy trình thủ công bằng cách dưới đây để kiểm tra code có hoạt động hay không

1. Đi tới tab `Actions` trong kho lưu trữ của bạn.  
2. Chọn quy trình `Automated-Commit`.  
3. Nhấn `Run workflow`, chọn `master`, sau đó nhấn `Run workflow` lần nữa và chờ trong khoảng 1 phút
