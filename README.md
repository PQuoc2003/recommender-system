# Recommender System using PCY Algorithm


Đây là thuật toán gợi ý sản phẩm sủ dụng thuật toán PYC (Park - Chen - Yu).


Thuật toán PCY là một cải tiến của thuật toán Apriori nhằm tối ưu hóa quá trình tìm tập phổ biến (frequent itemsets) trong khai phá luật kết hợp (Association Rule Mining). Thuật toán này giúp giảm thiểu số lượng ứng viên (candidate itemsets) cần kiểm tra ở bước thứ hai bằng cách sử dụng bộ đếm băm (hashing) để phát hiện sớm các cặp không tiềm năng.


## 📌 Ý tưởng chính của thuật toán PCY
Khi quét qua tập dữ liệu giao dịch trong bước đầu tiên (Pass 1), ngoài việc đếm tần số xuất hiện của các mục (items), thuật toán còn:

Tính toán hàm băm cho từng cặp mục (pair of items).
Lưu trữ kết quả băm trong bảng băm (hash bucket).
Xác định các bucket đủ điều kiện (có số lượng cặp vượt ngưỡng tối thiểu – support threshold) và chỉ kiểm tra các cặp nằm trong các bucket hợp lệ ở Pass 2.


## 📊 So sánh PCY với Apriori

| Đặc điểm  | A-priori | PCY |
| ------ | ------- |-----|
| Chiến lược | Duyệt và đếm toàn bộ các cặp|Sử dụng bảng băm để lọc cặp không tiềm năng|
| Số lượng cặp xét |Tất cả các cặp có item phổ biến	|Chỉ xét các cặp thuộc bucket hợp lệ|
|Tối ưu bộ nhớ|Không tối ưu|Sử dụng bảng băm để tiết kiệm bộ nhớ|
|Hiệu suất|Thấp khi tập dữ liệu lớn|Nhanh hơn Apriori với dữ liệu lớn|


## 📌 Ưu điểm của thuật toán PCY
Tiết kiệm bộ nhớ: Chỉ lưu trữ bảng băm thay vì toàn bộ cặp item.
Tăng tốc độ: Giảm số lượng cặp cần kiểm tra ở Pass 2.
Hiệu quả với dữ liệu lớn: Đặc biệt hữu ích khi tập dữ liệu có số lượng giao dịch lớn.
## 📉 Nhược điểm của thuật toán PCY
Phụ thuộc vào hàm băm: Nếu hàm băm không đều (collision cao), hiệu năng giảm.
Không áp dụng được với tập itemset lớn hơn 2 trực tiếp (cần mở rộng thành Multi-hash PCY hoặc cải tiến khác).
		




