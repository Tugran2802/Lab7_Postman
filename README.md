# BÁO CÁO KẾT QUẢ KIỂM THỬ API BẰNG POSTMAN

## 1. Giới thiệu dự án
Dự án này thực hiện thiết lập kịch bản và kiểm thử tự động các endpoint từ API công cộng PokéAPI tại địa chỉ: `https://pokeapi.co/api/v2/`.
- **Công cụ sử dụng:** Postman Desktop App.
- **Mục tiêu:** Xác thực khả năng hoạt động của URL, kiểm tra các tham số truyền lên và các mã trạng thái phản hồi từ hệ thống.

---

## 2. Danh Sách Các Kịch Bản Kiểm Thử (Test Cases)

### 2.1. Kịch Bản Kiểm Thử Lần 1:
- **Tên Kịch Bản:** Kiểm thử cơ bản của 1 URL
- **Mục Đích:** Test khả năng hoạt động của URL và phần mềm Postman
- **Phương Thức HTTP (GET/POST/PUT/DELETE):** GET
- **URL:** `https://pokeapi.co/api/v2/`
- **Tham Số:** Không có
- **Kết Quả Mong Đợi:** Gửi yêu cầu thành công, nhận được phản hồi từ hệ thống.
- **Kết Quả Thực Tế:** Đã gửi yêu cầu thành công.
- **Trạng Thái:** Thành công
- **Kết quả sau khi kiểm thử:**
<img width="1222" height="953" alt="image" src="https://github.com/user-attachments/assets/c8d67678-b86a-4100-ad27-38642c7d913f" />

---

### 2.2. Kịch Bản Kiểm Thử Lần 2:
- **Tên Kịch Bản:** Kiểm thử lấy thông tin chi tiết của một Pokémon cụ thể
- **Mục Đích:** Kiểm tra khả năng truy xuất dữ liệu chính xác theo tên định danh (Path Parameter)
- **Phương Thức HTTP (GET/POST/PUT/DELETE):** GET
- **URL:** `https://pokeapi.co/api/v2/pokemon/ditto`
- **Tham Số:** Không có
- **Kết Quả Mong Đợi:** Hệ thống trả về mã trạng thái 200 OK và chứa thông tin chính xác của Pokémon tên "ditto".
- **Kết Quả Thực Tế:** Hệ thống trả về đúng mã trạng thái 200 OK và cấu trúc dữ liệu JSON hiển thị đúng tên "ditto".
- **Trạng Thái:** Thành công
- **Kết quả sau khi kiểm thử:**
<img width="1229" height="968" alt="image" src="https://github.com/user-attachments/assets/30c66ac9-076c-4200-9e39-1b96cb3b5fcd" />

---

### 2.3. Kịch Bản Kiểm Thử Lần 3:
- **Tên Kịch Bản:** Kiểm thử tính năng phân trang danh sách Pokémon
- **Mục Đích:** Xác thực tham số giới hạn số lượng kết quả trả về trong một trang (Query Parameter)
- **Phương Thức HTTP (GET/POST/PUT/DELETE):** GET
- **URL:** `https://pokeapi.co/api/v2/pokemon`
- **Tham Số:** `limit=10&offset=0`
- **Kết Quả Mong Đợi:** Hệ thống phản hồi mã trạng thái 200 OK và danh sách mảng dữ liệu chỉ chứa đúng 10 Pokémon.
- **Kết Quả Thực Tế:** Đã nhận mã 200 OK, mảng dữ liệu trả về đếm đủ 10 phần tử theo đúng giới hạn `limit=10`.
- **Trạng Thái:** Thành công
- **Kết quả sau khi kiểm thử:**
<img width="1234" height="967" alt="image" src="https://github.com/user-attachments/assets/7f726f58-6184-45b9-a4ad-9934b6c92c6c" />

---

### 2.4. Kịch Bản Kiểm Thử Lần 4:
- **Tên Kịch Bản:** Kiểm thử trường hợp tìm kiếm dữ liệu không tồn tại (Negative Testing)
- **Mục Đích:** Kiểm tra khả năng bắt lỗi và phản hồi mã trạng thái của hệ thống khi nhập sai dữ liệu URL
- **Phương Thức HTTP (GET/POST/PUT/DELETE):** GET
- **URL:** `https://pokeapi.co/api/v2/pokemon/pikachu-sieu-cap-pro`
- **Tham Số:** Không có
- **Kết Quả Mong Đợi:** Hệ thống nhận diện được dữ liệu không tồn tại, trả về mã lỗi 404 Not Found để thông báo cho người dùng.
- **Kết Quả Thực Tế:** Hệ thống trả về đúng mã lỗi 404 Not Found và dòng text thông báo "Not Found".
- **Trạng Thái:** Thành công (Hệ thống bắt lỗi đúng kịch bản mong đợi)
- **Kết quả sau khi kiểm thử:**
<img width="1223" height="879" alt="image" src="https://github.com/user-attachments/assets/5b849ac4-9547-45b7-9808-26ee096e8e8d" />

---

## 3. Bảng Tổng Hợp Kết Quả (Test Summary)

| STT | Tên Kịch Bản Kiểm Thử | Phương Thức | URL / Tham Số | Kết Quả Thực Tế | Trạng Thái |
|:---|:---|:---:|:---|:---|:---:|
| 1 | Kiểm thử cơ bản của 1 URL | GET | `https://pokeapi.co/api/v2/` | Đã gửi yêu cầu thành công | **Thành công** |
| 2 | Lấy thông tin chi tiết Pokémon | GET | `/pokemon/ditto` | Trả về đúng mã 200 OK & dữ liệu | **Thành công** |
| 3 | Phân trang danh sách Pokémon | GET | `/pokemon?limit=10` | Trả về đúng mã 200 OK & đủ 10 phần tử | **Thành công** |
| 4 | Tìm kiếm dữ liệu không tồn tại | GET | `/pokemon/pikachu-sieu-cap-pro` | Trả về đúng mã lỗi 404 Not Found | **Thành công** |

---

## 4. Bài học kinh nghiệm thu được
1. Biết cách áp dụng cấu trúc báo cáo kiểm thử API chuẩn chỉnh theo định dạng rõ ràng (Mục đích, Tham số, Kết quả mong đợi, Kết quả thực tế).
2. Làm quen và sử dụng thành thạo hai loại tham số thông dụng khi làm việc với API: **Path Parameter** (đường dẫn trực tiếp) và **Query Parameter** (tham số lọc bắt đầu sau dấu `?`).
3. Hiểu được tầm quan trọng của việc kiểm thử các trường hợp lỗi (Mã lỗi 404) để đảm bảo hệ thống phản hồi chính xác khi dữ liệu đầu vào bị sai sót.
