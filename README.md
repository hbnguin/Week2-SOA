
# Tổng hợp kết quả dự án

## 1. Giới thiệu chung
Dự án này xây dựng một **Minimal API** sử dụng .NET, với **In-Memory Database** được tích hợp để quản lý danh sách công việc (To-Do Items). API cung cấp các chức năng CRUD (Create, Read, Update, Delete) đơn giản và hiệu quả.

---

## 2. Kết quả chính

### Các chức năng chính của API
- **Thêm công việc mới** (POST):  
  Cho phép thêm công việc mới với các thông tin như tên (`Name`) và trạng thái hoàn thành (`IsComplete`).

- **Truy xuất danh sách công việc** (GET):  
  Lấy toàn bộ danh sách công việc hiện có từ cơ sở dữ liệu.

- **Lọc danh sách công việc đã hoàn thành** (GET):  
  Lấy các công việc có trạng thái `IsComplete = true`.

- **Xem chi tiết công việc** (GET):  
  Truy cập thông tin chi tiết của một công việc cụ thể dựa trên `Id`.

- **Cập nhật công việc** (PUT):  
  Chỉnh sửa tên (`Name`) hoặc trạng thái hoàn thành (`IsComplete`) của công việc.

- **Xóa công việc** (DELETE):  
  Xóa công việc khỏi danh sách dựa trên `Id` của công việc.

---

## 3. Danh sách Endpoint của API

| HTTP Method | Endpoint                      | Chức năng                                  |
|-------------|-------------------------------|--------------------------------------------|
| GET         | `/todoitems`                  | Lấy toàn bộ danh sách công việc.          |
| GET         | `/todoitems/complete`         | Lấy danh sách các công việc hoàn thành.   |
| GET         | `/todoitems/{id}`             | Xem chi tiết một công việc cụ thể.         |
| POST        | `/todoitems`                  | Thêm mới một công việc.                   |
| PUT         | `/todoitems/{id}`             | Cập nhật thông tin công việc.             |
| DELETE      | `/todoitems/{id}`             | Xóa một công việc theo `Id`.              |

---

## 4. Hướng dẫn kiểm thử API
Dưới đây là các bước kiểm thử API thông qua các công cụ như Postman hoặc HTTP Client (file `MinimalAPI.http`):

1. **Thêm công việc mới** (POST)
   - URL: `http://localhost:5000/todoitems`
   - Body:
     ```json
     {
       "name": "walk dog - 3",
       "isComplete": true
     }
     ```
     ![Hình minh họa](./photos/POST.png)

2. **Lấy danh sách công việc** (GET)
   - URL: `http://localhost:5000/todoitems`
     ![Hình minh họa](./photos/GETAll.png)

3. **Lọc công việc hoàn thành** (GET)
   - URL: `http://localhost:5000/todoitems/complete`
     ![Hình minh họa](./photos/GETComplete.png)

4. **Xóa công việc** (DELETE)
   - URL: `http://localhost:5000/todoitems/1`
     ![Hình minh họa](./photos/DELETE.png)

5. **Xem chi tiết công việc** (GET)
   - URL: `http://localhost:5000/todoitems/2`
     ![Hình minh họa](./photos/GETByID.png)

6. **Cập nhật thông tin công việc** (PUT)
   - URL: `http://localhost:5000/todoitems/2`
   - Body:
     ```json
     {
       "name": "walk dog Test Put Method",
       "isComplete": true
     }
     ```
     ![Hình minh họa](./photos/PUT.png)

---

## 5. Công nghệ sử dụng
- **Back-End**: ASP.NET Core Minimal API, Entity Framework Core
- **Cơ sở dữ liệu**: In-Memory Database
- **Quản lý yêu cầu HTTP**: HTTP Client (`MinimalAPI.http` file)

---
