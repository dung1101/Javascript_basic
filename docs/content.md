# 1.Cơ bản về Javascript
### Tất cả những đoạn mã Javascript đều phải đặt trong cặp thẻ mở `<script>` và thẻ đóng `</script>`
### cách đặt thẻ
* Internal:viết trong file html hiện tại
 ```
 <html>
    <head>
        <title></title>
        <script language="javascript">
            alert("Hello World!");
        </script>
    </head>
    <body>
         
    </body>
</html>
 ```
* viết ra một file js khác rồi import vào
 ```
 <script language="javascript" src="demo.js"></script>
 ```
* viết trực tiếp trong thẻ HTML
 ```
 <input type="button" onclick="alert(1)" value="Click Me"/>
 ```
 # 2.Biến và khai báo biến
 ## Khai báo biến
 - Để khai báo một biến ta sử dụng từ khóa  `var tenbien;`
 - Khai báo nhiêù biến `var tenbien1, tenbien2, tenbien3;`
 ## Kiểu dữ liệu
 kiểu chuỗi (String), số (Number), mảng (Array), đối tượng (Object)
 ## In giá trị của biến ra trình duyệt
 `document.write();`
 # 3.Hàm alert, confirm và prompt 
 ### Hàm alert() có nhiệm vụ in một thông báo popup, nó có một tham số truyền vào và tham số này chính là nội dung ta muốn thông báo với người dùng.
 ```
 <html>
  <head>
  </head>
  <body>
    <input type="button" onclick="alert('Xin chào các bạn')" value="Click Me"/>
  </body>
</html>
 ```
### Hàm confirm() cũng sẽ xuất hiện một thông báo popup nhưng nó có thêm hai sự lựa chọn là Yes và No, nếu người dùng chọn Yes thì nó trả về TRUE và ngược lại nếu chọn NO thì nó sẽ trả về FALSE. Nó cũng có một tham số truyền vào và tham số này chính là nội dung thông báo.
```
<html>
    <head>
        <title></title>
        <script language="javascript">
            confirm("Do you like freetuts.net");
        </script>
    </head>
    <body>
         
    </body>
</html>
```
### Hàm prompt() dùng  để lấy thông tin từ người dùng, gồm có hai tham số truyền vào là nội dung thông báo và giá trị ban đầu. Nếu người dùng không nhập vào thì giá trị nó sẽ trả về là NULL
```
<html>
    <head>
        <title></title>
        <script language="javascript">
            var t = prompt("Nhập tên của bạn", '');
            alert(t);
        </script>
    </head>
    <body>
         
    </body>
</html>
```
# 4.Toán tử
### Lưu ý với toán tử so sánh bằng
Chúng ta có hai toán tử so sánh bằng đó là toán tử == và ===
```
var a = 12; // a đang ở kiểu number
a = '12'; // a bây giờ là kiểu string

// TRUE vì cả hai đều có giá trị là 12
document.write(a == b); 
 
// FALSE vì mặc dù giá trị bằng nhau nhưng
// kiểu dữ liệu của a là number, của b là string
document.write(a === b);
```
# 5.if else
giống java
# 6.Switch 
giống java
# 7.Function
```
function name_of_function(var1, var2, var3, ...)
{
    // Some code
    return something;
}
```
dùng từ khóa `function` để định nghĩa<br/>
### Giá trị mặc định của tham số
Có một số trường hợp bạn muốn một tham số nào đó có thể được truyền hoặc không cần truyền vào đều được, lúc này chúng ta phải sử dụng nó như một tham số mặc định. Javascript không có cú pháp gán giá trị mặc định như PHP mà thay vào đó chúng ta sử dụng toán tử ||.
```
function showMessage(message)
{
   // Nếu message không được truyền vào hoặc giá trị nó là rỗng
   // thì sẽ được thay thế bằng giá trị 'Không có tin nhắn'
   message = message || 'Không có tin nhắn <br/>';
   document.write(message);
}
 
// Cách 1: không truyền tham số
showMessage();
 
// Cách 2: Truyền tham số
showMessage('Chào mừng bạn đến với freetuts.net');

```
# 10.console.log()
Trong Javascript có một hàm thường được sử dụng để debug đó là hàm console.log(), nó có nhiệm vụ show ra giá trị của tất cả các loại dữ liệu như number, integer, array, object, chính vì vậy khi muốn biết trong một biến đó có giá trị gì thì ta sẽ sử dụng hàm `console.log()`.
# 11.setTimeout() và setInterval() 
### Hàm setTimeout() dùng để thiết lập một khoảng thời gian nào đó sẽ thực hiện một nhiệm vụ nào đó và nó chỉ thực hiện đúng một lần.
Cú pháp: `setTimeout(function, time)`<br />
Trong đó:<br />
* function: là nội dung cần thực hiện, đây là một hàm
* time: là khoảng thời gian bao nhiêu (tính bằng mili giây) thì function đó sẽ thực hiện
```
setTimeout(function(){
    alert("Chào mừng bạn đến với freetuts.net");
}, 3000);
```
### Hàm `clearTimeout()` hủy bỏ `setTimeout()`<br/>
Tham số truyền vào hàm clearTimeout() là đối tượng setTimeout() nên lúc này ban phải đặt hàm setTimeout() vào một biến cụ thể.
```
<script language="javascript">
    var do_alert = setTimeout(function(){
        alert("Chào mừng bạn đến với freetuts.net");
    }, 3000);
 
    function clearAlert()
    {
        clearTimeout(do_alert);
    }
</script>
 
<input type="button" onclick="clearAlert()" value="Clear" />

```
### Hàm setInterval() có cú pháp và chức năng giống như hàm setTimeout(), tuy nhiên với hàm setInterval() thì số lần thực hiện lã mãi mãi.
```
setInterval(function(){
    alert("Chào mừng bạn đến với freetuts.net");
}, 3000);
```
Tương tự như hàm `clearTimeout()`, hàm `clearInterval()` sẽ xóa đi nhiệm vụ mà ta đã thiết lập trong hàm `setInterval()`, và ta cũng phải đặt `setInterval()` trong một biến thì mới clear được.
# 12.Vòng lặp for, while, do while; câu lệnh break,continue
giống java
# 13.Event
## các sự kiện thông dụng trong javascript

