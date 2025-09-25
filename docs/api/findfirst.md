## f_findfirst

f_findfirst 函数在目录中搜索一个项目。

```c
FRESULT f_findfirst (
  DIR* dp,              /* [输出] 指向目录对象的指针 */
  FILINFO* fno,         /* [输出] 指向文件信息结构的指针 */
  const TCHAR* path,    /* [输入] 指向要打开的目录名的指针 */
  const TCHAR* pattern  /* [输入] 指向匹配模式字符串的指针 */
);
```

### 参数

*   **dp**: 指向空白目录对象的指针。
*   **fno**: 指向文件信息结构的指针，用于存储找到的项目的相关信息。
*   **path**: 指向一个以 null 结尾的字符串，该字符串指定要打开的目录名。
*   **pattern**: 指向一个以 null 结尾的字符串，该字符串指定要搜索的名称匹配模式。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_NOT_READY`, `FR_NO_PATH`, `FR_INVALID_NAME`, `FR_INVALID_OBJECT`, `FR_INVALID_DRIVE`, `FR_NOT_ENABLED`, `FR_NO_FILESYSTEM`, `FR_TIMEOUT`, `FR_NOT_ENOUGH_CORE`, `FR_TOO_MANY_OPEN_FILES`

### 描述

此函数开始在目录中搜索与 `pattern` 指定的匹配模式相匹配的项目。如果找到第一个项目，则有关该项目的信息将存储到 `fno` 中。

### 快速信息

当 `FF_USE_FIND >= 1` 且 `FF_FS_MINIMIZE <= 1` 时可用。

### 相关参考

`f_findnext`, `f_closedir`, `DIR`, `FILINFO`
