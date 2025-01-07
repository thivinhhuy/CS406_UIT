<p align="center">
  <a href="https://www.uit.edu.vn/" title="Trường Đại học Công nghệ Thông tin" style="border: 5;">
    <img src="https://i.imgur.com/WmMnSRt.png" alt="Trường Đại học Công nghệ Thông tin | University of Information Technology">
  </a>
</p>

<!-- Title -->
<h1 align="center"><b>Xử lý ảnh và ứng dụng - CS406.P12.CLC</b></h1>



## Lecturer
<a name="lecturer"></a>
**Cáp Phạm Đình Thăng**

## Member
<a name="member"></a>
<a name="member"></a>
|**ID**|**Student ID**|**Name**|**Email**|
| ------ |-------------|----------------------|-------------------------|
| 1      | 21522110   	 |Thi Vinh Huy|21522165@gm.uit.edu.vn|
| 2      | 21522089      |Ngô Trần Tuấn Anh|21520567@gm.uit.edu.vn|
| 3      | 21522165 	   |Nguyễn Minh Hiếu|21520853@gm.uit.edu.vn|
| 4      | 21522507      |Trần Thanh Hà|21521749@gm.uit.edu.vn|

## Project
<a name="project"></a>
# Hệ thống trích xuất thông tin từ căn cước công dân

## Mục tiêu
Dự án này tập trung vào việc huấn luyện và triển khai các mô hình YOLO và Detectron2 để phát hiện đối tượng, đồng thời sử dụng Tesseract OCR để trích xuất văn bản từ ảnh.

## Hướng dẫn cài đặt

### 1. Cài đặt các công cụ cần thiết

#### a. Cài đặt YOLO

Sử dụng thư viện Ultralytics để huấn luyện YOLOv5 và YOLOv8:

```bash
pip install ultralytics
```

#### b. Cài đặt Detectron2

Cài đặt Detectron2 từ repository chính thức của Facebook Research:

```bash
pip install git+https://github.com/facebookresearch/detectron2.git
```

#### c. Cài đặt Tesseract OCR

Cài đặt Tesseract OCR và thư viện Python hỗ trợ:

```bash
pip install pytesseract
```

Trên hệ điều hành Linux hoặc macOS, cài đặt Tesseract OCR qua trình quản lý gói:

Ubuntu:

```bash
sudo apt update
sudo apt install tesseract-ocr
sudo apt install tesseract-ocr-vie
```

macOS (Homebrew):

```bash
brew install tesseract-lang
brew install tesseract-lang/tesseract/tesseract-lang-vie
```

Sau khi cài đặt, kiểm tra đường dẫn cấu hình Tesseract OCR bằng lệnh:

```bash
!which tesseract
```

### 2. Huấn luyện các mô hình

#### Huấn luyện YOLO

- Sử dụng YOLOv5 hoặc YOLOv8 để huấn luyện mô hình của bạn.
- Tham khảo tài liệu [Ultralytics](https://github.com/ultralytics/ultralytics) để thiết lập và chạy các lệnh huấn luyện phù hợp.

##### Huấn luyện YOLO với các mô hình cụ thể

- Mô hình 1:

```bash
!yolo task=detect mode=train model=yolo11n.pt data=/content/drive/MyDrive/CS406/Project/datasets/dataset_chip/data.yaml epochs=10 imgsz=640
```

- Mô hình 2:

```bash
!yolo task=detect mode=train model=yolo11n.pt data=/content/drive/MyDrive/CS406/Project/datasets/dataset_order/data.yaml epochs=10 imgsz=640
```

#### Huấn luyện Detectron2

- Sử dụng các công cụ của Detectron2 để thiết lập và huấn luyện mô hình.
- Tài liệu tham khảo: [Detectron2 Documentation](https://detectron2.readthedocs.io/).

### 3. Sử dụng OCR với Tesseract

Sử dụng thư viện `pytesseract` để trích xuất văn bản từ ảnh. Đảm bảo cấu hình đúng đường dẫn đến Tesseract nếu cần.

```python
import pytesseract
from PIL import Image

# Cấu hình đường dẫn nếu cần
pytesseract.pytesseract.tesseract_cmd = "/path/to/tesseract"

# Đọc văn bản từ ảnh
text = pytesseract.image_to_string(Image.open("image.png"), lang="vie")
print(text)
```

## Triển khai mô hình

Sử dụng file `app.py` để chạy và kiểm thử các mô hình YOLO, Detectron2 và OCR:

```bash
python app.py
```

### Nội dung `app.py`
- Tải mô hình đã huấn luyện (YOLO hoặc Detectron2).
- Tiền xử lý dữ liệu đầu vào (ảnh).
- Sử dụng OCR để trích xuất văn bản.
- Hiển thị kết quả.

## Ghi chú
- Đảm bảo rằng bạn có đủ tài nguyên phần cứng (GPU) để huấn luyện các mô hình.
- Kiểm tra các phiên bản thư viện để tránh xung đột.

