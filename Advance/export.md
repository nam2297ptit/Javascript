# Export and Import

## Export trước khi khai báo

Có thể đặt `export` ở trước bất cứ `variable`, `function` hay `class` nào nếu bạn muốn sử dụng chúng ở trong module hoặc file khác.

Ví dụ

```js
// export an array
export let months = ["Jan", "Feb", "Mar", "Apr", "Aug", "Sep", "Oct", "Nov", "Dec"];

// export a constant
export const MODULES_BECAME_STANDARD_YEAR = 2015;

// export a class
export class User {
  constructor(name) {
    this.name = name;
  }
}
```

> Note: Không có dấu chấm phẩy ở sau export class,function
> Hãy lưu ý răng đặt `export` ở trước class hoặc function không làm cho nó thành `function expression`. Nó vẫn là `function declaration` mặc dù đươc export.
>
> ```js
> export function sayHi(user) {
>   alert(`Hello, ${user}!`);
> } // no ; at the end
> ```

## Export sau khi khai báo

```js
// 📁 say.js
function sayHi(user) {
  alert(`Hello, ${user}!`);
}

function sayBye(user) {
  alert(`Bye, ${user}!`);
}

export { sayHi, sayBye }; // a list of exported variables
```

## Import \*

Thông thường cú pháp pháp import sẽ giống như dưới đây

```js
// 📁 main.js
import { sayHi, sayBye } from "./say.js";

sayHi("John"); // Hello, John!
sayBye("John"); // Bye, John!
```

Nhưng nếu có rất nhiều thứ để import ta có thể dùng cú pháp

```js
// 📁 main.js
import * as say from "./say.js";

say.sayHi("John");
say.sayBye("John");
```

Câu hỏi đặt ra là việc "import every things" có vẻ cú pháp rất ngắn và tiện lợi. Nhưng điều này không được khuyến khích dùng vì:

1. Chỉ cần import những thứ cần thiết giúp tối ưu hóa và tăng tốc độ tải

Ví dụ

```js
// 📁 say.js
export function sayHi() { ... }
export function sayBye() { ... }
export function becomeSilent() { ... }
```

Nếu bạn chỉ muốn sử dụng một hàm trong file `say.js` ta làm như sau:

```js
// 📁 main.js
import { sayHi } from "./say.js";
```

Sau đó, trình tối ưu hóa sẽ thấy điều đó và loại bỏ các chức năng khác khỏi mã được đóng gói, do đó làm cho bản dựng nhỏ hơn. Cái đó được gọi là "tree-shaking".

2. Liệt kê rõ những gì cần import sẽ giúp khi cần gọi hàm với tên ngắn hơn

Ví dụ: Theo trên, ta chỉ cần gọi `sayHi()` thay vì `say.sayHi()`

3. Danh sách import rõ ràng giúp cho việc review code được dễ dàng và thuận tiện. Hỗ trợ và tái cấu trúc code một cách dễ dàng

## Import `as`

Ta cso thể dùng `as` để import với một tên khác

```js
// 📁 main.js
import { sayHi as hi, sayBye as bye } from "./say.js";

hi("John"); // Hello, John!
bye("John"); // Bye, John!
```

## Export `as`

Tương tự ta có ví dụ

```js
// 📁 say.js
...
export {sayHi as hi, sayBye as bye};
```

```js
// 📁 main.js
import * as say from "./say.js";

say.hi("John"); // Hello, John!
say.bye("John"); // Bye, John!
```

## Export default

Trong thực tế có 2 cách để `export` module

1. Module chứa các thư viện, gói các hàm như file `say.js` ở trên

1. Module chỉ khai báo một thực thể duy nhất. Ví dú file `user.js` chỉ export ra `class User`

Hầu hết, cách tiếp cận thứ hai được ưa thích hơn, do đó, mọi thứ c đều nằm trong mô-đun riêng.

Đương nhiên, điều đó đòi hỏi rất nhiều tệp, vì mọi thứ đều muốn mô-đun của riêng nó, nhưng điều đó không phải là vấn đề. Trên thực tế, điều hướng mã trở nên dễ dàng hơn nếu các tệp được đặt tên tốt và được cấu trúc thành các thư mục.

Các mô-đun cung cấp một cú pháp `export default` để làm cho một điều trên `on thing per module` trông đẹp hơn.

Ví dụ

```js
// 📁 user.js
export default class User {
  // just add "default"
  constructor(name) {
    this.name = name;
  }
}
```

Do đó chỉ có thể `export default` cho mối tệp.

Sau đó `import` mà không cần `{}`

```js
// 📁 main.js
import User from "./user.js"; // not {User}, just User

new User("John");
```

## Note

| Named export            | Default export                  |
| ----------------------- | ------------------------------- |
| export class User {...} | export default class User {...} |
| import {User} from ...  | import {User} from ...          |

Về mặt kỹ thuật, chúng ta có thể có cả default và named export trong một mô-đun duy nhất, nhưng trong thực tế, mọi người thường không kết hợp chúng. Một mô-đun có tên xuất khẩu hoặc mặc định.

```js
export default class { // no class name
  constructor() { ... }
}
```

```js
export default function (user) {
  // no function name
  alert(`Hello, ${user}!`);
}
```

```js
// export a single value, without making a variable
export default ["Jan", "Feb", "Mar", "Apr", "Aug", "Sep", "Oct", "Nov", "Dec"];
```

Lỗi

```js
export class { // Error! (non-default export needs a name)
  constructor() {}
}
```

## The "default" name

Trong một số trường hợp, từ khóa `default` được sử dụng để tham chiếu default export

```js
function sayHi(user) {
  alert(`Hello, ${user}!`);
}

// same as if we added "export default" before the function
export { sayHi as default };
```

## Summary

Dưới đây là tất cả các loại hình `export` và `import` đề cập trong bài viết.

You can check yourself by reading them and recalling what they mean:

- Trước khi khai báo class/function/…:

  - `export [default] class/function/variable ...`

- Export độc lập:
  - `export {x [as y], ...}`
- Re-export:
  - `export {x [as y], ...} from "module"`
  - `export * from "module" (doesn’t re-export default).`
  - `export {default [as y]} from "module"` (re-export default)

Import:

- `exports` được đặt tên từ mô-đun::
  - `import {x [as y], ...} from "module"`
- Default export:
  - `import x from "module"`
  - `import {default as x} from "module"`
- Everything:
  - `import \* as obj from "module"`
- Import the module (its code runs), but do not assign it to a variable:
  - `import "module"`
