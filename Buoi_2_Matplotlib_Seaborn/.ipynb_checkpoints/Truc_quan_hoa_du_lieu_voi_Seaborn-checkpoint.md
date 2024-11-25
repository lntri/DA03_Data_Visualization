# Trực quan hóa dữ liệu với Seaborn

## Các dạng biểu đồ phân phối dữ liệu
**Cú pháp chung**: `sns.<ten bieu do>(data = dataframe, x= <column_name>, y = <column_name>,…)`


<!-- > this is a quote -->

Các dạng biểu đồ thể hiện phân phối dữ liệu đóng vai trò quan trọng trong việc hiểu và phân tích dữ liệu. Chúng giúp chúng ta nhanh chóng nắm bắt được đặc điểm tổng quát của một tập dữ liệu, như xu hướng trung tâm, sự phân tán, và hình dạng của phân phối. Những biểu đồ này không chỉ giúp chúng ta đưa ra những nhận định chính xác mà còn hỗ trợ trong việc truyền đạt thông tin một cách trực quan và dễ hiểu đến người xem. Việc sử dụng đúng loại biểu đồ có thể làm nổi bật những đặc điểm quan trọng của dữ liệu, giúp đưa ra quyết định dựa trên dữ liệu một cách hiệu quả hơn.

### Density Plot
`Biểu đồ mật độ (Density Plot)` là một biểu đồ thể hiện phân phối dữ liệu dưới dạng đường cong liên tục. Nó cho ta thấy xác suất xuất hiện của các giá trị trong tập dữ liệu. Phần cao nhất của đường cong chỉ ra giá trị xuất hiện nhiều nhất, trong khi độ rộng của đường cong cho biết mức độ phân tán của dữ liệu. `Density Plot` hữu ích trong việc nhận biết hình dạng tổng thể của phân phối dữ liệu, cho phép ta dễ dàng xác định xem phân phối có đối xứng hay lệch về một bên. Biểu đồ Density sẽ thể hiện bằng các dạng biểu đồ lệch phải (hay còn gọi là Right – Skew, Positive – Skew), đối xứng (hay còn gọi là đồ thị hình chuông – Bell curved), lệch trái (hay còn gọi là Left – skew, Negative Skew) thông qua các giá trị thống kê Mean, Median, Mode. Nó cũng giúp phát hiện các đỉnh trong dữ liệu, chỉ ra có thể có nhiều nhóm con trong tập dữ liệu. Biểu đồ này đặc biệt hữu ích khi so sánh phân phối của nhiều nhóm dữ liệu khác nhau, vì các đường cong có thể được vẽ chồng lên nhau mà vẫn dễ nhìn.

```{figure} ../img/density_skew.png
---
name: density_skew
---
Density là biểu đồ thể hiện phân phối mật độ xác suất tương tự như Histogram, nhưng thay vì là hình các cột bar như Histogram thì Density thể hiện đường phân phối KDE để thể hiện mật độ xác suất.
```

**Cú pháp**: `sns.displot(data = titanic, x= "age")`

```{figure} ../img/histogram_density.png
---
name: histogram_density
---
Density Plot không khác gì Histogram cả, cũng là biểu đồ cột bar và đếm tần suất xảy ra của các giá trị.
```

**Cú pháp**: `sns.displot(data = titanic, x= "age", kind= "kde")`
```{figure} ../img/kde_density.png
---
name: kde_density
---
Khi thêm thuộc tính `kind= kde`, lúc này từ các cột bar sẽ chuyển thành các đường phân phối kde và trục y lúc này không còn là count nữa, mà thể hiện giá trị của hàm mật độ phân phối.
```

**Cú pháp**: `sns.displot(data=titanic, x='age', kind='kde', hue = 'survived')`
```{figure} ../img/density_hue.png
---
name: density_hue
---
Lúc này biểu đồ sẽ tách phân phối của **người sống sót** riêng và **người không sống sót** riêng chỉ bằng một tham số duy nhất là `hue`.
```

**Cú pháp**: `sns.kdeplot(data=titanic, x='age', hue='survived', fill=True)`
```{figure} ../img/kde_plot.png
---
name: kde_plot
---
Chúng ta có thể biểu diễn biểu đồ Density Plot bằng `kde plot`.
```

