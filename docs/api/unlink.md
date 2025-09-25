## f_unlink

f_unlink 函数从卷中删除文件或子目录。

```c
FRESULT f_unlink (
  const TCHAR* path  /* [输入] 对象名 */
);
```

### 参数

*   **path**: 指向一个以 null 结尾的字符串，该字符串指定要删除的[文件或子目录](filename.md)。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_NOT_READY`, `FR_NO_FILE`, `FR_NO_PATH`, `FR_INVALID_NAME`, `FR_DENIED`, `FR_WRITE_PROTECTED`, `FR_INVALID_DRIVE`, `FR_NOT_ENABLED`, `FR_NO_FILESYSTEM`, `FR_TIMEOUT`, `FR_LOCKED`, `FR_NOT_ENOUGH_CORE`

### 描述

如果待删除对象的条件适用于以下条款，则函数将被拒绝。
*   文件/子目录不能具有只读属性 (`AM_RDO`)。
*   子目录必须为空且不能是当前目录。
*   文件/子目录不能是打开的。

### 快速信息

当 `FF_FS_READONLY == 0` 且 `FF_FS_MINIMIZE == 0` 时可用。

### 相关参考

`f_rename`, `f_mkdir`
