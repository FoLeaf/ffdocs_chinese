## f_read

f_read 函数从文件中读取数据。

```c
FRESULT f_read (
  FIL* fp,     /* [输入] 文件对象 */
  void* buff,  /* [输出] 存储读取数据的缓冲区 */
  UINT btr,    /* [输入] 要读取的字节数 */
  UINT* br     /* [输出] 已读取的字节数 */
);
```

### 参数

*   **fp**: 指向已打开的文件对象结构的指针。
*   **buff**: 指向用于存储读取数据的缓冲区的指针。
*   **btr**: 要读取的字节数。
*   **br**: 指向 `UINT` 类型变量的指针，该变量用于接收已读取的字节数。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_DENIED`, `FR_INVALID_OBJECT`, `FR_TIMEOUT`

### 描述

该函数从文件读/写指针所指向的文件偏移处开始读取数据。读/写指针会根据读取的字节数向前移动。如果 `*br` < `btr`，则表示在读取操作期间读/写指针到达了文件末尾。

### 示例

请参考 `f_open` 中的示例。

### 相关参考

`f_open`, `fgets`, `f_write`, `f_close`, `FIL`