### Box Plot
`Box Plot`, hay còn gọi là biểu đồ hộp, là một cách hiệu quả để tóm tắt phân phối dữ liệu. Nó hiển thị năm số tóm tắt quan trọng: giá trị nhỏ nhất, tứ phân vị thứ nhất, trung vị, tứ phân vị thứ ba, và giá trị lớn nhất. Hộp chính giữa đại diện cho 50% dữ liệu ở giữa, với đường ngang trong hộp là trung vị. Các điểm nằm ngoài giá trị nhỏ nhất và giá trị lớn nhất được coi là các giá trị ngoại lệ và được biểu diễn riêng lẻ. `Box Plot` rất hữu ích trong việc so sánh phân phối giữa nhiều nhóm dữ liệu, cho phép ta dễ dàng nhận ra sự khác biệt về trung tâm, độ phân tán và sự xuất hiện của các giá trị ngoại lệ. Nó cũng giúp phát hiện nhanh chóng sự bất đối xứng trong phân phối dữ liệu.

**Cú pháp**: `sns.boxplot(data = dataframe, x= <column_name>, y = <column_name>,…)`
```{figure} ../img/boxplot_outliers_1.png
---
name: boxplot_outlier
---
Box Plot cũng là dạng biểu đồ phân phối nhưng phân phối giá trị theo khoảng gọi là tứ phân vị.
```

Có 2 cách vẽ biểu đồ Box Plot: phân tích đơn biến (biến liên tục) và phân tích biến phân loại – biến liên tục.

#### Phân tích đơn biến (biến liên tục)
Phân tích đơn biến là việc xem xét một biến số duy nhất tại một thời điểm. Khi sử dụng `Box Plot` cho phân tích đơn biến với biến liên tục, chúng ta tạo ra một biểu đồ hộp duy nhất cho toàn bộ tập dữ liệu. Phân tích này giúp chúng ta hiểu được phân phối tổng thể của biến, bao gồm xu hướng trung tâm, độ phân tán, và sự xuất hiện của các giá trị ngoại lệ.

**Cú pháp**: `sns.boxplot(data=titanic, x='age')`
```{figure} ../img/boxplot_bien_lien_tuc.png
---
name: boxplot_bien_lien_tuc
---
Phân tích đơn biến về tuổi của hành khách dao động như thế nào trong tập dữ liệu titanic.
```

#### Phân tích biến phân loại – biến liên tục
Phân tích này liên quan đến việc xem xét mối quan hệ giữa một biến phân loại (categorical) và một biến liên tục. Trong Box Plot, chúng ta tạo ra nhiều hộp, mỗi hộp đại diện cho một nhóm của biến phân loại. Phân tích này cho phép chúng ta so sánh phân phối của biến liên tục giữa các nhóm khác nhau. Chúng ta có thể dễ dàng nhận ra sự khác biệt về trung vị, độ phân tán, và sự xuất hiện của các giá trị ngoại lệ giữa các nhóm.

**Cú pháp**: `sns.boxplot(data=titanic, x='class', y='age')`
```{figure} ../img/boxplot_bien_phan_loai_lien_tuc.png
---
name: boxplot_bien_phan_loai_lien_tuc
---
Phân tích biến phân loại – biến liên tục: Sự phân bổ về độ tuổi giữa các hạng vé khác nhau như thế nào trong tập dữ liệu titanic.
```


### Violin Plot
`Violin Plot` là sự kết hợp của Box Plot và Density Plot. Nó có hình dạng giống như một cây đàn violin, với phần rộng nhất thể hiện nơi dữ liệu tập trung nhiều nhất. Phần giữa của Violin Plot thường chứa một Box Plot thu nhỏ, cung cấp thông tin về các tứ phân vị và trung vị. Đường cong bên ngoài cho thấy phân phối dữ liệu, tương tự như Density Plot. `Violin Plot` đặc biệt hữu ích khi muốn hiểu sâu hơn về cấu trúc của dữ liệu, cho phép ta nhận ra các đặc điểm như tính đa phương thức (nhiều đỉnh) mà có thể bị bỏ qua trong Box Plot. Nó cũng giúp so sánh phân phối giữa nhiều nhóm dữ liệu một cách trực quan, cho thấy không chỉ các giá trị tóm tắt mà còn cả hình dạng tổng thể của phân phối.

