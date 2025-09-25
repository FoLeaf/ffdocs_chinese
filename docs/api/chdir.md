## f_chdir

f_chdir 函数更改逻辑驱动器的当前目录。

```c
FRESULT f_chdir (
  const TCHAR* path /* [输入] 路径名 */
);
```

### 参数

*   **path**: 指向一个以 null 结尾的字符串，该字符串指定要设置为当前目录的目录。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_NOT_READY`, `FR_NO_PATH`, `FR_INVALID_NAME`, `FR_INVALID_DRIVE`, `FR_NOT_ENABLED`, `FR_NO_FILESYSTEM`, `FR_TIMEOUT`, `FR_NOT_ENOUGH_CORE`

### 描述

`f_chdir` 函数更改逻辑驱动器的当前目录。每个逻辑驱动器的当前目录在挂载时被设置为根目录。

### 快速信息

当 `FF_FS_RPATH >= 1` 时可用。

### 相关参考

`f_chdrive`, `f_getcwd`
