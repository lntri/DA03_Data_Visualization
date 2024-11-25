# Dạng biểu đồ thể hiện xu hướng dữ liệu
**Cú pháp**: `sns.lineplot(data = dataframe, x= <column_name>, y = <column_name>,…)`

Biểu đồ thể hiện xu hướng dữ liệu đóng vai trò quan trọng trong việc phân tích và truyền đạt thông tin về sự thay đổi của dữ liệu theo thời gian hoặc theo một biến số khác. Chúng giúp người xem nhanh chóng nắm bắt được hướng phát triển, mức độ tăng giảm, và các điểm đột biến trong dữ liệu. Biểu đồ xu hướng không chỉ cho phép nhìn thấy bức tranh tổng thể về quá trình biến động của dữ liệu mà còn giúp dự đoán các xu hướng trong tương lai. Đây là công cụ không thể thiếu trong nhiều lĩnh vực như kinh tế, khoa học, và quản lý dự án, giúp các nhà phân tích và người ra quyết định có cái nhìn sâu sắc về dữ liệu, từ đó đưa ra các quyết định dựa trên thông tin chính xác và cập nhật.

## Line Plot
`Line Plot`, hay biểu đồ đường, là một trong những dạng biểu đồ phổ biến nhất để thể hiện xu hướng dữ liệu. Nó sử dụng các điểm dữ liệu được kết nối bằng đường thẳng để biểu diễn sự thay đổi của một biến số theo thời gian hoặc theo một biến số khác. Trục ngang (x) thường biểu diễn thời gian hoặc một biến số độc lập, trong khi trục dọc (y) thể hiện giá trị của biến số phụ thuộc. Line Plot đặc biệt hữu ích trong việc hiển thị xu hướng liên tục và mượt mà, cho phép người xem dễ dàng nhận ra các mẫu hình như tăng, giảm, hoặc dao động theo chu kỳ. Nó cũng cho phép so sánh nhiều bộ dữ liệu trên cùng một biểu đồ bằng cách sử dụng nhiều đường khác nhau. Một ưu điểm lớn của Line Plot là khả năng hiển thị một lượng lớn dữ liệu một cách rõ ràng và súc tích, giúp người xem nhanh chóng nắm bắt được xu hướng tổng thể cũng như các biến động ngắn hạn. Tuy nhiên, cần lưu ý rằng Line Plot giả định có sự liên tục giữa các điểm dữ liệu, do đó nó phù hợp nhất với dữ liệu liên tục hoặc dữ liệu được đo lường thường xuyên.

**Cú pháp**: `sns.lineplot(data = msft_stock, x=msft_stock.index, y=msft_stock["Close"])`
```{figure} ../img/line_plot.png
name: line_plot
---
Biểu đồ Line Plot thể hiện xu hướng biến động giá đóng cổ phiếu Microsoft trong năm 2023.
```
