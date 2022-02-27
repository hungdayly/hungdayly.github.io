# Giới thiệu về JavaScript

Hãy xem JavaScript có những gì đặc biệt, những gì chúng ta có thể đạt được với nó và những công nghệ nào khác hoạt động tốt với nó.

## JavaScript là gì?

Ban đầu JavaScript được tạo ra để "làm cho các trang web trở nên sống động".

Các chương trình trong ngôn ngữ này được gọi là "kịch bản" (script). Chúng có thể được viết ngay trong mã HTML của trang web và chạy tự động khi trang web được tải.

Các script được cung cấp và thực thi dưới dạng văn bản thuần túy. Chúng không cần các sự chuẩn bị hoặc biên soạn đặc biệt nào để chạy. Về điểm này JavaScript rất khác so với một ngôn ngữ khác có tên gần giống nó là Java.

Ngày nay, JavaScript có thể thực thi không chỉ trên trình duyệt mà còn trên máy chủ hoặc trên bất kỳ thiết bị nào có một chương trình đặc biệt gọi là JavaScript engine (trình thông dịch JavaScript).

Các JavaScript Engine trên trình duyệt đôi khi còn được gọi là "JavaScript virtual machine" (máy ảo JavaScript).

Các trình duyệt khác nhau có các JavaScript Engine khác nhau. Ví dụ:

- V8 - trong các trình duyệt Chrome, Opera và Edge.
- SpiderMonkey - trong trình duyệt Firefox.
- ...

## JavaScript có thể làm gì trên trình duyệt

JavaScript hiện đại là một ngôn ngữ lập trình "an toàn". Nó không cung cấp quyền truy cập cấp thấp vào bộ nhớ hoặc CPU, vì ban đầu nó được tạo cho các trình duyệt không yêu cầu những công việc này.

Khả năng của JavaScript phụ thuộc rất nhiều vào môi trường mà nó đang chạy. Ví dụ Node.js (môi trường chạy JavaScript chạy trên máy chủ) hỗ trợ các chức năng cho phép JavaScript đọc/ghi các file tùy ý, thực hiện các yêu cầu mạng, ...

JavaScript trong trình duyệt có thể thực hiện mọi thứ liên quan đến thao tác trang web, tương tác với người dùng và máy chủ web.

Ví dụ, JavaScript trong trình duyệt có thể:

- Thêm phần tử HTML mới vào trang, thay đổi nội dung hiện có, sửa đổi các style của CSS.
- Phản ứng lại với hành động của người dùng, chạy khi nhấp chuột, di chuyển con trỏ, nhấn phím.
- Gửi yêu cầu qua mạng tới các máy chủ ở xa, tải xuống và tài lên các file.
- Nhận và đặt cookie, đặt câu hỏi cho khách truy cập, hiển thị tin nhắn.
- Ghi nhớ dữ liệu ở phía máy khách trên bộ nhớ cục bộ.

## JavaScript không thể làm gì trên trình duyệt

Khả năng của JavaScript trên trình duyệt bị giới hạn vì an toàn của người dùng. Mục đích là để ngắn chặn một trang web xấu truy cập lén lút thông tin cá nhân hoặc gây hại cho thông tin của người dùng.

Ví dụ về những hạn chế đó bao gồm:

- JavaScript trên một trang web không được phép đọc/ghi các file trên ổ cứng, sao chép chúng hoặc chạy các chương trình trên ổ cứng. Nó không có quyền truy cập trực tiếp vào các chức năng của hệ điều hành.
  
    Các trình duyệt hiện đại cho phép JavaScript hoạt động với các tệp, nhưng quyền truy cập bị hạn chế và chỉ được cung cấp nếu người dùng thực hiện một số hành động nhất định, chẳng hạn như "thả" tệp vào cửa sổ trình duyệt hoặc chọn tệp thông qua thẻ `<input>`.

    Có nhiều cách để tương tác với máy ảnh/micrô và các thiết bị khác, nhưng chúng yêu cầu sự cho phép rõ ràng của người dùng. Vì vậy, một trang web hỗ trợ JavaScript không thể lén lút bật camera của bạn, ghi hình và gửi hình ảnh một cách bất hợp pháp khi chưa được sự cho phép của bạn.

- Các tab/cửa sổ khác nhau thường không biết về nhau. Ngay cả khi một cửa sổ ứng dụng JavaScript để mở một cửa sổ khác thì JavaScript trong cửa sổ này cũng không thể truy cập trang kia nếu chúng đến từ các trang khác nhau (từ một tên miền, giao thức hoặc công khác).

    Đây được gọi là "Same Origin Policy" (chính sách xuất sứ giống nhau). Để giải quyết vấn đề này, cả hai trang phải đồng ý trao đổi dữ liệu và chứa mã JavaScript đặc biệt để xử lý nó.

    Hạn chế này, một lần nữa, vì sự an toàn của người dùng. Một trang `https://anysite.com` mà người dùng mở không được phép truy cập vào một tab khác đang mở, chẳng hạn, có địa chỉ là `https://gmail.com` và lấy cắp thông tin từ đó.

