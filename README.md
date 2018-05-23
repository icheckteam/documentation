## Tổng quan
Ichain là một blockchain được phát triển dựa trên Iendermint. Ichain làm cho việc triển khai, kết nối đa mạng lưới và chạy ứng dụng truy xuất chuỗi cung ứng trở nên dễ dàng hơn.

Ichain có thể được sử dụng như một mạng lưới riêng tư hoặc triển khai trên một mạng lưới công cộng.
## Kiến trúc ứng dụng
### Tài sản
Tài sản đại diện cho một hàng hóa đang được theo dõi bới chuỗi cung ứng. Hầu như mọi giao dịch đều tham chiếu đến số nhận dạng tài sản.

Một tài sản có chứa số nhận dạng duy nhất, tên, số lượng, danh sách tài sản, thuộc tính và danh sách chủ sở hữu và người giám hộ.

Chủ sở hữu chỉ được phép cập nhật thêm hoặc bớt số lượng tài sản đang nắm giữ.

Chủ sở hữu tài sản có thể gửi một đề nghị ủy thác quyền như một chủ sở hữu, người giám hộ hoặc một báo cáo viên kèm theo các thuộc tính được phép báo cáo.

Tài sản có thể kết hợp với một danh sách tài sản khác để tạo ra một tài sản có đặc tính mới. trường hợp này có thể là một sản phẩm được hoàn thiện từ nhiều nguồn nguyên liệu thô. Chủ sở hữu sẽ phải xây dựng một công thức xác định rằng đủ nguồn nguyên liệu thô để tạo ra số lượng sản phẩm tương ứng.

Các thuộc tính được cập nhật bởi chủ sở hữu và người giám hộ được lưu  trữ trong một danh sách thuộc tính bao gồm giá trị, thời gian và chữ ký của người báo cáo. Các thuộc tính được cập nhật ở trạng thái cuối cùng bởi vì điều này sẽ giảm tải số dữ liệu lưu trữ, và dễ dàng ghi chép thuộc tính mà hạn chế đọc và ghi chép lại toàn bộ lịch sử. 

Tuy nhiên dữ liệu lịch sử cập nhật thuộc tính có thể  được phân tích và ghi chép lại ở dữ liệu phía ứng dụng bằng việc đồng bộ lại các khối và danh sách giao dịch.
### Danh tính kỹ thuật số
Danh tính đề cập tới thông tin nhận dạng cá nhân, tổ chức, doanh nghiệp được cấp chứng chỉ số giống như chứng nhận đạt tiêu chuẩn nuôi trồng được cung cấp bởi cơ quan nhà nước, tổ chức chứng thực hoặc bên thứ 3 có khả năng xác thực danh tính. 

Danh tính bao gồm một số nhận dạng duy nhất, nội dung chứng chỉ, ngày hết hạn và người nhận. 

Tổ chức chứng thực được phát hàng và thu hồi các chứng chỉ số đã cấp phép cho cá nhân, tổ chức và doanh nghiệp.
### Vận chuyển
Những người đang nắm giữ khối lượng tài  sản được phép tạo đơn hàng đến đơn vị giao vận sau đó chuyển đến người mua.

Một đơn hàng có chứa số nhận dạng duy nhất, danh sách tài sản, trạng thái, người vận chuyển và người nhận. 

Chủ sở hữu được phép hủy đơn hàng, số lượng tài sản trong đơn hàng sẽ được hoàn lại như ban đầu.

Người vận chuyển có thể cập nhật trạng thái đã nhận hàng và có thể chuyển người nắm giữ mới trong trường hợp đơn hàng được nhận từ chủ sở hữu và chuyển đến người vận chuyển mới sau đó được giao tới khách hàng. Người vận chuyển có trách nhiệm báo cáo vị trí nhận hàng, ví trí chuyển giao hàng hóa.

Khách hàng có thể hoàn thành và theo dõi thông tin vị trí, người đang nắm giữ và hoàn thành đơn hàng.

Dữ liệu lịch sử vận chuyển được lưu trữ ở trạng thái cuối cùng tuy nhiên dữ liệu lịch sử có thể được ghi chép lại ở phía ứng dụng băng việc đồng bộ lại các khối và danh sách giao dịch trong khối.
### Bảo hành
Bảo hành được nói đến như một hợp đồng bảo đảm cho một tài sản được bán cho người mua mà bao gồm các bên tham gia như người bán, trung tâm bảo hành, người mua và cảnh sát

Hợp đồng bảo hành bao gồm một số nhận dạng duy nhất, số nhận dạng tài sản, ngày hết hạn và yêu cầu bảo hành

Người bán có sở hữu tài sản có thể tạo hợp đồng bảo hành theo nhu cầu người mua, hợp đồng bảo hành sau đó được chuyển đến người mua. Người mua có thể yêu cầu sửa chữa tại các trung tâm bảo hành có hỗ trợ bảo hành hoặc gửi thông báo đến cảnh sát với hành vi trộm cắm.

Dữ liệu lịch sử yêu cầu bảo hành được lưu trữ ở trạng thái cuối cùng tuy nhiên dữ liệu lịch sử có thể được ghi chép lại ở phía ứng dụng băng việc đồng bộ lại các khối và danh sách giao dịch trong khối.

### Cổ phần
Ichain sử dụng cơ chế đồng thuận "bằng chứng cổ phần"  trong đó các nút đồng thuận trong mạng lưới được gọi là những người xác thực. Người xác thực sẽ được yêu cầu gửi một số lượng đơn vị tiền tệ nội địa  để được có quyền biểu quyết tạo ra khối mới, số tiền có thể bị hủy nếu phát hiện sai trong quá trình đồng thuận. Việc áp dụng trừng phạt bằng  giá trị kinh tế góp phần làm tăng an toàn cho mạng lưới so với các thuật toán đồng thuận khác.

## Trường hợp sử dụng
### Ichain trong hệ thống quản trị doanh nghiệp:
Ichain được tích hợp trong các hệ thống quản trị doanh nghiệp làm tự động hóa việc trao đổi dữ liệu, trao đổi tài sản giữa nhiều tổ chức tham gia trong chuỗi cung ứng mà không cần phải nhập liệu thông tin bằng tay dẫn đến dữ liệu bị sai lệch. Dễ dàng thống kê và  kiểm soát lượng tồn kho,  phân phối, tiêu thụ trên thị trường, ngăn chặn hoàn toàn việc làm giả sản phẩm trên thị trường gây ảnh hưởng xấu đến thương hiệu doanh nghiệp. 
### Ichain trong thương mại điện tử:
Ichain được tích hợp trong hệ thống thương mại điện tử nhằm giảm thiểu tối đa thời gian xác minh nguồn gốc sản phẩm của người bán, giúp người mua hiểu rõ hơn về nguồn gốc sản phẩm, dễ dàng kết nối bất kỳ đối tác vận chuyển trong mạng lưới mà không cần phải viết thêm chương trình phụ trợ.
### Ichain trong thiết bị điện tử
Ichain được tích hợp trong các thiết bị điện tử để ghi chép lại toàn bộ quá trình theo dõi tài sản.
###Ichain trong xác minh danh tính
