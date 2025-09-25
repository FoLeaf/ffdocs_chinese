## f_truncate

f_truncate 函数截断文件大小。

```c
FRESULT f_truncate (
  FIL* fp     /* [输入] 文件对象 */
);
```

### 参数

*   **fp**: 指向要截断的已打开文件对象的指针。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_DENIED`, `FR_INVALID_OBJECT`, `FR_TIMEOUT`

### 描述

`f_truncate` 函数将文件大小截断到当前文件读/写指针的位置。如果文件读/写指针已经指向文件末尾，则此函数无效。

### 快速信息

当 `FF_FS_READONLY == 0` 且 `FF_FS_MINIMIZE == 0` 时可用。

### 相关参考

`f_open`, `f_lseek`, `FIL`
