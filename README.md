# customer-product-segmentation

## Tổng quan đề tài: Customer-Product Segmentation

### Lý do chọn đề tài
Trong kỷ nguyên số, dữ liệu là tài sản chiến lược giúp doanh nghiệp cạnh tranh và ra quyết định hiệu quả. Đặc biệt trong lĩnh vực thương mại điện tử, việc ứng dụng Business Intelligence (BI) giúp doanh nghiệp hiểu rõ hành vi khách hàng, tối ưu vận hành và đưa ra chiến lược phù hợp.
![image](https://github.com/user-attachments/assets/e7f82ab4-67cf-4a6b-a858-c728c4efeac4)
Dữ liệu từ bộ **Global Superstore** (50.000+ bản ghi) cung cấp thông tin đa chiều về khách hàng, sản phẩm, đơn hàng – là nền tảng lý tưởng để triển khai các kỹ thuật BI như phân tích, trực quan hóa, và học máy.

### Mục tiêu nghiên cứu
- Phân tích các chỉ số cốt lõi: doanh thu, lợi nhuận, chiết khấu, thời gian giao hàng...
- Xây dựng dashboard tương tác bằng **Power BI**.
- Phân cụm khách hàng & sản phẩm bằng **K-Means**, **DBSCAN**.
- Đề xuất chiến lược kinh doanh từ kết quả phân tích.

### Phương pháp & Công cụ
- **Power BI**: trực quan hóa và dashboard phân tích tương tác.
- **Python**: xử lý và phân tích dữ liệu (Jupyter Notebook).
- **Machine Learning**: phân cụm bằng K-Means, DBSCAN để khám phá phân khúc tiềm ẩn.
- **Dữ liệu sử dụng**: [Global Superstore Dataset on Kaggle](https://www.kaggle.com/datasets/apoorvaappz/global-super-store-dataset/data)

### Phạm vi nghiên cứu
- Tập trung vào 3 khía cạnh: hoạt động kinh doanh tổng thể, hành vi khách hàng và hiệu suất sản phẩm.
- Ứng dụng kiến thức học thuật vào phân tích thực tiễn và trực quan hoá dữ liệu.

---

## 📊 Tổng quan dashboard kinh doanh

Dashboard cung cấp cái nhìn trực quan về hiệu suất doanh nghiệp:

- **KPIs chính**: Doanh thu 12.64M, lợi nhuận 1.47M, lợi nhuận 11.61%, phí giao hàng, chiết khấu, số đơn hàng.
- **Phân tích theo nhiều chiều**: thời gian, segment, category, ship mode, khu vực thị trường.
- **Bản đồ phân phối doanh thu toàn cầu**: phát hiện thị trường tiềm năng và yếu điểm.
- **Biểu đồ xu hướng doanh thu/lợi nhuận qua năm**: theo dõi tăng trưởng.
- **Bộ lọc động**: theo năm, phân khúc, thị trường, danh mục, giúp khai thác dữ liệu linh hoạt.

### ❓ Câu hỏi giải đáp từ dashboard:
- Doanh thu/lợi nhuận/tỷ suất hiện tại là bao nhiêu?
- Khách hàng theo từng phân khúc có hiệu quả ra sao?
- Ship mode nào phổ biến nhất?
- Doanh thu/lợi nhuận theo năm thay đổi thế nào?
- Quốc gia/thị trường nào đang hoạt động hiệu quả?
---

## 📈 Kết quả phân tích tổng thể
![image](https://github.com/user-attachments/assets/2787329f-afb4-4de3-8ce0-5390c256043c)

### Doanh thu và lợi nhuận:
- Doanh thu đạt **12.64 triệu USD**, lợi nhuận **1.47 triệu USD**, tỷ suất lợi nhuận chỉ **11.61%**.
- Chi phí giao hàng (**1.35 triệu USD**) và chiết khấu cao (**7.33K USD**) là nguyên nhân làm giảm hiệu quả.

### Phân khúc khách hàng:
- **Consumer**: đóng góp **51% lợi nhuận** – nhóm cần được tập trung chăm sóc.
- **Corporate & Home Office**: ít lợi nhuận hơn, nhưng Home Office có tỷ suất lợi nhuận cao nhất.

### Nhóm sản phẩm:
- **Technology** chiếm tỷ trọng lợi nhuận cao nhất (663K USD – 45%).
- **Furniture** doanh thu lớn nhưng lợi nhuận thấp → cần tối ưu.

### Thị trường:
- Doanh thu tập trung tại Bắc Mỹ, châu Âu và châu Á.
- Các thành phố lớn đóng vai trò trung tâm doanh thu.

### Giao hàng:
- **Standard Class** chiếm đa số đơn hàng → tiết kiệm chi phí là ưu tiên.
- **First Class**, **Same Day** ít phổ biến → có thể đẩy mạnh vào nhóm khách hàng cao cấp.

### Tăng trưởng qua các năm:
- Doanh thu tăng từ 2.3M (2011) lên 4.3M (2014).
- Lợi nhuận tăng từ 250K lên 500K USD → ổn định nhưng cần bứt phá.

---

## 👤 Phân tích khách hàng
![image](https://github.com/user-attachments/assets/ab724f53-f7c1-40ee-bef5-dadf6654b9c8)

### Hướng khai thác
- Xác định phân khúc khách hàng chính theo số lượng, doanh thu, lợi nhuận.
- Theo dõi xu hướng tăng trưởng từng phân khúc qua các năm.
- Phân tích **top khách hàng theo giá trị đơn hàng & chiết khấu**.
- Hỗ trợ ra quyết định phân bổ nguồn lực và chiến lược chăm sóc.

### Kết quả nổi bật
- **Consumer** dẫn đầu về số lượng đơn hàng (12.6K/25K), doanh thu (6.5M) và lợi nhuận (0.75M).
- **Home Office** có tỷ suất lợi nhuận cao nhất nhưng quy mô nhỏ.
- Đơn hàng của nhóm Consumer tăng mạnh từ 4.7K (2011) lên gần 9K (2014).
- Chi phí vận chuyển vẫn chiếm tỷ trọng lớn → cần tối ưu logistics.

---

## 📦 Phân tích sản phẩm
![image](https://github.com/user-attachments/assets/39c07106-c065-4096-92ec-e35893ab068f)

### Hướng phân tích
- Doanh thu, lợi nhuận, số sản phẩm bán ra theo từng **category**.
- Phân tích **Top 10 sản phẩm** có doanh thu/lợi nhuận cao nhất.
- Theo dõi xu hướng lợi nhuận từng danh mục qua các năm.
- Phân tích tỷ lệ chiết khấu và hiệu suất từng danh mục con.

### Kết quả nổi bật
- **Technology, Office Supplies, Furniture** doanh thu gần tương đương.
- Nhưng **biên lợi nhuận chênh lệch rõ rệt**: Tech và Office Supplies ~14%, Furniture chỉ 7%.
- **Technology** là động lực tăng trưởng mạnh mẽ từ năm 2013 trở đi.
- Top sản phẩm lợi nhuận cao chủ yếu thuộc nhóm công nghệ.

---

## Đề xuất chiến lược

- ✅ **Tập trung vào nhóm sản phẩm lợi nhuận cao**
- ✅ **Chăm sóc khách hàng trung thành**
- ✅ **Tối ưu chi phí giao hàng**
- ✅ **Rà soát nhóm sản phẩm kém hiệu quả**
- ✅ **Tận dụng thời điểm cao điểm & hành vi theo mùa** 
## Kết luận mô hình phân cụm

### 🎯 Các kết quả đạt được
| Phân cụm     | Silhouette (K‑Means) | Silhouette (DBSCAN) |
|--------------|----------------------|---------------------|
| Khách hàng   | 0.5776               | 0.325               |
| Sản phẩm     | 0.7770               | 0.751               |

![image](https://github.com/user-attachments/assets/a5e04e0d-9cbb-4731-b45e-b0d8a0409b44)
> **Hình 7.** So sánh kết quả phân cụm RFM (K‑Means vs. DBSCAN) trên PCA
![image](https://github.com/user-attachments/assets/d4a306b8-80e1-4ffd-870a-430f642f1bc4)
> **Hình 8.** Kết quả phân cụm sản phẩm (K‑Means vs. DBSCAN) trên PCA

### 📝 Đánh giá mô hình
- **K‑Means**  
  - Phân chia rõ 3 nhóm “cao – trung bình – thấp” (RFM) và “bán chậm – tầm trung – bán chạy” (sản phẩm).  
  - Silhouette cao: 0.58 (khách), 0.78 (sản phẩm).  
  - Phù hợp khi biết trước số cụm và cần kết quả minh bạch.

- **DBSCAN**  
  - Tự động phát hiện cụm mật độ và noise.  
  - Hiệu quả trên sản phẩm (Silhouette 0.75), kém trên RFM khách hàng (0.33).  
  - Không cần xác định k nhưng phụ thuộc EPS & minPts.

### ⚠️ Hạn chế
- **K‑Means**:  
  - Cần chọn trước k, giả định hình cầu, kết quả phụ thuộc khởi tạo ngẫu nhiên.  
- **DBSCAN**:  
  - Nhạy với tham số; kém hiệu quả trên dữ liệu đa chiều hoặc mật độ biến thiên.

### 💡 Đề xuất cải tiến
1. **Mở rộng bộ đặc trưng**  
   - Khách hàng: thêm “thời gian gắn bó”, “biến động chi tiêu”,…  
   - Sản phẩm: thêm “tỷ lệ trả lại”, “biên lợi nhuận trung bình”, “tăng trưởng doanh số”,…

2. **Thử thuật toán khác**  
   - **Gaussian Mixture Models (GMM)** để phân cụm mềm, phát hiện nhóm chuyển tiếp.

### 🔚 Kết luận & Khuyến nghị
- **Kết luận**:  
  BI + Power BI kết hợp phân cụm (K‑Means, DBSCAN) đã giúp phân khúc rõ ràng, hỗ trợ cá nhân hóa và tối ưu danh mục.

- **Khuyến nghị**:  
  - Duy trì dashboard theo dõi định kỳ.  
  - Kết hợp linh hoạt K‑Means & DBSCAN, thử GMM.  
  - Liên tục bổ sung đặc trưng, tối ưu tham số và kiểm thử nhiều phương pháp.
--- Theo bạn cần chỉnh thêm gì về nội dung hay gì không
