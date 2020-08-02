## Function (hàm) là gì 

Function (Hàm) là một nhóm các câu lệnh thực hiện các nhiệm vụ cụ thể và có thể được giữ và duy trì riêng biệt tạo thành chương trình chính. Các hàm cung cấp một cách để tạo các gói code(mã) có thể tái sử dụng, dễ mang theo hơn và dễ gỡ lỗi hơn. Dưới đây là một số lợi thế của việc sử dụng function:

1. Functions giảm sự lặp lại code trong chương trình — Function cho phép bạn trích xuất khối lệnh thường được sử dụng thành một thành phần duy nhất. Bây giờ bạn có thể thực hiện cùng một tác vụ bằng cách gọi hàm này bất cứ nơi nào bạn muốn trong tập lệnh của mình mà không phải sao chép và dán cùng một khối lệnh nhiều lần
0
2. Functions giúp các dòng code dễ bảo trì hơn — Do một function được tạo một lần có thể được sử dụng nhiều lần, do đó, mọi thay đổi được thực hiện bên trong một function sẽ tự động được thực hiện tại tất cả các vị trí mà không cần thay đổi ở nhiều nơi.

3. Functions giúp dễ dàng hơn để loại bỏ các lỗi — Khi chương trình được chia thành các function, nếu có lỗi xảy ra, bạn biết chính xác function nào gây ra lỗi và tìm nó ở đâu. Do đó, sửa lỗi trở nên dễ dàng hơn nhiều

## Khai báo và gọi một function

Khởi tạo 1 function bắt đầu với từ khóa function, tiếp theo đó là tên mà function mà bạn muốn tạo, tiếp theo là ngoặc đơn () và cuối cùng là nơi cách lệnh của function giữa các dấu ngoặc nhọn {}.

Đây là cú pháp cơ bản để khai báo hàm:

```
function functionName() {
    // Code to be executed
}
```
Ví dụ 

```js
// Defining function
function sayHello() {
    console.log("Hello");
}
 
// Calling function
sayHello(); // 0utputs: Hello

```

## Truyền tham số vào function

Bạn có thể chỉ định tham số khi bạn khai báo function của mình để nhận giá trị đầu vào trong thời gian chạy. Các tham số hoạt động như các biến giữ chỗ trong một function; chúng được thay thế vào thời gian chạy bằng các giá trị (được gọi là đối số) được cung cấp cho function tại thời điểm gọi.

Các tham số được đặt trên dòng đầu tiên của hàm bên trong bộ dấu ngoặc đơn, như thế này:

```js
function functionName(parameter1, parameter2, parameter3) {
    // Code to be executed
}
```

```js
Function displaySum() trong ví dụ sau lấy hai số làm đối số, chỉ cần thêm chúng vào và sau đó chúng sẽ hiển thị kết quả.
```

Bạn có thể định nghĩa bao nhiêu tham số tùy thích. Tuy nhiên, đối với mỗi tham số bạn chỉ định, một đối số tương ứng cần được truyền cho hàm khi nó được gọi, nếu không giá trị của nó sẽ không được xác định undefined. Hãy xem xét ví dụ sau:

```
// Defining function
function showFullname(firstName, lastName) {
    console.log(firstName + " " + lastName);
}
 
// Calling function
showFullname("Tuan", "Phong"); // 0utputs: Tuan Phong
showFullname("Vuong"); // 0utputs: Vuong undefined
```

## Giá trị trả về của một funtions

Một function có thể trả về một giá trị cho tập lệnh gọi function là kết quả bằng cách sử dụng câu lệnh return. Giá trị có thể thuộc bất kỳ loại nào, bao gồm mảng và đối tượng

Lệnh `return` thường được đặt là dòng cuối cùng của hàm trước dấu ngoặc nhọn đóng và kết thúc nó bằng dấu chấm phẩy, như trong ví dụ sau.

```js
// Defining function
function getSum(num1, num2) {
    var total = num1 + num2;
    return total;
}
 
// Displaying returned value
console.log(getSum(6, 20)); // 0utputs: 26
console.log(getSum(-5, 17)); // 0utputs: 12
```

Function không thể trả về nhiều giá trị. Tuy nhiên, bạn có thể thu được kết quả tương tự bằng cách trả về một mảng các giá trị, như được minh họa trong ví dụ sau..

```js
// Defining function
function get_name(){
    var name1 = "Tuan";
	var name2 = "Phong";
	var name3 = "Vuong";
    var arr = [name1, name2, name3];
    return arr;
}
 
// Store returned value in a variable
var all = get_name();
 
// Displaying individual values
console.log(all[0]); // 0utput: Tuan
console.log(all[1]); // 0utput: Phong
console.log(all[2]); // 0utput: Vuong
```

