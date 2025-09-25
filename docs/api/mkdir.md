## f_mkdir

f_mkdir 函数创建一个新目录。

```c
FRESULT f_mkdir (
  const TCHAR* path /* [输入] 目录名 */
);
```

### 参数

*   **path**: 指向一个以 null 结尾的字符串，该字符串指定要创建的[目录名](filename.md)。

### 返回值

`FR_OK`, `FR_DISK_ERR`, `FR_INT_ERR`, `FR_NOT_READY`, `FR_NO_PATH`, `FR_INVALID_NAME`, `FR_DENIED`, `FR_EXIST`, `FR_WRITE_PROTECTED`, `FR_INVALID_DRIVE`, `FR_NOT_ENABLED`, `FR_NO_FILESYSTEM`, `FR_TIMEOUT`, `FR_NOT_ENOUGH_CORE`

### 描述

此函数创建一个新目录。要删除目录，请使用 `f_unlink` 函数。

### 快速信息

当 `FF_FS_READONLY == 0` 且 `FF_FS_MINIMIZE == 0` 时可用。

### 示例

```c
res = f_mkdir("sub1");
if (res) die(res);
res = f_mkdir("sub1/sub2");
if (res) die(res);
```

### 相关参考

`f_unlink`
