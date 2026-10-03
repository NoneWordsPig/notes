# C 语言基础笔记

> 本页整理 C 语言关键字、控制语句、标准库与常用工具链。重点放在日常编程中会反复查阅的内容；不在这里展开语法结构和算法。

## 1. 关键字（保留字）

### 1.1 按功能整理

以下是原笔记中的 32 个经典 C 关键字，按用途重新分组：

| 类别 | 关键字 |
| --- | --- |
| 基本类型 | `char`、`double`、`float`、`int`、`void` |
| 类型修饰 | `signed`、`unsigned`、`short`、`long` |
| 类型构造 | `enum`、`struct`、`union`、`typedef` |
| 类型限定与运算 | `const`、`volatile`、`sizeof` |
| 存储类别 | `auto`、`extern`、`register`、`static` |
| 分支与循环 | `if`、`else`、`switch`、`case`、`default`、`for`、`while`、`do` |
| 跳转 | `break`、`continue`、`goto`、`return` |

也可以按字母顺序速查：

```text
auto      break     case      char
const     continue  default   do
double    else      enum      extern
float     for       goto      if
int       long      register  return
short     signed    sizeof    static
struct    switch    typedef   union
unsigned  void      volatile  while
```

> 版本提示：上表对应经典 C90 的 32 个关键字。C99、C11 及更新标准还增加了其他关键字；这里暂不展开，以免与语法笔记混在一起。

### 1.2 需要区分的概念

- **关键字**：由语言标准保留，不能用作普通变量名，例如 `int`、`return`。
- **标准库函数**：由头文件提供，不是关键字，例如 `printf`、`malloc`、`strlen`。
- **宏或常量**：通常由头文件定义，例如 `NULL`、`EXIT_SUCCESS`、`EOF`。

## 2. 控制语句速查

| 类别 | 关键字或形式 | 作用 |
| --- | --- | --- |
| 条件分支 | `if`、`else` | 根据条件选择执行路径 |
| 多路分支 | `switch`、`case`、`default` | 根据整数或枚举值选择分支 |
| 计数循环 | `for` | 适合循环次数或步进关系明确的场景 |
| 条件循环 | `while` | 先判断条件，再决定是否执行 |
| 至少执行一次 | `do ... while` | 先执行一次，再判断是否继续 |
| 提前结束循环或分支 | `break` | 退出当前循环或 `switch` |
| 跳过本轮循环 | `continue` | 进入当前循环的下一轮 |
| 无条件跳转 | `goto` | 跳转到同一函数内的标签；通常应谨慎使用 |
| 返回 | `return` | 结束当前函数，并可返回结果 |

## 3. 标准库总览

C 的标准库按“头文件”组织。使用函数前，先包含对应头文件；头文件只提供声明，具体实现由编译器和 C 运行库提供。

### 3.1 最常用的头文件

| 头文件 | 主要用途 | 常见内容 |
| --- | --- | --- |
| `<stdio.h>` | 标准输入输出、文件 | `printf`、`scanf`、`fgets`、`fopen`、`FILE`、`EOF` |
| `<stdlib.h>` | 动态内存、数值转换、程序控制 | `malloc`、`calloc`、`realloc`、`free`、`strtol`、`exit` |
| `<string.h>` | C 字符串与内存块操作 | `strlen`、`strcmp`、`strstr`、`memcpy`、`memset` |
| `<ctype.h>` | 字符分类与大小写转换 | `isalpha`、`isdigit`、`isspace`、`tolower` |
| `<math.h>` | 数学函数 | `sqrt`、`pow`、`fabs`、`sin`、`cos`、`floor` |
| `<stdbool.h>` | 布尔类型 | `bool`、`true`、`false`（C99） |
| `<stdint.h>` | 宽度明确的整数类型 | `int8_t`、`uint32_t`、`int64_t` |
| `<stddef.h>` | 通用类型与宏 | `size_t`、`ptrdiff_t`、`NULL`、`offsetof` |
| `<limits.h>` | 整数类型的范围 | `INT_MIN`、`INT_MAX`、`CHAR_BIT` |
| `<float.h>` | 浮点类型的范围与精度 | `FLT_MAX`、`DBL_MAX`、`DBL_EPSILON` |
| `<time.h>` | 时间、日期、计时 | `time`、`localtime`、`strftime`、`clock` |
| `<assert.h>` | 调试期断言 | `assert`、`NDEBUG` |
| `<errno.h>` | 错误状态 | `errno`、`EDOM`、`ERANGE` |
| `<stdarg.h>` | 可变参数函数 | `va_list`、`va_start`、`va_arg`、`va_end` |
| `<inttypes.h>` | 可移植的整数格式化 | `PRId64`、`SCNu32` 等宏 |

