## Trực quan đa biến với lưới
Trực quan đa biến với lưới là một phương pháp mạnh mẽ trong phân tích dữ liệu, cho phép chúng ta khám phá và hiểu rõ mối quan hệ giữa nhiều biến số cùng một lúc. Phương pháp này tạo ra một ma trận các biểu đồ nhỏ, mỗi biểu đồ thể hiện mối quan hệ giữa các biến trong các điều kiện hoặc nhóm khác nhau. Điều này giúp chúng ta không chỉ nhìn thấy xu hướng tổng thể mà còn phát hiện ra những mẫu hình và sự khác biệt tinh tế giữa các phân nhóm trong dữ liệu. Trực quan đa biến với lưới đặc biệt hữu ích khi chúng ta muốn so sánh nhiều biến số hoặc xem xét ảnh hưởng của một hoặc nhiều biến phân loại đến mối quan hệ giữa các biến khác. Phương pháp này giúp tối đa hóa lượng thông tin được truyền đạt trong một không gian hạn chế, cho phép người xem nhanh chóng nắm bắt được bức tranh toàn cảnh về dữ liệu.


### Facet Grid
**Cú pháp chung**: `sns.FacetGrid(data = dataframe, row= <column_name>, col= <column_name>,…)`
`Facet Grid` là một công cụ trực quan hóa mạnh mẽ trong thư viện Seaborn của Python, được sử dụng để tạo ra một lưới các biểu đồ con dựa trên một hoặc hai biến phân loại. Mỗi biểu đồ con trong lưới đại diện cho một tổ hợp cụ thể của các giá trị từ các biến phân loại này. `Facet Grid` cho phép chúng ta xem xét mối quan hệ giữa các biến số trong các nhóm hoặc điều kiện khác nhau, giúp phát hiện các mẫu hình và xu hướng mà có thể bị bỏ qua khi nhìn vào dữ liệu tổng thể. Công cụ này đặc biệt hữu ích khi chúng ta muốn so sánh sự phân phối hoặc mối quan hệ giữa các biến số trong các phân nhóm khác nhau của dữ liệu. `Facet Grid` tự động xử lý việc chia nhỏ dữ liệu và tạo ra các biểu đồ con, đảm bảo rằng tất cả các biểu đồ đều có cùng tỷ lệ và định dạng, giúp dễ dàng so sánh giữa các nhóm. Nó cũng cung cấp nhiều tùy chọn để điều chỉnh cách hiển thị, như thay đổi loại biểu đồ, thêm các đường hồi quy, hoặc tùy chỉnh các yếu tố thẩm mỹ khác.

**Cú pháp**: `g = sns.FacetGrid(tip, col="day", hue="sex")`
             `g.map(sns.scatterplot, "total_bill", "tip",alpha = 0.7)`
```{figure} ../img/facet_grid_col.png
---
name: facet_grid_col
---
Dùng Facet Grid kết hợp với biểu đồ Scatter Plot để phân tích mối quan hệ giữa tổng số tiền hóa đơn và tiền tip, phân tách dữ liệu theo ngày (`col = day`) trong tuần và giới tính (`hue = sex`).
```

**Cú pháp**: `g = sns.FacetGrid(titanic, row="class", col="survived", hue="survived")`
             `g.map(sns.histplot, "age")`
```{figure} ../img/facet_grid_row_col.png
---
name: facet_grid_row_col
---
Phân tích mối quan hệ giữa tuổi (age) và số người sống sót trên tàu Titanic (survived) (`col` và `hue` đều là Survived), với mỗi hàng biểu đồ đại diện cho một nhóm khác nhau (`row = class`) về hạng vé (class).
```