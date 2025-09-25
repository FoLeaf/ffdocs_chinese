## f_getcwd

f_getcwd 函数检索当前目录和当前驱动器。

```c
FRESULT f_getcwd (
  TCHAR* buff, /* [输出] 用于返回路径名的缓冲区 */
  UINT len     /* [输入] 缓冲区长度 */
);
```

### 参数

*   **buff**: 指向用于接收当前目录路径的字符串缓冲区的指针。
*   **len**: 缓冲区的大小，单位为 `(TCHAR)`。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_NOT_READY`, `FR_NOT_ENABLED`, `FR_NO_FILESYSTEM`, `FR_TIMEOUT`, `FR_NOT_ENOUGH_CORE`

### 描述

`f_getcwd` 函数检索当前驱动器的当前目录的完整路径名。

### 快速信息

当 `FF_FS_RPATH == 2` 时可用。

### 相关参考

`f_chdrive`, `f_chdir`
