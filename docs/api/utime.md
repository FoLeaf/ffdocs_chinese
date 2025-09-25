## f_utime

f_utime 函数更改文件或子目录的时间戳。

```c
FRESULT f_utime (
  const TCHAR* path,  /* [输入] 对象名 */
  const FILINFO* fno  /* [输入] 要设置的时间和日期 */
);
```

### 参数

*   **path**: 指向一个以 null 结尾的字符串，该字符串指定要更改的[对象](filename.md)。
*   **fno**: 指向文件信息结构的指针，该结构具有要设置的新时间戳。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_NOT_READY`, `FR_NO_FILE`, `FR_NO_PATH`, `FR_INVALID_NAME`, `FR_WRITE_PROTECTED`, `FR_INVALID_DRIVE`, `FR_NOT_ENABLED`, `FR_NO_FILESYSTEM`, `FR_TIMEOUT`, `FR_NOT_ENOUGH_CORE`

### 描述

`f_utime` 函数更改文件或子目录的时间戳。

### 快速信息

当 `FF_FS_READONLY == 0` 且 `FF_USE_CHMOD == 1` 时可用。
