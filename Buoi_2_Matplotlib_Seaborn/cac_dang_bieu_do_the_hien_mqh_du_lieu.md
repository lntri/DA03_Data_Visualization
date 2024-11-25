# Các dạng biểu đồ thể hiện mối quan hệ dữ liệu
Các dạng biểu đồ thể hiện mối quan hệ dữ liệu đóng vai trò quan trọng trong việc khám phá và hiểu rõ cách các biến số trong một tập dữ liệu tương tác với nhau. Chúng giúp nhà phân tích dữ liệu và người ra quyết định nhanh chóng nhận ra các mẫu hình, xu hướng, và mối tương quan giữa các biến số khác nhau. Biểu đồ mối quan hệ không chỉ cho phép chúng ta xác định xem các biến có liên quan đến nhau hay không, mà còn giúp đánh giá mức độ và bản chất của mối quan hệ đó. Điều này đặc biệt quan trọng trong nhiều lĩnh vực như khoa học dữ liệu, nghiên cứu thị trường, và phân tích tài chính, nơi việc hiểu rõ cách các yếu tố khác nhau ảnh hưởng lẫn nhau là chìa khóa để đưa ra quyết định thông minh và dự đoán chính xác.

## Regression Plot
`Regression Plot`, hay biểu đồ hồi quy, là một công cụ mạnh mẽ để khám phá mối quan hệ tuyến tính giữa hai biến số. Biểu đồ này kết hợp một biểu đồ phân tán, hiển thị các điểm dữ liệu riêng lẻ, với một đường hồi quy thể hiện xu hướng chung của mối quan hệ. Trục ngang (x) thường biểu diễn biến độc lập, trong khi trục dọc (y) thể hiện biến phụ thuộc. Đường hồi quy giúp chúng ta dễ dàng nhận ra xu hướng tổng thể: nếu đường này đi lên, nó chỉ ra một mối quan hệ tích cực; nếu đi xuống, nó thể hiện một mối quan hệ tiêu cực. Độ dốc của đường này cho biết mức độ mạnh mẽ của mối quan hệ. `Regression Plot` thường đi kèm với một vùng bóng mờ xung quanh đường hồi quy, biểu thị khoảng tin cậy của dự đoán. Biểu đồ này đặc biệt hữu ích khi muốn dự đoán giá trị của một biến dựa trên giá trị của biến khác, và khi cần đánh giá mức độ phù hợp của mô hình hồi quy với dữ liệu.
**Cú pháp**: `sns.regplot(data=tip, x='total_bill', y='tip')`

```{figure} ../img/regression_plot.png
name: regression_plot
---
Biểu đồ Regression Plot giúp khám phá mối quan hệ giữa tổng tiền hóa đơn và tiền tip: tổng bill càng cao thì tiền tip càng nhiều. Nhờ đó hiểu rõ hơn về hành vi khách hàng trong việc để lại tiền tip.
```


## Heatmap
`Heatmap`, hay bản đồ nhiệt, là một công cụ trực quan hóa mạnh mẽ để hiển thị mối quan hệ giữa nhiều biến số cùng một lúc. Trong `Heatmap`, dữ liệu được biểu diễn bằng một ma trận màu sắc, trong đó mỗi ô đại diện cho mối quan hệ giữa hai biến. Màu sắc của mỗi ô thể hiện cường độ hoặc giá trị của mối quan hệ: màu sáng thường biểu thị giá trị cao, trong khi màu tối biểu thị giá trị thấp. `Heatmap` đặc biệt hữu ích khi làm việc với ma trận tương quan, nơi nó có thể nhanh chóng cho thấy các cặp biến có mối tương quan mạnh mẽ. Biểu đồ này cho phép người xem nhanh chóng xác định các mẫu hình và nhóm trong dữ liệu, cũng như phát hiện các giá trị bất thường. Một ưu điểm lớn của `Heatmap` là khả năng hiển thị một lượng lớn thông tin trong một không gian nhỏ gọn, giúp so sánh nhiều biến số cùng một lúc. Tuy nhiên, việc giải thích `Heatmap` đôi khi có thể phức tạp và đòi hỏi sự quen thuộc với dữ liệu và ngữ cảnh.

**Cú pháp**: `sns.heatmap(data = tip.corr(), annot=True, cmap='coolwarm')`

```{figure} ../img/heat_map_tip.png
name: heat_map_tip
---
Biểu đồ Heatmap thể hiện mối tương quan giữa các biến số như tổng giá trị hóa đơn (total_bill), tiền tip (tip) và số lượng thực khách (size).
```


## Pair Plot
`Pair Plot` là một cách mạnh mẽ để khám phá mối quan hệ giữa nhiều biến số trong một tập dữ liệu. Nó tạo ra một ma trận của biểu đồ, trong đó mỗi biến được so sánh với tất cả các biến khác. Trên đường chéo chính của ma trận thường là histogram hoặc KDE plot của mỗi biến, cho phép xem xét phân phối của từng biến riêng lẻ. Các ô khác trong ma trận là biểu đồ phân tán, mỗi ô thể hiện mối quan hệ giữa hai biến. `Pair Plot` cho phép người xem nhanh chóng nhận ra các mẫu hình, xu hướng, và mối tương quan giữa các cặp biến khác nhau. Nó đặc biệt hữu ích trong giai đoạn khám phá dữ liệu ban đầu, giúp nhà phân tích xác định những biến nào có mối quan hệ đáng quan tâm và đáng được nghiên cứu sâu hơn. `Pair Plot` cũng có thể được tùy chỉnh để hiển thị các nhóm dữ liệu khác nhau bằng cách sử dụng màu sắc, giúp so sánh mối quan hệ giữa các biến trong các phân nhóm khác nhau của dữ liệu. Tuy nhiên, khi số lượng biến lớn, `Pair Plot` có thể trở nên phức tạp và khó đọc.

**Cú pháp**: `sns.pairplot(tip, hue='sex')`

```{figure} ../img/pair_plot.png
name: pair_plot
---
Mối quan hệ giữa các biến liên tục (như tuổi và giá vé) và các biến phân loại (như giới tính, lớp vé, và tỉ lệ sống sót) thông qua biểu đồ Pair Plot.
```
