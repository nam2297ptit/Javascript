## Hằng số là gì

Hằng số trong các ngôn ngữ lập trình là một biến giá trị không thay đổi. Trong bài này, chúng ta sẽ học cú pháp để khai báo một hằng số trong Java script.

## Cú pháp

Một hằng số được khai báo với từ khóa const. Giá trị của hằng số sẽ ko thể nào thay đổi khi đã khởi tạo:

```js
const PI = 3.141592653589793;
PI = 3.14; // This will give an error
PI = PI + 10; // This will also give an error
var a = PI + 10; // OK
```

Các biến const JavaScript phải được gán một giá trị khi chúng được khai báo:

```js
// Incorrect
const PI;
PI = 3.14159265359;

// Correct
const PI = 3.14159265359;
```

### `Hằng số Object có thể thay đổi`

Bạn có thể thay đổi các thuộc tính của một hằng số object:

```js
// You can create a const object:
const car = { type: "Fiat", model: "500", color: "white" };

// You can change a property:
car.color = "red";

// You can add a property:
car.owner = "Johnson";
```

Nhưng bạn không thể gán lại một hằng số object:

```js
const car = { type: "Fiat", model: "500", color: "white" };
car = { type: "Volvo", model: "EX60", color: "red" }; // ERROR
```

### `Hằng số mảng có thể thay đổi`

Bạn có thể thay đổi các phần tử của hằng số mảng:

```js
// You can create a constant array:
const cars = ["Saab", "Volvo", "BMW"];

// You can change an element:
cars[0] = "Toyota";

// You can add an element:
cars.push("Audi");
```

Nhưng cũng không thể gán lại hằng số mảng:

```js
const cars = ["Saab", "Volvo", "BMW"];
cars = ["Toyota", "Volvo", "Audi"]; // ERROR
```
