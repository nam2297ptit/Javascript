# Sắp Xếp Mảng Trong JavaScript

Sắp Xếp Mảng
Phương thức sort() sắp xếp một mảng theo thứ tự abc:

Ví dụ sắp xếp một mảng đơn giản:

```js
fruits = ["Chuoi", "Cam", "Tao", "Xoai"];
fruits.sort(); // Sắp xếp các phần tử trong mảng fruits[]
```

# Cách Sắp Xếp Mảng Đảo Ngược

Phương thức reverse() đảo ngược các phần tử trong mảng – nó là ngược lại phương thức sort().

Bạn có thể dùng nó để sắp xếp mảng theo chiều giảm dần.

Ví dụ

```js
var fruits = ["Chuoi", "Cam", "Tao", "Xoai"];
fruits.sort(); // First sort the elements of fruits
fruits.reverse(); // Then reverse the order of the elements
```

## Sắp xếp số

Mặc định, hàm `sort()` xem các giá trị như chuỗi để thực hiện sắp xếp.

Nó sẽ thực hiện sắp xếp hiệu quả đối với các chuỗi (“Anh” xếp trước “Ba”)

Tuy nhiên, nếu các số được sắp xếp như chuỗi thì “25” sẽ lớn hơn “100” vì “2” lớn hơn “1”

Vì vậy, phương thức `sort()` sẽ đưa ra kết quả sai khi sắp xếp các số.

Bạn vẫn có thể thực hiện sắp xếp bằng cách sử dụng một hàm so sánh (compare function).

Ví dụ:

```js
var points = [40, 100, 1, 5, 25, 10];
points.sort(function (a, b) {
  return a - b;
});
```

Thực hiện tương tự ở trên để sắp xếp mảng giảm dần.

Ví dụ:

```js
var points = [40, 100, 1, 5, 25, 10];
points.sort(function (a, b) {
  return b - a;
});
```

Hàm So Sánh
Hàm so sánh sẽ trả về một giá trị âm, 0 hoặc giá trị dương phụ thuộc vào các đối số:

Ví dụ:

```js
function(a, b){return a-b}
```

Trước tiên, hàm sort() so sánh hai 2 trị bằng cách đưa 2 giá trị đó vào hàm so sánh. Sau đó mới thực hiện sắp xếp chúng dựa trên kết quả trả về (là giá trị âm, 0 hoặc giá trị dương).

Ví dụ:

Khi so sánh 40 và 100, phương thức sort() gọi hàm so sánh compare(40,100)

Hàm so sánh tính toán 40-100 và trả về kết quả -60 (giá trị âm).

Hàm sort dựa vào kết quả đó nhận biết 40 nhỏ hơn 100 và tiến hành sắp xếp.

Bạn có thể dùng đoạn code sau để thử nghiệm với việc sắp xếp số và chữ:

```js
<button onclick="myFunction1()">Sort Alphabetically</button>
<button onclick="myFunction2()">Sort Numerically</button>

<p id="demo"></p>

<script>
var points = [40, 100, 1, 5, 25, 10];
document.getElementById("demo").innerHTML = points;

function myFunction1() {
    points.sort();
    document.getElementById("demo").innerHTML = points;
}
function myFunction2() {
    points.sort(function(a, b){return a - b});
    document.getElementById("demo").innerHTML = points;
}
</script>
```

Sắp Xếp Mảng Theo Thứ Tự Ngẫu Nhiên
Ví dụ về sắp xếp ngẫu nhiên:

```js
var points = [40, 100, 1, 5, 25, 10];
points.sort(function (a, b) {
  return 0.5 - Math.random();
});
```

Tìm Giá Trị Lớn Nhất (Nhỏ Nhất) Của Mảng
Không có hàm đặt đặt sẵn (built-in functions) để tìm giá trị lớn nhất, nhỏ nhất của mảng.

Tuy nhiên, sau khi bạn có một mảng đã được sắp xếp, bạn có thể sử dụng chỉ số (index) để tìm được giá trị lớn nhất, nhỏ nhất của mảng đó.

Ví dụ về sắp xếp tăng dần:

```js
var points = [40, 100, 1, 5, 25, 10];
points.sort(function (a, b) {
  return a - b;
});
// Lúc này, vị trí points[0] chứa giá trị nhỏ nhất.
// và points[points.length-1] chứa giá trị lớn nhất.
```

Ví dụ về sắp xếp giảm dần:

```js
var points = [40, 100, 1, 5, 25, 10];
points.sort(function (a, b) {
  return b - a;
});
// Lúc này, vị trí points[0] chứa giá trị lớn nhất.
// và points[points.length-1] chứa giá trị nhỏ nhất.
```

Sắp xếp toàn bộ mảng chỉ để tìm ra giá trị lớn nhất (hay nhỏ nhất) là
một phương pháp rất kém hiệu quả.

Sử Dụng `Math.max()`
Bạn có thể dùng Math.max.apply để tìm số lớn nhất trong một mảng.

Ví dụ:

```js
function myArrayMax(arr) {
  return Math.max.apply(null, arr);
}
```

Sử Dụng Math.min()
Bạn có thể dùng Math.min.apply để tìm số nhỏ nhất trong một mảng.

Ví dụ:

```js
function myArrayMin(arr) {
  return Math.min.apply(null, arr);
}
```

> Math.min.apply([1, 2, 3]) tương đương với Math.min(1, 2, 3).

Tự Viết Hàm Tìm Min/Max Thôi!
Giải pháp nhanh nhất là dùng một phương thức “nhà làm” như bên dưới.

Hàm này lặp qua một mảng, lần lượt so sánh mỗi giá trị với giá trị lớn nhất đã tìm được.

Ví dụ hàm tìm Max:

```js
function myArrayMax(arr) {
  var len = arr.length;
  var max = -Infinity;
  while (len--) {
    if (arr[len] > max) {
      max = arr[len];
    }
  }
  return max;
}
```

Hàm này lặp qua một mảng, lần lượt so sánh mỗi giá trị với giá trị nhỏ nhất đã tìm được.

Ví dụ hàm tìm Min:

```js
function myArrayMin(arr) {
  var len = arr.length;
  var min = Infinity;
  while (len--) {
    if (arr[len] < min) {
      min = arr[len];
    }
  }
  return min;
}
```

Sắp Xếp Mảng Đối Tượng
Mảng trong JavaScript thường chứa các đối tượng.

Ví dụ:

```js
var cars = [
  { type: "Volvo", year: 2016 },
  { type: "Saab", year: 2001 },
  { type: "BMW", year: 2010 },
];
```

Ngay cả khi các đối đượng có nhiều thuộc tính và kiểu dữ liệu của chúng khác nhau thì phương thức `sort()` vẫn có thể sử dụng để sắp xếp mảng đó.

Giải pháp là viết một hàm so sánh để so sánh các giá trị của thuộc tính.

Ví dụ sắp xếp các đối tượng xe dựa trên tuổi

cars.sort(function(a, b){return a.year - b.year});

So sánh các thuộc tính của chuỗi thì phức tạp hơn một chút.

Ví dụ về so sánh chuỗi chứa cả chữ hoa và chữ thường:

```js
cars.sort(function (a, b) {
  var x = a.type.toLowerCase();
  var y = b.type.toLowerCase();
  if (x < y) {
    return -1;
  }
  if (x > y) {
    return 1;
  }
  return 0;
});
```
