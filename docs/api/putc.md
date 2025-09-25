## f_putc

f_putc 函数向文件写入一个字符。

```c
int f_putc (
  TCHAR chr,  /* [输入] 要写入的字符 */
  FIL* fp     /* [输入] 文件对象 */
);
```

### 参数

*   **chr**: 要写入的字符。
*   **fp**: 指向已打开的文件对象结构的指针。

### 返回值

如果字符成功写入，则返回写入文件的字符编码单元数。如果由于磁盘已满或任何错误而导致函数失败，则返回一个负值。

### 描述

当 `FF_USE_STRFUNC == 2` 时，一个 `\n` 会被输出为 `\r`+`\n`。

### 快速信息

当 `FF_FS_READONLY == 0` 且 `FF_USE_STRFUNC >= 1` 时可用。

### 相关参考

`f_open`, `f_puts`, `f_printf`, `f_gets`, `f_close`, `FIL`

```