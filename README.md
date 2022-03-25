# Tình hình Covid tại Việt Nam đến 20/9/2020

This is my project in the Data Visualization course at the university.

## Nội dung
1. [Mô tả dữ liệu](Mô-tả-dữ-liệu)
2. [Trực quan và phân tích](Trực-quan-và-phân-tích)
3. [Áp dụng mô hình học máy](Áp-dụng-mô-hình-học-máy)


## Mô tả dữ liệu

1. **Dữ liệu về các bệnh nhân từ [Bộ Y Tế](https://ncov.moh.gov.vn/).**

Vì trang này không cho sẵn file dataset nên nhóm đã sử dụng thư viện selenium kết hợp với thư viện requests (python) để tiến hành lấy dữ liệu.

2. Dữ liệu về sự thay đổi các thông số về dịch bệnh từ trang web [worldometers](https://www.worldometers.info/coronavirus/) và lấy riêng cho Việt Nam.

Vì trang web chỉ hiển thị 3 ngày gần nhất nên nhóm lấy dữ liệu hằng ngày. Và để các con số cập nhật chính xác thì nhóm chỉ lấy dữ liệu sau khi ngày đó đã kết thúc (Lấy ở mục Yesterday hoặc 2 days ago).

Thư viện được sử dụng để lấy dữ liệu là requests và beautifulsoup (bs4) (python)

Sau đó, tiền xử lý dữ liệu lấy riêng dữ liệu cho Việt Nam và ghép các dữ liệu đó vào chung một file dataset.


## Trực quan và phân tích

Một số dashboard nhóm phân tích (những dashboard khác có thể xem trong file pdf): 

### Dashboard chính

[Dashboard](/Dashboard/Dashboard.png)

- Biểu đồ tròn bên trái thể hiện tỷ lệ của các tình trạng bệnh nhân Covid-19 tại Việt Nam, trong đấy chiếm tỷ lệ cao nhất là các bệnh nhân đã được chữa khỏi với tỷ lệ rất cao là 88.18% hay cụ thể là 940 bệnh nhân đã được chữa khỏi, tiếp đến là các bệnh nhân đang điều trị chiếm tỷ lệ 8.26%, số lượng bệnh nhận tử vong cả do COVID-19 lẫn không do virus này đều ở mức khá thấp, lần lượt là 3.28% và 0.28%.

- Biểu đồ tròn bên phải thể hiện phân bố về quốc tịch của các bệnh nhân tại Việt Nam. Khá rõ ràng với việc chúng ta cố gắng đóng của biên giới và kiểm soát dịch từ ngoài nước vào nên tỷ lệ số người bệnh là người nước ngoài rất thấp so với người VN, cụ thể chỉ chiếm 7.13% trong tổng số 1066 người bệnh tính đến thời điểm được lấy dữ liệu.

- Biểu đồ cột thống kê quốc tịch của các bệnh nhân ở Việt Nam, theo biểu đồ này có thể thấy rõ, những nơi có lượng bệnh nhân có quốc tịch không phải người Việt Nam thường là các thành phố lớn như Đà Nẵng, Hà Nội, Thành phố Hồ Chí Minh hoặc địa điểm du lịch nổi tiếng và có nhiều du khách nước ngoài như Vũng Tàu và tỷ lệ thường không chiếm đa số. Thành phố có nhiều người nước ngoài bị mắc bệnh nhất là Thành phố Hồ Chí Minh với 26 ca. Có một trường hợp đặc biệt đó là tỉnh Quảng Ninh, tỉnh này có số người mắc bệnh là người nước ngoài cao hơn người trong nước, cụ thể có 6 ca mắc bệnh ở Quảng Ninh là người nước ngoài trong khi người Việt Nam mắc bệnh ở đây là 5 ca.

- Biểu đồ chuyển động thể hiện phân bố về độ tuổi của các bệnh nhân mắc COVID-19 ở Việt Nam, có thể thấy rõ ràng rằng bệnh từ trẻ em vài tháng tuổi cho đến các cụ già gần 100 tuổi đều có ca mắc bệnh, nên COVID-19 không phải bệnh dành cho một 1 độ tuổi nhất định, và khác với nhận định ban đầu của mọi người, tỷ lệ người trẻ tuổi (10-30 tuổi) cũng có tỷ lệ mắc bệnh cao không khác gì những lứa tuổi lớn hơn.

- Bản đồ phân bố tình hình bệnh của Việt Nam, có thể thấy rõ ổ dịch lớn nhất nước là nằm ở Đà Nẵng với số lượng tử vong đủ để thể hiện rõ ràng trên bản đồ, bên cạnh đó, các tỉnh, khu vực nằm xung quanh các thành phố lớn như Hà Nội, Thành phố Hồ Chí Minh đều bị ảnh hưởng nặng nề. Bên cạnh tâm dịch Đà Nặng, rõ ràng nhận thấy khu vực đồng bằng Sông Hồng, đồng bằng Sông Cửu Long, vừng Đông Nam Bộ và vùng Tây Bắc là những nơi có lượng mắc bệnh tập trung thành khu vực đáng chú ý nhất.

### Dashboard về độ tuổi

[Dashboard về độ tuổi](/Dashboard/DBofAge.png)

Histogram dưới đây thể hiện mức độ phân bố của độ tuổi cũng như tình trạng của các bệnh nhân. Một lần nữa ta thấy được, bệnh được phủ rộng qua các độ tuổi, không nhất thiết phải là người lớn tuổi mới là đối tượng bị bệnh. Ngược lại, số lượng những người bị bệnh từ 20 đến 30 tuổi chiếm số lượng vượt trội so với các lứa tuổi khác. Thế nhưng, đa phần các trường hợp tử vòng thì lại rơi vào những người có độ tuổi trên 50 tuổi, với một ngoại lệ duy nhất. Và như các thông số đã nêu từ trước, số ca được chữa khỏi vẫn chiếm đa số trong tất cả các độ tuổi.

### Dashboard về số ca nhiễm mới

[Dashboard về số ca nhiễm mới](/Dashboard/DBofNewCases.png)

Biểu đồ đường thể hiện biến đông trong số ca nhiễm mới mỗi ngày trong hơn 1 tháng từ ngày 9/8 đến ngày 17/9. Có thể thấy được rằng trong khoảng 10 ngày đầu tiên số ca nhiễm mới tăng một cách đột biến, số lượng là rất lớn, sau đấy số lượng tăng theo ngày giảm dần, đến những ngày cuối thì rất ít, có nhiều ngày liền không có ca mắc mới.

Biểu đồ thứ hai: thể hiện sự tăng giảm của số nhiễm mới và số ca được trị khỏi trong khoảng thời gian xét dữ liệu. Có thể chi biểu đồ thành 2 giai đoạn, giải đoạn trước 21/8 và sau mốc thời gian trên. Trước ngày 21/8 có thể thấy qua từng ngày dù có biến động lớn giữa 2 giá trị nhưng chênh lệch vẫn là rất lớn và đáng kể. Thế nhưng sau mốc thời gian này, gần như không có sự khác biệt giữa 2 giá trị trên, gần như là tương đồng, trong đó về số ca nhiễm mới vẫn ít nhiều cao hơn số ca hồi phục mỗi ngày, dù chênh lệch là không còn lớn nữa.

### Dashboard về trạng thái

[Dashboard về trạng thái](/Dashboard/DBofStatus.png)

Các biểu đồ khác nhau thể hiện tỷ lệ tình trạng các bệnh nhân mắc Covid-19 tại Việt Nam. Tuy cách thể hiện là khác nhau nhưng đều thể hiện chung một ý chính. Các bệnh nhân đã được chữa khỏi vẫn chiếm tỷ lệ cao nhất và bỏ xa các tình trạng khác, Số lượng bệnh nhận đang điều trị tuy không cao bằng số người được chữa khỏi, nhưng vẫn không phải là quá lớn. Tỷ lệ tử vong do virus lẫn không do Virus đều không quá cao.


## Áp dụng mô hình học máy
Nhóm sử dụng 2 thư viện là `sklearn` và `statmodels` với 2 mô hình là OLS và ARIMA để dự đoán số ca nhiễm của ngày kế tiếp.