**Cú pháp**: `sns.violinplot(x='class', y='age', hue='sex', data=titanic)`
```{figure} ../img/violin_plot.png
---
name: violin_plot
---
Biểu đồ Violin thể hiện tuổi của hành khách phân phối như thế nào khi xét theo giới tính và hạng vé trong tập dữ liệu titanic.
```


### Swarm Plot
`Swarm Plot` là một biểu đồ thể hiện tất cả các điểm dữ liệu riêng lẻ mà không bị chồng chéo. Mỗi điểm trong `Swarm Plot` đại diện cho một quan sát trong tập dữ liệu. Các điểm được xếp dọc theo một trục (thường là trục y) và được "đẩy" sang ngang để tránh chồng lên nhau. Kết quả là một hình dạng giống như một đám ong, nơi phần rộng nhất cho biết nơi có nhiều điểm dữ liệu tập trung nhất. `Swarm Plot` rất hữu ích khi ta muốn thấy được phân phối thực tế của dữ liệu, đặc biệt khi số lượng điểm dữ liệu không quá lớn. Nó cho phép ta nhìn thấy mọi điểm dữ liệu, giúp phát hiện các mẫu hình, cụm, hoặc giá trị ngoại lệ mà có thể bị che giấu trong các loại biểu đồ khác. `Swarm Plot` cũng thường được kết hợp với các loại biểu đồ khác như Box Plot để cung cấp cái nhìn toàn diện hơn về dữ liệu.

**Cú pháp**: `sns.swarmplot(x='class', y='fare', hue='survived', data=titanic)`
```{figure} ../img/swarm_plot.png
---
name: swarm_plot
---
Biểu đồ Swarm Plot trả lời cho câu hỏi: <i><b>Liệu hành khách mua vé giá cao hơn có khả năng sống sót cao hơn không?</b></i> trong tập dữ liệu titanic.
```


### Strip Plot
`Strip Plot` là một phiên bản đơn giản hơn của Swarm Plot. Nó hiển thị mỗi điểm dữ liệu như một dấu chấm riêng biệt, nhưng không cố gắng tránh sự chồng chéo giữa các điểm. Tất cả các điểm được đặt dọc theo một đường thẳng, thường là trục y. Vị trí của mỗi điểm trên trục này phản ánh giá trị của nó, trong khi vị trí ngang được chọn ngẫu nhiên trong một phạm vi nhất định. `Strip Plot` hữu ích khi ta muốn xem xét phân phối tổng thể của dữ liệu và nhận ra các giá trị cụ thể. Nó đặc biệt hiệu quả khi số lượng điểm dữ liệu không quá lớn và khi ta muốn so sánh phân phối giữa các nhóm khác nhau. Mặc dù đơn giản, `Strip Plot` vẫn cung cấp một cái nhìn trực quan về mật độ của dữ liệu ở các vùng khác nhau. Nó thường được kết hợp với các loại biểu đồ khác như Box Plot để cung cấp thêm thông tin chi tiết về phân phối dữ liệu.

**Cú pháp**: `sns.stripplot(x='class', y='fare', hue='survived', data=titanic)`
```{figure} ../img/strip_plot.png
name: strip_plot
---
Biểu đồ Strip Plot trả lời cho câu hỏi: <i><b>Liệu hành khách mua vé giá cao hơn có khả năng sống sót cao hơn không?</b></i> trong tập dữ liệu titanic.
```

```{note}
Các điểm dữ liệu trong cả biểu đồ Strip plot và Swam plot được giữ đúng như giá trị thật của nó (chứ không bị biến đối như Histogram hay Density).
```



## Các dạng biểu đồ thể hiện thống kê dữ liệu
**Cú pháp**: `sns.<ten bieu do>(data = dataframe, x= <column_name>, y = <column_name>,…)`

