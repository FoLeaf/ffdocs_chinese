## f_size

f_size 函数获取文件的大小。

```c
FSIZE_t f_size (
  FIL* fp   /* [输入] 文件对象 */
);
```

### 参数

*   **fp**: 指向已打开的文件对象结构的指针。

### 返回值

返回文件的大小，单位为字节。

### 描述

在此版本中，`f_size` 函数是作为宏实现的。它没有任何验证和互斥。

```c
#define f_size(fp) ((fp)->obj.objsize)
```

### 快速信息

始终可用。

### 相关参考

`f_open`, `f_lseek`, `FIL`
