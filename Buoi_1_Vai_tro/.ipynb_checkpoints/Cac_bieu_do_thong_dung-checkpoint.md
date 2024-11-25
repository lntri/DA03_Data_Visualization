# Các loại biểu đồ thông dụng
Trong lĩnh vực phân tích trực quan hóa dữ liệu, việc lựa chọn loại biểu đồ phù hợp đóng vai trò chủ chốt trong việc truyền tải thông tin một cách hiệu quả và chính xác. Mỗi loại biểu đồ mang cho mình những đặc điểm riêng biệt, phù hợp với từng loại dữ liệu và mục đích phân tích cụ thể. Việc hiểu rõ đặc điểm của từng loại biểu đồ không chỉ giúp người phân tích lựa chọn công cụ thích hợp mà còn có thể truyền tải thông tin đến người xem một cách trọn vẹn.

## Bar Chart
**Bar Chart** (hay còn gọi là biểu đồ cột) là một trong những loại biểu đồ phổ biến nhất, được sử dụng để so sánh các giá trị giữa các danh mục hoặc nhóm khác nhau. Với cấu trúc gồm các cột hoặc thanh đặt song song nhau, chiều cao hoặc độ dài của mỗi cột đại diện cho giá trị của từng danh mục. Biểu đồ cột giúp người xem dễ dàng nhận biết sự chênh lệch giữa các nhóm, từ đó rút ra những kết luận quan trọng.
```{figure} ../img/bar_chart.png
---
name: bar_chart
---
Top 10 quốc gia sản xuất vàng lớn nhất thế giới năm 2019 (Nguồn: World Gold Council, U.S. Golbal Investors).
```

## Stacked Bar Chart
**Stacked Bar Chart** - hay còn gọi là biểu đồ cột xếp chồng - là một dạng biểu đồ cột đặc biệt trong đó các thành phần dữ liệu được xếp chồng lên nhau trong mỗi cột hoặc thanh. Mục đích của biểu đồ này là hiển thị tổng thể dữ liệu và phân tích cơ cấu thành phần của từng nhóm trong tổng thể đó. Mỗi cột đại diện cho tổng giá trị của một nhóm, và các phần trong cột biểu thị tỷ lệ hoặc giá trị của các thành phần con trong nhóm đó.

```{figure} ../img/stacked_bar_chart.png
---
name: stacked_bar_chart
---
Tổng chi phí bán hàng của Vinamilk từ 2017 - 2023 (Ảnh sưu tầm).
```

## Histogram
Biểu đồ Histogram là một dạng biểu đồ thể hiện tần suất theo dạng cột. Dữ liệu được biểu thị bằng các cột trên biểu đồ có độ cao khác nhau tùy thuộc vào tần suất (xuất hiện bao nhiêu lần) phạm vi dữ liệu cụ thể xảy ra.

```{figure} ../img/Histogram.png
---
name: histogram
---
Biểu đồ phổ điểm thi THPT môn Toán - năm 2024 (Nguồn: https://tuoitre.vn/)
```

## Line Chart
**Line Chart** (biểu đồ đường) thường được sử dụng để hiển thị sự thay đổi của một hoặc nhiều biến số theo thời gian. Với trục hoành thường đại diện cho thời gian và trục tung biểu thị giá trị của biến số, các điểm dữ liệu được kết nối với nhau bằng đường thẳng tạo thành một đường liên tục. Biểu đồ đường giúp nhấn mạnh xu hướng, biến động và chu kỳ của dữ liệu theo thời gian.
```{figure} ../img/line_chart.jpg
---
name: line_chart
---
Biểu đồ đường thể hiện dân số thế giới tăng từ hơn 3 tỉ dân lên đến gần 7 tỉ dân trong hơn 5 thập kỉ qua (Ảnh sưu tầm).
```

## Box Plot
**Box Plot** - còn được gọi là biểu đồ hộp - là công cụ mạnh mẽ để biểu diễn phân bố của dữ liệu thông qua các thống kê như trung vị, tứ phân vị và các giá trị ngoại lai (outliers). Biểu đồ hộp giúp người xem hiểu rõ hơn về sự phân tán, độ lệch và sự đối xứng của dữ liệu, rất hữu ích cho việc so sánh phân bố của nhiều nhóm dữ liệu khác nhau.
```{figure} ../img/boxplot_outliers.png
---
name: box_plot_outliers
---
Những giá trị thống kê giúp phát hiện giá trị ngoại lai (outliers) (Ảnh sưu tầm).
```

