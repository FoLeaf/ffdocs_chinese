## f_getlabel

f_getlabel 函数返回卷的卷标和卷序列号。

```c
FRESULT f_getlabel (
  const TCHAR* path,  /* [输入] 驱动器号 */
  TCHAR* label,       /* [输出] 卷标 */
  DWORD* vsn          /* [输出] 卷序列号 */
);
```

### 参数

*   **path**: 指向一个以 null 结尾的字符串，该字符串指定逻辑驱动器。
*   **label**: 指向用于存储卷标的缓冲区的指针。
*   **vsn**: 指向 `DWORD` 变量的指针，用于存储卷序列号。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_NOT_READY`, `FR_INVALID_DRIVE`, `FR_NOT_ENABLED`, `FR_NO_FILESYSTEM`, `FR_TIMEOUT`

### 描述

此函数获取卷的卷标和/或卷序列号。

### 快速信息

当 `FF_USE_LABEL == 1` 时可用。

### 相关参考

`f_setlabel`
