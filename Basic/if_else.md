## Lệnh if-else
Các lệnh lựa chọn có 3 biến thể:

- Lệnh if

- Lệnh if...else

- Lệnh if...else if-...-else

## Lệnh if
Câu lệnh if đơn giản cho phép thực thi một câu lệnh nhất định hoặc một khối điều kiện, chỉ khi kết quả của biểu thức đánh giá được thỏa mãn:

```js
if (condition) {
	// Do something
}
```

ví dụ

```js
if(true) console.log("true");    //1: true
if(false) console.log("false");  //2:

int x = 1, y = 5;
if(x > y) console.log("x > y");  //3:
if(x < y) console.log("x < y");  //4: x < y

if((x + 5) > y) {			     //5: x + 5 > y
  console.log("x + 5 > y");    
  x = y;
}

if(x == y){ 					//6: x == y
  console.log("x == y");       
}
```

Để chứng minh rằng dấu ngoặc nhọn cũng có thể được sử dụng với một câu lệnh, do đó tạo thành một khối lệnh chỉ gồm một câu lệnh.
Đó một cách thực hành tốt, nói chung, để có ngoặc nhọn sau if; điều này giúp cho việc đọc tôt hơn và giúp tránh những lỗi gây bực bội: bạn thêm một câu lệnh khác sau if, và nó sẽ được thực thi chỉ khi biểu thức trả về true:

```js
if(x > y) console.log("x > y"); 
  x = y;
```

Như chúng ta đã đề cập, bên trong câu lệnh điều kiện có thể bao gồm một câu lệnh điều kiện khác để tạo ra một logic chặt chẽ hơn cho luồng điều khiển:

```js
if(x > y){
  console.log("x > y");
  if(x == 3){
    console.log("x == 3");
  }
  if(y == 3){
    console.log("y == 3");
    console.log("x == " + x);
  }
}
```

Nó có thể chứa (lồng nhau) để thỏa mãn yêu cầu về mặt logic.

## Lệnh if-else

Cấu trúc if...else cho phép xử lí một khối lệnh nếu biểu thức trong if có giá trị là true, ngược lại, khối lệnh khác được xử lí:

```js
if(condition){
  //do something
} else {
  //do something else
}

```

Dưới đây có 2 ví dụ:

```js
var x = 1, y = 1; 
if(x == y){                        
	console.log("x == y");  //Output: x == y
	x = y - 1;
} else {
	console.log("x != y");  
}

if(x == y){                        
	console.log("x == y");
} else {
	console.log("x != y");  //Output: x != y
}
```
Bạn có thể thấy dễ ràng hơn cho việc đọc code khi dấu {} được sử dụng thích hợp. Như trong phần trước của lệnh if, mỗi khối lệnh có thể có nhiều khối lệnh con khác với lệnh if khác, và cứ như thế có thể có nhiều khối lệnh con phía trong nếu cần thiết.

if...else if-...-else

Bạn có thể sử dụng hình thức này để tránh tạo ra nhiều khối lệnh con và làm code dễ để đọc và hiểu hơn. Ví dụ, xem đoạn trích lệnh sau đây:

```js
if(n > 5){
  console.log("n > 5");
} else {
  if (n == 5) {
    console.log("n == 5");
  } else {
    if (n == 4) {
      console.log("n == 4");
    } else {
      console.log("n < 4");
    }
  }
}
```

Các lệnh if...else con này có thể thay thế bởi lệnh if...else...if như sau đây:

```js
if(n > 5){
  console.log("n > 5");
} else if (n == 5) {
  console.log("n == 5");
} else if (n == 4) {
  console.log("n == 4");
} else {
  console.log("n < 4");
}
```

Lệnh như vậy là dễ đọc và hiểu hơn.

Nếu bạn không cần làm bất kỳ điều gì khi n < 4, bạn có thể bỏ qua mệnh đề else cuối cùng dùng để bắt trường hợp còn lại của các lựa chọn trên:

```js

if(n > 5){
  console.log("n > 5");
} else if (n == 5) {
  console.log("n == 5");
} else if (n == 4) {
  console.log("n == 4");
} ​
```