# 🧬 Genetic Algorithm - Bài toán Xếp Thời Khóa Biểu

## 📋 Giới thiệu

Dự án này sử dụng **Thuật toán Di truyền (Genetic Algorithm)** để giải quyết bài toán xếp thời khóa biểu tự động. Thuật toán sẽ tìm ra lịch học tối ưu dựa trên các ràng buộc về phòng học, giảng viên và thời gian.

## 🎯 Mục tiêu

- Xếp lịch học cho các môn học sao cho:
  - Không có xung đột về phòng học (cùng phòng, cùng thời gian)
  - Không có xung đột về giảng viên (giảng viên không dạy 2 lớp cùng lúc)
  - Tối ưu hóa việc sử dụng tài nguyên

## 🛠️ Công nghệ sử dụng

- **Python 3.x**
- **Pandas** - Đọc/ghi dữ liệu Excel
- **NumPy** - Xử lý tính toán
- **Jupyter Notebook** - Môi trường phát triển

## 📁 Cấu trúc dự án

```
source/
├── _ver2_GeneticAlgorithm.ipynb    # Notebook chính chứa thuật toán
├── data.xlsx                        # File dữ liệu đầu vào (courses, rooms, instructors)
├── KQ.xlsx                          # File kết quả thời khóa biểu tối ưu
├── VD.xlsx                          # File ví dụ về crossover (bố mẹ và con)
└── README.md                        # File hướng dẫn
```

## 📊 Dữ liệu đầu vào

File `data.xlsx` chứa 3 sheet:
1. **Sheet 1**: Danh sách các môn học (Code, Name)
2. **Sheet 2**: Danh sách phòng học
3. **Sheet 3**: Danh sách giảng viên

## 🔧 Các thành phần của thuật toán

### 1. Khởi tạo quần thể (`create_population`)
- Tạo quần thể ban đầu với các cá thể ngẫu nhiên
- Mỗi cá thể là một lịch học hoàn chỉnh

### 2. Hàm đánh giá (`calculate_fitness`)
- Đánh giá độ phù hợp của mỗi cá thể
- Trừ điểm khi vi phạm ràng buộc:
  - Xung đột phòng học
  - Xung đột giảng viên

### 3. Chọn lọc (`selection`)
- Giữ lại 50% cá thể tốt nhất trong quần thể

### 4. Lai ghép (`crossover`)
- Kết hợp gen từ 2 cá thể cha mẹ để tạo cá thể con

### 5. Đột biến (`mutate`)
- Thay đổi ngẫu nhiên một số gen của cá thể
- Xác suất đột biến: 10%

## 🚀 Cách sử dụng

### Cài đặt thư viện

```bash
pip install pandas numpy openpyxl
```

### Chạy chương trình

1. Mở file `_ver2_GeneticAlgorithm.ipynb` trong Jupyter Notebook hoặc VS Code
2. Chuẩn bị file `data.xlsx` với dữ liệu môn học, phòng học và giảng viên
3. Chạy lần lượt các cell trong notebook
4. Kết quả sẽ được lưu vào file `KQ.xlsx`

## ⚙️ Tham số thuật toán

| Tham số | Giá trị mặc định | Mô tả |
|---------|-----------------|-------|
| `generations` | 200 | Số thế hệ tối đa |
| `population_size` | 100 | Kích thước quần thể |
| `mutation_rate` | 0.1 (10%) | Xác suất đột biến |

## 📈 Kết quả

Sau khi chạy thuật toán, chương trình sẽ:
- In ra fitness tốt nhất của mỗi thế hệ
- Xuất thời khóa biểu tối ưu ra file `KQ.xlsx`
- Có thể xuất ví dụ về crossover ra file `VD.xlsx`

## 📝 Ví dụ kết quả

```python
{
    'course': 'CS101',
    'instructor': {'Instructor': 'Mr. Lưu Tiến Đạo'},
    'room': {'room': 'Room 101'},
    'time': {'day': 'Monday', 'session': 'Morning'}
}
```

## 👥 Tác giả

Dự án được phát triển cho môn học **Trí tuệ nhân tạo (Artificial Intelligence)** - Học kỳ 1 năm học 2024-2025.

## 📄 License

Dự án này được sử dụng cho mục đích học tập và nghiên cứu.
