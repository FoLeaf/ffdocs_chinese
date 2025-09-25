## f_forward

f_forward 函数读取文件数据并将其转发到数据流设备。

```c
FRESULT f_forward (
  FIL* fp,                        /* [输入] 文件对象 */
  UINT (*func)(const BYTE*,UINT), /* [输入] 数据流函数 */
  UINT btf,                       /* [输入] 要转发的字节数 */
  UINT* bf                        /* [输出] 已转发的字节数 */
);
```

### 参数

*   **fp**: 指向已打开文件对象的指针。
*   **func**: 指向用户定义的数据流函数的指针。
*   **btf**: 要转发的字节数。
*   **bf**: 指向 `UINT` 类型变量的指针，用于返回已转发的字节数。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_INVALID_OBJECT`, `FR_DENIED`, `FR_TIMEOUT`

### 描述

`f_forward` 函数从文件中读取数据并将其转发到输出流。此函数适用于内存较小的系统，因为它不需要应用程序模块中的任何数据缓冲区。

### 快速信息

当 `FF_USE_FORWARD == 1` 时可用。

### 相关参考

`f_open`, `f_read`, `f_write`, `f_close`, `FIL`
