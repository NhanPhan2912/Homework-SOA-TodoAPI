# Minimal API với ASP.NET Core và Cơ sở Dữ liệu In-Memory

## Tổng quan
Dự án này minh họa cách tạo một Minimal API bằng ASP.NET Core, với mục tiêu tối giản hóa cấu hình và giảm thiểu phụ thuộc. API sử dụng cơ sở dữ liệu In-Memory để thực hiện các thao tác CRUD (Tạo, Đọc, Cập nhật, Xóa) trên danh sách công việc cần làm (To-Do List). Đây là một lựa chọn lý tưởng cho các microservices hoặc ứng dụng yêu cầu tốc độ cao và cấu hình nhẹ.

## Cấu trúc Dự án

### `Program.cs`
- Chứa toàn bộ logic chính của ứng dụng.
- Định nghĩa các endpoint của API cho các thao tác CRUD.
- Cấu hình cơ sở dữ liệu In-Memory và tích hợp các dịch vụ cần thiết.

### `Models`
- **Todo.cs**: Định nghĩa cấu trúc của một công việc với các thuộc tính sau:
  - `Id`: Định danh duy nhất của công việc.
  - `Name`: Tên của công việc.
  - `IsComplete`: Trạng thái hoàn thành của công việc.

- **TodoDb.cs**: Định nghĩa lớp database context, sử dụng Entity Framework Core để quản lý dữ liệu.

### Các Endpoint
API này định nghĩa các endpoint trực tiếp trong `Program.cs`, với các thao tác CRUD tương ứng như sau:

- **GET `/todoitems`**: Lấy tất cả các công việc từ cơ sở dữ liệu In-Memory.
- **GET `/todoitems/complete`**: Lấy danh sách các công việc đã hoàn thành.
- **GET `/todoitems/{id}`**: Lấy thông tin chi tiết của một công việc dựa trên ID.
- **POST `/todoitems`**: Thêm một công việc mới vào danh sách.
- **PUT `/todoitems/{id}`**: Cập nhật thông tin của công việc đã tồn tại, được xác định bởi ID.
- **DELETE `/todoitems/{id}`**: Xóa công việc khỏi danh sách theo ID.

## Các Tính Năng

- **Kiến trúc Minimal API**: Dự án sử dụng cấu trúc đơn giản, giảm thiểu tối đa các phụ thuộc, giúp ứng dụng nhẹ và nhanh chóng.
- **Cơ sở Dữ liệu In-Memory**: Dữ liệu được lưu trữ trong bộ nhớ tạm thời, không yêu cầu cài đặt cơ sở dữ liệu phức tạp.
- **Entity Framework Core**: Hỗ trợ truy vấn và thao tác dữ liệu hiệu quả thông qua các phương thức của DbContext.
- **Swagger UI**: Tự động tài liệu hóa API và cung cấp giao diện dễ sử dụng để thử nghiệm các endpoint.
- **Dễ Dàng Thử Nghiệm và Học Hỏi**: Phù hợp cho các dự án thử nghiệm hoặc học tập về cách hoạt động của Minimal API.

## Kết quả đạt được
- Triển khai thành công một Minimal API với cấu trúc gọn gàng và dễ hiểu.
- Tích hợp cơ sở dữ liệu In-Memory để lưu trữ tạm thời mà không cần cài đặt thêm bất kỳ phần mềm nào.
- Tích hợp Swagger UI để dễ dàng kiểm tra và thử nghiệm các endpoint của API.
- Cấu trúc đơn giản, dễ duy trì và mở rộng cho các dự án trong tương lai.