Các dạng biểu đồ thể hiện thống kê dữ liệu đóng vai trò quan trọng trong việc truyền tải thông tin một cách trực quan và dễ hiểu. Chúng giúp người xem nhanh chóng nắm bắt được những đặc điểm chính của dữ liệu, như sự phân bố, tần suất xuất hiện, hoặc so sánh giữa các nhóm khác nhau. Biểu đồ thống kê không chỉ làm cho dữ liệu trở nên dễ tiếp cận hơn mà còn giúp phát hiện các mẫu hình và xu hướng mà có thể khó nhận ra khi chỉ nhìn vào các bảng số liệu. Chúng là công cụ không thể thiếu trong quá trình phân tích dữ liệu, hỗ trợ việc ra quyết định dựa trên dữ liệu và truyền đạt kết quả nghiên cứu một cách hiệu quả.

### Bar Plot
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

### Count Plot
`Count Plot` là một biến thể đặc biệt của Bar Plot, được sử dụng để hiển thị số lượng quan sát trong mỗi danh mục của một biến phân loại. Nó tự động đếm số lượng mục trong mỗi nhóm và hiển thị kết quả dưới dạng các cột. Trục x thường biểu diễn các danh mục của biến phân loại, trong khi trục y thể hiện số lượng quan sát. `Count Plot` đặc biệt hữu ích khi bạn muốn nhanh chóng hiểu được phân phối của một biến phân loại trong tập dữ liệu của mình. Nó cho phép bạn dễ dàng nhận ra những danh mục xuất hiện nhiều nhất và ít nhất. `Count Plot` cũng có thể được sử dụng để so sánh phân phối của một biến phân loại giữa các nhóm khác nhau bằng cách sử dụng màu sắc hoặc chia nhỏ các cột. Một lợi ích lớn của Count Plot là nó tự động tính toán và hiển thị số lượng, giúp tiết kiệm thời gian và giảm khả năng sai sót khi phải đếm thủ công.

**Cú pháp**: `sns.countplot(data=titanic, x='survived', hue='survived')`
```{figure} ../img/count_plot.png
name: count_plot
---
Thống kê số lượng hành khách còn sống và qua đời bằng biểu đồ Count Plot.
```

### Pie Chart
`Pie Chart` (biểu đồ tròn) là một loại biểu đồ được thiết kế dưới dạng hình tròn, chia thành các phần tương tự như những lát cắt của một chiếc bánh. Mỗi phần đại diện cho tỷ lệ hoặc phần trăm của một thành phần so với tổng thể. `Pie Chart` giúp người xem dễ dàng hiểu được cách các thành phần trong một tập dữ liệu được phân chia và so sánh tỷ lệ của chúng một cách trực quan.
```{figure} ../img/pie_chart_Apple.png
name: pie_chart_Apple
---
Cơ cấu doanh thu theo các dòng sản phẩm của Apple trong quý 4 niên độ tài chính năm 2023 (Nguồn: MacRumors) (thể hiện bằng biểu đồ Pie Chart).
```

### Donut Chart
`Donut Chart` là một dạng biến thể của Pie Chart (biểu đồ tròn), với đặc điểm là phần trung tâm bị rỗng, tạo thành hình dạng giống chiếc bánh donut. `Donut Chart` được sử dụng để biểu diễn tỷ lệ hoặc phần trăm của các thành phần trong tổng thể, tương tự Pie Chart, nhưng khác biệt về thiết kế hình học, mang lại cảm giác hiện đại và thẩm mỹ hơn. Phần trống ở giữa biểu đồ có thể được tận dụng để chèn tiêu đề, số liệu tổng hợp hoặc các thông tin bổ sung, giúp tăng tính trực quan và hấp dẫn mà không làm cho biểu đồ trở nên phức tạp.
```{figure} ../img/donut_chart.png
name: donut_chart
---
Cơ cấu doanh thu theo các dòng sản phẩm của Apple trong quý 4 niên độ tài chính năm 2023 (Nguồn: MacRumors) (thể hiện bằng biểu đồ Donut Chart).
```



## Dạng biểu đồ thể hiện xu hướng dữ liệu
**Cú pháp**: `sns.lineplot(data = dataframe, x= <column_name>, y = <column_name>,…)`