|	Event Name|	Description|
|-----------|------------|
|onclick	|Xảy ra khi click vào thẻ HTML|
|ondbclick	|Xảy ra khi double click vào thẻ HTML|
|onchange	|Xảy ra khi giá trị (value) của thẻ HTML đổi. Thường dùng trong các đối thẻ form input|
|onmouseover|	Xảy ra khi con trỏ chuột bắt đầu đi vào thẻ HTML|
|onmouseout	|Xảy ra khi con trỏ chuột bắt đầu rời khỏi thẻ HTML|
|onmouseenter|	Tương tự như onmouseover|
|onmouseleave	|Tương tự như onmouseout|
|onmousemove	|Xảy ra khi con chuột di chuyển bên trong thẻ HTML|
|onkeydown	|Xảy ra khi gõ một phím bất kì vào ô input|
|onload	|Sảy ra khi thẻ HTML bắt đầu chạy, nó giống như hàm khởi tạo trong lập trình hướng đối tượng vậy đó.|
|onkeyup	|Xảy ra khi bạn gõ phím nhưng lúc bạn nhã phím ra sẽ được kích hoạt|
|onkeypress|	Xảy ra khi bạn nhấn môt phím vào ô input|
|onblur	|Xảy ra khi con trỏ chuột rời khỏi ô input|
|oncopy	|Xảy ra khi bạn copy nội dung của thẻ|
|oncut	|Xảy ra khi bạn cắt nội dung của thẻ|
|onpaste	|Xảy ra khi bạn dán nội dung vào thẻ|

##Thêm sự kiện (Event) bằng Javascript