- JavaScript có thể dễ dàng giao tiếp qua mạng với máy chủ chứa trang hiện tại. Nhưng khả năng nhận dữ liệu từ các trang web/tên miền khác của nó bị tê liệt trừ khi yêu cầu có chứa một thỏa thuận rõ ràng (được thể hiện trong tiêu đề HTTP của yêu cầu) và được chấp nhận từ phía trang web/tên miền này. Một lần nữa, đây là một giới hạn an toàn.

    ![](limitations.svg)


Các giới hạn như vậy không tồn tại nếu JavaScript được sử dụng bên ngoài trình duyệt, chẳng hạn như trên máy chủ. Các trình duyệt hiện đại cũng cho phép plugin/tiện ích mở rộng có thể yêu cầu các quyền mở rộng.

## Điều gì làm cho JavaScript trở nên độc đáo ?

Có ít nhất *ba* điều tuyệt vời về JavaScript:

- Tích hợp hoàn toàn với HTML/CSS.
- Những điều đơn giản được thực hiện một cách đơn giản.
- Được hỗ trợ bởi tất cả các trình duyệt và được bật theo mặc định.

JavaScript là công nghệ trình duyệt duy nhất kết hợp ba thứ này.

Đó là điều làm cho JavaScript trở nên độc đáo. Đó là lý do tại sao nó là công cụ phổ biến nhất để tạo giao diện trình duyệt.

Ngoài ra JavaScript cũng cho phép tạo các ứng dụng trên máy chủ, ứng dụng di động, ...

## Các ngôn ngữ dựa trên JavaScript

Cú pháp của JavaScript không phù hợp với nhu cầu của mọi người. Những người khác nhau muốn các tính năng khác nhau.

Điều đó là dễ hiểu, bởi vì các dự án và yêu cầu không thể giống nhau đối với tất cả mọi người.

Vì vậy, gần đây đã xuất hiện nhiều ngôn ngữ mới, được chuyển đổi sang JavaScript trước khi chúng chạy trong trình duyệt.

Các công cụ hiện đại làm cho quá trình chuyển đổi này diễn ra rất nhanh chóng và gần như vô hình trước con mắt của bạn. Điều này thực sự cho phép các nhà phát triển viết mã bằng ngôn ngữ khác và tự động chuyển đổi nó thành JavaScript một cách "bí mật".

Ví dụ về các ngôn ngữ như vậy:

- CoffeeScript: nó giới thiệu một cú pháp ngắn gọn hơn JavaScript gốc, cho phép chúng ta viết mã rõ ràng và chính xác hơn. Thông thường các nhà phát triển Ruby thích nó.
- TypeScript: tập trung vào việc bổ sung "kiểu dữ liệu nghiêm ngặt" cho JavaScript để đơn giản hóa việc phát triển và hỗ trợ các hệ thống phức tạp. Nó được phát triển bởi Microsoft.
- Flow: bổ sung tính năng nhập dữ liệu, nhưng theo một cách khác. Được phát triển bởi Facebook.
- Dart: là một ngôn ngữ độc lập có công cụ riêng chạy trong môi trường không có trình duyệt (như ứng dụng dành cho di động), nhưng cũng có thể được chuyển sang JavaScript. Được phát triển bởi Google.
- Brython: là một trình chuyển tiếp Python sang JavaScript cho phép viết các ứng dụng bằng Python thuần túy mà không cần JavaScript.
- Kotlin: là một ngôn ngữ lập trình hiện đại, ngắn gọn và an toàn, có thể nhắm mục tiêu trình duyệt hoặc Node.

Có nhiều. Tất nhiên, ngay cả khi chúng ta sử dụng một trong các ngôn ngữ trên, chúng ta cũng nên biết JavaScript để thực sự hiểu những gì chúng ta đang làm.

## Tóm lược

- Ban đầu JavaScript được tạo ra như một ngôn ngữ lập trình dành cho trình duyệt, nhưng bây giờ nó cũng được sử dụng trong nhiều môi trường khác.
- Ngày nay, JavaScript có một vị trí độc tôn, là ngôn ngữ trình duyệt được chấp nhận rộng rãi nhất, được tích hợp hoàn toàn với HTML/CSS.
- Có nhiều ngôn ngữ có thể được "chuyển đổi" sang JavaScript và cung cấp một số tính năng bổ sung nhất định. Ban nên xem qua chúng, ít nhất là trong thời gian ngắn, sau khi thành thạo JavaScript.