Biểu đồ thể hiện xu hướng dữ liệu đóng vai trò quan trọng trong việc phân tích và truyền đạt thông tin về sự thay đổi của dữ liệu theo thời gian hoặc theo một biến số khác. Chúng giúp người xem nhanh chóng nắm bắt được hướng phát triển, mức độ tăng giảm, và các điểm đột biến trong dữ liệu. Biểu đồ xu hướng không chỉ cho phép nhìn thấy bức tranh tổng thể về quá trình biến động của dữ liệu mà còn giúp dự đoán các xu hướng trong tương lai. Đây là công cụ không thể thiếu trong nhiều lĩnh vực như kinh tế, khoa học, và quản lý dự án, giúp các nhà phân tích và người ra quyết định có cái nhìn sâu sắc về dữ liệu, từ đó đưa ra các quyết định dựa trên thông tin chính xác và cập nhật.

### Line Plot
`Line Plot`, hay biểu đồ đường, là một trong những dạng biểu đồ phổ biến nhất để thể hiện xu hướng dữ liệu. Nó sử dụng các điểm dữ liệu được kết nối bằng đường thẳng để biểu diễn sự thay đổi của một biến số theo thời gian hoặc theo một biến số khác. Trục ngang (x) thường biểu diễn thời gian hoặc một biến số độc lập, trong khi trục dọc (y) thể hiện giá trị của biến số phụ thuộc. Line Plot đặc biệt hữu ích trong việc hiển thị xu hướng liên tục và mượt mà, cho phép người xem dễ dàng nhận ra các mẫu hình như tăng, giảm, hoặc dao động theo chu kỳ. Nó cũng cho phép so sánh nhiều bộ dữ liệu trên cùng một biểu đồ bằng cách sử dụng nhiều đường khác nhau. Một ưu điểm lớn của Line Plot là khả năng hiển thị một lượng lớn dữ liệu một cách rõ ràng và súc tích, giúp người xem nhanh chóng nắm bắt được xu hướng tổng thể cũng như các biến động ngắn hạn. Tuy nhiên, cần lưu ý rằng Line Plot giả định có sự liên tục giữa các điểm dữ liệu, do đó nó phù hợp nhất với dữ liệu liên tục hoặc dữ liệu được đo lường thường xuyên.

**Cú pháp**: `sns.lineplot(data = msft_stock, x=msft_stock.index, y=msft_stock["Close"])`
```{figure} ../img/line_plot.png
name: line_plot
---
Biểu đồ Line Plot thể hiện xu hướng biến động giá đóng cổ phiếu Microsoft trong năm 2023.
```



## Các dạng biểu đồ thể hiện mối quan hệ dữ liệu
Các dạng biểu đồ thể hiện mối quan hệ dữ liệu đóng vai trò quan trọng trong việc khám phá và hiểu rõ cách các biến số trong một tập dữ liệu tương tác với nhau. Chúng giúp nhà phân tích dữ liệu và người ra quyết định nhanh chóng nhận ra các mẫu hình, xu hướng, và mối tương quan giữa các biến số khác nhau. Biểu đồ mối quan hệ không chỉ cho phép chúng ta xác định xem các biến có liên quan đến nhau hay không, mà còn giúp đánh giá mức độ và bản chất của mối quan hệ đó. Điều này đặc biệt quan trọng trong nhiều lĩnh vực như khoa học dữ liệu, nghiên cứu thị trường, và phân tích tài chính, nơi việc hiểu rõ cách các yếu tố khác nhau ảnh hưởng lẫn nhau là chìa khóa để đưa ra quyết định thông minh và dự đoán chính xác.

### Regression Plot
`Regression Plot`, hay biểu đồ hồi quy, là một công cụ mạnh mẽ để khám phá mối quan hệ tuyến tính giữa hai biến số. Biểu đồ này kết hợp một biểu đồ phân tán, hiển thị các điểm dữ liệu riêng lẻ, với một đường hồi quy thể hiện xu hướng chung của mối quan hệ. Trục ngang (x) thường biểu diễn biến độc lập, trong khi trục dọc (y) thể hiện biến phụ thuộc. Đường hồi quy giúp chúng ta dễ dàng nhận ra xu hướng tổng thể: nếu đường này đi lên, nó chỉ ra một mối quan hệ tích cực; nếu đi xuống, nó thể hiện một mối quan hệ tiêu cực. Độ dốc của đường này cho biết mức độ mạnh mẽ của mối quan hệ. `Regression Plot` thường đi kèm với một vùng bóng mờ xung quanh đường hồi quy, biểu thị khoảng tin cậy của dự đoán. Biểu đồ này đặc biệt hữu ích khi muốn dự đoán giá trị của một biến dựa trên giá trị của biến khác, và khi cần đánh giá mức độ phù hợp của mô hình hồi quy với dữ liệu.
**Cú pháp**: `sns.regplot(data=tip, x='total_bill', y='tip')`

