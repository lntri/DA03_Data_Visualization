# Các dạng biểu đồ phân phối dữ liệu
**Cú pháp chung**: `sns.<ten bieu do>(data = dataframe, x= <column_name>, y = <column_name>,…)`


Các dạng biểu đồ thể hiện phân phối dữ liệu đóng vai trò quan trọng trong việc hiểu và phân tích dữ liệu. Chúng giúp chúng ta nhanh chóng nắm bắt được đặc điểm tổng quát của một tập dữ liệu, như xu hướng trung tâm, sự phân tán, và hình dạng của phân phối. Những biểu đồ này không chỉ giúp chúng ta đưa ra những nhận định chính xác mà còn hỗ trợ trong việc truyền đạt thông tin một cách trực quan và dễ hiểu đến người xem. Việc sử dụng đúng loại biểu đồ có thể làm nổi bật những đặc điểm quan trọng của dữ liệu, giúp đưa ra quyết định dựa trên dữ liệu một cách hiệu quả hơn.

## Density Plot
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

## Box Plot
`Box Plot`, hay còn gọi là biểu đồ hộp, là một cách hiệu quả để tóm tắt phân phối dữ liệu. Nó hiển thị năm số tóm tắt quan trọng: giá trị nhỏ nhất, tứ phân vị thứ nhất, trung vị, tứ phân vị thứ ba, và giá trị lớn nhất. Hộp chính giữa đại diện cho 50% dữ liệu ở giữa, với đường ngang trong hộp là trung vị. Các điểm nằm ngoài giá trị nhỏ nhất và giá trị lớn nhất được coi là các giá trị ngoại lệ và được biểu diễn riêng lẻ. `Box Plot` rất hữu ích trong việc so sánh phân phối giữa nhiều nhóm dữ liệu, cho phép ta dễ dàng nhận ra sự khác biệt về trung tâm, độ phân tán và sự xuất hiện của các giá trị ngoại lệ. Nó cũng giúp phát hiện nhanh chóng sự bất đối xứng trong phân phối dữ liệu.

**Cú pháp**: `sns.boxplot(data = dataframe, x= <column_name>, y = <column_name>,…)`
```{figure} ../img/boxplot_outliers_1.png
---
name: boxplot_outlier
---
Box Plot cũng là dạng biểu đồ phân phối nhưng phân phối giá trị theo khoảng gọi là tứ phân vị.
```

Có 2 cách vẽ biểu đồ Box Plot: phân tích đơn biến (biến liên tục) và phân tích biến phân loại – biến liên tục.

### Phân tích đơn biến (biến liên tục)
Phân tích đơn biến là việc xem xét một biến số duy nhất tại một thời điểm. Khi sử dụng `Box Plot` cho phân tích đơn biến với biến liên tục, chúng ta tạo ra một biểu đồ hộp duy nhất cho toàn bộ tập dữ liệu. Phân tích này giúp chúng ta hiểu được phân phối tổng thể của biến, bao gồm xu hướng trung tâm, độ phân tán, và sự xuất hiện của các giá trị ngoại lệ.

**Cú pháp**: `sns.boxplot(data=titanic, x='age')`
```{figure} ../img/boxplot_bien_lien_tuc.png
---
name: boxplot_bien_lien_tuc
---
Phân tích đơn biến về tuổi của hành khách dao động như thế nào trong tập dữ liệu titanic.
```

### Phân tích biến phân loại – biến liên tục
Phân tích này liên quan đến việc xem xét mối quan hệ giữa một biến phân loại (categorical) và một biến liên tục. Trong Box Plot, chúng ta tạo ra nhiều hộp, mỗi hộp đại diện cho một nhóm của biến phân loại. Phân tích này cho phép chúng ta so sánh phân phối của biến liên tục giữa các nhóm khác nhau. Chúng ta có thể dễ dàng nhận ra sự khác biệt về trung vị, độ phân tán, và sự xuất hiện của các giá trị ngoại lệ giữa các nhóm.

**Cú pháp**: `sns.boxplot(data=titanic, x='class', y='age')`
```{figure} ../img/boxplot_bien_phan_loai_lien_tuc.png
---
name: boxplot_bien_phan_loai_lien_tuc
---
Phân tích biến phân loại – biến liên tục: Sự phân bổ về độ tuổi giữa các hạng vé khác nhau như thế nào trong tập dữ liệu titanic.
```


## Violin Plot
`Violin Plot` là sự kết hợp của Box Plot và Density Plot. Nó có hình dạng giống như một cây đàn violin, với phần rộng nhất thể hiện nơi dữ liệu tập trung nhiều nhất. Phần giữa của Violin Plot thường chứa một Box Plot thu nhỏ, cung cấp thông tin về các tứ phân vị và trung vị. Đường cong bên ngoài cho thấy phân phối dữ liệu, tương tự như Density Plot. `Violin Plot` đặc biệt hữu ích khi muốn hiểu sâu hơn về cấu trúc của dữ liệu, cho phép ta nhận ra các đặc điểm như tính đa phương thức (nhiều đỉnh) mà có thể bị bỏ qua trong Box Plot. Nó cũng giúp so sánh phân phối giữa nhiều nhóm dữ liệu một cách trực quan, cho thấy không chỉ các giá trị tóm tắt mà còn cả hình dạng tổng thể của phân phối.

**Cú pháp**: `sns.violinplot(x='class', y='age', hue='sex', data=titanic)`
```{figure} ../img/violin_plot.png
---
name: violin_plot
---
Biểu đồ Violin thể hiện tuổi của hành khách phân phối như thế nào khi xét theo giới tính và hạng vé trong tập dữ liệu titanic.
```


## Swarm Plot
`Swarm Plot` là một biểu đồ thể hiện tất cả các điểm dữ liệu riêng lẻ mà không bị chồng chéo. Mỗi điểm trong `Swarm Plot` đại diện cho một quan sát trong tập dữ liệu. Các điểm được xếp dọc theo một trục (thường là trục y) và được "đẩy" sang ngang để tránh chồng lên nhau. Kết quả là một hình dạng giống như một đám ong, nơi phần rộng nhất cho biết nơi có nhiều điểm dữ liệu tập trung nhất. `Swarm Plot` rất hữu ích khi ta muốn thấy được phân phối thực tế của dữ liệu, đặc biệt khi số lượng điểm dữ liệu không quá lớn. Nó cho phép ta nhìn thấy mọi điểm dữ liệu, giúp phát hiện các mẫu hình, cụm, hoặc giá trị ngoại lệ mà có thể bị che giấu trong các loại biểu đồ khác. `Swarm Plot` cũng thường được kết hợp với các loại biểu đồ khác như Box Plot để cung cấp cái nhìn toàn diện hơn về dữ liệu.

**Cú pháp**: `sns.swarmplot(x='class', y='fare', hue='survived', data=titanic)`
```{figure} ../img/swarm_plot.png
---
name: swarm_plot
---
Biểu đồ Swarm Plot trả lời cho câu hỏi: <i><b>Liệu hành khách mua vé giá cao hơn có khả năng sống sót cao hơn không?</b></i> trong tập dữ liệu titanic.
```


## Strip Plot
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
