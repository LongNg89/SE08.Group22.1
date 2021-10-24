# SE08-Nhom22.1
Thử nghiệm code script bằng Gcode để cho máy cắt CNC thực hiện sản xuất đồ nội thất công nghiệp.

## Team Members:
### [Nguyễn Sỹ Phi Long](https://www.facebook.com/longnguyen.0809/)
### [Đàm Quỳnh Giang](https://www.facebook.com/duckiee.1701)
### [Nguyễn Thị Thảo Trang](https://www.facebook.com/nguyenthithaotrang2310)


# Mục lục:
1. [Idea](#idea)
2. [Goals](#goals)
3. [Objectives](#objectives)
4. [Technology & Tools](#technology-&-tools)
5. [System Architecture](#system-architecture)
6. [Project Report](#report)

<a name="idea"> </a>
## 1. Idea
* **Gia công cơ khí** là thuật ngữ chuyên ngành của lĩnh vực cơ khí. Cụm từ này chỉ toàn bộ thao tác sử dụng máy móc, công nghệ và các nguyên liệu vật lý để tạo ra thành phẩm có độ chính xác cao, tính ứng dụng tốt trong cuộc sống. Cùng với sự phát triển không ngừng của ngành cơ khí, các kỹ thuật trong gia công cơ khí cũng đạt được nhiều bước phát triển vượt bậc. Từ đó giúp con người tiết kiệm thời gian, công sức và đem lại hiệu quả sản xuất cao.

* Hiện nay, có 2 phương pháp gia công cơ khí để tạo ra những sản phẩm đáp ứng nhu cầu. Đó là gia công cơ khí chính xác và gia công cơ.
  * **Gia công cơ** là phương pháp cần đến đôi tay của người thợ cơ khí. Họ dùng sức và đôi tay của mình để mài, phay, tiện, cắt nhằm tạo ra các sản phẩm như ý muốn. Phương pháp này khá tốn sức và mất nhiều thời gian, nên đa số chỉ áp dụng tại các phân xưởng nhỏ.
  * **Gia công cơ khí chính xác** còn được gọi là gia công bằng máy CNC. Phương pháp này có độ chính xác cực cao theo khuôn mẫu hoặc bản vẽ, có độ tinh xảo cao. Máy CNC là loại máy gia công hiện đại, đa dạng, độ chế tác chuẩn, sắc nét. Nên được áp dụng khá rộng rãi ở những nhà xưởng vừa và lớn. Trên thị trường, máy CNC có các loại như CNC phay, tiện, máy laser, máy cắt CNC,... Sản phẩm được gia công trên loại máy này cũng rất đa dạng, bao gồm sắt, thép, inox, đồng, nhựa,...
  
* Khi nhu cầu toàn cầu về các sản phẩm gia công CNC tăng lên và thay đổi, nhiều sự đổi mới hiện đang diễn ra trong ngành gia công CNC.
  * **Robotics** – không chỉ là máy phay và máy tiện, CNC ngày càng được áp dụng cho robot công nghiệp. Trong một số nhà máy, máy móc không chỉ xử lý các công việc như cắt và hàn, mà còn vận chuyển và lắp ráp. 
  * **In 3D** – vừa là đối thủ cạnh tranh của gia công CNC vừa là quá trình bổ sung cho gia công tạo mẫu. In 3D công nghiệp cũng đang phát triển nhanh chóng. Trong khi gia công là một quy trình trừ (cắt gọt, chi tiết được tạo ra nhờ loại bỏ những phần không cần thiết của phôi). Bắt đầu với khối phôi lớn và cắt bỏ vật liệu để tạo thành hình dạng. Trong nhiều trường hợp, các nhà thiết kế có thể in 3D nguyên mẫu và sử dụng nó làm mẫu để định cấu hình thiết bị CNC. Trong các trường hợp khác, các sản phẩm có thể được in 3D chính xác từ phần mềm thiết kế. 
  * **At-Home CNC** – Thị trường bộ dụng cụ CNC DIY và máy móc CNC rẻ tiền đã tăng trưởng theo cấp số nhân trong vài thập kỷ qua. Mặc dù họ không cung cấp bất cứ điều gì mới về quy trình, các trạm CNC tại nhà này giúp việc phát triển sản phẩm trở nên dễ dàng hơn, nhanh hơn và rẻ hơn bao giờ hết. Với gánh nặng tài chính của ngành gia công kim loại giảm đáng kể. Gia công CNC hiện đại giúp mọi người đều có thể thỏa mãn ước mơ chế tạo những sản phẩm của mình.

* Tuy nhiên, kỹ thuật sử dụng máy CNC lại không hề dễ dàng, đòi hỏi trình độ của nhân công phải nắm rõ kiến thức về công nghệ thông tin, cấu tạo của máy, các quy tắc vận hành.
* Bài toán thực tế yêu cầu: Thử nghiệm code script bằng G-Code để cho máy cắt CNC thực hiện sản xuất đồ nội thất công nghiệp. Sinh viên sẽ được thực hành thử nghiệm chương trình trên xưởng có máy CNC.

<a name="goals"> </a>
## 2. Goals
* Cắt được sản phẩm bằng máy CNC từ script G-Code.

<a name="objectives"></a>
## 3. Objectives
* Sử dụng công cụ AlphaCAM để chuyển file DXF sang G-Code.
* Tinh chỉnh, tối ưu hóa G-Code.
* Từ G-Code đã có, sử dụng máy CNC cắt được sản phẩm hoàn chỉnh.

<a name="technology-&-tools"> </a>
## 4. Technology & Tools
* G-Code
* Github
* AlphaCAM Ultimate Simulator
* DXF2GCODE
* G-Code Simulator
* Visual Studio Code

<a name="system-architecture"> </a>
## 5. System Architecture

<a name="report"> </a>
## 6. Project Report