```{figure} ../img/regression_plot.png
name: regression_plot
---
Biểu đồ Regression Plot giúp khám phá mối quan hệ giữa tổng tiền hóa đơn và tiền tip: tổng bill càng cao thì tiền tip càng nhiều. Nhờ đó hiểu rõ hơn về hành vi khách hàng trong việc để lại tiền tip.
```


### Heatmap
`Heatmap`, hay bản đồ nhiệt, là một công cụ trực quan hóa mạnh mẽ để hiển thị mối quan hệ giữa nhiều biến số cùng một lúc. Trong `Heatmap`, dữ liệu được biểu diễn bằng một ma trận màu sắc, trong đó mỗi ô đại diện cho mối quan hệ giữa hai biến. Màu sắc của mỗi ô thể hiện cường độ hoặc giá trị của mối quan hệ: màu sáng thường biểu thị giá trị cao, trong khi màu tối biểu thị giá trị thấp. `Heatmap` đặc biệt hữu ích khi làm việc với ma trận tương quan, nơi nó có thể nhanh chóng cho thấy các cặp biến có mối tương quan mạnh mẽ. Biểu đồ này cho phép người xem nhanh chóng xác định các mẫu hình và nhóm trong dữ liệu, cũng như phát hiện các giá trị bất thường. Một ưu điểm lớn của `Heatmap` là khả năng hiển thị một lượng lớn thông tin trong một không gian nhỏ gọn, giúp so sánh nhiều biến số cùng một lúc. Tuy nhiên, việc giải thích `Heatmap` đôi khi có thể phức tạp và đòi hỏi sự quen thuộc với dữ liệu và ngữ cảnh.

**Cú pháp**: `sns.heatmap(data = tip.corr(), annot=True, cmap='coolwarm')`

```{figure} ../img/heat_map_tip.png
name: heat_map_tip
---
Biểu đồ Heatmap thể hiện mối tương quan giữa các biến số như tổng giá trị hóa đơn (total_bill), tiền tip (tip) và số lượng thực khách (size).
```


### Pair Plot
`Pair Plot` là một cách mạnh mẽ để khám phá mối quan hệ giữa nhiều biến số trong một tập dữ liệu. Nó tạo ra một ma trận của biểu đồ, trong đó mỗi biến được so sánh với tất cả các biến khác. Trên đường chéo chính của ma trận thường là histogram hoặc KDE plot của mỗi biến, cho phép xem xét phân phối của từng biến riêng lẻ. Các ô khác trong ma trận là biểu đồ phân tán, mỗi ô thể hiện mối quan hệ giữa hai biến. `Pair Plot` cho phép người xem nhanh chóng nhận ra các mẫu hình, xu hướng, và mối tương quan giữa các cặp biến khác nhau. Nó đặc biệt hữu ích trong giai đoạn khám phá dữ liệu ban đầu, giúp nhà phân tích xác định những biến nào có mối quan hệ đáng quan tâm và đáng được nghiên cứu sâu hơn. `Pair Plot` cũng có thể được tùy chỉnh để hiển thị các nhóm dữ liệu khác nhau bằng cách sử dụng màu sắc, giúp so sánh mối quan hệ giữa các biến trong các phân nhóm khác nhau của dữ liệu. Tuy nhiên, khi số lượng biến lớn, `Pair Plot` có thể trở nên phức tạp và khó đọc.

**Cú pháp**: `sns.pairplot(tip, hue='sex')`

```{figure} ../img/pair_plot.png
name: pair_plot
---
Mối quan hệ giữa các biến liên tục (như tuổi và giá vé) và các biến phân loại (như giới tính, lớp vé, và tỉ lệ sống sót) thông qua biểu đồ Pair Plot.
```





