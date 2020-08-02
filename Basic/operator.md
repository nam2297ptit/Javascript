## Toán tử trong javascipt

Javascript cung cấp một tập hợp các toán tử phong phú để thao tác các biến. Chúng tôi có thể chia tất cả các toán tử thành các nhóm sau:

- Toán tử số học
- Toán tử quan hệ
- Toán tử logic
- Toán tử gán
- Toán tử typeof

Trong phần này, chúng ta sẽ thảo luận về các toán tử số học được sử dụng trong các biểu thức toán học giống như cách chúng được sử dụng trong đại số.

Toán tử số học được sử dụng để thực hiện các phép toán số học trên các toán hạng. Các toán tử sau được gọi là toán tử số học JavaScript.

### Toán tử số học

| Toán tử |Mô tả | Ví dụ
|---|---|---|---|
| + | Phép cộng | 2+3 = 5
| - | Phép trừ  | 10-2 = 8
| * | Phép nhân | 2*4 = 8
| / | Phéo chia | 50/5 = 10
| % | Phép chia lấy phần dư | 11%4 = 3
|++ | tăng lên 1 | var a=10; a++; Now a = 11
|-- | giảm xuống 1| var a=10; a --; Now a = 9
| == |bằng với |10 == 20 = false <br/> "abc" == "xyz" = false <br/> "js"=="js" = true
| !=| Không bằng với| 10!=20 = true

Ví dụ:

```js
var a = 3;
var b = 2;
var x = a * b;

console.log(x); // output: 6

var c = 3;
x = (a * b) + c;

console.log(x); // output: 9

x = (a * b) % 5;

console.log(x); // output: 1s
```

### Toán tử so sánh

| Toán tử |Mô tả | Ví dụ
|---|---|---|---|
| == |bằng với |10 == 20 = false <br/> "abc" == "xyz" = false <br/> "js"=="js" = true
| !=| Không bằng với| 10!=20 = true

Các toán tử đẳng thức == (có nghĩa là bằng) và != (Có nghĩa là không bằng) so sánh các giá trị cùng loại và trả về giá trị Boolean true nếu giá trị của các toán hạng bằng nhau hoặc ngược lại là false. Sự so sánh của kiểu nguyên thủy  và Boolean rất đơn giản.

```js
var x = 1;
var y = 2;
var z = "2";
var w = "2";

console.log(x != y); // output: true
console.log(x == y); // output: false
console.log(z == y); // output: true

console.log(true == true); // output: true
console.log(true != true); // output: false
```

### Toán tử quan hệ

| Toán tử| Mô tả| Ví dụ
|---|---|---|---|
| > | Lớn hơn| 20>10 = true
| >= | Lớn hơn hoạc bằng | 20>=10 = true |
| < | Nhỏ hơn | 20<10 = false
| <=| Nhỏ hơn hoạc bằng | 20<=10 = false

```js
var i1 = 1;
var i2 = 2;
var i3 = 1;
console.log(i1 > i2);    //prints: false
console.log(i1 >= i2);   //prints: false
console.log(i1 >= i3);   //prints: true
console.log(i1 < i2);    //prints: true
console.log(i1 <= i2);   //prints: true
console.log(i1 <= i3);   //prints: true

console.log('a' >= 'b');  //prints: false
console.log('a' <= 'b');  //prints: true
```

## Toán tử logic

| Toán tử| Mô tả| Ví dụ | Mô tả
|---|---|---|---|
| && | AND |expession1 && expression2 | Cả hai biểu thức phải trả về true nếu kết quả là true
| || | OR | Lexpession1 || expression2 | Một trong các biểu thức phải trả về true nếu kết quả sẽ đúng
| !	 | NOT | !expression | rả về true nếu expression là false và ngược lại trả về false nếu expression là true	

## Toán tử gán

Assignment operators (most popular):  =   +=  -=   *=   /=   %=

Mặc dù chúng ta thảo luận về chúng không phải là những toán tử đầu tiên, nhưng đây là các toán tử được sử dụng thường xuyên nhất, đặc biệt là toán tử gán đơn giản = để gán giá trị cho một biến (cũng được gọi là gán giá trị cho biến). Chúng ta đã nhiều lần thấy các ví dụ về việc sử dụng các phép gán đơn giản. 

Chú ý duy nhất có thể có trong việc sử dụng phép gán đơn giản là khi kiểu biến ở vế bên trái không tương đồng với giá trị hoặc loại biến ở  vế bên phải. Sự khác biệt về kiểu có thể dẫn đến thu hẹp hoặc mở rộng giá trị trong trường hợp kiểu biến là nguyên thủy, boxing hoặc unboxing khi một biến là loại nguyên thủy và biến còn lại là loại tham chiếu. Chúng ta sẽ thảo luận về Thu hẹp và mở rộng conversion of kiểu nguyên thủy và Boxing và unboxing giữa kiểu nguyên thủy và kiểu tham chiếu sau.  

Cách viết tắt của toán tử gán (+= -= *= /= %=) được gọi là toán tử gán phức hợp:

```js
x += 2; // assigns the result of this addition: x = x + 2;
x -= 2; // assigns the result of this subtraction: x = x - 2;
x *= 2; // assigns the result of this multiplication: x = x * 2;
x /= 2; // assigns the result of this division: x = x / 2;
x %= 2; // assigns the remainder of this division: x = x % 2;
```

Ví dụ dưới đây cho chúng ta biết cách các toán tử hoạt động. 

```js
var  x = 1;
x += 2;
console.log(x);    // output: 3
x -= 1;
console.log(x);    // output: 2
x *= 2;
console.log(x);    // output: 4
x /= 2;
console.log(x);    // output: 2
x %= 2;
console.log(x);    // output: 0
```

## Toán tử `typeof`

Toán tử `typeof` là toán tử đơn nguyên được đặt trước toán hạng đơn của nó, có thể là bất kỳ loại nào. Giá trị của nó là một chuỗi chỉ ra kiểu dữ liệu của toán hạng.

Toán tử `typeof` ước tính thành "number", "string" hoặc "boolean" nếu toán hạng của nó là một số, chuỗi hoặc giá trị boolean và trả về giá trị đúng hoặc sai dựa trên đánh giá.

Dưới đây là danh sách các giá trị trả về cho Toán tử typeof.

|Arr |Chuỗi trả về bởi typeof
|---|---|
|Number |"number"|
|String|"string"
|Boolean|"boolean"
|Object|"object"
|Array|"object"
|Function|"function"
|Undefined|"undefined"
|Null|"object"

## Ví dụ 

```js
console.log(typeof 42);
// expected output: "number"

console.log(typeof 'blubber');
// expected output: "string"

console.log(typeof true);
// expected output: "boolean"

console.log(typeof declaredButUndefinedVariable);
// expected output: "undefined";
```