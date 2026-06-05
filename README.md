# 🛒 Olist E-Commerce Customer Behavior & Retention Analysis

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Data Analysis](https://img.shields.io/badge/Analysis-RFM%20%7C%20Retention-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📌 Tổng quan dự án (Project Overview)
Dự án tập trung vào việc khai phá dữ liệu từ **100.000 đơn hàng thực tế** (giai đoạn 2016 - 2018) của **Olist** - nền tảng thương mại điện tử lớn nhất tại Brazil. Mục tiêu chính là phân tích hành vi mua sắm của khách hàng, đánh giá các yếu tố ảnh hưởng đến trải nghiệm người dùng, và ứng dụng **mô hình RFM (Recency, Frequency, Monetary)** để phân khúc khách hàng, từ đó đề xuất giải pháp tối ưu tỷ lệ giữ chân (Retention Rate).

---

## 🎯 Mục tiêu dự án (Objectives)
*   **Xử lý dữ liệu:** Làm sạch, xử lý dữ liệu khuyết thiếu/bất thường và liên kết 9 bảng dữ liệu quan hệ của Olist.
*   **Phân tích xu hướng kinh doanh (EDA):** Xác định xu hướng doanh thu theo thời gian, các ngành hàng chủ lực và phân bố địa lý của khách hàng.
*   **Đánh giá chất lượng dịch vụ:** Phân tích mối tương quan giữa thời gian giao hàng thực tế (Delivery Time) với điểm đánh giá của người dùng (Review Score).
*   **Phân khúc khách hàng (Segmentation):** Áp dụng mô hình RFM để nhóm khách hàng thành các tệp cụ thể (VIP, Loyal, At Risk, Hibernating).
*   **Phân tích tỷ lệ giữ chân (Retention Analysis):** Đo lường tần suất quay lại mua hàng và khoảng thời gian giữa các lần mua để tìm ra "nút thắt" trong bài toán duy trì khách hàng.

---

## 📊 Bộ dữ liệu sử dụng (Dataset)
Dự án sử dụng bộ dữ liệu công khai **Brazilian E-Commerce Public Dataset by Olist** từ Kaggle, bao gồm các thông tin về:
*   `olist_customers_dataset.csv`: Thông tin vị trí, định danh khách hàng.
*   `olist_orders_dataset.csv`: Trạng thái đơn hàng, mốc thời gian mua/giao hàng.
*   `olist_order_items_dataset.csv`: Chi tiết sản phẩm trong đơn, giá và phí vận chuyển.
*   `olist_order_payments_dataset.csv`: Phương thức và số lần trả góp.
*   `olist_order_reviews_dataset.csv`: Điểm số và bình luận đánh giá từ khách hàng.
*   *(Và các bảng bổ trợ về Sản phẩm, Người bán, Địa lý...)*

---

## 🛠️ Công nghệ & Thư viện sử dụng (Tech Stack)
*   **Ngôn ngữ chính:** Python
*   **Thư viện xử lý dữ liệu:** `Pandas`, `NumPy`
*   **Thư viện trực quan hóa:** `Matplotlib`, `Seaborn`, `Plotly` (nếu có)
*   **Môi trường phát triển:** Jupyter Notebook / Google Colab

---

## 🚀 Các bước triển khai (Project Steps)

### 1. Thu thập & Tiền xử lý dữ liệu (Data Cleaning & Preprocessing)
*   Hợp nhất (Merge) các bảng dữ liệu qua các khóa ngoại (`customer_id`, `order_id`, `product_id`).
*   Xử lý giá trị trống (Missing values) và ép kiểu dữ liệu (đặc biệt là định dạng `datetime`).
*   Lọc bỏ các đơn hàng có trạng thái hủy (canceled) hoặc không hợp lệ để tránh làm nhiễu kết quả phân tích.

### 2. Phân tích dữ liệu khám phá (EDA)
*   **Doanh thu & Đơn hàng:** Phân tích tăng trưởng doanh số theo tháng/quý.
*   **Vận chuyển vs. Đánh giá:** Chứng minh giả thuyết: *"Thời gian giao hàng càng lâu, điểm review càng thấp"* bằng biểu đồ tương quan.

### 3. Phân khúc khách hàng bằng Mô hình RFM
*   Tính toán 3 chỉ số cho từng khách hàng:
    *   **Recency (R):** Số ngày kể từ lần mua hàng cuối cùng.
    *   **Frequency (F):** Tổng số lần mua hàng.
    *   **Monetary (M):** Tổng số tiền đã chi tiêu.
*   Chia điểm (Scoring) từ 1-5 và nhóm thành các phân khúc chiến lược (VIP, Cần níu kéo, Khách hàng mới...).

### 4. Phân tích Tỷ lệ giữ chân (Retention Rate)
*   Tính toán tỷ lệ khách hàng quay lại mua hàng (Repeat Customer Rate).
*   Phân tích khoảng thời gian trung bình giữa các đơn hàng để đề xuất thời điểm kích hoạt chiến dịch Marketing.

---

## 📈 Kết quả nổi bật (Key Insights)
*   *Ví dụ: Nhận diện được logistics là điểm nghẽn chính: các đơn hàng giao trễ trên 15 ngày có tỷ lệ nhận điểm 1-star lên đến X%.*
*   *Ví dụ: Mô hình RFM chỉ ra nhóm khách hàng "At Risk" chiếm X% tổng số khách hàng cũ, cần có chương trình khuyến mãi kích cầu ngay lập tức.*
*   *Ví dụ: Đặc thù của Olist có tỷ lệ khách hàng mua 1 lần (One-time buyers) rất cao (khoảng X%), đòi hỏi chiến lược remarketing mạnh mẽ hơn.*

---

## 📁 Cấu trúc thư mục (Folder Structure)
```text
├── data/                  # Thư mục chứa file dữ liệu gốc (hoặc link tải)
├── notebooks/             # Thư mục chứa các file Jupyter Notebook (.ipynb)
│   ├── 1_data_cleaning.ipynb
│   ├── 2_eda_analysis.ipynb
│   └── 3_rfm_&_retention.ipynb
├── README.md              # Tài liệu hướng dẫn dự án
└── requirements.txt       # Danh sách các thư viện cần cài đặt
