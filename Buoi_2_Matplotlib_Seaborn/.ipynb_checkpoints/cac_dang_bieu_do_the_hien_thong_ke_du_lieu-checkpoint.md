# Các dạng biểu đồ thể hiện thống kê dữ liệu
**Cú pháp**: `sns.<ten bieu do>(data = dataframe, x= <column_name>, y = <column_name>,…)`

Các dạng biểu đồ thể hiện thống kê dữ liệu đóng vai trò quan trọng trong việc truyền tải thông tin một cách trực quan và dễ hiểu. Chúng giúp người xem nhanh chóng nắm bắt được những đặc điểm chính của dữ liệu, như sự phân bố, tần suất xuất hiện, hoặc so sánh giữa các nhóm khác nhau. Biểu đồ thống kê không chỉ làm cho dữ liệu trở nên dễ tiếp cận hơn mà còn giúp phát hiện các mẫu hình và xu hướng mà có thể khó nhận ra khi chỉ nhìn vào các bảng số liệu. Chúng là công cụ không thể thiếu trong quá trình phân tích dữ liệu, hỗ trợ việc ra quyết định dựa trên dữ liệu và truyền đạt kết quả nghiên cứu một cách hiệu quả.

## Bar Plot
`Bar Plot`, hay biểu đồ cột, là một trong những dạng biểu đồ phổ biến và dễ hiểu nhất để thể hiện thống kê dữ liệu. Nó sử dụng các cột hình chữ nhật để biểu diễn giá trị của dữ liệu, với chiều cao của mỗi cột tương ứng với giá trị đó. `Bar Plot` thường được sử dụng để so sánh giá trị giữa các nhóm khác nhau hoặc để hiển thị sự thay đổi của một biến số theo thời gian. Trục ngang (x) thường biểu diễn các danh mục hoặc nhóm, trong khi trục dọc (y) thể hiện giá trị số. `Bar Plot` có thể được vẽ theo chiều dọc hoặc chiều ngang, tùy thuộc vào mục đích và không gian hiển thị. Một ưu điểm lớn của `Bar Plot` là khả năng hiển thị rõ ràng sự khác biệt về độ lớn giữa các giá trị, giúp người xem dễ dàng so sánh và đánh giá. Ngoài ra, `Bar Plot` cũng có thể được sử dụng để hiển thị nhiều nhóm dữ liệu cùng lúc thông qua việc sử dụng các cột được nhóm hoặc xếp chồng.

**Cú pháp**: `sns.barplot(data=tip, x="day", y="total_bill", errorbar=None)`
```{figure} ../img/bar_plot_1.png
name: bar_plot_1
---
Biểu đồ Bar Plot thể hiện giá trị tổng hóa đơn trung bình theo ngày.
```

Ở biểu đồ `Bar Plot` có một thuộc tính là <b>estimator</b>, thuộc tính này mặc định sẽ tính giá trị trung bình (mean) trên bộ dữ liệu. Chúng ta có thể thay đổi <b>estimator</b> thành các hàm khác như _median() (trung vị), sum() (tổng), max() (giá trị lớn nhất), min() (giá trị nhỏ nhất)_, hoặc bất kỳ hàm tùy chỉnh nào.

**Cú pháp**: `sns.barplot(data=tip, x="day", y="total_bill", errorbar=None, estimator= "sum")`
```{figure} ../img/bar_plot_1_sum.png
name: bar_plot_1_sum
---
Biểu đồ Bar Plot thể hiện tổng giá trị hóa đơn trong ngày với `estimator = 'sum'`.
```

## Count Plot
`Count Plot` là một biến thể đặc biệt của Bar Plot, được sử dụng để hiển thị số lượng quan sát trong mỗi danh mục của một biến phân loại. Nó tự động đếm số lượng mục trong mỗi nhóm và hiển thị kết quả dưới dạng các cột. Trục x thường biểu diễn các danh mục của biến phân loại, trong khi trục y thể hiện số lượng quan sát. `Count Plot` đặc biệt hữu ích khi bạn muốn nhanh chóng hiểu được phân phối của một biến phân loại trong tập dữ liệu của mình. Nó cho phép bạn dễ dàng nhận ra những danh mục xuất hiện nhiều nhất và ít nhất. `Count Plot` cũng có thể được sử dụng để so sánh phân phối của một biến phân loại giữa các nhóm khác nhau bằng cách sử dụng màu sắc hoặc chia nhỏ các cột. Một lợi ích lớn của Count Plot là nó tự động tính toán và hiển thị số lượng, giúp tiết kiệm thời gian và giảm khả năng sai sót khi phải đếm thủ công.

**Cú pháp**: `sns.countplot(data=titanic, x='survived', hue='survived')`
```{figure} ../img/count_plot.png
name: count_plot
---
Thống kê số lượng hành khách còn sống và qua đời bằng biểu đồ Count Plot.
```

## Pie Chart
`Pie Chart` (biểu đồ tròn) là một loại biểu đồ được thiết kế dưới dạng hình tròn, chia thành các phần tương tự như những lát cắt của một chiếc bánh. Mỗi phần đại diện cho tỷ lệ hoặc phần trăm của một thành phần so với tổng thể. `Pie Chart` giúp người xem dễ dàng hiểu được cách các thành phần trong một tập dữ liệu được phân chia và so sánh tỷ lệ của chúng một cách trực quan.
```{figure} ../img/pie_chart_Apple.png
name: pie_chart_Apple
---
Cơ cấu doanh thu theo các dòng sản phẩm của Apple trong quý 4 niên độ tài chính năm 2023 (Nguồn: MacRumors) (thể hiện bằng biểu đồ Pie Chart).
```

<!-- ## Donut Chart
`Donut Chart` là một dạng biến thể của Pie Chart (biểu đồ tròn), với đặc điểm là phần trung tâm bị rỗng, tạo thành hình dạng giống chiếc bánh donut. `Donut Chart` được sử dụng để biểu diễn tỷ lệ hoặc phần trăm của các thành phần trong tổng thể, tương tự Pie Chart, nhưng khác biệt về thiết kế hình học, mang lại cảm giác hiện đại và thẩm mỹ hơn. Phần trống ở giữa biểu đồ có thể được tận dụng để chèn tiêu đề, số liệu tổng hợp hoặc các thông tin bổ sung, giúp tăng tính trực quan và hấp dẫn mà không làm cho biểu đồ trở nên phức tạp.
```{figure} ../img/donut_chart.png
name: donut_chart
---
Cơ cấu doanh thu theo các dòng sản phẩm của Apple trong quý 4 niên độ tài chính năm 2023 (Nguồn: MacRumors) (thể hiện bằng biểu đồ Donut Chart).
``` -->


