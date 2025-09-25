## f_close

f_close 函数关闭一个已打开的文件。

```c
FRESULT f_close (
  FIL* fp     /* [输入] 指向文件对象的指针 */
);
```

### 参数

*   **fp**: 指向要关闭的已打开文件对象结构的指针。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_INVALID_OBJECT`, `FR_TIMEOUT`

### 描述

`f_close` 函数关闭一个已打开的文件对象。如果文件已被更改，文件的缓存信息将被写回到卷中。函数成功后，该文件对象将不再有效，可以被丢弃。

### 快速信息

始终可用。

### 相关参考

`f_open`, `f_read`, `f_write`, `f_sync`, `FIL`, `FATFS`
