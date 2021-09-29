# 编码规范和注意事项

## 一、C++头文件包含的名称和顺序

### 1.`google`规范头文件的包含顺序

相关头文件、C系统头文件、C++标准库头文件、其他库头文件、项目的头文件

项目中的头文件都应该作为项目源目录的后代列出，例如，`project/src/server/server.h`应包括为

```cpp
#include "server/server.h"
```

### 2.在`cpp`文件中，头文件包含顺序

* 相关头文
* 一个空行
* C语言系统头文件（例如: `<stdio.h>` 的头文件）
* 一个空行
* C++标准库头文件 （例如：`<iostream>`）
* 一个空行
* 其他第三方库的.h文件
* 当前项目的.h文件
* 例如，包含在 `project/src/foo/internal/fooserver.cc` 如：

  ```cpp
  #include "foo/server/fooserver.h"

  #include <sys/types.h>
  #include <unistd.h>

  #include <string>
  #include <vector>

  #include "base/basictypes.h"
  #include "base/commandlineflags.h"
  #include "foo/server/bar.h"
  ```

## 参考

* `https://google.github.io/styleguide/cppguide.html`

