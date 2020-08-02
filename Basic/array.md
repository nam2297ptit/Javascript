## Khai báo mảng Javascript

1. Khai báo với từ kháo new Array()
1. Khai báo với cặp dấu ngoặc vuông

Note: Sự khác nhau giữa 2 cách khai báo

- `new Array()` hạn chế số phần tử có trong mảng

Ví dụ

```js
var a = [],            // these are the same
    b = new Array(),   // a and b are arrays with length 0

    c = ['foo', 'bar'],           // these are the same
    d = new Array('foo', 'bar'),  // c and d are arrays with 2 strings

    // these are different:
    e = [3]             // e.length == 1, e[0] == 3
    f = new Array(3),   // f.length == 3, f[0] == undefined;
```

### Các thuộc tính mảng

- `Tạo mảng`

  - [Array.prototype.filter](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/entries): Tạo mảng mới với phần tử thỏa mãn điều kiện yêu cầu của một hàm test.

- `Chia, tách, gộp mảng`

  - [Array.prototype.concat](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/concat): gộp 2 hay nhiều mảng

  - [Array.prototype.slice](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/slice): Phương thức slice() trả về một bản sao tham chiếu (shallow copy) một phần của một mảng dưới dạng một mảng mới nhận các giá trị có chỉ số từ begin dến end (không bao gồm end). Mảng ban đầu không bị thay đổi.

  - [Array.prototype.splice](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/splice): Phương thức splice() thay đổi phần tử của mảng bằng cách xóa phần tử đang tồn tại và/hoặc thêm phần tử mới.

  - [Array.prototype.join](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/joint): tạo ra một chuỗi mới bằng các nối tất cả các phần tử của mảng (hoặc một array-like object), ngăn cách chúng bởi dấu phẩy hoặc một chuỗi ký tự xác định. Nếu mảng chỉ có một phần tử, kết quả sẽ trả về chính phần tử đó

- `Kiểm tra mảng`

  - [Array.prototype.length](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/%08length): Thuộc tính length của một mảng trả về số phần tử trong mảng đó. Đó là một số nguyên 32 bit không dấu và luôn lớn hơn chỉ mục lớn nhất của mảng (chỉ mục lớn nhất chính là dộ dài của mảng trừ đi 1).

  - [Array.prototype.every](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/every): Duyệt tất cả phần tử trong mảng kiểm tra với một điều kiện thực hiện bởi function trả về kết quả boolean

  - [Array.prototype.some](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/some): Phương thức some() kiểm tra xem có ít nhất một phần tử của mảng thoả điều kiện ở hàm được truyền vào hay không. Kết quả trả về có kiểu Boolean.

- `Làm việc với các phần tử trong mảng`

  - [Array.prototype.keys](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/keys): method returns a new Array Iterator object that contains the keys for each index in the array.

  - [Array.prototype.values](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/values): method returns a new Array Iterator object that contains the values for each index in the array.

  - [Array.prototype.copyWithin](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/copyWithin) : Copy phần tử và ghi đè vào vị trí khác của mảng

  - [Array.prototype.fill](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/every): Sửa đổi phần tử trong mảng với một value cho trước. Độ dài mảng không đổi

  - [Array.prototype.reverse](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse): Hàm reverse() khi gọi bởi một mảng thì đảo ngược thứ tự của chính mảng đó. Phần tử đầu tiên của mảng trở thành phần tử cuối và ngược lại, phần tử cuối trở thành phần tử đầu tiên của mảng.

  - [Array.prototype.entries](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/entries): Trả về đối tượng chứa key/value

  - [Array.prototype.toLocaleString](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/toLocaleString): Hàm toLocaleString() trả về 1 chuỗi các phần tử trong mảng. Các phần tử này được chuyển đổi sang kiểu chuỗi nhờ hàm toLocalString và được ngăn cách với nhau bằng một xâu đặc biệt (ví dụ : dấu phẩy (,))

  - [Array.prototype.toString](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/toString): Phương thức toString()trả về một chuỗi string đại diện cho mảng được chỉ định và các phần tử trong mảng đó.

- `Tìm kiếm trong mảng`

  - [Array.prototype.find](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/find): Trả về giá trị đầu tiên tìm thấy ở trong mảng thỏa mãn điều kiện được cung cấp

  - [Array.prototype.findIndex](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex): Trả về chỉ số (index) của phần tử đầu tiên trong mảng thỏa mãn hàm truyền vào. Nếu không phần tử nào thỏa mãn, phương thức trả lại -1.

  - [Array.prototype.indexOf](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf): sẽ trả về giá trị index đầu tiên của mảng, nơi mà nó đc tìm thấy trong mảng, hoặc trả về -1 nếu không tồn tại trong mảng.

  - [Array.prototype.lastIndexOf](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/lastIndexOf): trả về chỉ mục cuối cùng mà tại đó một phần tử đã cho có thể được tìm thấy trong mảng hoặc -1 nếu không có. Mảng được tìm kiếm ngược, bắt đầu từ from Index.

  - [Array.prototype.includes](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/includes): kiểm tra xem phần tử đã cho có tồn tại trong mảng hay không, trả về kết quả true hoặc false.

  - [Array.prototype.push](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/push):Phương thức push() giúp thêm 1 hay nhiều phần tử vào cuối mảng và trả về chiều dài mới của mảng.

  - [Array.prototype.pop](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/pop):Phương thức pop() xoá phần tử cuối cùng của một mảng và trả về phần tử đó. Phương thức này làm thay đổi độ dài của mảng.

  - [Array.prototype.shift](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/shift): Hàm shift() sẽ xóa phần tử đầu tiên của một mảng và trả về phần tử đó. Hàm này sau khi thực thi sẽ làm thay đổi kích thước của mảng bị tác động.

  - [Array.prototype.unshift](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift): Phương thức unshift() thêm một hoặc nhiều phần tử vào vị trí đầu mảng sau đó trả về chiều dài của mảng mới.

* `Duyệt mảng`

  - [Array.prototype.forEach](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach): Phương thức forEach() sẽ thực thi một hàm khi duyệt qua từng phần tử của mảng.

  - [Array.prototype.map](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/map): Phương thức map() giúp tạo ra một mảng mới với các phần tử là kết quả từ việc thực thi một hàm lên từng phần tử của mảng được gọi.

  - [Array.prototype.reduce](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce): Phương thức reduce() dùng để thực thi một hàm lên từng phần tử của mảng (từ trái sang phải) với một biến tích lũy để thu về một giá trị duy nhất.

  - [Array.prototype.reduceRight](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce): Phương thức reduceRight() đảo ngược các giá trị trong mảng (từ phải sang trái), xử lý và trả về một giá trị duy nhất.

- Sắp xếp

  - [Array.prototype.sort](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Array/S%E1%BA%AFp_x%E1%BA%BFp): Phương thức sort() sẽ sắp xếp các phần tử của mảng ngay tại chỗ (in place) và trả về mảng đó. Kết quả sắp xếp có thể không ổn định (stable). Cách sắp xếp mặc định là theo Unicode code point của chuỗi.
