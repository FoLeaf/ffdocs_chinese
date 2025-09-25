## f_write

f_write 函数向文件写入数据。

```c
FRESULT f_write (
  FIL* fp,          /* [输入] 指向文件对象的指针 */
  const void* buff, /* [输入] 指向要写入数据的指针 */
  UINT btw,         /* [输入] 要写入的字节数 */
  UINT* bw          /* [输出] 指向变量的指针，用于返回已写入的字节数 */
);
```

### 参数

*   **fp**: 指向已打开的文件对象结构的指针。
*   **buff**: 指向要写入的数据的指针。
*   **btw**: 指定要写入的字节数。
*   **bw**: 指向 `UINT` 类型变量的指针，该变量用于接收已写入的字节数。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_DENIED`, `FR_INVALID_OBJECT`, `FR_TIMEOUT`

### 描述

该函数从文件读/写指针所指向的文件偏移处开始写入数据。读/写指针会根据写入的字节数向前移动。如果 `*bw` < `btw`，则表示在写入操作期间卷已满。

### 快速信息

当 `FF_FS_READONLY == 0` 时可用。

### 示例

请参考 `f_open` 中的示例。

### 相关参考

`f_open`, `f_read`, `f_putc`, `f_puts`, `f_printf`, `f_close`, `FIL`