### 3.2 一组常见的头文件组合

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <stdbool.h>
```

不要为了“保险”把所有头文件都包含进来；按实际使用的类型和函数引入即可。

## 4. 高频函数与类型速查

### 4.1 `<stdio.h>`：输入、输出与文件

| 内容 | 用途 | 注意事项 |
| --- | --- | --- |
| `printf`、`fprintf` | 格式化输出到终端或文件 | 格式占位符必须与参数类型匹配 |
| `scanf`、`fscanf` | 按格式读取输入 | 返回成功读取的项目数；输入不规则时容易留下缓冲区内容 |
| `fgets` | 读取一行文本 | 应传入缓冲区大小；可能保留换行符 |
| `puts`、`fputs` | 输出字符串 | `puts` 会自动追加换行，`fputs` 不会 |
| `fopen`、`fclose` | 打开、关闭文件 | 检查 `fopen` 是否返回 `NULL` |
| `fread`、`fwrite` | 读写二进制数据 | 根据返回值判断实际读写数量 |
| `perror` | 根据当前错误状态输出说明 | 通常在相关库函数失败后立即调用 |
| `FILE` | C 标准文件流类型 | 由 `fopen` 得到，不应自行修改其内部内容 |
| `EOF` | 输入结束或读取错误的标志 | 不是普通字符，通常用 `int` 接收 `getchar` 的结果 |

### 4.2 `<stdlib.h>`：内存、转换与程序控制

| 内容 | 用途 | 注意事项 |
| --- | --- | --- |
| `malloc` | 分配未初始化的内存 | 成功后必须在适当时机 `free` |
| `calloc` | 分配并清零一段内存 | 注意元素数量与单个元素大小的乘积是否溢出 |
| `realloc` | 调整已分配内存的大小 | 失败时原指针仍然有效，最好用临时指针接收结果 |
| `free` | 释放动态内存 | 释放后不要继续使用该指针；必要时将其置为 `NULL` |
| `strtol`、`strtoul` | 将字符串转换为整数 | 比 `atoi` 更容易检查错误和越界 |
| `strtod` | 将字符串转换为 `double` | 可配合结束位置指针检查是否完整解析 |
| `exit` | 正常结束程序 | 可使用 `EXIT_SUCCESS` 或 `EXIT_FAILURE` |
| `abort` | 异常终止程序 | 通常只用于不可恢复的错误或调试 |
| `rand`、`srand` | 生成伪随机数、设置种子 | 不适合密码学或安全场景 |

### 4.3 `<string.h>`：字符串与内存块

| 内容 | 用途 | 注意事项 |
| --- | --- | --- |
| `strlen` | 获取 C 字符串长度 | 不包括结尾的 `\0`；要求字符串以 `\0` 结束 |
| `strcmp`、`strncmp` | 比较字符串 | 返回值不保证是 `-1` 或 `1`，只需判断小于、等于或大于零 |
| `strchr`、`strrchr` | 查找字符首次或最后一次出现的位置 | 找不到时返回 `NULL` |
| `strstr` | 查找子字符串 | 找不到时返回 `NULL` |
| `strcspn` | 获取字符串中不属于指定集合的前缀长度 | 常用于处理 `fgets` 读入的换行符 |
| `strcpy`、`strcat` | 复制或拼接字符串 | 目标缓冲区必须足够大，否则会越界 |
| `memcpy` | 复制不重叠的内存区域 | 源和目标重叠时使用 `memmove` |
| `memmove` | 复制可能重叠的内存区域 | 比 `memcpy` 更适合处理重叠区间 |
| `memset` | 按字节填充内存 | 适合清零或填充字节，不等同于给任意类型数组逐元素赋值 |
| `memcmp` | 比较两段内存 | 比较的是字节，不是数值类型的数学大小 |

### 4.4 `<ctype.h>`：字符分类

常见函数包括：

- `isalpha`：是否为字母。
- `isdigit`：是否为十进制数字字符。
- `isalnum`：是否为字母或数字。
- `isspace`：是否为空白字符，如空格、换行、制表符。
- `islower`、`isupper`：判断大小写。
- `tolower`、`toupper`：转换大小写；无法转换时通常原样返回。

> 传给这些函数的参数应是 `EOF`，或能够转换为 `unsigned char` 的值。若 `char` 可能为有符号类型，处理非 ASCII 字符时应特别注意类型转换。

### 4.5 `<math.h>`：数学函数

| 内容 | 用途 |
| --- | --- |
| `sqrt` | 平方根 |
| `pow` | 幂运算 |
| `fabs` | 浮点绝对值 |
| `fmod` | 浮点余数 |
| `floor`、`ceil`、`round` | 向下取整、向上取整、四舍五入 |
| `sin`、`cos`、`tan` | 三角函数，参数使用弧度 |
| `log`、`log10`、`exp` | 对数与指数 |

部分 Unix-like 环境编译数学函数时还需要在命令末尾添加 `-lm`。

### 4.6 其他常用头文件

| 头文件 | 常见内容 | 使用场景 |
| --- | --- | --- |
| `<stdbool.h>` | `bool`、`true`、`false` | 需要明确表达布尔状态时 |
| `<stdint.h>` | `int32_t`、`uint64_t` 等 | 需要明确整数宽度或跨平台数据格式时 |
| `<stddef.h>` | `size_t`、`NULL` 等 | 数组长度、内存大小、指针差值 |
| `<limits.h>` | 整数范围宏 | 检查类型边界、避免溢出假设 |
| `<float.h>` | 浮点范围和精度宏 | 了解浮点数的表示能力 |
| `<time.h>` | 日历时间与 CPU 计时 | 时间戳、格式化日期、粗略性能测量 |
| `<assert.h>` | `assert(condition)` | 检查“按程序设计必然成立”的内部条件 |
| `<errno.h>` | `errno` 与错误码 | 配合返回值诊断库函数错误 |
| `<stdarg.h>` | 可变参数相关宏 | 编写类似 `printf` 的接口 |

## 5. 常用格式说明符

格式化输入输出时，格式说明符必须与实际类型一致。下面列出最常见的情况：

| 类型 | `printf` 常用写法 | `scanf` 常用写法 |
| --- | --- | --- |
| `char` | `%c` | `%c` |
| `char *` 字符串 | `%s` | `%s` |
| `int` | `%d` | `%d` |
| `unsigned int` | `%u` | `%u` |
| `long` | `%ld` | `%ld` |
| `long long` | `%lld` | `%lld` |
| `float` | `%f` | `%f` |
| `double` | `%f` | `%lf` |
| `size_t` | `%zu` | `%zu` |
| 指针地址 | `%p` | 通常不作为普通输入使用 |

补充：

- `printf` 中，`float` 会提升为 `double`，所以通常使用 `%f` 输出浮点数。
- `scanf` 需要传入变量地址，例如 `scanf("%d", &number)`。
- 输出字符串 `%s` 以前，必须确认指针有效且字符串以 `\0` 结束。
- 固定宽度整数使用 `<inttypes.h>` 提供的 `PRI...` 和 `SCN...` 宏，可减少平台差异。

## 6. 使用标准库时容易出错的地方

### 6.1 输入

- 读取整行文本时，优先考虑 `fgets`，它可以接收缓冲区大小，避免无界写入。
- `scanf` 的返回值表示成功匹配并写入的项目数，不应无条件假设输入成功。
- `fgets` 可能把换行符一并读入；需要时可配合 `strcspn` 删除它。

### 6.2 字符串

- C 字符串不是独立类型，而是以 `\0` 结尾的字符序列。
- 分配字符串空间时，要为结尾的 `\0` 多预留一个字节。
- `strcpy`、`strcat` 不会自动检查目标缓冲区大小；使用前先确认容量。
- `memcpy` 处理重叠区域会产生未定义行为；重叠时使用 `memmove`。

### 6.3 动态内存

- `malloc`、`calloc`、`realloc` 的结果都可能为 `NULL`，使用前要检查。
- `realloc` 不要直接覆盖唯一的原指针；失败时原内存仍需释放。
- 每一次成功的动态分配都应有清晰的释放责任，避免内存泄漏。
- 释放后的指针不能继续解引用；同一块内存也不能重复释放。

### 6.4 错误处理与调试

- 库函数通常通过返回值报告成功或失败；先看返回值，再看 `errno`。
- `perror` 适合立即打印当前错误；`strerror` 可把错误码转换为文字。
- `assert` 用于发现程序内部逻辑错误，不应替代对用户输入和外部文件的正常错误处理。
- `assert` 在定义 `NDEBUG` 后可能被禁用，因此不要把有副作用的操作写进断言条件。

## 7. 编译、警告与运行检查

### 7.1 基本编译

```bash
cc -std=c17 -Wall -Wextra -Wpedantic -g main.c -o main
./main
```

说明：

- `-std=c17`：指定使用 C17 标准；也可以根据课程要求改为其他标准。
- `-Wall -Wextra -Wpedantic`：打开常用警告，尽早发现类型和可移植性问题。
- `-g`：写入调试信息，便于使用调试器定位问题。

### 7.2 地址与未定义行为检查

Clang/GCC 通常可以使用 Sanitizer 辅助检查越界、释放后使用等问题：

```bash
cc -std=c17 -Wall -Wextra -Wpedantic -g \
   -fsanitize=address,undefined \
   main.c -o main
