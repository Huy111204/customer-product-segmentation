# customer-product-segmentation

[![Python](https://img.shields.io/badge/Python-3.10-blue)](https://www.python.org/) [![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-orange)](https://powerbi.microsoft.com/)  

---

## 📑 Mục lục
1. [Tổng quan đề tài](#tổng-quan-đề-tài)  
2. [Dashboard kinh doanh](#📊-tổng-quan-dashboard-kinh-doanh)  
3. [Kết quả phân tích tổng thể](#📈-kết-quả-phân-tích-tổng-thể)  
4. [Phân tích khách hàng](#👤-phân-tích-khách-hàng)  
5. [Phân tích sản phẩm](#📦-phân-tích-sản-phẩm)  
6. [Đề xuất chiến lược](#đề-xuất-chiến-lược)  
7. [Kết luận mô hình phân cụm](#5-3-kết-luận-mô-hình-phân-cụm)  

---

## Tổng quan đề tài

### Lý do chọn đề tài
Trong kỷ nguyên số, dữ liệu là tài sản chiến lược giúp doanh nghiệp cạnh tranh và ra quyết định hiệu quả. Đặc biệt trong thương mại điện tử, BI giúp hiểu rõ hành vi khách hàng, tối ưu vận hành và xây dựng chiến lược.

Dữ liệu từ bộ **Global Superstore** (50.000+ bản ghi) cung cấp nền tảng để triển khai phân tích đa chiều, trực quan hóa và học máy.

### Mục tiêu nghiên cứu
- Phân tích KPI chính: doanh thu, lợi nhuận, chiết khấu, thời gian giao hàng.  
- Xây dựng dashboard tương tác bằng **Power BI**.  
- Phân cụm khách hàng & sản phẩm với **K‑Means**, **DBSCAN**.  
- Đề xuất chiến lược kinh doanh dựa trên kết quả.

### Phương pháp & Công cụ
- **Power BI**: báo cáo & dashboard.  
- **Python** (Jupyter): tiền xử lý, phân tích, trực quan hóa.  
- **ML**: phân cụm K‑Means, DBSCAN.  
- **Dataset**: [Global Superstore on Kaggle](https://www.kaggle.com/datasets/apoorvaappz/global-super-store-dataset/data)  

### Phạm vi nghiên cứu
- Hoạt động kinh doanh tổng thể, hành vi khách hàng, hiệu suất sản phẩm.  
- Ứng dụng lý thuyết BI vào thực tiễn.

---

## 📊 Tổng quan dashboard kinh doanh

Dashboard cung cấp cái nhìn trực quan về hiệu suất doanh nghiệp:

![Dashboard tổng quan kinh doanh](./images/sales_dashboard.png)

- **KPIs**: Doanh thu 12.64M | Lợi nhuận 1.47M | Biên lợi nhuận 11.61% | Phí giao hàng | Chiết khấu | Số đơn hàng.  
- **Phân tích đa chiều**: thời gian, segment, category, ship mode, thị trường.  
- **Bản đồ toàn cầu**: phát hiện thị trường tiềm năng/yếu điểm.  
- **Xu hướng theo năm**: doanh thu & lợi nhuận.  
- **Bộ lọc**: năm, phân khúc, danh mục, phương thức vận chuyển.

### ❓ Câu hỏi giải đáp
- Doanh thu, lợi nhuận, biên lợi nhuận hiện tại?  
- Phân khúc nào hiệu quả nhất?  
- Ship mode ưu tiên?  
- Xu hướng qua năm ra sao?  
- Thị trường trọng điểm & thị trường cần cải thiện?

---

## 📈 Kết quả phân tích tổng thể

![Kết quả phân tích tổng thể](./images/overview_analysis.png)

### Doanh thu & lợi nhuận
- Doanh thu: **12.64M USD**  
- Lợi nhuận: **1.47M USD**  
- Biên lợi nhuận: **11.61%**  
- Phí giao hàng: **1.35M USD** | Chiết khấu: **7.33K USD**

### Phân khúc khách hàng
- **Consumer**: 51% lợi nhuận → ưu tiên duy trì.  
- **Corporate** & **Home Office**: lợi nhuận thấp, nhưng Home Office có biên cao nhất.

### Nhóm sản phẩm
- **Technology**: 45% lợi nhuận (663K USD).  
- **Furniture**: doanh thu lớn, biên thấp → cần tối ưu.

### Thị trường
- Tập trung tại Bắc Mỹ, châu Âu, châu Á.  
- Các thành phố lớn đóng góp chính.

### Phương thức vận chuyển
- **Standard Class**: chủ yếu → tiết kiệm chi phí.  
- **First Class**, **Same Day**: ít dùng → tiềm năng phát triển.

### Xu hướng qua năm
- Doanh thu tăng từ 2.3M (2011) → 4.3M (2014).  
- Lợi nhuận tăng từ 0.25M → 0.50M USD.

---

## 👤 Phân tích khách hàng

![Dashboard phân tích khách hàng](./images/customer_analysis.png)

### Hướng khai thác
- Nhận diện phân khúc theo số lượng, doanh thu, lợi nhuận.  
- Theo dõi biến động qua năm.  
- Phân tích Top‑ khách hàng & mức chiết khấu.  

### Kết quả nổi bật
- **Consumer**: 12.6K đơn, 6.5M doanh thu, 0.75M lợi nhuận.  
- **Home Office**: biên cao, quy mô nhỏ.  
- Đơn hàng Consumer tăng từ 4.7K → 9K.  
- Chi phí vận chuyển cao → tối ưu logistics.

---

## 📦 Phân tích sản phẩm

![Dashboard phân tích sản phẩm](./images/product_analysis.png)

### Hướng phân tích
- Doanh thu, lợi nhuận, số lượng theo category.  
- Top 10 sản phẩm doanh thu & lợi nhuận.  
- Xu hướng lợi nhuận theo năm.  
- Phân tích chiết khấu & hiệu suất danh mục con.

### Kết quả nổi bật
- **Technology, Office Supplies, Furniture** doanh thu cân bằng.  
- Biên lợi nhuận: Tech & Office ~14%; Furniture ~7%.  
- Tech tăng trưởng mạnh mẽ sau 2013.  
- Top lợi nhuận chủ yếu sản phẩm công nghệ.

---

## Đề xuất chiến lược
- **Tập trung nhóm lợi nhuận cao** (Tech).  
- **Chăm sóc khách hàng trung thành** (khuyến mãi, tích điểm).  
- **Tối ưu chi phí giao hàng** (hợp tác vận chuyển, gom đơn).  
- **Rà soát danh mục kém hiệu quả** (nội thất).  
- **Tận dụng mùa vụ & dịp cao điểm**.

---

## 5.3 Kết luận mô hình phân cụm

### 🎯 Các kết quả đạt được
| Phân cụm   | Silhouette (K‑Means) | Silhouette (DBSCAN) |
|------------|----------------------|---------------------|
| Khách hàng | 0.5776               | 0.325               |
| Sản phẩm   | 0.7770               | 0.751               |

![K‑Means vs DBSCAN RFM](./images/cluster_rfm.png)  
*Hình 7. So sánh phân cụm RFM trên PCA*

![K‑Means vs DBSCAN Product](./images/cluster_product.png)  
*Hình 8. So sánh phân cụm sản phẩm trên PCA*

### 📝 Đánh giá mô hình
- **K‑Means**:  
  - Ba cụm rõ ràng, Silhouette cao (0.58 khách, 0.78 sản phẩm).  
  - Cần chọn trước k, giả định hình cầu.

- **DBSCAN**:  
  - Tự phát hiện mật độ & noise.  
  - Hiệu quả với sản phẩm (0.75), kém với RFM (0.33).  
  - Nhạy tham số ε & minPts.

### ⚠️ Hạn chế
- K‑Means: yêu cầu k cố định, kết quả phụ thuộc khởi tạo.  
- DBSCAN: chọn tham số khó, kém trên dữ liệu đa chiều.

### 💡 Đề xuất cải tiến
1. **Mở rộng đặc trưng**:  
   - Khách hàng: “thời gian gắn bó”, “biến động chi tiêu”…  
   - Sản phẩm: “tỷ lệ trả lại”, “biên lợi nhuận trung bình”…  
2. **Thử GMM**: soft clustering để phát hiện nhóm chuyển tiếp.

### 🔚 Kết luận & Khuyến nghị
- BI + phân cụm K‑Means/DBSCAN đã phân khúc rõ, hỗ trợ cá nhân hóa và tối ưu danh mục.  
- Khuyến nghị: duy trì dashboard, kết hợp K‑Means & DBSCAN, thử GMM, liên tục bổ sung đặc trưng và tối ưu tham số.