Và nếu một function trả về một giá trị, nó sẽ dừng việc thực thi của function đó. Nó có nghĩa là phần còn lại của mã sẽ không được thực thi

```js
// Defining function
function print_numbers(x){
    if (x == 1) {
		console.log(1);
		return; // a function can return nothing
	}
    console.log(2);
	return; // a function can return nothing
	console.log(3);
}
 
// Displaying individual values
console.log(print_numbers(0)); // 0utput: 2
console.log(print_numbers(1)); // 0utput: 1
```

## Hàm callback

Hàm callback là một hàm được truyền vào một hàm khác dưới dạng đối số, sau đó được gọi bên trong hàm ngoài để hoàn thành một số loại thường trình hoặc hành động.

```js
function finish_add_numbers() {
	console.log('Finish function');
}

function add_two_numbers(a, b, callback) {
	var sum = a + b;
	console.log(sum);
	callback();
}

add_two_numbers(2, 4, finish_add_numbers);
// output: 
// 6
// Finish function
```

## Cú pháp

```js
function functionOne(x) { return x; };

function functionTwo(var1) {
    // some code
}

functionTwo(functionOne);
```

Phương thức chuyển các hàm này sang các hàm khác để sử dụng chúng bên trong được sử dụng trong các thư viện JavaScript ở hầu hết mọi nơi.

Tên chung cho hàm được truyền vào là hàm callback.

Trong lập trình máy tính, một cuộc gọi lại là một đoạn mã thực thi được truyền dưới dạng đối số cho mã khác, dự kiến sẽ gọi lại (thực thi) đối số vào một thời điểm thuận tiện.

Lệnh gọi có thể ngay lập tức như trong một cuộc gọi lại đồng bộ hoặc nó có thể xảy ra vào thời gian sau, như trong một cuộc gọi lại không đồng bộ.

Chúng tôi sẽ quay lại các cuộc gọi lại đồng bộ và không đồng bộ trong một phần khác.

```js
function functionOne(x) { console.log(x); }

function functionTwo(var1, callback) {
    callback(var1);		
}

functionTwo(2, functionOne);
```

Đây là một ví dụ về việc sử dụng biến callback trong Hàm JavaScript.

One nhận một đối số và đưa ra x là đối số của nó.

FunctionTwo nhận 1 đối số và 1  function.

Sau đó, FunctionTwo chuyển đối số mà nó đưa vào cho hàm mà nó đã thực hiện.

FunctionOne là hàm callback trong trường hợp này.

Vì JavaScript có sẵn các hàm vô danh, bạn cũng có thể chuyển các Hàm vô danh dưới dạng một biến cho một hàm.

```js
function functionTwo(var1, callback) {
    callback(var1);		
}

functionTwo(1, function (x) { alert(x); })
```

Trong trường hợp nay, hàm callback được khởi tạo khi chúng ta gọi functionTwo.

Hay nhớ rằng chúng ta có thể gọi hàm callback bên trong functionTwo nhiều lần nếu bạn muốn.

```js
function functionTwo(var1, callback) {
    callback(var1);	
    callback(var1);	
}

functionTwo(1, function (x) { console.log(x); })
```

Không giới hạn việc gọi bao nhiêu lần

Một điều khác cần chú ý là bạn có thể chuyển bao nhiêu hàm callback tùy thích sang chức năng khác.

```
function functionTwo(var1, var2, callback1, callback2) {
    callback1(var1);	
    callback2(var2);	
}

functionTwo(1, 2, function (x) { console.log(x); }, function (x) { console.log(x); })
```
Ở đây trong functionTwo chúng ta truyền vào hai biến và hai hàm làm đối số.
 
Bên trong functionTwo, chúng ta chạy callback1 với biến 1 và chúng ta chạy callback2 với biến 2.
 
Chúng ta hãy xem mã trong Bảng điều khiển JavaScript để xem nó hoạt động như thế nào.

```js
function functionOne(x) { console.log(x); }
```

FunctionOne được định nghĩa để hiển thị giá trị của đối số được truyền vào nó.
Kiểm tra

```js
functionOne(2);
```

Khi functionOne được gọi

FunctionOne sẽ hiển thị cho chúng ta số 2

Tiếp tục, Cũng định nghĩa functionTwo

```js
function functionTwo(x) { console.log(x); }

```

FunctionTwo được định nghĩa để hiển thị giá trị của đối số được truyền vào nó.

Nó chính xác là giông functionOne
