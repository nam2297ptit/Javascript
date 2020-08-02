### What is import

`import` là câu lệnh được sử dụng để vào module được `export` từ module khác.

Các module được import ở chế độ `trict mode` dù bạn có khai báo hay không.

Các câu lệnh `import` không được sử dụng trong embedded script trừ trường hợp tập lệnh đó có `type="module"`

Các ràng buộc được nhập được gọi là các ràng buộc trực tiếp vì chúng được cập nhật bởi mô-đun đã xuất liên kết

## Syntax

```js
import defaultExport from "module-name";
import * as name from "module-name";
import { export1 } from "module-name";
import { export1 as alias1 } from "module-name";
import { export1 , export2 } from "module-name";
import { foo , bar } from "module-name/path/to/specific/un-exported/file";
import { export1 , export2 as alias2 , [...] } from "module-name";
import defaultExport, { export1 [ , [...] ] } from "module-name";
import defaultExport, * as name from "module-name";
import "module-name";
var promise = import("module-name");
```

- `defaultExport`: Tên sẽ là mặc định khi export từ module

- `module-name`: Các module được import. Đây thường là tên đường dẫn tương đối hoặc tuyệt đối đến file `.js` chứa module.

- `name`: Tên của module object được sử dụng như laoij không gian khi đề cập đến imports

- `exportN`: Tên exports sẽ được import

- `alsias` Tên đề cập trong file imports