./main
```

如果使用了 `sqrt`、`pow` 等数学函数，而当前 Unix-like 环境提示链接错误，可尝试：

```bash
cc -std=c17 -Wall -Wextra -Wpedantic main.c -lm -o main
```

## 8. 标准库与平台库的区别

并非所有能被 `#include` 的头文件都属于 ISO C 标准库：

| 头文件或接口 | 性质 | 可移植性 |
| --- | --- | --- |
| `<stdio.h>`、`<stdlib.h>`、`<string.h>` | ISO C 标准库 | 跨平台性较好 |
| `<unistd.h>` | POSIX / Unix-like 接口 | Linux、macOS 常见，Windows 默认不提供 |
| `<windows.h>` | Windows API | Windows 专用 |
| `<conio.h>` | 编译器或平台扩展 | 不属于 ISO C，不建议依赖于通用代码 |
| `getch`、`system("pause")` | 常见平台相关用法 | 不具备通用可移植性 |

编写需要跨平台的 C 程序时，优先使用标准库；确实需要系统能力时，再把平台相关代码隔离起来。

## 9. 一页速记

- 输入输出、文件：`<stdio.h>`
- 动态内存、转换、程序退出：`<stdlib.h>`
- 字符串和内存块：`<string.h>`
- 字符判断和大小写：`<ctype.h>`
- 数学函数：`<math.h>`
- 布尔值：`<stdbool.h>`
- 固定宽度整数：`<stdint.h>`
- 大小、指针差值、`NULL`：`<stddef.h>`
- 整数和浮点边界：`<limits.h>`、`<float.h>`
- 时间和计时：`<time.h>`
- 调试断言：`<assert.h>`
- 错误状态：`<errno.h>`
- 可变参数：`<stdarg.h>`

> 查库函数时，先确认三件事：**头文件是什么、返回值如何表示失败、参数和缓冲区有什么边界要求**。这比只记住函数名更重要。