## Scatter Plot
**Scatter Plot** (biểu đồ phân tán) được sử dụng để khám phá và biểu thị mối quan hệ giữa hai biến số định lượng. Mỗi điểm trên biểu đồ đại diện cho một quan sát với tọa độ xác định bởi giá trị của hai biến số. Biểu đồ phân tán giúp phát hiện các xu hướng, tương quan hoặc ngoại lệ trong dữ liệu. 
Khi quan sát sự phân bố của các điểm dữ liệu trên biểu đồ, chúng ta có thể suy luận về tính chất của mối tương quan giữa hai biến số, bao gồm tương quan thuận, tương quan nghịch, hoặc không có tương quan.
    - **Mối tương quan thuận** (Positive Correlation) xảy ra khi giá trị của một biến số tăng lên thì giá trị của biến số kia cũng có xu hướng tăng theo. Trên biểu đồ Scatter Plot, điều này được thể hiện bằng việc các điểm dữ liệu tập trung theo một đường xu hướng đi lên từ trái sang phải.
    - **Mối tương quan nghịch** (Negative Correlation) ngược lại, xảy ra khi giá trị của một biến số tăng lên thì giá trị của biến số kia có xu hướng giảm xuống. Trên biểu đồ Scatter Plot, các điểm dữ liệu sẽ tập trung theo một đường xu hướng đi xuống từ trái sang phải.

```{figure} ../img/scatter-plot_correlation.png
---
name: scatter_plot_correlation
---
Tính chất mối tương quan tại biểu đồ Scatter Plot.
```

```{figure} ../img/scatter-plot_height_weight.png
---
name: scatter_plot
---
Các điểm dữ liệu phân bố theo một xu hướng tăng, cho thấy rằng có mối tương quan dương giữa chiều cao và cân nặng
```

## Heat Map
Heat Map (Biểu đồ nhiệt) là biểu đồ trực quan hóa dữ liệu đa biến thông qua việc sử dụng màu sắc để biểu thị giá trị của các biến số. Trong biểu đồ nhiệt, mỗi ô màu đại diện cho một cặp giá trị của hai biến số, với màu sắc thay đổi dựa trên giá trị của một biến số thứ ba hoặc mức độ tương quan. Mỗi màu sắc trong biểu đồ đại diện cho một phạm vi giá trị cụ thể, thường được biểu thị qua một bảng màu từ lạnh đến nóng, tương ứng với giá trị từ thấp đến cao. Biểu đồ nhiệt giúp nhận diện các mẫu hình, xu hướng và mối quan hệ phức tạp trong dữ liệu đa chiều.
```{figure} ../img/heat_map.png
---
name: heat_map
---
Biểu đồ Heat Map thể hiện lưu lượng truy cập website theo giờ và ngày trong tuần.
```

## Pie Chart
Pie Chart (Biểu đồ tròn) là biểu đồ thể hiện tỷ lệ hoặc phần trăm của các thành phần trong một tổng thể. Mỗi phần của hình tròn đại diện cho một danh mục, với kích thước tương ứng với tỷ lệ của danh mục đó trong tổng thể. Biểu đồ tròn giúp người xem dễ dàng nhận biết cơ cấu thành phần và so sánh tỷ lệ giữa các danh mục. Tuy nhiên, khi số lượng danh mục quá nhiều hoặc sự chênh lệch giữa các tỷ lệ không đáng kể, biểu đồ tròn có thể trở nên khó đọc và kém hiệu quả.
```{figure} ../img/pie_chart.png
---
name: pie_chart
---
Biểu đồ Pie Chart thể hiện thị phần các hãng điện thoại di động năm 2023.
```

## Tree Map
Biểu đồ **Tree Map** là một loại biểu đồ dùng để hiển thị dữ liệu phân cấp (hierarchical data) dưới dạng các hình chữ nhật lồng nhau. Mỗi hình chữ nhật đại diện cho một danh mục hoặc mục con, với kích thước và màu sắc tương ứng với các giá trị định lượng của chúng. Biểu đồ Tree Map giúp hiển thị mối quan hệ giữa các phần tử trong cấu trúc phân cấp và so sánh kích thước tương đối của chúng một cách trực quan và hiệu quả.
```{figure} ../img/tree_map.png
---
name: tree_map
---
Giá trị GDP của mỗi quốc gia năm 2021 (Nguồn: World Bank 2021).
```




