## f_opendir

f_opendir 函数打开一个目录。

```c
FRESULT f_opendir (
  DIR* dp,           /* [输出] 指向目录对象的指针 */
  const TCHAR* path  /* [输入] 目录名 */
);
```

### 参数

*   **dp**: 指向空白目录对象的指针，用于创建一个新的目录对象。
*   **path**: 指向一个以 null 结尾的字符串，该字符串指定要打开的[目录名](filename.md)。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_NOT_READY`, `FR_NO_PATH`, `FR_INVALID_NAME`, `FR_INVALID_OBJECT`, `FR_INVALID_DRIVE`, `FR_NOT_ENABLED`, `FR_NO_FILESYSTEM`, `FR_TIMEOUT`, `FR_NOT_ENOUGH_CORE`, `FR_TOO_MANY_OPEN_FILES`

### 描述

`f_opendir` 函数打开一个现有的目录，并为后续的 `f_readdir` 函数创建一个目录对象。

### 快速信息

当 `FF_FS_MINIMIZE <= 1` 时可用。

### 相关参考

`f_readdir`, `f_closedir`, `DIR`
