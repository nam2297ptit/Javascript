## Vòng lặp for

Vòng lặp JavaScript cho vòng lặp lặp lại các phần tử cho số lần cố định. Nó nên được sử dụng nếu số lần lặp được biết đến. Cú pháp của vòng lặp for được đưa ra dưới đây.

```js
for (initialization; condition; increment)
{
    code to be executed
}
// Example:
for (i = 0; i < 10; i++) {
  console.log("The number is " + i );
}
```

Trong ví dụ trên, Bạn có thể thấy:

- Initialization: Gán 1 biến trước khi bắt đầu vòng lặp (var i = 0).

- Condition: Xác định điều kiến cho vòng lặp chạy (i phải nhỏ hơn 10).

- Increment: Tăng giá trị (i++) sau mỗi lần đoạn code trong vòng lặp được thực hiện.

### `Initialization`

Thông thường bạn sẽ sử dụng câu lệnh initialization để khởi tạo biến được sử dụng trong vòng lặp (i = 0).

Điều này không phải lúc nào cũng đúng, JavaScript không quan tâm. initialization là tùy chọn.

Bạn có thể bắt đầu nhiều giá trị trong initialization (được phân tách bằng dấu phẩy):

Ví dụ:

```js
for (i = 0, len = 10, text = ""; i < len; i++) {
  text += i + " - ";
}
```

Và bạn có thể bỏ qua phần initialization (như khi giá trị của bạn được đặt trước khi vòng lặp bắt đầu):

```js
var i = 2;
var len = 10;
var text = "";
for (; i < len; i++) {
  text += i + " - ";
}
```

### `Condition`

Condition thường được sử dụng để đánh giá điều kiện của biến ban đầu.

Nếu Condition trả về true, vòng lặp sẽ bắt đầu lại, nếu nó trả về false, vòng lặp sẽ kết thúc.

### `Increment`

Increment thường tăng giá trị của biến ban đầu.

Điều này không phải lúc nào cũng đúng, JavaScript không quan tâm và Increment là không bắt buộc.

Increment có thể làm bất cứ điều gì như tăng âm (i--), tăng dương (i = i + 15) hoặc bất cứ điều gì khác.

Increment cũng có thể được bỏ qua (như khi bạn tăng các giá trị của mình bên trong vòng lặp):

Vi dụ:

```js
var i = 0;
var len = 10;
for (; i < len; ) {
  text += i + " - ";
  i++;
}
```

### `Sử dụng for cho một string`

Bạn có thể sử dụng for loop cho 1 string

```js
var str = "javascript";
for (i = 0; i < str.length; i++) {
  console.log(str[i]);
}
// output:
// j
// a
// v
// a
// s
// c
// r
// i
// p
// t
```

## Vòng lặp while

Lệnh `while` xử lí 1 biểu thức điều kiện và 1 khối lệnh được lặp lại cho đến khi giá trị của biểu thức cho ra giá trị `false`:

```js
while (condition) {
  //do something
}
```

Đây là 2 điều cần chú ý:

- Dấu {} là không cần thiết khi chỉ có một câu lệnh cần được xử lí lặp lại, tuy nhiên việc sử dụng nó được cân nhắc hơn cho tính đồng nhất và tốt hơn cho việc hiểu mã lệnh.
- Lệnh có thể không được xử lí bất kỳ lần nào (khi biểu thức điều kiện trả về false ngay từ ban đầu)

Chúng ta hãy xem một vài ví dụ. Vòng lặp dưới đây xử lí lệnh in 5 lần:

```js
var i = 0;
while (i++ < 5) {
  console.log(i + " "); //prints: 1 2 3 4 5
}
```

Và ở đây là 1 ví dụ về gọi 1 phương thức mà trả về mỗi vài giá trị, giá trị được tích lũy (cộng dần) cho tới khi ngưỡng yêu cầu được đạt tới.

```js
var result = 0;
while (result < 1) {
  result += 0.1;
}
```

Cộng dần `0.1` vào biến result cho tới khi biểu thức điều kiện `result < 1` trả về `false` thì vòng lặp dừng lại.

Đây là một cách để làm vòng lặp này trở nên đơn giản hơn:

```js
var result = 0;
while ((result += 0.1) < 1) {
  console.log(result);
}
```

Giá trị được in sẽ không bao giờ bằng hoặc vượt 1.0 vì biểu thức với giá trị cộng dồn mới nhất sẽ được kiểm tra trước khi vào khối lệnh xử lí. Đó là điều cần chú ý khi các tính toán được bao gồm trong biểu thức điều kiện, không ở trong khối lệnh xử lí.

## Do...While

Tương tự như lệnh `while`, lệnh `do...while` xử lí 1 biểu thức điều kiện và 1 khối lệnh được lặp lại cho đến khi giá trị của biểu thức cho ra giá trị `false`

```js
do {
  //statement or block
} while (condition);
```

Tuy nhiên nó xử lí khối lệnh một lần trước khi biểu thức điều kiện được kiểm tra, nghĩa là khối lệnh đó sẽ được xử lí ít nhất 1 lần.

Chúng ta hãy xem một số ví dụ. Mã lệnh sau xử lí lệnh in 6 lần (nhiều hơn một lần so với lệnh while thông thường)

```js
var i = 0;
do {
  console.log(i + " "); //prints: 0 1 2 3 4 5
} while (i++ < 5);
```

Trong khi mã lệnh sau vận hành một cách tương tự như một lệnh `while`:

```js
var result = 0;
do {
  result += 0.1;
  console.log(result);
} while (result < 1);
```

Điều này là vì giá trị được in sau khi nó được cộng dồn, và sau đó biểu thức điều kiện được kiểm tra trước khi đi vào khối lệnh xử lí lần nữa.

Lệnh do...while rút gọn vận hành một cách khác. Ở đây là một ví dụ:

```js
var result = 0;
do {
  console.log(result);
} while ((result += 0.1) < 1);
```

Giá trị ban đầu của biến `result` luôn được in đầu tiên bởi lệnh được xử lí ít nhất một lần trước khi biểu thức điều kiện được kiểm tra lần đầu.
