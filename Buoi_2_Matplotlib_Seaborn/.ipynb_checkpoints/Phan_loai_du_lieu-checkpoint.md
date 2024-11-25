# Phân loại dữ liệu
Phân loại dữ liệu là bước đầu tiên và quan trọng trong quá trình phân tích và trực quan hóa dữ liệu. Hiểu rõ về các loại dữ liệu giúp chúng ta lựa chọn phương pháp phân tích và biểu diễn phù hợp, từ đó tạo ra những thông tin có giá trị. Dữ liệu được chia thành hai loại chính: **dữ liệu định lượng** và **dữ liệu định tính**, mỗi loại lại có những đặc điểm và cách xử lý riêng.
```{figure} ../img/phan_loai_du_lieu.png
---
name: phan_loai_du_lieu
---
Phân loại dữ liệu.
```

## Dữ liệu định lượng
**Dữ liệu định lượng**: còn được gọi là dữ liệu số, đóng vai trò quan trọng trong phân tích và trực quan hóa dữ liệu. Loại dữ liệu này bao gồm những thông tin có thể đo lường được bằng con số, như chiều cao, cân nặng, doanh thu, hay nhiệt độ. Đặc điểm nổi bật của dữ liệu định lượng là khả năng áp dụng các phép tính toán và phân tích thống kê, giúp chúng ta hiểu sâu hơn về xu hướng và mối quan hệ trong dữ liệu. Ví dụ, khi phân tích doanh số bán hàng của một cửa hàng, ta có thể tính tổng doanh thu, doanh thu trung bình hàng ngày, hoặc so sánh doanh thu giữa các tháng để đưa ra chiến lược kinh doanh phù hợp. Trong dữ liệu định lượng được chia ra làm 2 dạng nhỏ nữa là:

### Dữ liệu liên tục
**Dữ liệu liên tục**: Dữ liệu liên tục là một loại dữ liệu định lượng đặc biệt, có thể nhận bất kỳ giá trị nào trong một khoảng xác định, thường là kết quả của phép đo lường. Đặc điểm quan trọng của dữ liệu liên tục là sự tồn tại của sai số, nghĩa là giá trị đo được có thể dao động trong một phạm vi nhỏ. Ví dụ: Nhiệt độ ở trung tâm quận 5 hiện tại là 30 độ, nhưng ở bên phường 3 lại là 30,4 độ và ở bên phường 5 là 31 độ chẳng hạn (tức là sẽ có sai số ở nhiệt độ mỗi phường). Một ví dụ nữa là cân nặng, chúng ta để ý là thông số trên cái cân nào cũng sẽ có sai số +/- bao nhiêu đó . Dữ liệu liên tục thường được biểu diễn bằng số thực và là giá trị qua đo lường như chiều cao, nhiệt độ, cân nặng,… 

### Dữ liệu rời rạc
**Dữ liệu rời rạc**: Dữ liệu rời rạc là một loại dữ liệu định lượng quan trọng trong phân tích và trực quan hóa, đặc trưng bởi các giá trị riêng biệt và đếm được. Trong trực quan hóa, dữ liệu rời rạc thường được biểu diễn bằng biểu đồ cột hoặc biểu đồ điểm, giúp người xem dễ dàng so sánh và nhận biết sự khác biệt giữa các giá trị. Ví dụ như số lượng khách hàng, số lượng sản phẩm,…


## Dữ liệu định tính
**Dữ liệu định tính**: còn gọi là dữ liệu phân loại (categorical data), đóng vai trò quan trọng trong việc mô tả các đặc điểm hoặc thuộc tính không thể đo lường bằng số. Trong dữ liệu định tính được chia ra làm 2 dạng nhỏ nữa là:


### Dữ liệu thứ tự
**Dữ liệu thứ tự**: Dữ liệu thứ tự là một loại dữ liệu định tính đặc biệt, có tính chất phân cấp tự nhiên giữa các giá trị. Yếu tố này làm cho dữ liệu thứ tự trở nên quan trọng trong việc đánh giá và so sánh. Ví dụ đơn giản nhất có thể thấy khi chúng ta mua hang hay đi Grab, sẽ có 1 bảng khảo sát đánh giá mức độ hài lòng của khách hang là “rất không hài lòng”, “không hài lòng”, “bình thường”, “hài lòng” và “rất hài lòng” hoặc là bằng cấp “Khá”, “Giỏi”, “Xuất sắc”.


### Dữ liệu định danh
**Dữ liệu định danh**: Dữ liệu định danh là một dạng dữ liệu định tính đặc biệt, không có thứ tự hoặc thứ bậc tự nhiên giữa các giá trị. Loại dữ liệu này đóng vai trò quan trọng trong việc phân loại và nhóm các đối tượng dựa trên các đặc điểm không thể so sánh về mặt số lượng. Trong phân tích và trực quan hóa dữ liệu, việc nhận diện đúng dữ liệu định danh giúp chúng ta lựa chọn phương pháp biểu diễn phù hợp, như biểu đồ cột hoặc biểu đồ tròn, để thể hiện rõ sự phân bố của các nhóm. Ví dụ: giới tính thì có nam/nữ, màu sắc thì có đỏ/vàng/xanh, hay trên 1 website bán hàng, khi bấm vào danh mục “Sản phẩm” sẽ sổ ra Dropdown gồm “quần”, “áo”, “nịt”, “tất”,…

```{figure} ../img/phan_loai_du_lieu_dap_an_bt.png
---
name: phan_loai_du_lieu
---
Một số ví dụ về các kiểu dữ liệu.
```
