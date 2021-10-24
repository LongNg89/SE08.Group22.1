# G-code là tên gọi chung cho một ngôn ngữ thuần văn bản mà máy CNC có thể hiểu được
* G-code bắt nguồn như là một dự án được phát triển bởi MIT cuối những năm 50. Vì sự phát triển hữu cơ của dự án mà không có 1 chuẩn G-code chung mà tất cả đều sử dụng. Có rất nhiều tiêu chuẩn khác nhau và các máy CNC không thể hiểu được tất cả. Vì vậy, sử dụng phiên bản G-code nào tuỳ thuộc vào máy đang sử dụng.
* Việc tuân thủ các tiêu chuẩn ít gặp vấn đề hơn khi sử dụng G-code được tạo bởi các gói CAM hiện đại, cung cấp nhiều bộ xử lý hậu kỳ để lựa chọn. Bộ xử lý hậu kỳ xuất ra G-code thích hợp cho một máy hoặc các dòng máy cụ thể. 
    * Bằng việc sử dụng các máy CNC hiện đại cùng với phần mềm, chúng ta sẽ không cần thiết phải nhập G-code một cách thủ công. Các phần mềm CAD/CAM và máy điều khiển sẽ làm thay công việc này.
# Ví dụ hướng dẫn vẽ hình vuông bằng máy
![content-table](https://f38-zpg.zdn.vn/3956706865987300749/39013be663a5abfbf2b4.jpg)
* ## Phân tích:
  * Bước 1: Đặt bút lên giấy - `G20 F20 X0 Y0 Z0`
      * `G20`: Sử dụng hệ đo lường Anh (đơn vị inches). Để đổi sang hệ Metric (đơn vị mm), dùng lệnh `G21`.
      * `F20`: Feed. Di chuyển theo chiều ngang 20 inches mỗi phút.
      * `X0 Y0 Z0`: Di chuyển công cụ về vị trí 0 trên trục X, Y, đưa trục Z đến bề mặt vật liệu.
  * Bước 2: Di chuyển bút 1 inch lên trên - `G1 Y1`
      * `G1`: Ra lệnh cho máy di chuyển với tốc độ được đặt ở bước 1 (`F20`). `G1` là lệnh di chuyển với tốc độ được điều khiển, `G0` là di chuyển với tốc độ tối đa.
      * `Y1`: Di chuyển đầu bút 1 inch theo hướng Y dương, _từ vị trí hiện tại của đầu công cụ_ (Hiện đang ở Y=0). Với phần lớn các máy, khi chúng ta đứng trước máy, hướng Y sẽ là trước và sau. Lệnh di chuyển dương sẽ đưa dao cắt đi xa ra và lệnh di chuyển âm ngược lại.
  * Bước 3: Di chuyển bút 1 inch sang phải - `G1 X1`
      * `G1`: Tương tự như trên.
      * `X1`: Di chuyển đầu bút 1 inch theo hướng X dương, _từ vị trí hiện tại của đầu công cụ_ (Hiện đang ở X=0). Với phần lớn các máy, khi chúng ta đứng trước máy, hướng X sẽ là trái và phải. Lệnh di chuyển dương sẽ đưa dao cắt sang phải và lệnh di chuyển âm ngược lại.
  * Bước 4: Di chuyển bút 1 inch xuống dưới - `G1 Y0`
      * `G1`: Tương tự như trên.
      * `Y0`: Ra lệnh cho máy di chuyển đến Y0 theo hướng Y âm. Lệnh này sẽ đưa đầu máy về phía bạn.
      > Theo mặc định, phần lớn các lệnh di chuyển trong G-Code là tuyệt đối. Nên nhớ máy di chuyển theo các tọa độ xác định. G-code chỉ định vị trí, không chỉ định hướng. Các toạ độ là tuyệt đối có nghĩa là chúng không phụ thuộc vào bước di chuyển trước đó.
  * Bước 5: Di chuyển bút 1 inch sang trái - `G1 X0`
      * `G1`: Tương tự như trên.
      * `X0`: Ra lệnh cho máy di chuyển đến X0 theo hướng X âm. Lệnh này sẽ đưa đầu máy sang trái 1 inch
  * Bước 6: Nhấc bsut i inch khỏi bề mặt - `G1 Z1`
      * `G1`: Tương tự như trên
      * `Z1`: Ra lệnh cho máy di chuyển theo hướng Z dương 1 inch 

* Thứ tự các lệnh
  * Cũng giống như phương trình toán học, G-code cũng có thứ tự ưu tiên các lệnh như sau (chú thích sẽ được thông dịch đầu tiên và các lệnh đổi công cụ cuối cùng):
  ```
  Cao nhất:  Chú thích (Comments)
             Tốc độ chạy dao (Feed rate)
             Tốc độ trục quay (Spindle speed)
             Chọn công cụ (Select tool)
  Thấp nhất: Thay đổi công cụ (Change tool)
  ```
# Bảng các lệnh gia công G
```
**Mã lệnh**         **Mô tả**
G00                 Di chuyển dao nhanh
G01                 Cắt theo đường thẳng
G02                 Cắt cung tròn theo chiều kim đồng hồ
G03                 Cắt cung tròn ngược chiều kim đồng hồ
G04                 Dừng di chuyển dao trong một khoảng thời gian ấn định
G10                 Thiết lập toạ độ của các bàn kẹp phôi, thông số bảng thay dao
G12                 Cắt lỗ tròn theo chiều kim đồng hồ
G13                 Cắt lỗ tròn theo chiều ngược kim đồng hồ
G15/G16             Toạ độ cực
G17                 Thiết lập XY là mặt phẳng gia công
G18                 Thiết lập XZ là mặt phẳng gia công
G19                 Thiết lập YZ là mặt phẳng gia công
G20/G21             Thiết lập đơn vị chiều dài (in/mm)
G28                 Đưa dao về vị trí tham chiếu
G28.1               Đưa dao về vị trí tham chiếu theo tham số trục đi kèm
G30                 Đưa dao về vị trí tham chiếu thay thế                
G31                 Dò toạ độ đầu dao trong thay dao bằng tay hoặc thay dao tự động
G40                 Tắt chế độ bù dao
G41/G42             Bật chế độ bù dao trái G41, bù dao phải G42 
G43                 Bật chế độ bù chiều cao dao cắt
G49                 Tắt chế độ bù chiều dài cán dao
G50                 Đưa tất cả các tỉ số kéo dãn của các toạ độ về 1
G51                 Thiết lập tỉ số kéo dãn của toạ độ
G52                 Dịch chuyển gốc toạ độ tương đối
G53                 Di chuyển trong toạ độ tuyệt đối
G54                 Sử dụng toạ độ của bàn kẹp phôi 1
G55                 Sử dụng toạ độ của bàn kẹp phôi 2
G56                 Sử dụng toạ độ của bàn kẹp phôi 3
G57                 Sử dụng toạ độ của bàn kẹp phôi 4
G58                 Sử dụng toạ độ của bàn kẹp phôi 5
G59                 Sử dụng toạ độ của bàn kẹp phôi 6
G61/G64             Chế độ kiểm soát đường chạy dao: dừng chính xác/ vận tốc không đổi
G68/G69             Xoay hệ toạ độ/ Huỷ chế độ xoay toạ độ
G70                 Chu kỳ cố định, nhiều chu kỳ lặp lại, để hoàn thiện (bao gồm cả đường viền)
G71                 Chu kỳ cố định, nhiều chu kỳ lặp lại, để gia công thô (nhấn mạnh trục Z)
G73                 Khoan tốc độ cao/ lỗ sâu/ có chế độ bẻ gãy phoi
G80                 Thoát chế độ khoan gộp
G81                 Khoan lỗ (di chuyển tới các lỗ)
G82                 Khoan lỗ với đầu dao di chuyển tới các toạ độ các lỗ - có điểm dừng gia công
G83                 Khoan lỗ (di chuyển tới các lỗ) - có chế độ bẻ gãy phoi
G85/G86/G88/G89     Khoan các lỗ - di chuyển theo cung tròn
G90                 Chuyển sang chế độ di chuyển trong hệ toạ độ tuyệt đối
G90.1               Chuyển sang chế độ tương đối IJK
G91                 Chuyển sang chế độ tương đối IJ
G91.1               Chuyển sang chế độ tương đối IJK
G92                 Thay đổi gốc hệ trục toạ độ theo giá trị đưa vào (vị trí dao cắt không di chuyển khi thực hiện lệnh)
G92.x               Xoá bỏ chế độ lệnh G92
G93                 Di chuyển theo tốc độ cắt 1/F
G94                 Di chuyển theo tốc độ cắt F
G98                 Rút dao nhanh theo Z trong các lệnh khoan
G99                 Rút dao nhanh theo R trong các lệnh khoan
```