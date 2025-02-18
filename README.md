# Mô tả kết quả đạt được

## 1. Tổng quan
Minimal API được thiết kế để tạo ra API HTTP với mức phụ thuộc tối thiểu. Chúng lý tưởng cho các dịch vụ vi mô và ứng dụng chỉ muốn bao gồm các tệp, tính năng và mức phụ thuộc tối thiểu trong ASP.NET Core.
---

## 2. Kết quả đạt được

### Chức năng chính của API
- **Tạo mới công việc** (POST):  
  Cho phép thêm một công việc vào danh sách với các thông tin như tên (`Name`) và trạng thái hoàn thành (`IsComplete`).

- **Lấy danh sách tất cả công việc** (GET):  
  Truy xuất danh sách tất cả các công việc hiện có trong cơ sở dữ liệu.

- **Lấy danh sách công việc đã hoàn thành** (GET):  
  Truy xuất danh sách các công việc có trạng thái `IsComplete = true`.

- **Xóa một công việc** (DELETE):  
  Xóa một công việc khỏi danh sách dựa trên `Id`.

- **Lấy thông tin chi tiết của một công việc** (GET):  
  Truy xuất một công việc cụ thể theo `Id`.

- **Cập nhật thông tin công việc** (PUT):  
  Cho phép chỉnh sửa tên (`Name`) hoặc trạng thái hoàn thành (`IsComplete`) của một công việc.
---

## 3. Endpoint API

| API               | Description                 | Request Body | Response Body         |
|--------------------------------------|-----------------------------|--------------|------------------------|
| **GET**    `/todoitems`              | Get all to-do items        | None         | Array of to-do items   |
| **GET**     `/todoitems/complete`     | Get completed to-do items  | None         | Array of to-do items   |
| **GET**     `/todoitems/{id}`         | Get an item by ID          | None         | To-do item             |
| **POST**    `/todoitems`              | Add a new item             | To-do item   | To-do item             |
| **PUT**    `/todoitems/{id}`         | Update an existing item    | To-do item   | None                   |
| **DELETE**  `/todoitems/{id}`         | Delete an item             | None         | None                   |
---

## 4. Các bước thử nghiệm API
Dưới đây là các bước thử nghiệm API bằng công cụ như Postman hoặc HTTP Client (`MinimalAPI.http` file):

1. **Thêm một công việc mới** (POST)
   - URL: `https://localhost:7099/todoitems`
   - Body:
     ```json
     {
       "name":"hello Minh",
        "isComplete":true
     }
     ```
    ![image](https://github.com/user-attachments/assets/fa7a7abd-37d1-4626-bbb1-a4a6bcbeb612)


2. **Lấy danh sách tất cả công việc** (GET)
   - URL: `https://localhost:7099/todoitems`
       ![image](https://github.com/user-attachments/assets/b19ccf7e-22d9-452c-a216-938e3384aa23)

3. **Lấy danh sách công việc hoàn thành** (GET)
   - URL: `https://localhost:7099/todoitems/complete`
       ![image](https://github.com/user-attachments/assets/877e5770-da6d-49cf-a639-660a8434b587)

4. **Xóa một công việc** (DELETE)
   - URL: `https://localhost:7099/todoitems/3`
        ![image](https://github.com/user-attachments/assets/32108198-65f6-4708-9683-edfc17befd8a)

5. **Lấy thông tin chi tiết một công việc** (GET)
   - URL: `http://localhost:5000/todoitems/2`
        ![image](https://github.com/user-attachments/assets/8872567a-579a-445c-b55f-0e957d73d59e)

6. **Cập nhật thông tin công việc** (PUT)
   - URL: `http://localhost:5000/todoitems/2`
   - Body:
     ```json
     {
       "name": "btvn 1 test put method",
       "isComplete": true
     }
     ```
     ![image](https://github.com/user-attachments/assets/c2bfdd7b-431d-46bf-aeda-61500c591b63)
    ![image](https://github.com/user-attachments/assets/039c3baa-a2e4-44ce-ae73-c058554e579c)
---
