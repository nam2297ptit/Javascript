## Swicth case

Bạn có thể dùng nhiều lệnh if...else…if , như đã cung cấp ở phần trước, để thực hiện 1 nhánh với nhiều lối đi. Tuy nhiên điều đó không phải là giải pháp tốt nhất, đặc biệt là khi tất cả các nhánh phụ thuộc vào giá trị của một biến duy nhất.

```js
if (x == 5) {
  //do something
} else if (x == 7) {
  //do something else
} else if (x == 12) {
  //do something different
} else if ((x = 50)) {
  //do something yet more different
} else {
  //do something completely different
}
```

Tuy nhiên ở đây mỗi trường hợp xác định bằng một lệnh điều kiện, bạn có thể sử dụng lệnh switch...case, lệnh mà dễ đọc và hiểu hơn.

```js
switch (x) {
  case 5:
    //do something
    break;
  case 7:
    //do something else
    break;
  case 12:
    //do something different
    break;
  case 50:
    //do something yet more different
    break;
  default:
  //do something completely different
}
```

Kiểu của biểu thức là trả về giá trị của biến x có thể một trong các kiểu char, byte, short, int, Character, Byte, Short, Integer, String hoặc enum. Hãy chú ý từ khóa break, nó buộc lệnh switch...case dừng lại. Nếu không có nó, việc này chỉ được chấp nhận khi case đó không có bất kỳ một lệnh nào, ngược lại, lệnh case đó sẽ bị báo lỗi cú pháp. Chúng ta sẽ nói về lệnh break trong một khóa phía sau về các lệnh rẽ nhánh.

Chúng ta hãy nhìn vào phương thức cho thấy lợi ích của lệnh switch:

```js
switch (n + 1) {
  case 1:
    console.log("case 1: " + n);
    break;
  case 2:
    console.log("case 2: " + n);
    break;
  default:
    console.log("default: " + n);
    break;
}
```

Và như mệnh đề else trong lệnh if, mệnh đề default không bắt buộc trong lệnh switch nếu nó không cần thiết cho logic chương trình:

```js
switch (n + 1) {
  case 1:
    console.log("case 1: " + n);
    break;
  case 2:
    console.log("case 2: " + n);
}
```

### Switch với nhiều trường hơp và có cũng cùng sử lý

Có nhiều trường hợp một phạm vi không phải là giải pháp phù hợp, nhưng bạn cần áp dụng cùng một thực thi cho nhiều giá trị. Đây là nơi mà câu lệnh chuyển đổi có thể rất tiện dụng.

Thay vì tạo một câu lệnh if lộn xộn với nhiều đánh giá biểu thức, bạn có thể 'xếp chồng' các trường hợp.

Đây là một biến thể, tất cả đều rất đơn giản, trong ngày của ví dụ trong tuần. Ở đây tôi trình bày cách bạn có thể sử dụng câu lệnh chuyển đổi trong ứng dụng lịch.

Vi dụ:

```js
switch (expr) {
  case "Oranges":
    console.log("Oranges are $0.59 a pound.");
    break;
  case "Apples":
  case "Papayas":
    console.log("Apples and Papayas are $2.79 a pound.");
    break;
  default:
    console.log("Sorry, we are out of " + expr + ".");
}
```
